<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portal Edukasi Safety Quarry NK</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
  <style>
    .shadow-text {
      text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.4);
    }
    .modal-open {
      overflow: hidden;
    }
  </style>
</head>
<body class="min-h-screen bg-gradient-to-b from-stone-200 via-stone-300 to-stone-500 bg-[radial-gradient(circle_at_20%_20%,rgba(255,255,255,0.25)_2px,transparent_3px),radial-gradient(circle_at_80%_40%,rgba(0,0,0,0.08)_2px,transparent_3px)] bg-[length:40px_40px,60px_60px]">

  <header class="bg-blue-700 text-white py-6 md:py-10 text-center shadow-lg">
    <h1 class="text-3xl md:text-5xl font-bold">Area Owner NK</h1>
    <p class="mt-2 text-xs md:text-lg opacity-90">Portal Edukasi Safety Quarry NK</p>
  </header>

  <section class="max-w-7xl mx-auto px-2 md:px-4 py-6 md:py-10">
    <div class="bg-white rounded-2xl shadow-xl p-4 md:p-6 text-center mb-6 md:mb-10 w-full max-w-xl mx-auto">
      <h2 class="text-xl md:text-3xl font-bold text-green-800">Selamat Datang</h2>
      <p class="mt-2 text-xs md:text-base text-gray-700">Silakan klik tombol puzzle untuk mempelajari standar keselamatan.</p>
    </div>

    <!-- Grid Konten -->
    <div id="grid-container" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-3 md:gap-6 pb-20 justify-items-center">
      <!-- Kartu di-render otomatis -->
    </div>
  </section>

  <!-- STRUKTUR MODAL POP-UP -->
  <div id="safety-modal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/60 backdrop-blur-sm hidden opacity-0 transition-opacity duration-300">
    <div class="bg-white w-full max-w-2xl rounded-2xl shadow-2xl overflow-hidden flex flex-col max-h-[90vh] scale-95 transition-transform duration-300" id="modal-content">
      
      <!-- Modal Header -->
      <div id="modal-header" class="p-4 md:p-5 text-white flex justify-between items-center bg-gradient-to-r">
        <div class="flex items-center gap-3">
          <span id="modal-icon" class="text-3xl"></span>
          <h3 id="modal-title" class="font-bold text-base md:text-xl"></h3>
        </div>
        <button onclick="closeModal()" class="text-white hover:bg-white/20 text-2xl font-bold w-8 h-8 flex items-center justify-center rounded-full transition-colors">&times;</button>
      </div>

      <!-- Modal Body (Scrollable) -->
      <div class="p-4 md:p-6 overflow-y-auto space-y-6 bg-stone-50">
        
        <!-- Baris Panduan Komparasi -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          
          <!-- Box: YANG BOLEH DILAKUKAN -->
          <div class="bg-green-50 border-2 border-green-200 rounded-xl p-4 flex flex-col shadow-sm">
            <div class="flex items-center gap-2 text-green-700 font-bold mb-3 text-sm md:text-base">
              <span>✅</span> YANG BOLEH / DIANJURKAN
            </div>
            <!-- Gambar Ilustrasi Boleh -->
            <div class="w-full h-40 bg-white rounded-lg overflow-hidden border border-green-300 mb-3 flex items-center justify-center">
              <img id="img-allowed" src="" alt="Ilustrasi Aman" class="w-full h-full object-cover">
            </div>
            <ul id="modal-allowed" class="text-xs md:text-sm text-gray-700 space-y-2 list-disc list-inside">
              <!-- Diisi via JS -->
            </ul>
          </div>

          <!-- Box: YANG TIDAK BOLEH DILAKUKAN -->
          <div class="bg-red-50 border-2 border-red-200 rounded-xl p-4 flex flex-col shadow-sm">
            <div class="flex items-center gap-2 text-red-700 font-bold mb-3 text-sm md:text-base">
              <span>❌</span> TIDAK BOLEH / DILARANG
            </div>
            <!-- Gambar Ilustrasi Tidak Boleh -->
            <div class="w-full h-40 bg-white rounded-lg overflow-hidden border border-red-300 mb-3 flex items-center justify-center">
              <img id="img-forbidden" src="" alt="Ilustrasi Bahaya" class="w-full h-full object-cover">
            </div>
            <ul id="modal-forbidden" class="text-xs md:text-sm text-gray-700 space-y-2 list-disc list-inside">
              <!-- Diisi via JS -->
            </ul>
          </div>

        </div>
      </div>

      <!-- Modal Footer (Tombol Persetujuan Kembali Ke Halaman Awal) -->
      <div class="p-4 bg-stone-100 border-t border-stone-200 flex justify-center">
        <button onclick="closeModal()" class="px-6 py-3 bg-green-700 hover:bg-green-800 text-white font-bold rounded-xl text-sm transition-all shadow-md flex items-center gap-2 transform active:scale-95 cursor-pointer">
          <span>👍</span> Saya Setuju & Paham
        </button>
      </div>
    </div>
  </div>

  <footer class="bg-green-800 text-white text-center py-4 text-xs md:text-sm">
    © 2026 HSE Learning Center | Zero Accident Starts With Me
  </footer>

  <script>
    // Data Induk K3 dengan tautan gambar ilustrasi animasi/vektor dari internet
    const menus = [
      { 
        title: 'Bahaya Jatuh dari Ketinggian', icon: '🪜', color: 'from-red-400 to-red-600 border-red-950',
        imgAllowed: 'https://images.unsplash.com/photo-1621905252507-b354bc25edac?w=400&auto=format&fit=crop&q=60', // Ilustrasi pekerja safety harness
        imgForbidden: 'https://images.unsplash.com/photo-1581092921461-eab62e97a780?w=400&auto=format&fit=crop&q=60', // Ilustrasi tidak aman
        allowed: ['Menggunakan Full Body Harness yang sudah di-inspect', 'Memastikan anchor point terpasang kokoh di atas kepala', 'Menggunakan tangga dengan sudut kemiringan aman 4:1'],
        forbidden: ['Bekerja di ketinggian > 1.8 meter tanpa APD penahan jatuh', 'Menggunakan perancah/scaffolding tanpa tag hijau (aman)', 'Mengantongi gadget saat memanjat']
      },
      { 
        title: 'Bahaya Tertimpa Material', icon: '🧱', color: 'from-orange-400 to-orange-600 border-orange-950',
        imgAllowed: 'https://images.unsplash.com/photo-1590069261209-f8e9b8642343?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=400&auto=format&fit=crop&q=60',
        allowed: ['Selalu memakai Safety Helmet berstandar SNI/ANSI', 'Memasang jaring pengaman (safety net) di area bawah kerja konstruksi', 'Menumpuk material dengan ketinggian aman & stabil'],
        forbidden: ['Berdiri atau melintas tepat di bawah beban yang sedang diangkat', 'Menaruh perkakas kerja di ujung lantai perancah tanpa pembatas', 'Mengabaikan rambu barikade daerah rawan jatuh']
      },
      { 
        title: 'Bahaya Alat Berat', icon: '🚜', color: 'from-yellow-400 to-yellow-600 border-yellow-950',
        imgAllowed: 'https://images.unsplash.com/photo-1578328819058-b69f3a3b0f6b?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1541625602330-2277a4c46182?w=400&auto=format&fit=crop&q=60',
        allowed: ['Menjaga jarak aman minimal 20 meter dari jangkauan alat', 'Melakukan kontak mata & konfirmasi radio sebelum mendekat', 'Memastikan operator memiliki Kimper/SIO aktif'],
        forbidden: ['Berada di area titik buta (blind spot) alat berat', 'Berdiri di area ayunan (swing radius) excavator', 'Menaiki bucket atau bagian luar alat berat saat beroperasi']
      },
      { 
        title: 'Bahaya Listrik', icon: '⚡', color: 'from-lime-400 to-lime-600 border-lime-950',
        imgAllowed: 'https://images.unsplash.com/photo-1621905251918-48416bd8575a?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1473341304170-971dccb5ac1e?w=400&auto=format&fit=crop&q=60',
        allowed: ['Menggunakan peralatan listrik dengan kabel utuh tanpa sambungan', 'Memastikan panel distribusi terkunci & tertutup rapat', 'Menggunakan sarung tangan isolasi khusus saat pemeliharaan'],
        forbidden: ['Menyambung kabel secara asal menggunakan isolasi lakban kertas', 'Mengoperasikan sakelar listrik dengan kondisi tangan basah', 'Membiarkan kabel terkelupas melintang di jalur lalu lintas unit']
      },
      { 
        title: 'Bahaya Kebakaran', icon: '🔥', color: 'from-rose-400 to-rose-600 border-rose-950',
        imgAllowed: 'https://images.unsplash.com/photo-1600697395593-e9dc66797b43?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1565538810844-1e119fa16873?w=400&auto=format&fit=crop&q=60',
        allowed: ['Menempatkan APAR di titik yang mudah dijangkau & bebas hambatan', 'Memastikan area Hot Work (pengelasan) dibersihkan dari benda mudah terbakar', 'Menyediakan Fire Blanket di area dapur/bengkel'],
        forbidden: ['Merokok di area dekat penyimpanan bahan bakar atau pelumas', 'Mengisi ulang bahan bakar genset dalam kondisi mesin menyala', 'Menyumbat akses jalan menuju hidran/alat pemadam']
      },
      { 
        title: 'Bahaya Debu Semen', icon: '🏭', color: 'from-cyan-400 to-cyan-600 border-cyan-950',
        imgAllowed: 'https://images.unsplash.com/photo-1516937941344-00b4e0337589?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1605787020600-b9ebd5df1d07?w=400&auto=format&fit=crop&q=60',
        allowed: ['Wajib memakai masker respirator minimal jenis P100/N95', 'Mengaktifkan sistem penyedot debu (dust collector) di ruang pengetokan', 'Mencuci tangan dan membilas mata segera setelah terpapar'],
        forbidden: ['Menggunakan masker kain biasa yang tipis untuk menahan debu semen', 'Makan atau minum di area kerja yang terpapar polusi debu', 'Membersihkan sisa debu dengan cara ditiup angin kompresor']
      },
      { 
        title: 'Bahaya Kebisingan', icon: '🔊', color: 'from-blue-400 to-blue-600 border-blue-950',
        imgAllowed: 'https://images.unsplash.com/photo-1598150490543-df4c0c5d57d5?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1469041797191-50ace28483c3?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memakai Ear Plug atau Ear Muff di area dengan tingkat bising > 85 dB', 'Melakukan rotasi kerja untuk membatasi durasi paparan suara', 'Melakukan perawatan berkala pada mesin peredam'],
        forbidden: ['Melepas alat pelindung telinga saat berada di dalam ruang mesin/crusher', 'Mengabaikan tanda peringatan "Wajib Gunakan Pelindung Telinga"', 'Mendengarkan musik keras lewat earphone saat mengemudi unit']
      },
      { 
        title: 'Bahaya Ruang Terbatas', icon: '🚪', color: 'from-violet-400 to-violet-600 border-violet-950',
        imgAllowed: 'https://images.unsplash.com/photo-1508873699372-7aeab60b44ab?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1527689368864-3a821dbccc34?w=400&auto=format&fit=crop&q=60',
        allowed: ['Melakukan tes atmosfer kadar gas beracun & oksigen sebelum masuk', 'Menunjuk satu orang pengawas stanby di luar pintu masuk', 'Mengamankan izin kerja (Confined Space Permit) tertulis'],
        forbidden: ['Masuk ke tangki/silo sendirian tanpa pengawasan dari luar', 'Mengabaikan ventilasi udara/blower paksa saat bekerja di dalam', 'Masuk tanpa membawa alat bantu pernapasan darurat jika diperlukan']
      },
      { 
        title: 'Slip Trip Fall', icon: '⚠️', color: 'from-pink-400 to-pink-600 border-pink-950',
        imgAllowed: 'https://images.unsplash.com/photo-1532601224476-15c79f2f7a51?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1584467541268-b040f83be3fd?w=400&auto=format&fit=crop&q=60',
        allowed: ['Menjaga jalur pejalan kaki tetap bersih dari tumpahan oli & air', 'Memastikan penerangan jalan cukup terang di malam hari', 'Berjalan memperhatikan langkah kaki & menggunakan handrail tangga'],
        forbidden: ['Berlari di koridor kerja atau anak tangga bengkel', 'Membiarkan kabel melintang tidak beraturan di lantai kerja', 'Melangkah sambil membaca dokumen atau fokus layar HP']
      },
      { 
        title: 'Bahaya Bahan Kimia', icon: '🧪', color: 'from-emerald-400 to-emerald-600 border-emerald-950',
        imgAllowed: 'https://images.unsplash.com/photo-1532187863486-abf9d39d6618?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1617155093730-a8bf47be792d?w=400&auto=format&fit=crop&q=60',
        allowed: ['Membaca lembar panduan keselamatan MSDS sebelum penanganan', 'Menggunakan kacamata safety (goggles) & sarung tangan nitrile', 'Menyimpan bahan kimia cair di atas bak penampung sekunder (bunding)'],
        forbidden: ['Memindahkan bahan kimia berbahaya ke botol minuman bekas tanpa label', 'Menghirup langsung aroma cairan kimia untuk mengidentifikasinya', 'Membuang sisa limbah kimia langsung ke saluran air umum']
      },
      { 
        title: 'Bahaya Longsoran', icon: '⛰️', color: 'from-amber-600 to-amber-800 border-amber-950',
        imgAllowed: 'https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1604147706283-d7119b5b822c?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memantau pergerakan dinding pit quarry menggunakan sistem radar/prism', 'Membuat kemiringan lereng (benching) sesuai dengan kajian geoteknik', 'Segera evakuasi jika mendengar suara rekahan tanah atau batu jatuh'],
        forbidden: ['Melakukan penggalian menggantung (undercutting) pada kaki dinding pit', 'Memarkir alat berat tepat di bawah lereng yang rapuh atau retak', 'Melintasi area zona merah longsor tanpa izin tim safety']
      },
      { 
        title: 'Bahaya Peledakan', icon: '💥', color: 'from-red-600 to-red-800 border-red-950',
        imgAllowed: 'https://images.unsplash.com/photo-1518156677180-95a2893f3e9f?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=400&auto=format&fit=crop&q=60',
        allowed: ['Membunyikan sirine peringatan berkala sebelum waktu blasting', 'Memastikan radius aman sterilisasi manusia sejauh minimal 500 meter', 'Menghitung ulang konfigurasi detonator oleh juru ledak bersertifikat'],
        forbidden: ['Memasuki area blasting sebelum ada pernyataan resmi aman "Clear"', 'Mengaktifkan sinyal radio atau HP di dekat area pengisian bahan peledak', 'Mengabaikan aba-aba hitung mundur evakuasi peledakan']
      },
      { 
        title: 'Rock Fall', icon: '🪨', color: 'from-stone-500 to-stone-700 border-stone-950',
        imgAllowed: 'https://images.unsplash.com/photo-1506744038136-46273834b3fb?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1469854523086-cc02fe5d8800?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memasang jaring kawat baja (wire mesh) pada lereng jalan tambang', 'Melakukan pembersihan berkala batu menggantung (scaling) manual/alat', 'Wajib memakai helm dengan tali dagu terpasang kencang'],
        forbidden: ['Berdiri santai atau beristirahat di bawah tebing quarry', 'Mengemudikan unit beratap terbuka tanpa kanopi pelindung FOPS', 'Mengabaikan rambu peringatan rawan jatuhan batu']
      },
      { 
        title: 'Dump Truck Interaction', icon: '🚛', color: 'from-orange-600 to-orange-800 border-orange-950',
        imgAllowed: 'https://images.unsplash.com/photo-1601584115197-04ecc0da31d7?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1516574187841-cb9cc2ca948b?w=400&auto=format&fit=crop&q=60',
        allowed: ['Mengalah dan memberi prioritas jalan utama kepada dump truck loaded', 'Memastikan lampu hazard & buggy whip menyala terang', 'Menjaga jarak antrean di area dumping minimal selebar 1 unit truck'],
        forbidden: ['Menyalip dump truck raksasa dari sisi sebelah kiri (blind spot utama)', 'Memotong jalur dump truck yang sedang melaju di turunan tambang', 'Berjalan kaki di jalur hauling aktif tanpa rompi reflektif']
      },
      { 
        title: 'Traffic Management', icon: '🚧', color: 'from-yellow-500 to-yellow-700 border-yellow-950',
        imgAllowed: 'https://images.unsplash.com/photo-1547496502-affa22d38842?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1590674899484-d5640e854abe?w=400&auto=format&fit=crop&q=60',
        allowed: ['Mematuhi batas kecepatan operasional maksimum di area tambang/quarry', 'Mengikuti rambu satu arah & tanda pemisah jalur separator', 'Memastikan klakson dibunyikan sesuai kode standar sebelum bergerak'],
        forbidden: ['Mengemudi secara ugal-ugalan atau zig-zag mendahului antrean', 'Mengubah rute perjalanan tanpa koordinasi dengan pos kontrol lalu lintas', 'Mengabaikan rambu larangan melintas yang dipasang petugas']
      },
      { 
        title: 'Fuel Storage', icon: '⛽', color: 'from-red-500 to-red-700 border-red-950',
        imgAllowed: 'https://images.unsplash.com/photo-1527018601619-a508a2be00cd?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1574689049868-e94ed5301745?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memasang sistem pembumian (grounding) tangki untuk cegah listrik statis', 'Menyiapkan kotak penimbun pasir & spill kit di dekat dispenser BBM', 'Memeriksa berkala katup pengaman tekanan udara (vent valve)'],
        forbidden: ['Menggunakan peralatan penghasil percikan api di radius 15 meter', 'Membiarkan kebocoran fuel merembes ke tanah tanpa penanganan cepat', 'Menumpuk barang bekas atau sampah organik di sekitar tangki induk']
      },
      { 
        title: 'Cuaca dan Hujan', icon: '🌧️', color: 'from-sky-500 to-sky-700 border-sky-950',
        imgAllowed: 'https://images.unsplash.com/photo-1534274988757-a28bf1a57c17?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1515694346937-94d85e41e6f0?w=400&auto=format&fit=crop&q=60',
        allowed: ['Menghentikan operasi tambang seketika jika terdengar petir beruntun', 'Memarkirkan unit di area datar dan aman saat jarak pandang memburuk', 'Menyalakan semua lampu unit termasuk fog lamp saat kabut turun'],
        forbidden: ['Memaksakan dump truck melewati jalur jalan hauling yang licin/berlumpur ekstrim', 'Berteduh di bawah pohon tinggi atau di dalam bucket alat berat saat badai', 'Menerobos genangan banjir luapan tanggul tambang']
      },
      { 
        title: 'Highwall Failure', icon: '🏔️', color: 'from-slate-600 to-slate-800 border-slate-950',
        imgAllowed: 'https://images.unsplash.com/photo-1504280390367-361c6d9f38f4?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1506744038136-46273834b3fb?w=400&auto=format&fit=crop&q=60',
        allowed: ['Melakukan inspeksi keretakan lereng atas setiap awal shift kerja', 'Memasang penanda batas jarak aman operasional dari tepi atas tebing', 'Memastikan drainase air permukaan di atas lereng lancar'],
        forbidden: ['Bekerja di bawah lereng tinggi yang memperlihatkan rembesan air aktif', 'Menumpuk material buangan (disposal) terlalu dekat di bibir tebing', 'Mengabaikan instruksi evakuasi geoteknik']
      },
      { 
        title: 'LOTO', icon: '🔒', color: 'from-indigo-500 to-indigo-700 border-indigo-950',
        imgAllowed: 'https://images.unsplash.com/photo-1581094288338-2314dddb7ece?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memasang gembok personal & tag bahaya pada sakelar isolasi utama', 'Melakukan uji coba fungsi mesin (test start) untuk memastikan energi nol', 'Menyimpan kunci gembok secara personal oleh mekanik bersangkutan'],
        forbidden: ['Menitipkan kunci gembok LOTO kepada rekan kerja lain', 'Melepas paksa gembok LOTO milik orang lain tanpa prosedur resmi', 'Memulai perbaikan mesin sebelum memastikan pasokan daya terputus total']
      },
      { 
        title: 'Lifting Rigging', icon: '🏋️', color: 'from-fuchsia-500 to-fuchsia-700 border-fuchsia-950',
        imgAllowed: 'https://images.unsplash.com/photo-1541534741688-6078c6bfb5c5?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1517838277536-f5f99be501cd?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memeriksa kelayakan webbing sling/shackle dari keretakan & keausan', 'Menggunakan tali penuntun (tag line) untuk mengontrol putaran beban', 'Memastikan sudut angkat sesuai dengan tabel kapasitas beban (SWL)'],
        forbidden: ['Menggunakan kawat seling pembungkus yang sudah berkarat atau putas serat', 'Mengikat beban langsung pada badan silinder hidrolik unit', 'Melakukan pengangkatan saat cuaca angin kencang di atas 20 knot']
      },
      { 
        title: 'Crane Operation', icon: '🏗️', color: 'from-yellow-600 to-yellow-800 border-yellow-950',
        imgAllowed: 'https://images.unsplash.com/photo-1542362567-b07eac790abc?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1579684385127-1ef15d508118?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memasang outrigger secara penuh di atas landasan papan penumpu yang kokoh', 'Mengecek indikator beban otomatis (LMI) berfungsi dengan normal', 'Memastikan area radius operasi crane steril dari kerumunan pekerja'],
        forbidden: ['Mengangkat beban melebihi grafik kapasitas aman crane (overload)', 'Menggunakan crane untuk menarik beban dari arah samping secara diagonal', 'Mengoperasikan boom crane dekat melintasi jalur kabel listrik udara kabel telanjang']
      },
      { 
        title: 'OTR Tire Safety', icon: '🛞', color: 'from-neutral-600 to-neutral-800 border-neutral-950',
        imgAllowed: 'https://images.unsplash.com/photo-1580273916550-e323be2ae537?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1619642751034-765dfdf7c58e?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memeriksa tekanan angin ban dalam keadaan dingin dengan pressure gauge', 'Menggunakan sangkar pengaman (tire cage) khusus saat memompa ban OTR', 'Memastikan baut roda dikencangkan menggunakan kunci torsi standar'],
        forbidden: ['Berdiri berhadapan langsung dengan sisi samping (sidewall) ban saat memompa', 'Menggunakan ban OTR yang tapaknya sudah gundul tembus kawat baja', 'Melakukan pengelasan velg tanpa melepas ban dari roda terlebih dahulu']
      },
      { 
        title: 'Kerja Malam', icon: '🌙', color: 'from-indigo-700 to-indigo-950 border-indigo-950',
        imgAllowed: 'https://images.unsplash.com/photo-1509114397022-ed747cca3f65?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?w=400&auto=format&fit=crop&q=60',
        allowed: ['Memastikan tidur siang yang cukup minimal 6 jam sebelum shift malam', 'Melaporkan kepada pengawas jika mulai merasakan kantuk berat (fatigue)', 'Wajib menyalakan lampu penerangan menara (light tower) di lokasi kerja'],
        forbidden: ['Memaksakan mengemudikan unit dalam kondisi micro-sleep (tertidur sekilas)', 'Bekerja sendirian di area terisolasi tanpa alat komunikasi radio aktif', 'Melewatkan jadwal pemeriksaan kebugaran (fit to work) sebelum kerja']
      },
      { 
        title: 'Heat Stress', icon: '🥵', color: 'from-orange-500 to-orange-700 border-orange-950',
        imgAllowed: 'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1495555961986-6d4c1ecb7be3?w=400&auto=format&fit=crop&q=60',
        allowed: ['Minum air putih sedikitnya 250 ml setiap 20 menit kerja panas', 'Memanfaatkan pos istirahat ber-AC/teduh secara berkala untuk pendinginan', 'Mengenali tanda kram, pusing, atau mual akibat sengatan terik matahari'],
        forbidden: ['Mengonsumsi minuman berkafein tinggi atau energi berlebih secara terus-menerus', 'Memaksakan diri bekerja di bawah terik ekstrem tanpa jeda istirahat', 'Mengabaikan rekan kerja yang terlihat kebingungan/lemas akibat dehidrasi']
      },
      { 
        title: 'APD Wajib', icon: '⛑️', color: 'from-green-600 to-green-800 border-green-950',
        imgAllowed: 'https://images.unsplash.com/photo-1531206715517-5c0ba140e2b8?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1573164713714-d95e436ab8d6?w=400&auto=format&fit=crop&q=60',
        allowed: ['Merawat dan mencuci APD secara berkala agar fungsinya optimal', 'Memastikan APD terpasang pas dan nyaman di badan (tidak longgar)', 'Meminta penggantian APD baru jika yang lama telah rusak atau kedaluwarsa'],
        forbidden: ['Memodifikasi APD secara sengaja seperti memotong bagian pelindung sepatu', 'Memasuki area aktif operasional tambang tanpa mengenakan rompi reflektif', 'Menggunakan safety glass yang buram/retak parah karena mengganggu pandangan']
      },
      { 
        title: 'Komunikasi Radio', icon: '📡', color: 'from-cyan-600 to-cyan-800 border-cyan-950',
        imgAllowed: 'https://images.unsplash.com/photo-1616447154831-2747597972a7?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1523240795612-9a054b0db644?w=400&auto=format&fit=crop&q=60',
        allowed: ['Menggunakan istilah komunikasi standar yang singkat, padat, dan jelas', 'Melakukan tes pancar (radio check) sebelum unit bergerak memasuki pit', 'Mendengarkan terlebih dahulu memastikan jalur radio kosong sebelum bicara'],
        forbidden: ['Menggunakan frekuensi radio darurat/kerja untuk mengobrol santai', 'Memotong pembicaraan penting unit lain yang sedang bermanuver di tikungan', 'Membiarkan radio dalam kondisi mati atau volume minim saat beroperasi']
      },
      { 
        title: 'Tanggap Darurat', icon: '🚨', color: 'from-red-700 to-red-900 border-red-950',
        imgAllowed: 'https://images.unsplash.com/photo-1546422401-68b415cbf8de?w=400&auto=format&fit=crop&q=60',
        imgForbidden: 'https://images.unsplash.com/photo-1506784983877-45594efa4cbe?w=400&auto=format&fit=crop&q=60',
        allowed: ['Menghafal nomor kontak darurat posko penyelamat (ER T Tambang)', 'Segera bergerak menuju titik kumpul (muster point) terdekat saat alarm berbunyi', 'Mengikuti instruksi dari petugas evacuation warden dengan tertib'],
        forbidden: ['Panik dan berlari saling mendahului berebut jalan keluar evac', 'Kembali ke area bahaya hanya demi menyelamatkan barang berharga pribadi', 'Membuat laporan darurat palsu yang dapat mengacaukan operasional posko']
      }
    ];

    function getPuzzleShape(index) {
      const shapes = [
        '38% 62% 55% 45% / 42% 35% 65% 58%',
        '55% 45% 35% 65% / 60% 40% 60% 40%',
        '48% 52% 68% 32% / 45% 60% 40% 55%',
        '60% 40% 50% 50% / 35% 55% 45% 65%'
      ];
      return shapes[index % shapes.length];
    }

    const container = document.getElementById('grid-container');

    // Render Grid Kartu Puzzle
    menus.forEach((menu, index) => {
      const card = document.createElement('button');
      card.className = `bg-gradient-to-br ${menu.color} w-36 h-36 md:w-48 md:h-48 text-white border-2 md:border-4 shadow-lg p-3 cursor-pointer hover:scale-105 transition-all duration-300 flex items-center justify-center`;
      card.style.borderRadius = getPuzzleShape(index);
      card.onclick = () => openModal(index);

      card.innerHTML = `
        <div class="flex flex-col items-center justify-center text-center h-full w-full shadow-text">
          <div class="text-4xl md:text-6xl mb-2 select-none">${menu.icon}</div>
          <p class="text-[10px] md:text-xs font-bold leading-tight break-words px-1">${menu.title}</p>
        </div>
      `;

      container.appendChild(card);
    });

    // Pengendali Jendela Pop-Up
    const modal = document.getElementById('safety-modal');
    const modalContent = document.getElementById('modal-content');

    function openModal(index) {
      const data = menus[index];
      
      document.getElementById('modal-header').className = `p-4 md:p-5 text-white flex justify-between items-center bg-gradient-to-r ${data.color}`;
      document.getElementById('modal-icon').innerText = data.icon;
      document.getElementById('modal-title').innerText = data.title;

      // Masukkan Gambar dari Data Master
      document.getElementById('img-allowed').src = data.imgAllowed;
      document.getElementById('img-forbidden').src = data.imgForbidden;

      // Suntik Teks Boleh
      const allowedList = document.getElementById('modal-allowed');
      allowedList.innerHTML = '';
      data.allowed.forEach(item => {
        const li = document.createElement('li');
        li.innerText = item;
        allowedList.appendChild(li);
      });

      // Suntik Teks Tidak Boleh
      const forbiddenList = document.getElementById('modal-forbidden');
      forbiddenList.innerHTML = '';
      data.forbidden.forEach(item => {
        const li = document.createElement('li');
        li.innerText = item;
        forbiddenList.appendChild(li);
      });

      // Buka dengan Animasi Smooth
      document.body.classList.add('modal-open');
      modal.classList.remove('hidden');
      setTimeout(() => {
        modal.classList.remove('opacity-0');
        modalContent.classList.remove('scale-95');
      }, 10);
    }

    function closeModal() {
      modal.classList.add('opacity-0');
      modalContent.classList.add('scale-95');
      setTimeout(() => {
        modal.classList.add('hidden');
        document.body.classList.remove('modal-open');
        window.scrollTo({ top: 0, behavior: 'smooth' }); // Otomatis kembali fokus ke atas halaman awal
      }, 300);
    }
  </script>
</body>
</html>
