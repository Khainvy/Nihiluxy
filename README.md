<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RuangMaster EdTech Ultimate - Portal SMA, SMK, UTBK & TKA</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: #f8fafc; color: #0f172a; display: flex; flex-direction: column; height: 100vh; overflow: hidden; }

        /* HEADER RUANGGURU STYLE */
        header { background: #ffffff; padding: 14px 28px; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #e2e8f0; z-index: 10; box-shadow: 0 2px 4px rgba(0,0,0,0.03); }
        .brand { font-size: 20px; font-weight: 800; color: #0284c7; display: flex; align-items: center; gap: 8px; }
        .tagline { font-size: 12px; background: #e0f2fe; color: #0369a1; padding: 4px 12px; border-radius: 20px; font-weight: 700; }
        .btn-tryout { background: linear-gradient(135deg, #f97316, #ea580c); color: white; border: none; padding: 8px 18px; border-radius: 20px; font-weight: 700; cursor: pointer; font-size: 13px; box-shadow: 0 4px 12px rgba(249, 115, 22, 0.25); transition: 0.2s; }
        .btn-tryout:hover { opacity: 0.9; transform: translateY(-1px); }

        /* LAYOUT UTAMA */
        .main-layout { display: flex; flex: 1; overflow: hidden; }

        /* SIDEBAR FILTERS */
        .sidebar { width: 360px; background: #ffffff; border-right: 1px solid #e2e8f0; display: flex; flex-direction: column; }
        .filter-section { padding: 16px; border-bottom: 1px solid #e2e8f0; background: #f8fafc; display: flex; flex-direction: column; gap: 12px; }
        .filter-group { display: flex; flex-direction: column; gap: 6px; }
        .filter-group label { font-size: 11px; font-weight: 700; color: #64748b; text-transform: uppercase; letter-spacing: 0.5px; }
        .filter-group select { padding: 10px 12px; border: 1px solid #cbd5e1; border-radius: 8px; font-weight: 600; font-size: 13px; color: #1e293b; outline: none; background: white; cursor: pointer; }

        .subject-list { flex: 1; overflow-y: auto; padding: 12px; }
        .subject-card { padding: 14px 16px; margin-bottom: 8px; background: #ffffff; border: 1px solid #e2e8f0; border-radius: 10px; cursor: pointer; transition: all 0.2s; display: flex; justify-content: space-between; align-items: center; }
        .subject-card:hover { border-color: #0284c7; background: #f0f9ff; }
        .subject-card.active { background: #0284c7; color: white; border-color: #0284c7; font-weight: 700; box-shadow: 0 4px 12px rgba(2, 132, 199, 0.25); }
        .subject-card.active .badge-count { background: rgba(255,255,255,0.25); color: white; }
        .badge-count { font-size: 11px; background: #f1f5f9; color: #475569; padding: 3px 8px; border-radius: 6px; font-weight: 600; }

        /* KONTEN UTAMA */
        .content-area { flex: 1; overflow-y: auto; padding: 32px; background: #f8fafc; }
        .content-container { max-width: 920px; margin: 0 auto; }

        .materi-header { margin-bottom: 24px; border-bottom: 2px solid #e2e8f0; padding-bottom: 16px; }
        .materi-header h2 { font-size: 26px; color: #0f172a; font-weight: 800; }
        .materi-header p { font-size: 14px; color: #64748b; margin-top: 4px; }

        /* AKORDION BAB MATERI */
        .chapter-container { display: flex; flex-direction: column; gap: 14px; }
        .chapter-card { background: white; border: 1px solid #e2e8f0; border-radius: 12px; overflow: hidden; box-shadow: 0 1px 3px rgba(0,0,0,0.02); }
        .chapter-header { padding: 18px 22px; background: #ffffff; cursor: pointer; display: flex; justify-content: space-between; align-items: center; font-weight: 700; font-size: 15px; color: #0f172a; transition: background 0.2s; }
        .chapter-header:hover { background: #f8fafc; }
        .chapter-header .toggle-icon { font-size: 18px; font-weight: 800; color: #0284c7; transition: transform 0.2s; }
        .chapter-body { display: none; padding: 24px; background: #f8fafc; border-top: 1px solid #e2e8f0; }
        .chapter-card.open .chapter-body { display: block; }
        .chapter-card.open .toggle-icon { transform: rotate(45deg); }

        .box-title { font-size: 14px; font-weight: 700; color: #0284c7; margin-bottom: 8px; display: flex; align-items: center; gap: 6px; }
        .explanation-box { background: #ffffff; border: 1px solid #cbd5e1; padding: 18px; border-radius: 8px; margin-bottom: 16px; font-size: 14px; line-height: 1.7; color: #334155; }
        .method-box { background: #f0f9ff; border-left: 4px solid #0284c7; padding: 16px; border-radius: 6px; margin-bottom: 18px; font-size: 14px; line-height: 1.6; color: #0369a1; }

        /* VIDEO PLAYER */
        .video-box-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
        .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 10px; background: #000; margin-bottom: 20px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
        .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; }

        /* KUIS EVALUASI */
        .quiz-box { background: white; border: 1px solid #cbd5e1; padding: 20px; border-radius: 10px; }
        .quiz-question { font-size: 14px; font-weight: 600; margin-bottom: 12px; color: #0f172a; line-height: 1.5; }
        .quiz-option { margin: 8px 0; padding: 12px 14px; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; cursor: pointer; font-size: 13px; transition: 0.2s; font-weight: 500; }
        .quiz-option:hover { background: #f0fdf4; border-color: #16a34a; }
        .quiz-feedback { margin-top: 12px; padding: 12px; border-radius: 6px; font-size: 13px; font-weight: 600; display: none; }

        /* CHATBOT AI TUTOR */
        .chat-btn { position: fixed; bottom: 24px; right: 24px; background: #0284c7; color: white; border: none; padding: 12px 22px; border-radius: 30px; font-weight: 700; font-size: 13px; box-shadow: 0 8px 20px rgba(2, 132, 199, 0.35); cursor: pointer; z-index: 100; transition: transform 0.2s; }
        .chat-btn:hover { transform: scale(1.05); }
        .chat-window { display: none; position: fixed; bottom: 85px; right: 24px; width: 350px; height: 450px; background: white; border-radius: 14px; box-shadow: 0 12px 32px rgba(0,0,0,0.15); border: 1px solid #cbd5e1; flex-direction: column; overflow: hidden; z-index: 100; }
        .chat-header { background: #0284c7; color: white; padding: 14px 18px; font-weight: 700; font-size: 14px; display: flex; justify-content: space-between; align-items: center; }
        .chat-body { flex: 1; padding: 14px; overflow-y: auto; font-size: 13px; background: #f8fafc; display: flex; flex-direction: column; gap: 10px; }
        .chat-input { display: flex; padding: 10px; border-top: 1px solid #e2e8f0; background: white; }
        .chat-input input { flex: 1; padding: 8px 12px; border: 1px solid #cbd5e1; border-radius: 6px; outline: none; font-size: 12px; }
        .chat-input button { background: #0284c7; color: white; border: none; padding: 8px 14px; margin-left: 6px; border-radius: 6px; cursor: pointer; font-weight: 700; font-size: 12px; }

        /* TRYOUT MODAL */
        .tryout-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.6); z-index: 2000; justify-content: center; align-items: center; }
        .tryout-box { background: white; width: 90%; max-width: 800px; height: 85vh; border-radius: 14px; display: flex; flex-direction: column; overflow: hidden; box-shadow: 0 20px 40px rgba(0,0,0,0.2); }
        .tryout-top { background: #0f172a; color: white; padding: 18px 24px; display: flex; justify-content: space-between; align-items: center; }
        .tryout-timer { background: #ea580c; padding: 5px 14px; border-radius: 12px; font-weight: 800; font-size: 14px; }
        .tryout-content { flex: 1; padding: 32px; overflow-y: auto; }
        .tryout-bottom { padding: 16px 24px; background: #f1f5f9; border-top: 1px solid #e2e8f0; display: flex; justify-content: space-between; align-items: center; }
    </style>
</head>
<body>

    <header>
        <div class="brand">
            <span>📚 RuangMaster EdTech Ultimate</span>
        </div>
        <div class="tagline">SMA (IPA/IPS), SMK & Modul Terlengkap UTBK/TPS/TKA</div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Tryout UTBK</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="filter-section">
                <div class="filter-group">
                    <label>Pilih Kelompok Program Belajar</label>
                    <select id="jenjangSelect" onchange="renderSubjects()">
                        <option value="utbk_tps" selected>UTBK - Tes Potensi Skolastik (TPS)</option>
                        <option value="utbk_literasi">UTBK - Literasi & Penalaran Matematika</option>
                        <option value="tka_saintek">TKA - Saintek (Matematika, Fisika, Kimia, Biologi)</option>
                        <option value="tka_soshum">TKA - Soshum (Sejarah, Geografi, Sosiologi, Ekonomi)</option>
                        <option value="sma_ipa">SMA - IPA (Saintek Terpadu - K13 & Merdeka)</option>
                        <option value="sma_ips">SMA - IPS (Soshum Terpadu - K13 & Merdeka)</option>
                        <option value="smk_kejuruan">SMK - Kejuruan (Teknik, Otomotif & Bisnis)</option>
                    </select>
                </div>
            </div>
            <div class="subject-list" id="subjectList"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer"></div>
        </main>
    </div>

    <!-- AI CHATBOT GAUTH TUTOR -->
    <button class="chat-btn" onclick="toggleChat()">✨ Tanya AI Tutor (Gauth AI)</button>
    <div class="chat-window" id="chatWindow">
        <div class="chat-header"><span>Gauth AI Smart Assistant</span><span style="cursor:pointer" onclick="toggleChat()">✖</span></div>
        <div class="chat-body" id="chatBody">
            <div style="background:#e0f2fe; padding:10px; border-radius:8px; color:#0369a1;">Halo! Tuliskan soal UTBK, TKA, atau materi SMA/SMK yang ingin kamu bedah solusinya!</div>
        </div>
        <div class="chat-input">
            <input type="text" id="chatInput" placeholder="Ketik soal atau materi..." onkeypress="if(event.key==='Enter') sendChat()">
            <button onclick="sendChat()">Kirim</button>
        </div>
    </div>

    <!-- MODAL TRYOUT SIMULASI UTBK -->
    <div class="tryout-overlay" id="tryoutOverlay">
        <div class="tryout-box">
            <div class="tryout-top">
                <h3>Simulasi Tryout UTBK SNBT Nasional</h3>
                <div class="tryout-timer">15:00</div>
            </div>
            <div class="tryout-content">
                <p style="font-weight: 700; margin-bottom: 12px; font-size: 16px; color:#0284c7;">Soal Penalaran Kuantitatif SNBT:</p>
                <p style="font-size: 15px; margin-bottom: 20px; line-height: 1.6;">
                    Jika 3 pangkat x sama dengan 81 dan 2 pangkat y sama dengan 32, berapakah nilai dari x dikali y (x * y)?
                </p>
                <div class="quiz-option" onclick="pickTryoutAns(this)">A. 15</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">B. 20</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">C. 25</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">D. 30</div>
            </div>
            <div class="tryout-bottom">
                <button style="padding: 10px 20px; border: 1px solid #cbd5e1; background: white; border-radius: 8px; cursor: pointer; font-weight: 600;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 10px 24px; background: #0284c7; color: white; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan Jawaban</button>
            </div>
        </div>
    </div>

    <script>
        // MASTER DATABASE GABUNGAN TOTAL (UTBK TPS, LITERASI, TKA SAINTEK/SOSHUM, SMA IPA/IPS, SMK)
        const MASTER_DATABASE = {
            utbk_tps: [
                {
                    name: "Penalaran Umum (PU)",
                    chapters: [
                        {
                            title: "Bab 1: Penalaran Deduktif & Silogisme",
                            exp: "Penalaran deduktif mengambil kesimpulan khusus dari premis umum. Prinsip utamanya meliputi Modus Ponens, Modus Tollens, dan Silogisme.",
                            trick: "Trik Cepat Silogisme: Jika Premis 1 (P -> Q) dan Premis 2 (Q -> R), langsung coret Q. Kesimpulannya 'P -> R'.",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg",
                            q: "Premis 1: Jika semua siswa rajin, maka nilai ujian tinggi. Premis 2: Nilai ujian tidak tinggi. Kesimpulannya adalah...",
                            opts: ["A. Semua siswa tidak rajin", "B. Ada siswa yang rajin", "C. Siswa tidak lulus", "D. Tidak dapat disimpulkan"],
                            corr: "A. Semua siswa tidak rajin",
                            explain: "Berdasarkan Modus Tollens: (P -> Q) dan (~Q), maka kesimpulannya (~P)."
                        },
                        {
                            title: "Bab 2: Penalaran Induktif & Kesesuaian Pernyataan",
                            exp: "Menganalisis teks parade data untuk menentukan pernyataan yang PASTI BENAR, MUNGKIN BENAR, atau PASTI SALAH.",
                            trick: "Metode Eliminasi Teks: Hindari asumsi luar. Pilih jawaban yang 100% didukung oleh data di dalam paragraf.",
                            video: "https://www.youtube.com/embed/ScMzIvxBSi4",
                            q: "Pernyataan mana yang paling menggambarkan sifat penalaran induktif?",
                            opts: ["A. Menarik kesimpulan umum dari fakta khusus", "B. Menggunakan hukum umum untuk kasus khusus", "C. Membuktikan teorema rumus", "D. Menghitung persamaan matematika"],
                            corr: "A. Menarik kesimpulan umum dari fakta khusus",
                            explain: "Penalaran induktif bergerak dari fakta spesifik menuju kesimpulan umum."
                        }
                    ]
                },
                {
                    name: "Penalaran Kuantitatif (PK)",
                    chapters: [
                        {
                            title: "Bab 1: Logika Aritmatika & Pola Barisan Angka",
                            exp: "Mengidentifikasi pola deret bilangan (loncat, bertingkat, atau Fibonacci) serta pengoperasian aljabar cepat.",
                            trick: "Trik Selisih Bertingkat: Jika pola utama tidak terlihat, cari selisih antar suku berturut-turut untuk menemukan pola tingkat kedua.",
                            video: "https://www.youtube.com/embed/Yt-3C1-eW-c",
                            q: "Berapa angka berikutnya dari deret: 2, 3, 5, 8, 13, 21, ...?",
                            opts: ["A. 34", "B. 32", "C. 30", "D. 35"],
                            corr: "A. 34",
                            explain: "Deret Fibonacci: suku berikutnya adalah jumlah 2 suku sebelumnya (13 + 21 = 34)."
                        }
                    ]
                }
            ],
            utbk_literasi: [
                {
                    name: "Penalaran Matematika (PM)",
                    chapters: [
                        {
                            title: "Bab 1: Aplikasi Matematika Finansial & Statistik Realistis",
                            exp: "Memecahkan kasus nyata berupa bunga tunggal/majemuk, inflasi, estimasi peluang, dan membaca diagram.",
                            trick: "Trik Soal Cerita PM: Ubah dulu cerita panjang ke dalam model matematika sederhana (variabel x dan y) sebelum menghitung.",
                            video: "https://www.youtube.com/embed/Gz_Z1p3p4wA",
                            q: "Sebuah modal Rp1.000.000 mendapat bunga tunggal 10% per tahun. Total uang setelah 2 tahun adalah...",
                            opts: ["A. Rp1.200.000", "B. Rp1.210.000", "C. Rp1.100.000", "D. Rp1.300.000"],
                            corr: "A. Rp1.200.000",
                            explain: "Bunga = 2 * 10% * 1.000.000 = 200.000. Total = 1.000.000 + 200.000 = 1.200.000."
                        }
                    ]
                }
            ],
            tka_saintek: [
                {
                    name: "Matematika Saintek TKA",
                    chapters: [
                        {
                            title: "Bab 1: Limit Fungsi Trigonometri",
                            exp: "Penggunaan rumus identitas jumlah dua sudut serta penyelesaian limit trigonometri mendekati nol.",
                            trick: "Trik Limit 0/0 Trigonometri: Coret fungsi sin(x) atau tan(x) dan ambil koefisien variabel x-nya langsung.",
                            video: "https://www.youtube.com/embed/dC_P0JkU9nE",
                            q: "Berapakah nilai dari lim (x->0) [sin(4x) / tan(2x)]?",
                            opts: ["A. 2", "B. 4", "C. 1/2", "D. 8"],
                            corr: "A. 2",
                            explain: "Coret sin dan tan, ambil koefisiennya: 4 / 2 = 2."
                        }
                    ]
                },
                {
                    name: "Fisika Lanjut TKA",
                    chapters: [
                        {
                            title: "Bab 1: Termodinamika & Hukum Gas Ideal",
                            exp: "Analisis siklus Carnot, perubahan energi dalam, usaha sistem gas (PV = nRT), dan entropi.",
                            trick: "Siklus Carnot: Efisiensi η = 1 - (T_rendah / T_tinggi). Suhu WAJIB menggunakan Kelvin (K = °C + 273).",
                            video: "https://www.youtube.com/embed/2M-vU7fK7-8",
                            q: "Suhu 27°C jika diubah ke dalam skala Kelvin menjadi...",
                            opts: ["A. 300 K", "B. 273 K", "C. 327 K", "D. 373 K"],
                            corr: "A. 300 K",
                            explain: "K = 27 + 273 = 300 K."
                        }
                    ]
                }
            ],
            tka_soshum: [
                {
                    name: "Sejarah Lanjut TKA",
                    chapters: [
                        {
                            title: "Bab 1: Peradaban Dunia Kuno & Perang Dunia I-II",
                            exp: "Analisis dampak revolusi industri, pembentukan aliansi Perang Dunia, dan organisasi pascaperang (PBB).",
                            trick: "Pemicu PD I: Pembunuhan Putra Mahkota Austria-Hongaria (Franz Ferdinand) di Sarajevo oleh Gavrilo Princip.",
                            video: "https://www.youtube.com/embed/ScMzIvxBSi4",
                            q: "Peristiwa pemicu utama meletusnya Perang Dunia I adalah...",
                            opts: ["A. Pembunuhan Franz Ferdinand", "B. Penyerangan Pearl Harbor", "C. Invasi Polandia", "D. Revolusi Rusia"],
                            corr: "A. Pembunuhan Franz Ferdinand",
                            explain: "Pembunuhan Franz Ferdinand memicu reaksi berantai aliansi militer Eropa tahun 1914."
                        }
                    ]
                }
            ],
            sma_ipa: [
                {
                    name: "Matematika IPA Terpadu (K13 + Merdeka)",
                    chapters: [
                        {
                            title: "Bab 1: Eksponen, Bentuk Akar & Logaritma",
                            exp: "Penggabungan konsep pangkat, penyederhanaan bentuk akar, serta invers eksponen berupa logaritma.",
                            trick: "Metode Cepat Logaritma: Gunakan sifat a^log(b) * b^log(c) = a^log(c). Coret basis/numerus yang sama.",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg",
                            q: "Jika 2^x = 32 dan 3^y = 81, berapakah nilai dari x + y?",
                            opts: ["A. 7", "B. 8", "C. 9", "D. 10"],
                            corr: "C. 9",
                            explain: "2^5 = 32 (x = 5) dan 3^4 = 81 (y = 4). Maka x + y = 5 + 4 = 9."
                        },
                        {
                            title: "Bab 2: Persamaan & Fungsi Kuadrat",
                            exp: "Memahami pola grafik parabola, menentukan titik puncak, diskriminan (D = b^2 - 4ac), serta sifat-sifat akar.",
                            trick: "Trik Akar Cepat: Jumlah akar x1 + x2 = -b/a dan perkalian akar x1 * x2 = c/a tanpa perlu memfaktorkan.",
                            video: "https://www.youtube.com/embed/Yt-3C1-eW-c",
                            q: "Jumlah akar-akar dari x^2 - 8x + 12 = 0 adalah...",
                            opts: ["A. 8", "B. -8", "C. 12", "D. -12"],
                            corr: "A. 8",
                            explain: "x1 + x2 = -(-8)/1 = 8."
                        }
                    ]
                },
                {
                    name: "Fisika Mekanika",
                    chapters: [
                        {
                            title: "Bab 1: Kinematika Gerak Lurus (GLB & GLBB)",
                            exp: "Mempelajari posisi, kecepatan, dan percepatan benda pada lintasan lurus beraturan maupun berubah beraturan.",
                            trick: "Formula Tanpa Waktu: Gunakan vt^2 = v0^2 + 2as ketika nilai waktu (t) tidak diketahui.",
                            video: "https://www.youtube.com/embed/2M-vU7fK7-8",
                            q: "Benda bermassa 5 kg ditarik gaya 30 N. Percepatannya adalah...",
                            opts: ["A. 6 m/s^2", "B. 5 m/s^2", "C. 150 m/s^2", "D. 10 m/s^2"],
                            corr: "A. 6 m/s^2",
                            explain: "a = F / m = 30 / 5 = 6 m/s^2."
                        }
                    ]
                }
            ],
            sma_ips: [
                {
                    name: "Ekonomi & Akuntansi Terpadu",
                    chapters: [
                        {
                            title: "Bab 1: Permintaan, Penawaran & Keseimbangan Pasar",
                            exp: "Analisis pergerakan kurva permintaan dan penawaran serta penentuan titik keseimbangan harga (equilibrium).",
                            trick: "Trik Equilibrium: Samakan nilai Qd = Qs atau Pd = Ps secara langsung.",
                            video: "https://www.youtube.com/embed/xQx9hW6j1U0",
                            q: "Titik keseimbangan pasar terjadi pada saat...",
                            opts: ["A. Qd = Qs", "B. Qd > Qs", "C. Qd < Qs", "D. Harga jual tertinggi"],
                            corr: "A. Qd = Qs",
                            explain: "Keseimbangan terjadi saat kuantitas permintaan sama dengan penawaran."
                        },
                        {
                            title: "Bab 2: Siklus Akuntansi Perusahaan Jasa",
                            exp: "Pencatatan transaksi keuangan mulai dari Jurnal Umum, Buku Besar, Neraca Saldo, hingga Laporan Keuangan.",
                            trick: "Aturan H-E-L-P: Harta dan Beban bertambah di Debit. Utang, Modal, dan Pendapatan bertambah di Kredit.",
                            video: "https://www.youtube.com/embed/z9zX4eW-Zcw",
                            q: "Akun beban gaji yang bertambah dicatat di sisi...",
                            opts: ["A. Debit", "B. Kredit", "C. Ikhtisar Laba/Rugi", "D. Penyesuaian"],
                            corr: "A. Debit",
                            explain: "Beban bertambah selalu dicatat di sisi Debit."
                        }
                    ]
                }
            ],
            smk_kejuruan: [
                {
                    name: "Teknik Otomotif & Mesin",
                    chapters: [
                        {
                            title: "Bab 1: Prinsip Kerja Motor 4 Langkah (4-Tak)",
                            exp: "Mesin 4-tak menyelesaikan 1 siklus kerja dalam 4 langkah torak dan 2 putaran poros engkol.",
                            trick: "Ingat Urutan H-K-U-B: Hisap, Kompresi, Usaha, Buang.",
                            video: "https://www.youtube.com/embed/ScMzIvxBSi4",
                            q: "Percikan api busi terjadi pada akhir langkah...",
                            opts: ["A. Kompresi", "B. Hisap", "C. Buang", "D. Usaha"],
                            corr: "A. Kompresi",
                            explain: "Busi memercikkan api pada akhir langkah kompresi."
                        }
                    ]
                }
            ]
        };

        function renderSubjects() {
            const jenjang = document.getElementById('jenjangSelect').value;
            const subjects = MASTER_DATABASE[jenjang] || [];
            const listContainer = document.getElementById('subjectList');
            listContainer.innerHTML = "";

            if(subjects.length === 0) {
                listContainer.innerHTML = "<p style='font-size:12px; padding:10px; color:#64748b;'>Materi sedang diperbarui...</p>";
                return;
            }

            subjects.forEach((sub, idx) => {
                const card = document.createElement('div');
                card.className = `subject-card ${idx === 0 ? 'active' : ''}`;
                card.onclick = () => {
                    document.querySelectorAll('.subject-card').forEach(c => c.classList.remove('active'));
                    card.classList.add('active');
                    renderContent(sub);
                };
                card.innerHTML = `<span>${sub.name}</span><span class="badge-count">${sub.chapters.length} Bab</span>`;
                listContainer.appendChild(card);
            });

            renderContent(subjects[0]);
        }

        function renderContent(sub) {
            const container = document.getElementById('materiContainer');
            if(!sub) { container.innerHTML = ""; return; }

            let html = `
                <div class="materi-header">
                    <h2>${sub.name}</h2>
                    <p>Modul Terpadu & Bank Soal Evaluasi Persiapan Akademik</p>
                </div>
                <div class="chapter-container">
            `;

            sub.chapters.forEach((chap, idx) => {
                html += `
                    <div class="chapter-card" id="chap-${idx}">
                        <div class="chapter-header" onclick="toggleChapter(${idx})">
                            <span>${chap.title}</span>
                            <span class="toggle-icon">+</span>
                        </div>
                        <div class="chapter-body">
                            <div class="box-title">📖 Penjelasan Konsep Akademik</div>
                            <div class="explanation-box">${chap.exp}</div>
                            
                            <div class="box-title">💡 Metode Trik Cepat (RuangMaster / Gauth AI)</div>
                            <div class="method-box">${chap.trick}</div>

                            <div class="video-box-header">
                                <div class="box-title" style="margin-bottom:0;">🎥 Video Pembelajaran Bab Ini</div>
                                <span style="font-size:11px; color:#64748b;">(Ganti URL iframe pada kode untuk ubah video)</span>
                            </div>
                            <div class="video-wrapper">
                                <iframe src="${chap.video}" allowfullscreen></iframe>
                            </div>

                            <div class="quiz-box">
                                <div class="box-title">✏️ Latihan Soal Evaluasi Bab</div>
                                <div class="quiz-question">${chap.q}</div>
                                ${chap.opts.map(opt => `
                                    <div class="quiz-option" onclick="checkQuiz(this, '${opt}', '${chap.corr}', '${chap.explain}')">${opt}</div>
                                `).join('')}
                                <div class="quiz-feedback"></div>
                            </div>
                        </div>
                    </div>
                `;
            });

            html += `</div>`;
            container.innerHTML = html;
        }

        function toggleChapter(idx) {
            const card = document.getElementById(`chap-${idx}`);
            card.classList.toggle('open');
        }

        function checkQuiz(el, selected, correct, explain) {
            const parent = el.closest('.quiz-box');
            const feedback = parent.querySelector('.quiz-feedback');
            feedback.style.display = 'block';

            if(selected === correct) {
                feedback.style.background = '#dcfce7';
                feedback.style.color = '#15803d';
                feedback.innerHTML = `✅ <strong>Jawaban Benar!</strong> ${explain}`;
            } else {
                feedback.style.background = '#fee2e2';
                feedback.style.color = '#b91c1c';
                feedback.innerHTML = `❌ <strong>Kurang tepat.</strong> Jawaban benar: ${correct}. Pembahasan: ${explain}`;
            }
        }

        function openTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'flex'; }
        function closeTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'none'; }
        function pickTryoutAns(el) {
            document.querySelectorAll('.quiz-option').forEach(o => o.style.background = '#f8fafc');
            el.style.background = '#e0f2fe';
        }
        function submitTryout() {
            alert("Hasil Tryout Anda Dikirim!\n• Skor IRT: 890 / 1000\n• Prediksi Masuk PTN: Sangat Tinggi (99%)");
            closeTryoutModal();
        }

        function toggleChat() {
            const win = document.getElementById('chatWindow');
            win.style.display = win.style.display === 'flex' ? 'none' : 'flex';
        }

        function sendChat() {
            const input = document.getElementById('chatInput');
            const body = document.getElementById('chatBody');
            if(input.value.trim() !== "") {
                const text = input.value;
                body.innerHTML += `<div style="text-align:right; margin:4px 0;"><span style="background:#0284c7; color:white; padding:8px 12px; border-radius:8px; font-size:12px; display:inline-block;">${text}</span></div>`;
                input.value = "";
                body.scrollTop = body.scrollHeight;

                setTimeout(() => {
                    body.innerHTML += `<div style="background:#e0f2fe; padding:10px; border-radius:8px; color:#0369a1;"><strong>Gauth AI Assistant:</strong> Untuk pertanyaan tentang "${text}", kamu dapat menelusuri modul bab terkait atau membedah solusinya dengan trik cepat yang ada!</div>`;
                    body.scrollTop = body.scrollHeight;
                }, 600);
            }
        }

        window.onload = () => { renderSubjects(); };
    </script>
</body>
</html>
