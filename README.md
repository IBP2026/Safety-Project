<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Safety First - Media Edukasi K3 Pabrik Semen</title>
    <style>
        /* Google Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Chalan:wght@700&family=Roboto:wght@400;500;700&display=swap');

        :root {
            --cement-dark: #2b2d2f;
            --cement-light: #f4f5f7;
            --cement-grey: #70757a;
            --safety-yellow: #ffcc00;
            --safety-orange: #ff5500;
            --danger-red: #d9534f;
            --text-dark: #1a1a1a;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', sans-serif;
        }

        body {
            background-color: var(--cement-light);
            color: var(--text-dark);
            line-height: 1.6;
        }

        /* Hero Banner dengan Nuansa Pabrik */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.75), rgba(43, 45, 47, 0.9)), 
                        url('https://images.unsplash.com/photo-1590069261209-f8e9b8642343?auto=format&fit=crop&q=80&w=1200') no-repeat center center/cover;
            color: #fff;
            padding: 100px 20px;
            text-align: center;
            border-bottom: 8px solid var(--safety-yellow);
        }

        .hero h1 {
            font-size: 3rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 10px;
            color: #fff;
        }

        .hero h1 span {
            color: var(--safety-yellow);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto;
            color: #ddd;
        }

        /* Container Utama */
        .container {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }

        /* Section Title */
        .section-title {
            font-size: 2rem;
            text-transform: uppercase;
            border-left: 6px solid var(--safety-orange);
            padding-left: 15px;
            margin-bottom: 30px;
            color: var(--cement-dark);
        }

        /* Grid Bahaya & Mitigasi */
        .hazard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .hazard-card {
            background: #fff;
            border: 1px solid #e0e0e0;
            border-radius: 4px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }

        .hazard-card:hover {
            transform: translateY(-5px);
        }

        .hazard-image {
            height: 200px;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        /* Label Bahaya Utam */
        .hazard-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background: var(--danger-red);
            color: white;
            padding: 5px 12px;
            font-weight: bold;
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .hazard-content {
            padding: 25px;
        }

        .hazard-content h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--cement-dark);
        }

        .hazard-content h4 {
            color: var(--safety-orange);
            margin-top: 15px;
            font-size: 1rem;
            text-transform: uppercase;
        }

        .hazard-content ul {
            list-style-type: none;
            margin-top: 5px;
        }

        .hazard-content ul li {
            position: relative;
            padding-left: 20px;
            margin-bottom: 8px;
        }

        .hazard-content ul li::before {
            content: "➔";
            position: absolute;
            left: 0;
            color: var(--safety-orange);
        }

        /* Section Insiden / Lesson Learned */
        .incident-box {
            background: var(--cement-dark);
            color: #fff;
            padding: 40px;
            border-radius: 4px;
            border-top: 6px solid var(--danger-red);
            margin-bottom: 50px;
        }

        .incident-box h2 {
            color: #fff;
            margin-bottom: 20px;
        }

        .incident-card {
            background: rgba(255, 255, 255, 0.05);
            border-left: 4px solid var(--safety-yellow);
            padding: 20px;
            margin-bottom: 20px;
        }

        .incident-card h3 {
            color: var(--safety-yellow);
            margin-bottom: 10px;
        }

        .incident-card p strong {
            color: #ff8888;
        }

        /* Aturan Emas / Golden Rules */
        .golden-rules {
            background: #fff;
            padding: 30px;
            border: 2px dashed var(--safety-yellow);
            border-radius: 4px;
            text-align: center;
        }

        .rule-badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }

        .rule-chip {
            background: var(--cement-dark);
            color: var(--safety-yellow);
            padding: 10px 20px;
            font-weight: bold;
            text-transform: uppercase;
            font-size: 0.9rem;
            border-radius: 3px;
        }

        /* Footer */
        footer {
            background: var(--cement-dark);
            color: var(--cement-grey);
            text-align: center;
            padding: 20px;
            margin-top: 6px;
            font-size: 0.9rem;
            border-top: 4px solid var(--cement-grey);
        }
    </style>
</head>
<body>

    <!-- Header Banner -->
    <div class="hero">
        <h1>Safety First: <span>Pabrik Semen</span></h1>
        <p>Identifikasi Bahaya Utama, Aturan Keselamatan, dan Komitmen Nol Kecelakaan Kerja (Zero Accident).</p>
    </div>

    <div class="container">
        
        <!-- Section Bahaya Utama -->
        <h2 class="section-title">Bahaya Utama &amp; Tindakan Pencegahan</h2>
        
        <div class="hazard-grid">
            
            <!-- Bahaya 1: Suhu Tinggi -->
            <div class="hazard-card">
                <div class="hazard-image" style="background-image: url('https://images.unsplash.com/photo-1504917595217-d4dc5ebe6122?auto=format&fit=crop&q=80&w=600');">
                    <span class="hazard-badge">Suhu Tinggi &amp; Klinker</span>
                </div>
                <div class="hazard-content">
                    <h3>Area Kiln &amp; Preheater</h3>
                    <p>Proses pembakaran material semen mencapai suhu 1400°C. Bahaya meliputi radiasi panas, semburan batubara, dan kontak dengan klinker panas.</p>
                    
                    <h4>Yang Harus Dilakukan:</h4>
                    <ul>
                        <li>Wajib menggunakan APD Tahan Panas (Aluminized Suit) saat mendekati area inspeksi aktif.</li>
                        <li>Pastikan sistem interlock pemutus aliran batubara berfungsi sebelum perbaikan.</li>
                        <li>Lakukan pemantauan suhu dinding luar Kiln secara berkala.</li>
                    </ul>
                </div>
            </div>

            <!-- Bahaya 2: Ruang Terbatas -->
            <div class="hazard-card">
                <div class="hazard-image" style="background-image: url('https://images.unsplash.com/photo-1581092160607-ee22621dd758?auto=format&fit=crop&q=80&w=600');">
                    <span class="hazard-badge">Ruang Terbatas</span>
                </div>
                <div class="hazard-content">
                    <h3>Silo &amp; Cement Mill</h3>
                    <p>Pembersihan kerak di dalam silo material atau perawatan bagian dalam Mill berisiko tinggi terhadap kekurangan oksigen, gas beracun, dan tertimbun material.</p>
                    
                    <h4>Yang Harus Dilakukan:</h4>
                    <ul>
                        <li>Wajib menerbitkan <strong>Sertifikat Izin Kerja Ruang Terbatas (Confined Space Permit)</strong>.</li>
                        <li>Lakukan uji gas atmosfer (O2, CO, Gas mudah terbakar) sebelum masuk.</li>
                        <li>Wajib ada 1 orang petugas jaga (Standby Man) di luar area selama pekerjaan berlangsung.</li>
                    </ul>
                </div>
            </div>

            <!-- Bahaya 3: Debu Respirabel -->
            <div class="hazard-card">
                <div class="hazard-image" style="background-image: url('https://images.unsplash.com/photo-1535930749574-1399327ce78f?auto=format&fit=crop&q=80&w=600');">
                    <span class="hazard-badge">Kesehatan Kerja</span>
                </div>
                <div class="hazard-content">
                    <h3>Paparan Debu Silika</h3>
                    <p>Debu halus hasil penggilingan bahan baku (Raw Mill) dan semen dapat menyebabkan gangguan pernapasan kronis hingga Silikosis jika terpapar jangka panjang.</p>
                    
                    <h4>Yang Harus Dilakukan:</h4>
                    <ul>
                        <li>Wajib menggunakan masker respirator minimal tipe N95 atau dust-mask standar industri di seluruh area produksi.</li>
                        <li>Pastikan sistem dust collector (Bag Filter/EP) beroperasi optimal.</li>
                        <li>Lakukan penyemprotan air (water spraying) di area stockpile material.</li>
                    </ul>
                </div>
            </div>

        </div>

        <!-- Section Contoh Insiden -->
        <div class="incident-box">
            <h2 class="section-title" style="color:#fff; border-left-color: var(--danger-red)">Belajar dari Insiden (Lessons Learned)</h2>
            <p style="margin-bottom: 25px; color: #ccc;">Kecelakaan kerja terjadi karena kegagalan dalam mematuhi prosedur baku. Berikut adalah contoh insiden nyata di industri semen global sebagai pengingat pentingnya K3:</p>
            
            <div class="incident-card">
                <h3>Kasus 1: Terperangkap Longsoran Material di Dalam Silo</h3>
                <p><strong>Kronologi:</strong> Dua teknisi masuk ke dalam Silo Semen untuk merontokkan material yang membeku di dinding (*coating*). Mereka tidak menggunakan *safety harness* yang diikat ke luar dan tidak menerapkan sistem LOTO pada conveyor pengisi.</p>
                <p style="margin-top: 10px;"><strong>Dampak:</strong> Material di bagian atas runtuh mendadak, menimbun pekerja. Terjadi fatalitas (korban jiwa).</p>
                <p><strong>Pencegahan:</strong> Selalu gunakan *safety harness* dengan *lifeline* independen, lakukan metode pembersihan dari atas, dan pastikan isolasi energi total (LOTO).</p>
            </div>

            <div class="incident-card">
                <h3>Kasus 2: Luka Bakar Akibat Semburan Flashback Kiln</h3>
                <p><strong>Kronologi:</strong> Saat melakukan pembersihan kerak di area *cyclone preheater*, terjadi sumbatan material (*plugging*). Ketika sumbatan dicolok, material panas meluncur turun dan mendorong udara panas keluar ke arah pintu inspeksi.</p>
                <p style="margin-top: 10px;"><strong>Dampak:</strong> Pekerja di depan pintu inspeksi mengalami luka bakar serius karena tidak menggunakan pakaian pelindung tahan api (*aluminized*).</p>
                <p><strong>Pencegahan:</strong> Jaga jarak aman, gunakan alat mekanis jarak jauh, dan gunakan APD spesifik bahaya radiasi panas tinggi.</p>
            </div>
        </div>

        <!-- Section Golden Rules -->
        <div class="golden-rules">
            <h2 style="text-transform: uppercase; color: var(--cement-dark);">5 Aturan Emas Keselamatan (Safety Golden Rules)</h2>
            <p>Patuhi aturan ini tanpa eksepsi demi pulang dengan selamat ke rumah:</p>
            <div class="rule-badges">
                <span class="rule-chip">1. Patuhi LOTO (Lock Out, Tag Out)</span>
                <span class="rule-chip">2. Izin Kerja Sesuai Risiko</span>
                <span class="rule-chip">3. Gunakan APD Standar &amp; Spesifik</span>
                <span class="rule-chip">4. Dilarang Berada di Bawah Beban Gantung</span>
                <span class="rule-chip">5. Laporkan Setiap Kondisi Tidak Aman (Unsafe Condition)</span>
            </div>
        </div>

    </div>

    <footer>
        <p>&copy; 2026 Departemen Keselamatan &amp; Kesehatan Kerja (K3) - PT Semen Indonesia Perkasa. All Rights Reserved.</p>
    </footer>

</body>
</html>
