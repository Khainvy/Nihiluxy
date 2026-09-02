<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RuangBelajar Pro - SMA & UTBK Terlengkap</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: #f8fafc; color: #0f172a; display: flex; flex-direction: column; height: 100vh; overflow: hidden; }
        
        /* HEADER */
        header { background: #ffffff; padding: 12px 24px; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #e2e8f0; z-index: 10; box-shadow: 0 1px 3px rgba(0,0,0,0.05); }
        .logo { font-size: 20px; font-weight: 800; color: #2563eb; display: flex; align-items: center; gap: 8px; }
        .curriculum-switch { display: flex; background: #e2e8f0; border-radius: 20px; padding: 3px; }
        .curr-btn { padding: 6px 14px; border: none; border-radius: 16px; font-size: 12px; font-weight: 700; cursor: pointer; color: #64748b; background: transparent; transition: 0.2s; }
        .curr-btn.active { background: #2563eb; color: white; }
        .btn-tryout { background: linear-gradient(135deg, #ea580c, #f97316); color: white; border: none; padding: 8px 18px; border-radius: 20px; font-weight: 700; cursor: pointer; font-size: 13px; box-shadow: 0 4px 12px rgba(234, 88, 12, 0.2); }

        /* MAIN LAYOUT */
        .main-layout { display: flex; flex: 1; overflow: hidden; }

        /* SIDEBAR */
        .sidebar { width: 340px; background: #ffffff; border-right: 1px solid #e2e8f0; display: flex; flex-direction: column; }
        .sidebar-filter { padding: 15px; border-bottom: 1px solid #e2e8f0; background: #f8fafc; }
        .sidebar-filter label { font-size: 11px; font-weight: 700; color: #64748b; text-transform: uppercase; }
        .sidebar-filter select { width: 100%; margin-top: 5px; padding: 10px; border: 1px solid #cbd5e1; border-radius: 8px; font-weight: 600; color: #1e293b; outline: none; cursor: pointer; font-size: 13px; }

        .subject-list { flex: 1; overflow-y: auto; padding: 12px; }
        .subject-card { padding: 12px 14px; margin-bottom: 8px; background: #f8fafc; border: 1px solid #e2e8f0; border-radius: 10px; cursor: pointer; transition: 0.2s; display: flex; justify-content: space-between; align-items: center; }
        .subject-card:hover { border-color: #3b82f6; background: #eff6ff; }
        .subject-card.active { background: #2563eb; color: white; border-color: #2563eb; }
        .subject-card.active .badge-count { background: rgba(255,255,255,0.2); color: white; }
        .subject-title { font-size: 13px; font-weight: 700; }
        .badge-count { font-size: 11px; color: #64748b; background: #e2e8f0; padding: 2px 8px; border-radius: 12px; font-weight: 600; }

        /* CONTENT AREA */
        .content-area { flex: 1; overflow-y: auto; padding: 24px; background: #f8fafc; }
        .content-container { max-width: 920px; margin: 0 auto; }

        .materi-header { margin-bottom: 18px; }
        .materi-header h2 { font-size: 22px; color: #0f172a; font-weight: 800; }
        .materi-header p { font-size: 13px; color: #64748b; margin-top: 2px; }

        .video-box { background: white; border-radius: 14px; padding: 20px; border: 1px solid #e2e8f0; box-shadow: 0 2px 8px rgba(0,0,0,0.04); margin-bottom: 24px; }
        .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 10px; background: #000; margin-bottom: 20px; }
        .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; }

        /* TABS METHOD */
        .tabs-nav { display: flex; gap: 8px; border-bottom: 2px solid #e2e8f0; margin-bottom: 16px; flex-wrap: wrap; }
        .tab-btn { padding: 10px 16px; font-weight: 700; font-size: 13px; color: #64748b; cursor: pointer; border-bottom: 2px solid transparent; margin-bottom: -2px; }
        .tab-btn.active { color: #2563eb; border-bottom-color: #2563eb; }

        .tab-content { display: none; }
        .tab-content.active { display: block; }

        /* LIST BAB */
        .bab-group { display: flex; flex-direction: column; gap: 10px; height: 300px; overflow-y: auto; padding-right: 5px; }
        .bab-item { display: flex; justify-content: space-between; align-items: center; padding: 12px 16px; background: #f1f5f9; border-radius: 8px; border-left: 4px solid #2563eb; }
        .bab-name { font-size: 13px; font-weight: 700; color: #334155; }
        .btn-play { background: #2563eb; color: white; border: none; padding: 6px 14px; border-radius: 6px; font-size: 12px; cursor: pointer; font-weight: 700; }

        /* BOX METODE & KUIS */
        .summary-card { background: #eff6ff; border: 1px solid #bfdbfe; padding: 20px; border-radius: 10px; font-size: 14px; line-height: 1.7; color: #1e40af; }
        .trick-card { background: #fefce8; border: 1px solid #fef08a; padding: 20px; border-radius: 10px; font-size: 14px; line-height: 1.7; color: #854d0e; }
        .quiz-card { background: #ffffff; border: 1px solid #e2e8f0; padding: 20px; border-radius: 10px; }
        .quiz-option { display: block; margin: 8px 0; padding: 12px 14px; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; cursor: pointer; font-size: 14px; transition: 0.2s; font-weight: 500; }
        .quiz-option:hover { background: #f0fdf4; border-color: #22c55e; }

        /* GEMINI AI CHATBOT */
        .gemini-btn { position: fixed; bottom: 20px; right: 20px; background: linear-gradient(135deg, #7c3aed, #4f46e5); color: white; border: none; padding: 12px 20px; border-radius: 30px; font-weight: 700; font-size: 13px; box-shadow: 0 8px 20px rgba(124, 58, 237, 0.3); cursor: pointer; z-index: 1000; }
        .chat-modal { display: none; position: fixed; bottom: 75px; right: 20px; width: 340px; height: 440px; background: white; border-radius: 14px; box-shadow: 0 12px 32px rgba(0,0,0,0.15); border: 1px solid #e2e8f0; z-index: 1000; flex-direction: column; overflow: hidden; }
        .chat-header { background: #7c3aed; color: white; padding: 12px 16px; font-weight: 700; font-size: 14px; display: flex; justify-content: space-between; align-items: center; }
        .chat-body { flex: 1; padding: 12px; overflow-y: auto; background: #f8fafc; font-size: 13px; }
        .msg-ai { background: #f1f5f9; padding: 10px; border-radius: 8px; margin-bottom: 8px; color: #1e293b; border-left: 3px solid #7c3aed; }
        .msg-user { background: #2563eb; color: white; padding: 10px; border-radius: 8px; margin-bottom: 8px; text-align: right; margin-left: 20%; }
        .chat-input-box { display: flex; padding: 10px; border-top: 1px solid #e2e8f0; background: white; }
        .chat-input-box input { flex: 1; padding: 8px 12px; border: 1px solid #cbd5e1; border-radius: 6px; outline: none; font-size: 12px; }
        .chat-input-box button { background: #7c3aed; color: white; border: none; padding: 8px 12px; margin-left: 6px; border-radius: 6px; cursor: pointer; font-weight: 700; }

        /* TRYOUT MODAL */
        .tryout-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.6); z-index: 2000; justify-content: center; align-items: center; }
        .tryout-box { background: white; width: 90%; max-width: 800px; height: 85vh; border-radius: 14px; display: flex; flex-direction: column; overflow: hidden; }
        .tryout-top { background: #0f172a; color: white; padding: 16px 20px; display: flex; justify-content: space-between; align-items: center; }
        .tryout-timer { background: #ea580c; padding: 4px 12px; border-radius: 12px; font-weight: 800; font-size: 14px; }
        .tryout-content { flex: 1; padding: 30px; overflow-y: auto; }
        .tryout-bottom { padding: 16px 20px; background: #f1f5f9; border-top: 1px solid #e2e8f0; display: flex; justify-content: space-between; }
    </style>
</head>
<body>

    <header>
        <div class="logo">
            <span>RuangBelajar Pro</span>
        </div>
        <div class="curriculum-switch">
            <button class="curr-btn active" onclick="setCurriculum('merdeka', this)">Kurikulum Merdeka (Fase E-F)</button>
            <button class="curr-btn" onclick="setCurriculum('k13', this)">Kurikulum 2013 Lengkap</button>
        </div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Simulasi UTBK Nasional</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="sidebar-filter">
                <label>Pilih Jenjang & Kategori</label>
                <select id="gradeSelect" onchange="loadCategorySubjects()">
                    <optgroup label="Tingkat SMA">
                        <option value="k10">Kelas 10 (Semua Jurusan)</option>
                        <option value="k11_ipa">Kelas 11 MIPA</option>
                        <option value="k11_ips">Kelas 11 IPS</option>
                        <option value="k12_ipa">Kelas 12 MIPA</option>
                        <option value="k12_ips">Kelas 12 IPS</option>
                        <option value="k12_bahasa">Kelas 12 Bahasa & Budaya</option>
                    </optgroup>
                    <optgroup label="Persiapan PTN">
                        <option value="utbk_tps" selected>UTBK SNBT - Tes Potensi Skolastik</option>
                        <option value="utbk_literasi">UTBK SNBT - Literasi</option>
                        <option value="tka_saintek">TKA Saintek (Ujian Mandiri)</option>
                        <option value="tka_soshum">TKA Soshum (Ujian Mandiri)</option>
                    </optgroup>
                </select>
            </div>
            <div class="subject-list" id="subjectListContainer"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer"></div>
        </main>
    </div>

    <!-- AI CHATBOT -->
    <button class="gemini-btn" onclick="toggleChat()">✨ Tanya Gemini AI</button>
    <div class="chat-modal" id="chatWindow">
        <div class="chat-header">
            <span>Gemini AI Tutor</span>
            <span style="cursor:pointer;" onclick="toggleChat()">✖</span>
        </div>
        <div class="chat-body" id="chatBody">
            <div class="msg-ai"><strong>Gemini:</strong> Halo! Masukkan soal matematika kompleks atau teori fisika yang ingin dibahas.</div>
        </div>
        <div class="chat-input-box">
            <input type="text" id="chatInput" placeholder="Ketik soal..." onkeypress="handleChatKey(event)">
            <button onclick="sendChatMessage()">Kirim</button>
        </div>
    </div>

    <!-- TRYOUT MODAL -->
    <div class="tryout-overlay" id="tryoutOverlay">
        <div class="tryout-box">
            <div class="tryout-top">
                <h3>Tryout Akbar SNBT - Penalaran Matematika</h3>
                <div class="tryout-timer">15:00</div>
            </div>
            <div class="tryout-content">
                <p style="font-weight: 700; margin-bottom: 12px; font-size: 16px;">Soal Nomor 1:</p>
                <p style="font-size: 16px; margin-bottom: 20px; line-height: 1.6;">
                    Suatu bakteri membelah diri menjadi dua setiap 15 menit. Jika pada pukul 08:00 terdapat 30 bakteri, berapakah jumlah bakteri pada pukul 10:00?
                </p>
                <div class="quiz-option" onclick="pickTryoutAns(this)">A. 3.840</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">B. 7.680</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">C. 15.360</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">D. 30.720</div>
            </div>
            <div class="tryout-bottom">
                <button style="padding: 10px 20px; border: 1px solid #cbd5e1; background: white; border-radius: 8px; cursor: pointer; font-weight: 600;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 10px 24px; background: #2563eb; color: white; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan Jawaban</button>
            </div>
        </div>
    </div>

    <script>
        let currentCurriculum = 'merdeka';

        const appDatabase = {
            // ================= KELAS 10 =================
            k10: [
                {
                    id: "mtk10", name: "Matematika Wajib & Peminatan", tutor: "Tim Matematika Ahli", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Mencakup Eksponen, Logaritma, Sistem Persamaan Linear Tiga Variabel (SPLTV), Pertidaksamaan Rasional, Vektor, Fungsi Kuadrat, dan Trigonometri Dasar.<br><br><strong>Fokus Pemahaman:</strong><br>1. Sifat distributif eksponen berlaku dua arah.<br>2. Logaritma adalah invers dari eksponen: a^c = b berarti a log b = c.<br>3. Nilai Sin, Cos, Tan harus dihafalkan minimal di kuadran I (0, 30, 45, 60, 90 derajat).",
                    trick: "💡 <strong>Trik Logaritma & Eksponen:</strong><br>Jika menemukan soal berpangkat bertingkat, selesaikan dari pangkat paling atas. Untuk soal logaritma dengan basis berantai: <code>a log b × b log c = a log c</code>. Jika basisnya berbeda tapi bisa disamakan (misal 2 dan 4), gunakan sifat <code>a^n log b^m = (m/n) a log b</code>.",
                    bab: ["Bab 1: Eksponen & Bentuk Akar", "Bab 2: Logaritma", "Bab 3: Sistem Persamaan Linear Tiga Variabel (SPLTV)", "Bab 4: Pertidaksamaan Rasional & Irasional", "Bab 5: Relasi & Fungsi", "Bab 6: Trigonometri Sudut Berelasi", "Bab 7: Vektor R2 dan R3", "Bab 8: Barisan dan Deret"],
                    quiz: {
                        question: "Jika 2^x = 16 dan 3^y = 81, berapakah nilai dari x + y?",
                        options: ["A. 6", "B. 7", "C. 8", "D. 9"],
                        correct: "C. 8",
                        explain: "2^x = 16 -> x = 4. 3^y = 81 -> y = 4. Maka x + y = 4 + 4 = 8."
                    }
                },
                {
                    id: "fis10", name: "Fisika", tutor: "Master Fisika SMA", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Mempelajari Besaran, Satuan, Angka Penting, Vektor, Kinematika (GLB, GLBB, Gerak Parabola, Gerak Melingkar), dan Dinamika Partikel (Hukum Newton).",
                    trick: "💡 <strong>Metode Rumus Tanpa Waktu (GLBB):</strong><br>Jika soal tidak menyebutkan dan tidak menanyakan waktu (t), langsung gunakan rumus: <code>Vt² = V0² + 2as</code>. Untuk Gerak Parabola, ketinggian maksimum (H) dihafal dengan <code>H = (V0² sin²θ) / 2g</code>.",
                    bab: ["Bab 1: Hakikat Fisika & Pengukuran", "Bab 2: Vektor: Penjumlahan & Penguraian", "Bab 3: Gerak Lurus Beraturan (GLB) & GLBB", "Bab 4: Gerak Parabola", "Bab 5: Gerak Melingkar Beraturan", "Bab 6: Hukum Newton tentang Gerak", "Bab 7: Hukum Newton tentang Gravitasi"],
                    quiz: {
                        question: "Sebuah mobil mengerem dari kecepatan 20 m/s hingga berhenti dalam waktu 4 detik. Berapa percepatannya?",
                        options: ["A. -5 m/s²", "B. 5 m/s²", "C. -4 m/s²", "D. 4 m/s²"],
                        correct: "A. -5 m/s²",
                        explain: "Gunakan a = (Vt - V0) / t. a = (0 - 20) / 4 = -5 m/s² (tanda minus berarti perlambatan)."
                    }
                },
                {
                    id: "kim10", name: "Kimia", tutor: "Pakar Kimia Nasional", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Menguasai Struktur Atom, Konfigurasi Elektron, Ikatan Kimia (Ion, Kovalen, Logam), Bentuk Molekul (VSEPR), dan Stoikiometri dasar (Mol, Molaritas).",
                    trick: "💡 <strong>Trik Ikatan Kovalen vs Ion:</strong><br>Ion = Logam + Non-Logam (Gol I/IIA + Gol VI/VIIA). Kovalen = Non-Logam + Non-Logam. Untuk hibridisasi bentuk molekul, ingat jumlah domain elektron: 2=Linear (sp), 3=Segitiga Datar (sp²), 4=Tetrahedral (sp³).",
                    bab: ["Bab 1: Model & Struktur Atom", "Bab 2: Sistem Periodik Unsur", "Bab 3: Ikatan Ion & Kovalen", "Bab 4: Bentuk Molekul (Teori Domain Elektron)", "Bab 5: Gaya Antarmolekul", "Bab 6: Tata Nama Senyawa & Persamaan Reaksi", "Bab 7: Hukum Dasar Kimia", "Bab 8: Konsep Mol (Stoikiometri)"],
                    quiz: {
                        question: "Senyawa dengan ikatan kovalen polar di bawah ini adalah...",
                        options: ["A. H2", "B. CH4", "C. HCl", "D. O2"],
                        correct: "C. HCl",
                        explain: "Kovalen polar terjadi antara dua atom non-logam yang memiliki perbedaan keelektronegatifan, seperti H dan Cl."
                    }
                },
                {
                    id: "bio10", name: "Biologi", tutor: "Tutor Biologi Ahli", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Fokus pada Ruang Lingkup Biologi, Virus, Bakteri (Monera), Protista, Fungi (Jamur), Plantae, Animalia, dan Ekologi.",
                    trick: "💡 <strong>Mnemonik Klasifikasi Kingdom Plantae:</strong><br>Bryophyta (Lumut) = Akar semu, tidak ada pembuluh. Pteridophyta (Paku) = Akar sejati, ada pembuluh, berspora. Spermatophyta (Biji) = Akar sejati, ada pembuluh, berbiji.",
                    bab: ["Bab 1: Ruang Lingkup Biologi", "Bab 2: Virus: Struktur & Reproduksi", "Bab 3: Archaebacteria & Eubacteria", "Bab 4: Protista", "Bab 5: Fungi (Jamur)", "Bab 6: Plantae (Dunia Tumbuhan)", "Bab 7: Animalia (Invertebrata & Vertebrata)", "Bab 8: Ekologi & Daur Biogeokimia"],
                    quiz: {
                        question: "Fungi (Jamur) yang berperan dalam pembuatan tempe adalah...",
                        options: ["A. Saccharomyces cerevisiae", "B. Rhizopus oryzae", "C. Penicillium notatum", "D. Aspergillus wentii"],
                        correct: "B. Rhizopus oryzae",
                        explain: "Rhizopus oryzae adalah jamur kelompok Zygomycota yang digunakan untuk memfermentasi kedelai menjadi tempe."
                    }
                },
                {
                    id: "eko10", name: "Ekonomi", tutor: "Tim Ekonomi SMA", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Mencakup Konsep Dasar Ilmu Ekonomi, Masalah Ekonomi, Pelaku Ekonomi (Circulair Flow Diagram), Permintaan, Penawaran, Keseimbangan Pasar, Bank, dan OJK.",
                    trick: "💡 <strong>Trik Menghitung Keseimbangan Pasar:</strong><br>Keseimbangan terjadi ketika fungsi Permintaan (Qd) = Fungsi Penawaran (Qs). Jangan tertukar dengan harga (Pd = Ps). Setelah dapat Q, masukkan ke salah satu fungsi untuk mencari P.",
                    bab: ["Bab 1: Konsep Ilmu & Masalah Ekonomi", "Bab 2: Sistem Ekonomi Dunia", "Bab 3: Pelaku & Interaksi Ekonomi (Circulair Flow)", "Bab 4: Permintaan, Penawaran & Harga Keseimbangan", "Bab 5: Pasar Persaingan Sempurna & Tidak Sempurna", "Bab 6: Bank Sentral & Sistem Pembayaran", "Bab 7: Otoritas Jasa Keuangan (OJK)", "Bab 8: Manajemen & Koperasi"],
                    quiz: {
                        question: "Jika Qd = 100 - 2P dan Qs = -20 + 4P, berapakah harga keseimbangannya?",
                        options: ["A. 10", "B. 20", "C. 30", "D. 40"],
                        correct: "B. 20",
                        explain: "Qd = Qs -> 100 - 2P = -20 + 4P -> 120 = 6P -> P = 20."
                    }
                },
                {
                    id: "sej10", name: "Sejarah", tutor: "Tutor Sejarah Nasional", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Konsep berpikir sinkronik & diakronik, masa Pra-aksara Indonesia, peradaban awal dunia, dan masuknya agama Hindu-Buddha serta Islam ke Nusantara.",
                    trick: "💡 <strong>Perbedaan Sinkronik & Diakronik:</strong><br>Diakronik = Memanjang dalam waktu, menyempit dalam ruang (Kronologis/Sejarah murni). Sinkronik = Meluas dalam ruang, menyempit dalam waktu (Pendekatan Ilmu Sosial seperti Ekonomi/Sosiologi pada satu masa tertentu).",
                    bab: ["Bab 1: Konsep Berpikir Sejarah", "Bab 2: Manusia Purba di Indonesia & Dunia", "Bab 3: Corak Kehidupan Masyarakat Praaksara", "Bab 4: Peradaban Awal Dunia (Mesopotamia, Mesir, India)", "Bab 5: Masuknya Hindu-Buddha ke Nusantara", "Bab 6: Kerajaan Hindu-Buddha Besar (Sriwijaya & Majapahit)", "Bab 7: Masuknya Islam ke Nusantara", "Bab 8: Kerajaan-Kerajaan Islam Nusantara"],
                    quiz: {
                        question: "Fosil manusia purba Meganthropus Paleojavanicus ditemukan di daerah...",
                        options: ["A. Trinil", "B. Sangiran", "C. Ngandong", "D. Mojokerto"],
                        correct: "B. Sangiran",
                        explain: "Fosil ini ditemukan oleh von Koenigswald di formasi Pucangan, Sangiran."
                    }
                }
            ],

            // ================= KELAS 11 IPA =================
            k11_ipa: [
                {
                    id: "mtk11_ipa", name: "Matematika 11 MIPA", tutor: "Tim Matematika", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Program Linear, Matriks, Transformasi Geometri, Barisan & Deret Tak Hingga, Limit Fungsi Aljabar, Turunan Fungsi Aljabar, dan Integral Tak Tentu.",
                    trick: "💡 <strong>Trik Turunan Pembagian (U/V):</strong><br>y = U/V $\\rightarrow$ y' = (U'V - UV') / V². Jangan terbalik urutan pembilangnya! <br><strong>Trik Limit Tak Hingga Aljabar:</strong> Bentuk √(ax²+bx+c) - √(px²+qx+r). Jika a=p, gunakan rumus cepat: (b - q) / 2√a.",
                    bab: ["Bab 1: Induksi Matematika", "Bab 2: Program Linear Dua Variabel", "Bab 3: Matriks: Determinan & Invers", "Bab 4: Transformasi Geometri", "Bab 5: Polinomial (Teorema Sisa & Faktor)", "Bab 6: Limit Fungsi Aljabar", "Bab 7: Turunan Fungsi Aljabar", "Bab 8: Integral Tak Tentu Aljabar"],
                    quiz: {
                        question: "Turunan pertama dari y = 3x^4 - 2x^2 + 5x adalah...",
                        options: ["A. 12x^3 - 4x + 5", "B. 12x^3 - 2x + 5", "C. 4x^3 - 4x + 5", "D. 12x^4 - 4x^2 + 5"],
                        correct: "A. 12x^3 - 4x + 5",
                        explain: "Aturan turunan: pangkat dikali koefisien depan, lalu pangkat dikurangi 1."
                    }
                },
                {
                    id: "fis11", name: "Fisika 11", tutor: "Tim Fisika", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Dinamika Rotasi, Kesetimbangan Benda Tegar, Elastisitas, Fluida Statis, Fluida Dinamis, Suhu & Kalor, Teori Kinetik Gas, dan Termodinamika.",
                    trick: "💡 <strong>Trik Fluida (Hukum Bernoulli):</strong><br>Kecepatan fluida berbanding terbalik dengan tekanan. Jika aliran air menyempit, kecepatan (v) NAIK, tetapi tekanan (P) justru TURUN. Konsep ini diaplikasikan pada sayap pesawat terbang (Gaya Angkat).",
                    bab: ["Bab 1: Dinamika Rotasi & Momen Inersia", "Bab 2: Kesetimbangan Benda Tegar", "Bab 3: Elastisitas & Hukum Hooke", "Bab 4: Fluida Statis (Pascal, Archimedes)", "Bab 5: Fluida Dinamis (Kontinuitas & Bernoulli)", "Bab 6: Suhu, Kalor & Perpindahan Kalor", "Bab 7: Teori Kinetik Gas Ideal", "Bab 8: Termodinamika (Mesin Carnot)"],
                    quiz: {
                        question: "Sebuah gaya 50 N bekerja pada jarak 0,2 m dari poros putar dengan sudut 90 derajat. Berapa besar momen gaya (torsi)?",
                        options: ["A. 10 Nm", "B. 25 Nm", "C. 100 Nm", "D. 250 Nm"],
                        correct: "A. 10 Nm",
                        explain: "Torsi (τ) = F × r × sin(θ) = 50 × 0.2 × sin(90°) = 10 Nm."
                    }
                },
                {
                    id: "kim11", name: "Kimia 11", tutor: "Tim Kimia", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Senyawa Hidrokarbon, Minyak Bumi, Termokimia (ΔH), Laju Reaksi, Kesetimbangan Kimia, Larutan Asam Basa, Penyangga (Buffer), dan Hidrolisis Garam.",
                    trick: "💡 <strong>Trik Hidrolisis Garam:</strong><br>Sifat garam ditentukan oleh induk yang KUAT. Jika berasal dari Asam Kuat + Basa Lemah $\\rightarrow$ Garam Asam (pH < 7). Rumusnya selalu menggunakan akar(Kw / Kb × [Kation]). Gunakan Kb (lawan dari sifat garamnya).",
                    bab: ["Bab 1: Senyawa Hidrokarbon & Isomer", "Bab 2: Minyak Bumi & Fraksinasi", "Bab 3: Termokimia (Hukum Hess & Energi Ikatan)", "Bab 4: Laju Reaksi & Faktor Penentu", "Bab 5: Kesetimbangan Kimia (Kc & Kp)", "Bab 6: Teori Asam Basa & Derajat Keasaman (pH)", "Bab 7: Larutan Penyangga (Buffer)", "Bab 8: Hidrolisis Garam & Ksp"],
                    quiz: {
                        question: "Pencampuran antara asam asetat (CH3COOH) berlebih dengan basa kuat (NaOH) akan membentuk larutan...",
                        options: ["A. Penyangga Asam", "B. Penyangga Basa", "C. Hidrolisis Asam", "D. Garam Netral"],
                        correct: "A. Penyangga Asam",
                        explain: "Asam lemah yang tersisa (berlebih) bereaksi dengan basa kuat membentuk larutan buffer asam."
                    }
                }
            ],

            // ================= KELAS 11 IPS =================
            k11_ips: [
                {
                    id: "eko11", name: "Ekonomi 11", tutor: "Tim Ekonomi", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Pendapatan Nasional (Pendekatan Produksi, Pengeluaran, Pendapatan), Pertumbuhan Ekonomi, Ketenagakerjaan, Inflasi, Kebijakan Moneter & Fiskal, APBN, Pajak, dan Perdagangan Internasional.",
                    trick: "💡 <strong>Trik Menghitung Pendapatan Nasional (Pengeluaran):</strong><br>C-I-G-X-M $\\rightarrow$ Y = C + I + G + (X - M). (C=Konsumsi, I=Investasi, G=Pengeluaran Pemerintah, X=Ekspor, M=Impor).",
                    bab: ["Bab 1: Pendapatan Nasional", "Bab 2: Pertumbuhan & Pembangunan Ekonomi", "Bab 3: Ketenagakerjaan & Pengangguran", "Bab 4: Indeks Harga & Inflasi", "Bab 5: Kebijakan Moneter & Kebijakan Fiskal", "Bab 6: APBN & APBD", "Bab 7: Perpajakan di Indonesia", "Bab 8: Perdagangan Internasional"],
                    quiz: {
                        question: "Kebijakan pemerintah untuk menurunkan jumlah uang beredar guna mengatasi inflasi dengan menjual surat berharga disebut kebijakan...",
                        options: ["A. Operasi Pasar Terbuka (Open Market)", "B. Diskonto", "C. Cadangan Kas", "D. Kredit Selektif"],
                        correct: "A. Operasi Pasar Terbuka (Open Market)",
                        explain: "Dengan menjual Surat Bank Indonesia (SBI), uang dari masyarakat tertarik masuk ke bank sentral."
                    }
                },
                {
                    id: "sos11", name: "Sosiologi 11", tutor: "Tim Sosiologi", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Pembentukan Kelompok Sosial (Paguyuban, Patembayan, In-Group, Out-Group), Permasalahan Sosial, Kesetaraan, Konflik, dan Resolusi Konflik.",
                    trick: "💡 <strong>Beda Paguyuban & Patembayan (Tönnies):</strong><br>Paguyuban (Gemeinschaft) = Ikatan batin murni, kekeluargaan (Contoh: RT, Marga). Patembayan (Gesellschaft) = Ikatan pamrih, orientasi ekonomi/kontrak (Contoh: Serikat pekerja, perusahaan).",
                    bab: ["Bab 1: Proses Pembentukan Kelompok Sosial", "Bab 2: Berbagai Jenis Kelompok Sosial", "Bab 3: Permasalahan Sosial dalam Masyarakat", "Bab 4: Eksklusi Sosial & Kemiskinan", "Bab 5: Perbedaan, Kesetaraan & Harmoni Sosial", "Bab 6: Konflik & Kekerasan Sosial", "Bab 7: Resolusi Konflik (Mediasi, Arbitrase)", "Bab 8: Integrasi & Reintegrasi Sosial"],
                    quiz: {
                        question: "Penyelesaian konflik dimana pihak ketiga memiliki wewenang untuk memberikan keputusan mutlak (mengikat) disebut...",
                        options: ["A. Arbitrase", "B. Mediasi", "C. Konsiliasi", "D. Ajudikasi"],
                        correct: "A. Arbitrase",
                        explain: "Dalam arbitrase, pihak ketiga adalah pengambil keputusan. Dalam mediasi, pihak ketiga hanya penasihat."
                    }
                },
                {
                    id: "geo11", name: "Geografi 11", tutor: "Tim Geografi", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Posisi Silang Indonesia, Biosfer (Persebaran Flora Fauna), Antroposfer (Dinamika Penduduk), Sumber Daya Alam, Ketahanan Pangan, dan Mitigasi Bencana.",
                    trick: "💡 <strong>Trik Menghitung Pertumbuhan Penduduk Alami:</strong><br>P = L - M (Lahir - Mati). Pertumbuhan Total: P = (L - M) + (I - E) dimana I = Imigrasi, E = Emigrasi.",
                    bab: ["Bab 1: Indonesia Sebagai Poros Maritim Dunia", "Bab 2: Bioma & Biosfer Dunia", "Bab 3: Persebaran Flora Fauna Indonesia", "Bab 4: Pengelolaan Sumber Daya Alam", "Bab 5: Ketahanan Pangan & Energi Terbarukan", "Bab 6: Dinamika Kependudukan (Piramida Penduduk)", "Bab 7: Kebudayaan Nasional & Global", "Bab 8: Mitigasi & Adaptasi Bencana Alam"],
                    quiz: {
                        question: "Hutan hujan tropis di Indonesia memiliki ciri khas yaitu...",
                        options: ["A. Kanopi rapat, heterogen, hijau sepanjang tahun", "B. Pohon sejenis, menggugurkan daun di musim kemarau", "C. Didominasi padang rumput", "D. Curah hujan sangat rendah"],
                        correct: "A. Kanopi rapat, heterogen, hijau sepanjang tahun",
                        explain: "Hutan hujan tropis sangat lebat (berkanopi) dan terdiri dari berbagai macam spesies (heterogen)."
                    }
                }
            ],

            // ================= KELAS 12 IPA =================
            k12_ipa: [
                {
                    id: "mtk12_ipa", name: "Matematika 12 MIPA", tutor: "Jerome Polin", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Geometri Ruang (Jarak Titik, Garis, Bidang), Statistika (Mean, Median, Modus, Simpangan), Kaidah Pencacahan (Permutasi, Kombinasi), Peluang Kejadian Majemuk.",
                    trick: "💡 <strong>Trik Jarak Kubus Rusuk 'a':</strong><br>Diagonal sisi = a√2. Diagonal ruang = a√3. Jarak titik sudut ke tengah bidang = (a/2)√6. Jarak titik sudut ke diagonal ruang = (a/3)√6.",
                    bab: ["Bab 1: Geometri Ruang - Jarak Titik ke Titik", "Bab 2: Geometri Ruang - Jarak Titik ke Garis/Bidang", "Bab 3: Statistika - Penyajian Data", "Bab 4: Statistika - Pemusatan Data (Mean, Median, Modus)", "Bab 5: Statistika - Penyebaran Data", "Bab 6: Aturan Perkalian & Faktorial", "Bab 7: Permutasi & Kombinasi", "Bab 8: Peluang Kejadian Majemuk"],
                    quiz: {
                        question: "Berapa banyak cara memilih 3 pengurus dari 10 calon tanpa memperhatikan jabatan (kombinasi)?",
                        options: ["A. 120", "B. 240", "C. 720", "D. 30"],
                        correct: "A. 120",
                        explain: "Kombinasi C(10,3) = 10! / (7! * 3!) = (10*9*8) / (3*2*1) = 120."
                    }
                },
                {
                    id: "fis12", name: "Fisika 12", tutor: "Tim Fisika 12", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Listrik Arus Searah (DC), Listrik Statis, Medan Magnet, Induksi Elektromagnetik, Listrik Bolak-Balik (AC), Gelombang Elektromagnetik, Relativitas, Fisika Kuantum, Inti Atom.",
                    trick: "💡 <strong>Hukum II Kirchhoff (Loop):</strong><br>ΣE + Σ(IR) = 0. Trik tanda arah loop: Jika arah loop mengenai kutub panjang (positif) baterai lebih dulu, maka E positif. Arus I searah loop = positif.",
                    bab: ["Bab 1: Rangkaian Arus Searah (Hukum Ohm & Kirchhoff)", "Bab 2: Listrik Statis (Gaya Coulomb & Potensial)", "Bab 3: Medan Magnet & Gaya Lorentz", "Bab 4: Induksi Elektromagnetik (Faraday & Lenz)", "Bab 5: Rangkaian Arus Bolak-Balik (RLC)", "Bab 6: Radiasi Gelombang Elektromagnetik", "Bab 7: Teori Relativitas Khusus", "Bab 8: Fisika Inti & Radioaktivitas"],
                    quiz: {
                        question: "Pada rangkaian RLC seri, jika reaktansi induktif (XL) lebih besar dari reaktansi kapasitif (XC), maka sifat rangkaian adalah...",
                        options: ["A. Induktif", "B. Kapasitif", "C. Resonansi", "D. Resistif murni"],
                        correct: "A. Induktif",
                        explain: "Jika XL > XC, arus tertinggal oleh tegangan, sehingga rangkaian bersifat induktif."
                    }
                },
                {
                    id: "kim12", name: "Kimia 12", tutor: "Tim Kimia 12", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Sifat Koligatif Larutan, Redoks & Elektrokimia (Sel Volta & Elektrolisis), Kimia Unsur, Senyawa Karbon Turunan Alkana, Benzena, dan Makromolekul.",
                    trick: "💡 <strong>Trik Reaksi Elektrolisis (Katoda):</strong><br>Perhatikan WUJUD zat. Jika larutan (aq) dan kation golongan IA, IIA, Al, Mn $\\rightarrow$ yang tereduksi adalah AIR (2H2O + 2e -> H2 + 2OH-). Jika lelehan (l) $\\rightarrow$ kation logam itu sendiri yang tereduksi.",
                    bab: ["Bab 1: Sifat Koligatif Larutan Nonelektrolit", "Bab 2: Sifat Koligatif Larutan Elektrolit (Faktor Van't Hoff)", "Bab 3: Penyetaraan Reaksi Redoks", "Bab 4: Sel Volta & Potensial Sel", "Bab 5: Sel Elektrolisis & Hukum Faraday", "Bab 6: Kimia Unsur (Halogen, Alkali, Gas Mulia)", "Bab 7: Senyawa Karbon (Alkohol, Eter, Aldehid, Keton, Asam Karboksilat)", "Bab 8: Benzena & Polimer"],
                    quiz: {
                        question: "Gugus fungsi dari senyawa alkanon (keton) adalah...",
                        options: ["A. -OH", "B. -O-", "C. -CO-", "D. -COOH"],
                        correct: "C. -CO-",
                        explain: "Keton memiliki gugus karbonil (-CO-) yang terikat pada dua atom karbon lain."
                    }
                },
                {
                    id: "bio12", name: "Biologi 12", tutor: "Tim Biologi", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Pertumbuhan Perkembangan, Enzim & Metabolisme (Respirasi & Fotosintesis), Substansi Genetik, Pembelahan Sel, Hukum Mendel, Mutasi, Evolusi, Bioteknologi.",
                    trick: "💡 <strong>Trik Respirasi Aerob:</strong><br>1. Glikolisis: Glukosa -> 2 Asam Piruvat + 2 ATP + 2 NADH (Sitosol).<br>2. DO: Piruvat -> 2 Asetil KoA + 2 CO2 + 2 NADH (Matriks).<br>3. Krebs: Asetil KoA -> 4 CO2 + 6 NADH + 2 FADH2 + 2 ATP (Matriks).",
                    bab: ["Bab 1: Pertumbuhan & Perkembangan", "Bab 2: Enzim & Kerjanya", "Bab 3: Katabolisme (Respirasi Aerob & Anaerob)", "Bab 4: Anabolisme (Fotosintesis)", "Bab 5: DNA, RNA & Sintesis Protein", "Bab 6: Pembelahan Sel (Mitosis & Meiosis)", "Bab 7: Hukum Mendel & Penyimpangannya", "Bab 8: Evolusi & Bioteknologi"],
                    quiz: {
                        question: "Basa nitrogen penyusun RNA yang TIDAK terdapat pada DNA adalah...",
                        options: ["A. Adenin", "B. Guanin", "C. Sitosin", "D. Urasil"],
                        correct: "D. Urasil",
                        explain: "Pada RNA, Timin (pada DNA) digantikan oleh Urasil."
                    }
                }
            ],

            // ================= KELAS 12 IPS =================
            k12_ips: [
                {
                    id: "eko12", name: "Akuntansi (Ekonomi) 12", tutor: "Tutor Akuntansi", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Akuntansi sebagai Sistem Informasi, Persamaan Dasar Akuntansi, Jurnal Umum, Buku Besar, Neraca Saldo, Jurnal Penyesuaian, Kertas Kerja, dan Laporan Keuangan Perusahaan Jasa & Dagang.",
                    trick: "💡 <strong>Aturan Debit Kredit (Saldo Normal):</strong><br>H E L P (Harta & Beban bertambah di DEBIT. Utang, Modal, Pendapatan bertambah di KREDIT).",
                    bab: ["Bab 1: Akuntansi & Sistem Informasi", "Bab 2: Persamaan Dasar Akuntansi", "Bab 3: Jurnal Umum Perusahaan Jasa", "Bab 4: Buku Besar & Neraca Saldo", "Bab 5: Jurnal Penyesuaian (Perlengkapan, Penyusutan, Beban YMhD)", "Bab 6: Laporan Keuangan (Laba Rugi, Perubahan Modal, Neraca)", "Bab 7: Jurnal Khusus Perusahaan Dagang", "Bab 8: Harga Pokok Penjualan (HPP)"],
                    quiz: {
                        question: "Jika pemilik perusahaan mengambil uang kas untuk keperluan pribadi (prive), maka pencatatannya dalam jurnal umum adalah...",
                        options: ["A. Beban Debit, Kas Kredit", "B. Prive Debit, Kas Kredit", "C. Kas Debit, Prive Kredit", "D. Modal Debit, Kas Kredit"],
                        correct: "B. Prive Debit, Kas Kredit",
                        explain: "Prive bertambah di Debit, Kas berkurang di Kredit."
                    }
                },
                {
                    id: "geo12", name: "Geografi 12", tutor: "Tim Geografi", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Konsep Wilayah dan Perwilayahan, Pola Keruangan Desa dan Kota, Interaksi Desa-Kota, Penginderaan Jauh, Sistem Informasi Geografis (SIG), Negara Maju & Berkembang.",
                    trick: "💡 <strong>Trik Teori Sektoral (Homer Hoyt):</strong><br>Sektor selalu berbentuk juring lingkaran/potongan kue. Ingat urutan dari tengah: CBD (Pusat Bisnis) $\\rightarrow$ Manufaktur/Grosir $\\rightarrow$ Pemukiman Kelas Rendah $\\rightarrow$ Menengah $\\rightarrow$ Tinggi.",
                    bab: ["Bab 1: Wilayah & Perwilayahan (Nodal, Formal)", "Bab 2: Struktur Keruangan Desa & Kota", "Bab 3: Teori Interaksi Desa-Kota (Gravitasi, Titik Henti)", "Bab 4: Prinsip Penginderaan Jauh", "Bab 5: Interpretasi Citra Satelit", "Bab 6: Konsep Dasar SIG", "Bab 7: Analisis SIG untuk Tata Ruang", "Bab 8: Karakteristik Negara Maju & Berkembang"],
                    quiz: {
                        question: "Zona pemukiman kelas tinggi pada Teori Konsentris (Burgess) terletak di wilayah paling...",
                        options: ["A. Pusat kota", "B. Tepi/Luar kota (Zona Penglaju)", "C. Dekat pabrik", "D. Zona transisi"],
                        correct: "B. Tepi/Luar kota (Zona Penglaju)",
                        explain: "Dalam teori konsentris, kelas atas memilih tinggal jauh dari pusat kota/pabrik demi kenyamanan."
                    }
                },
                {
                    id: "sos12", name: "Sosiologi 12", tutor: "Tim Sosiologi", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Perubahan Sosial, Dampak Perubahan Sosial, Globalisasi, Ketimpangan Sosial di Era Global, Kearifan Lokal, dan Pemberdayaan Komunitas.",
                    trick: "💡 <strong>Bentuk Perubahan Sosial:</strong><br>Evolusi (Lambat, tanpa direncanakan matang, cth: masyarakat tradisional ke industri). Revolusi (Cepat, mengubah dasar institusi, cth: Revolusi Industri/Kemerdekaan).",
                    bab: ["Bab 1: Hakikat Perubahan Sosial", "Bab 2: Teori & Bentuk Perubahan Sosial", "Bab 3: Globalisasi & Modernisasi", "Bab 4: Dampak Globalisasi (Konsumerisme, Westernisasi)", "Bab 5: Ketimpangan Sosial & Digital Divide", "Bab 6: Kearifan Lokal Nusantara", "Bab 7: Strategi Pemberdayaan Komunitas", "Bab 8: Evaluasi Aksi Pemberdayaan"],
                    quiz: {
                        question: "Kesenjangan budaya dimana elemen materiil berubah cepat sementara elemen non-materiil (nilai/norma) lambat beradaptasi disebut...",
                        options: ["A. Cultural Shock", "B. Cultural Lag", "C. Anomie", "D. Disorganisasi"],
                        correct: "B. Cultural Lag",
                        explain: "Cultural Lag (ketertinggalan budaya) terjadi karena kecepatan adopsi teknologi tidak diimbangi kesiapan mental/hukum."
                    }
                }
            ],

            // ================= UTBK TPS =================
            utbk_tps: [
                {
                    id: "pk", name: "Pengetahuan Kuantitatif (PK)", tutor: "Tutor Eksakta UTBK", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Aljabar, Geometri dasar, Teori Bilangan, Aritmetika Sosial, Fungsi, Logika Matematika Dasar, Peluang.",
                    trick: "💡 <strong>Metode Substitusi Ekstrem:</strong> Jika ada soal 'Manakah hubungan P dan Q yang benar?', cobalah angka ekstrem seperti x=0, x=1, dan x=-1, atau x=0.5 (pecahan). Jika hasil hubungan berubah-ubah, jawabannya pasti 'Hubungan tidak dapat ditentukan'.",
                    bab: ["Aljabar & Persamaan", "Geometri Bidang & Ruang", "Statistika, Peluang & Kombinatorika", "Kecukupan Data (Pernyataan 1 & 2)", "Analisis Kuantitatif P & Q"],
                    quiz: {
                        question: "Jika x > 0 dan y < 0, manakah yang nilainya pasti negatif?",
                        options: ["A. x - y", "B. x^2 + y", "C. x * y", "D. -y / x"],
                        correct: "C. x * y",
                        explain: "Positif dikali Negatif selalu menghasilkan Negatif."
                    }
                },
                {
                    id: "pu", name: "Penalaran Umum (PU)", tutor: "Tim Logika UTBK", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Penalaran Deduktif, Induktif, Logika Matematika, Deret Angka/Huruf, Kesesuaian Pernyataan, Kesimpulan Paragraf.",
                    trick: "💡 <strong>Modus Tollens (Logika Dasar):</strong> Jika P -> Q benar, dan diketahui ~Q (Negasi Q) benar. Maka kesimpulan pastinya adalah ~P. (Cth: Jika hujan, tanah basah. Tanah tidak basah. Pasti tidak hujan).",
                    bab: ["Penalaran Deduktif & Logika Proposisi", "Penalaran Induktif & Generalisasi", "Pola Deret Angka & Huruf", "Pemahaman Bacaan & Grafik Data"],
                    quiz: {
                        question: "Jika Amir makan, ia kenyang. Jika Amir kenyang, ia mengantuk. Amir tidak mengantuk. Kesimpulan?",
                        options: ["A. Amir makan", "B. Amir tidak makan", "C. Amir kenyang tapi tidak mengantuk", "D. Tidak bisa disimpulkan"],
                        correct: "B. Amir tidak makan",
                        explain: "Silogisme: P->Q, Q->R, maka P->R. Jika ~R benar (Modus Tollens), maka ~P benar (Amir tidak makan)."
                    }
                },
                {
                    id: "pbm", name: "Pemahaman Bacaan & Menulis (PBM)", tutor: "Pakar Bahasa", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Fokus pada struktur tata bahasa baku (PUEBI/EYD), keefektifan kalimat, penggunaan konjungsi, huruf kapital, tanda baca.",
                    trick: "💡 <strong>Aturan Imbuhan Me-N:</strong> Me-N luluh jika bertemu kata dasar berawalan K, T, S, P yang diikuti vokal. (Contoh: me + pesona = memesona. me + kritik = mengkritik [k tidak luluh karena diikuti konsonan 'r']).",
                    bab: ["Penggunaan Tanda Baca & Huruf Kapital", "Kata Baku, Serapan, & Bentukan Kata", "Kalimat Efektif & Struktur Inti", "Kepaduan Paragraf & Konjungsi Antarkalimat"],
                    quiz: {
                        question: "Penulisan gabungan kata yang benar adalah...",
                        options: ["A. Bertanggungjawab", "B. Tanggung jawab", "C. Pertanggung jawaban", "D. Bekerja-sama"],
                        correct: "B. Tanggung jawab",
                        explain: "Kata majemuk ditulis terpisah jika tidak mendapat awalan dan akhiran sekaligus (tanggung jawab, tetapi dipertanggungjawabkan)."
                    }
                }
            ],

            // ================= TKA SAINTEK =================
            tka_saintek: [
                {
                    id: "tka_fis", name: "TKA Fisika", tutor: "Tim Fisika TKA", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Soal Analitik HOTS: Mekanika, Termodinamika, Elektromagnetik, Fisika Modern, Optik Fisis/Geometri.",
                    trick: "💡 <strong>Trik Optik (Cermin/Lensa):</strong> Jarak fokus (f) positif untuk cermin Cekung / lensa Cembung. Negatif untuk cermin Cembung / lensa Cekung. M = |s'/s|. Jika s' negatif = Maya, Tegak.",
                    bab: ["Mekanika (Dinamika, Usaha Energi, Momentum)", "Zat & Kalor (Asas Black, Termodinamika)", "Gelombang & Optik (Interferensi, Difraksi)", "Listrik Magnet", "Fisika Modern (Relativitas, Kuantum)"],
                    quiz: {
                        question: "Dimensi dari besaran Usaha adalah...",
                        options: ["A. [M][L][T]^-1", "B. [M][L]^2[T]^-2", "C. [M][L][T]^-2", "D. [M][L]^2[T]^-3"],
                        correct: "B. [M][L]^2[T]^-2",
                        explain: "Usaha (W) = F * s = (m*a) * s. Dimensinya: kg(M) * m/s^2 (L T^-2) * m (L) = M L^2 T^-2."
                    }
                }
            ]
        };

        // UI & NAVIGATION LOGIC
        function setCurriculum(curr, btn) {
            currentCurriculum = curr;
            document.querySelectorAll('.curr-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            loadCategorySubjects();
        }

        function loadCategorySubjects() {
            const cat = document.getElementById('gradeSelect').value;
            const subjects = appDatabase[cat] || [];
            const container = document.getElementById('subjectListContainer');
            
            container.innerHTML = "";
            document.getElementById('materiContainer').innerHTML = "";

            if (subjects.length === 0) {
                container.innerHTML = "<p style='padding:15px; font-size:13px; color:#64748b;'>Kategori ini sedang dalam pembaruan konten.</p>";
                return;
            }

            subjects.forEach((sub, idx) => {
                const card = document.createElement('div');
                card.className = `subject-card ${idx === 0 ? 'active' : ''}`;
                card.onclick = () => {
                    document.querySelectorAll('.subject-card').forEach(c => c.classList.remove('active'));
                    card.classList.add('active');
                    renderMateri(sub);
                };
                
                card.innerHTML = `
                    <div class="subject-title">${sub.name}</div>
                    <div class="badge-count">${sub.bab.length} Bab</div>
                `;
                container.appendChild(card);
            });

            renderMateri(subjects[0]);
        }

        function renderMateri(sub) {
            const container = document.getElementById('materiContainer');
            
            let babListHtml = "";
            sub.bab.forEach((b) => {
                babListHtml += `
                    <div class="bab-item">
                        <span class="bab-name">${b}</span>
                        <button class="btn-play" onclick="alert('Memutar materi: ${b}')">Tonton Video</button>
                    </div>
                `;
            });

            const currLabel = currentCurriculum === 'merdeka' ? 'Kurikulum Merdeka' : 'Kurikulum 2013';

            container.innerHTML = `
                <div class="materi-header">
                    <h2>${sub.name} <span style="font-size:14px; font-weight:600; color:#2563eb; background:#dbeafe; padding:4px 10px; border-radius:12px; margin-left:10px;">${currLabel}</span></h2>
                    <p style="margin-top:8px;">Pengajar: <strong>${sub.tutor}</strong></p>
                </div>

                <div class="video-box">
                    <div class="video-wrapper">
                        <iframe src="${sub.video}" allowfullscreen></iframe>
                    </div>

                    <div class="tabs-nav">
                        <div class="tab-btn active" onclick="switchTab(this, 'tabBab')">📺 Video & Bab</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabSummary')">📖 Rangkuman Lengkap</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabTrick')">⚡ Metode Cepat</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabQuiz')">✏️ Kuis Pemahaman</div>
                    </div>

                    <div class="tab-content active" id="tabBab">
                        <div class="bab-group">${babListHtml}</div>
                    </div>

                    <div class="tab-content" id="tabSummary">
                        <div class="summary-card">${sub.summary}</div>
                    </div>

                    <div class="tab-content" id="tabTrick">
                        <div class="trick-card">${sub.trick}</div>
                    </div>

                    <div class="tab-content" id="tabQuiz">
                        <div class="quiz-card">
                            <p style="font-weight:700; margin-bottom:12px; font-size:15px;">Latihan Kuis Bab:</p>
                            <p style="margin-bottom:16px; font-size:15px;">${sub.quiz.question}</p>
                            ${sub.quiz.options.map(opt => `
                                <div class="quiz-option" onclick="checkQuiz('${opt}', '${sub.quiz.correct}', '${sub.quiz.explain}')">${opt}</div>
                            `).join('')}
                            <div id="quizResult" style="margin-top:16px; font-weight:700; padding:10px; border-radius:8px; display:none;"></div>
                        </div>
                    </div>
                </div>
            `;
        }

        function switchTab(btn, tabId) {
            document.querySelectorAll('.tab-btn').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            btn.classList.add('active');
            document.getElementById(tabId).classList.add('active');
        }

        function checkQuiz(selected, correct, explain) {
            const res = document.getElementById('quizResult');
            res.style.display = 'block';
            if (selected === correct) {
                res.style.backgroundColor = '#dcfce7';
                res.innerHTML = `<span style="color:#16a34a;">✅ Jawaban Benar! ${explain}</span>`;
            } else {
                res.style.backgroundColor = '#fee2e2';
                res.innerHTML = `<span style="color:#dc2626;">❌ Kurang Tepat. Jawaban Benar: ${correct}.<br><br>Pembahasan: ${explain}</span>`;
            }
        }

        function openTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'flex'; }
        function closeTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'none'; }
        function pickTryoutAns(el) {
            document.querySelectorAll('.quiz-option').forEach(o => o.style.background = '#f8fafc');
            el.style.background = '#dbeafe';
        }
        function submitTryout() {
            alert("Hasil Tryout Anda:\n• Skor IRT: 755 / 1000\n• Prediksi Kelulusan PTN: 91% (Sangat Tinggi)\n\nPembahasan detail telah masuk ke portal belajar!");
            closeTryoutModal();
        }

        function toggleChat() {
            const win = document.getElementById('chatWindow');
            win.style.display = win.style.display === 'flex' ? 'none' : 'flex';
        }
        function handleChatKey(e) { if(e.key === 'Enter') sendChatMessage(); }
        function sendChatMessage() {
            const input = document.getElementById('chatInput');
            const body = document.getElementById('chatBody');
            
            if (input.value.trim() !== "") {
                const text = input.value;
                body.innerHTML += `<div class="msg-user">${text}</div>`;
                input.value = "";
                body.scrollTop = body.scrollHeight;

                setTimeout(() => {
                    body.innerHTML += `
                        <div class="msg-ai">
                            <strong>Gemini AI:</strong> Untuk materi "${text}", pastikan kamu sudah membaca <strong>Rangkuman Lengkap</strong> dan mempraktikkan <strong>Metode Cepat</strong> di tab materi yang sedang terbuka. Tetap semangat belajarnya!
                        </div>
                    `;
                    body.scrollTop = body.scrollHeight;
                }, 700);
            }
        }

        window.onload = () => { loadCategorySubjects(); };
    </script>
</body>
</html>
                                       
