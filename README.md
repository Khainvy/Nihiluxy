    <!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SMArt Academy - Ruang Belajar SMA & UTBK Gratis</title>
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
        .bab-group { display: flex; flex-direction: column; gap: 10px; }
        .bab-item { display: flex; justify-content: space-between; align-items: center; padding: 12px 16px; background: #f1f5f9; border-radius: 8px; border-left: 4px solid #2563eb; }
        .bab-name { font-size: 13px; font-weight: 700; color: #334155; }
        .btn-play { background: #2563eb; color: white; border: none; padding: 6px 14px; border-radius: 6px; font-size: 12px; cursor: pointer; font-weight: 700; }

        /* BOX METODE & KUIS */
        .summary-card { background: #eff6ff; border: 1px solid #bfdbfe; padding: 16px; border-radius: 10px; font-size: 13px; line-height: 1.6; color: #1e40af; }
        .trick-card { background: #fefce8; border: 1px solid #fef08a; padding: 16px; border-radius: 10px; font-size: 13px; line-height: 1.6; color: #854d0e; }
        .quiz-card { background: #ffffff; border: 1px solid #e2e8f0; padding: 18px; border-radius: 10px; }
        .quiz-option { display: block; margin: 8px 0; padding: 10px 14px; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; cursor: pointer; font-size: 13px; transition: 0.2s; }
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
        .tryout-box { background: white; width: 90%; max-width: 750px; height: 80vh; border-radius: 14px; display: flex; flex-direction: column; overflow: hidden; }
        .tryout-top { background: #0f172a; color: white; padding: 16px 20px; display: flex; justify-content: space-between; align-items: center; }
        .tryout-timer { background: #ea580c; padding: 4px 12px; border-radius: 12px; font-weight: 800; font-size: 13px; }
        .tryout-content { flex: 1; padding: 24px; overflow-y: auto; }
        .tryout-bottom { padding: 14px 20px; background: #f1f5f9; border-top: 1px solid #e2e8f0; display: flex; justify-content: space-between; }
    </style>
</head>
<body>

    <header>
        <div class="logo">
            <span>SMArt Academy</span>
        </div>
        <div class="curriculum-switch">
            <button class="curr-btn active" onclick="setCurriculum('merdeka', this)">Kurikulum Merdeka</button>
            <button class="curr-btn" onclick="setCurriculum('k13', this)">Kurikulum 2013</button>
        </div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Tryout UTBK & TKA</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="sidebar-filter">
                <label>Pilihan Kelas / Program</label>
                <select id="gradeSelect" onchange="loadCategorySubjects()">
                    <optgroup label="Tingkat SMA Regular">
                        <option value="k10">Kelas 10 (Fase E / IPA & IPS)</option>
                        <option value="k11_ipa">Kelas 11 IPA (Fase F)</option>
                        <option value="k11_ips">Kelas 11 IPS (Fase F)</option>
                        <option value="k12_ipa">Kelas 12 IPA</option>
                        <option value="k12_ips">Kelas 12 IPS</option>
                        <option value="k12_bahasa">Kelas 12 Bahasa & Budaya</option>
                    </optgroup>
                    <optgroup label="Persiapan UTBK & Ujian Mandiri">
                        <option value="utbk_tps" selected>UTBK SNBT - Tes Potensi Skolastik (TPS)</option>
                        <option value="utbk_literasi">UTBK SNBT - Literasi & Penalaran</option>
                        <option value="tka_saintek">TKA Saintek (Ujian Mandiri PTN)</option>
                        <option value="tka_soshum">TKA Soshum (Ujian Mandiri PTN)</option>
                    </optgroup>
                </select>
            </div>
            <div class="subject-list" id="subjectListContainer"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer"></div>
        </main>
    </div>

    <button class="gemini-btn" onclick="toggleChat()">✨ Asisten Belajar Gemini</button>
    <div class="chat-modal" id="chatWindow">
        <div class="chat-header">
            <span>Gemini AI Tutor</span>
            <span style="cursor:pointer;" onclick="toggleChat()">✖</span>
        </div>
        <div class="chat-body" id="chatBody">
            <div class="msg-ai"><strong>Gemini:</strong> Halo! Bingung dengan rumus matematika atau soal UTBK? Tanyakan padaku sekarang!</div>
        </div>
        <div class="chat-input-box">
            <input type="text" id="chatInput" placeholder="Ketik soal/pertanyaan..." onkeypress="handleChatKey(event)">
            <button onclick="sendChatMessage()">Kirim</button>
        </div>
    </div>

    <div class="tryout-overlay" id="tryoutOverlay">
        <div class="tryout-box">
            <div class="tryout-top">
                <h3>Simulasi UTBK SNBT - Penalaran Matematika & Kuantitatif</h3>
                <div class="tryout-timer">15:00</div>
            </div>
            <div class="tryout-content">
                <p style="font-weight: 700; margin-bottom: 12px;">Soal Nomor 1:</p>
                <p style="font-size: 15px; margin-bottom: 18px; line-height:1.5;">
                    Jika $f(x) = 2x + 5$ dan $g(x) = x^2 - 1$, berapakah nilai dari komposisi $(f \circ g)(3)$?
                </p>
                <div class="quiz-option" onclick="pickTryoutAns(this)">A. 21</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">B. 23</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">C. 25</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">D. 27</div>
            </div>
            <div class="tryout-bottom">
                <button style="padding: 8px 16px; border: 1px solid #cbd5e1; background: white; border-radius: 6px; cursor: pointer;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 8px 18px; background: #2563eb; color: white; border: none; border-radius: 6px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan Jawaban</button>
            </div>
        </div>
    </div>

    <script>
        let currentCurriculum = 'merdeka';

        const appDatabase = {
            // ================= UTBK TPS =================
            utbk_tps: [
                {
                    id: "pk",
                    name: "Pengetahuan Kuantitatif (PK)",
                    tutor: "Jerome Polin (Eksakta Expert)",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Menguji kemampuan perhitungan aljabar dasar, geometri, teori bilangan, aritmetika sosial, serta pemecahan masalah numerik cepat.",
                    trick: "💡 <strong>Metode Solusi 10 Detik:</strong> Pada soal perbandingan kuantitatif P dan Q, gunakan substitusi angka ekstrem (seperti -1, 0, 1) daripada menguraikan persamaan aljabar rumit.",
                    bab: ["Bab 1: Aljabar Dasar & Persamaan Kuadrat", "Bab 2: Geometri & Pola Bangun Datar/Ruang", "Bab 3: Peluang, Permutasi & Kombinasi", "Bab 4: Statistika & Rata-rata Gabungan", "Bab 5: Matriks & Sistem Persamaan Linear"],
                    quiz: {
                        question: "Berapakah nilai dari 15% dari 200 ditambah 3^3?",
                        options: ["A. 57", "B. 47", "C. 37", "D. 27"],
                        correct: "A. 57",
                        explain: "15% x 200 = 30. Nilai 3^3 = 27. Hasil = 30 + 27 = 57."
                    }
                },
                {
                    id: "pu",
                    name: "Penalaran Umum (PU)",
                    tutor: "Tim Master UTBK",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Penalaran deduktif, induktif, penalaran kuantitatif, serta kemampuan menganalisis grafik dan data statistik.",
                    trick: "💡 <strong>Metode Logika Deduktif:</strong> Semua A adalah B. Sebagian A adalah C. Kesimpulan pasti: Sebagian B adalah C.",
                    bab: ["Bab 1: Penalaran Deduktif & Silogisme", "Bab 2: Penalaran Induktif & Pola Deret", "Bab 3: Analisis Tabel, Bar-chart & Grafik Data"],
                    quiz: {
                        question: "Semua siswa rajin belajar. Sebagian siswa lulus UTBK. Kesimpulannya?",
                        options: ["A. Semua siswa lulus UTBK", "B. Sebagian siswa rajin belajar dan lulus UTBK", "C. Tidak ada yang lulus", "D. Semua tidak rajin"],
                        correct: "B. Sebagian siswa rajin belajar dan lulus UTBK",
                        explain: "Penggabungan premis universal (Semua) dan partikular (Sebagian)."
                    }
                },
                {
                    id: "pbm",
                    name: "Pemahaman Bacaan & Menulis (PBM)",
                    tutor: "Tim Literasi Indonesia",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Menguji tata bahasa EYD/PUEBI, keefektifan kalimat, penggabungan paragraf, konjungsi, dan struktur wacana.",
                    trick: "💡 <strong>Trik Kalimat Efektif:</strong> Kalimat efektif wajib memiliki Subjek dan Predikat yang jelas tanpa konjungsi ganda di awal kalimat.",
                    bab: ["Bab 1: Ejaan, Tanda Baca & PUEBI", "Bab 2: Kalimat Efektif & Kalimat Transformasi", "Bab 3: Kepaduan & Penggabungan Paragraf"],
                    quiz: {
                        question: "Manakah penulisan kata berimbuhan yang baku sesuai PUEBI?",
                        options: ["A. Mengkristal", "B. Meng-kristal", "C. Mengristal", "D. Peng-kristalan"],
                        correct: "C. Mengristal",
                        explain: "Awalan me- bertemu kata dasar yang diawali K, T, S, P mengalami peluluhan (K -> ng)."
                    }
                },
                {
                    id: "ppu",
                    name: "Pengetahuan & Pemahaman Umum (PPU)",
                    tutor: "Tim Bahasa & Kebahasaan",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Memahami makna kata, sinonim, antonim, ungkapan, hiponim/hipernim, serta ide pokok teks umum.",
                    trick: "💡 <strong>Trik Sinonim Konteks:</strong> Baca kalimat sebelum dan sesudah kata yang ditanyakan untuk menemukan nuansa makna tepat.",
                    bab: ["Bab 1: Semantik & Makna Kata Kontekstual", "Bab 2: Makna Implisit & Eksplisit Teks", "Bab 3: Bentukan Kata & Penyerapan"],
                    quiz: {
                        question: "Sinonim dari kata 'Inovatif' dalam konteks perkembangan teknologi adalah...",
                        options: ["A. Kuno", "B. Pembaruan", "C. Statis", "D. Tradisional"],
                        correct: "B. Pembaruan",
                        explain: "Inovatif berarti bersifat memperkenalkan hal-hal baru/pembaruan."
                    }
                }
            ],

            // ================= UTBK LITERASI =================
            utbk_literasi: [
                {
                    id: "pm",
                    name: "Penalaran Matematika (PM)",
                    tutor: "Jerome Polin",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Penerapan konsep matematika pada masalah dunia nyata: finansial, pertumbuhan, peluruhan, dan pemodelan.",
                    trick: "💡 <strong>Trik PM:</strong> Fokus pada pertanyaan di akhir narasi teks panjang untuk menghemat waktu analisis angka.",
                    bab: ["Bab 1: Pemodelan Matematika & Sistem Linear", "Bab 2: Aritmetika Sosial & Finansial", "Bab 3: Pertumbuhan & Peluruhan Eksponensial", "Bab 4: Peluang & Analisis Risiko"],
                    quiz: {
                        question: "Jika modal awal Rp 1.000.000 mengalami bunga majemuk 10% per tahun, berapakah modal akhir tahun ke-2?",
                        options: ["A. Rp 1.210.000", "B. Rp 1.200.000", "C. Rp 1.100.000", "D. Rp 1.300.000"],
                        correct: "A. Rp 1.210.000",
                        explain: "Tahun 1: 1.000.000 + 10% = 1.100.000. Tahun 2: 1.100.000 + 10% = 1.210.000."
                    }
                },
                {
                    id: "lit_indo",
                    name: "Literasi Bahasa Indonesia",
                    tutor: "Master Bahasa Indonesia",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Menganalisis teks sastra dan sains, menyimpulkan asumsi penulis, serta menilai keakuratan informasi teks.",
                    trick: "💡 <strong>Trik Simpulan:</strong> Simpulan yang benar harus mencakup gagasan utama dan tidak menentang fakta teks.",
                    bab: ["Bab 1: Analisis Teks Informasi & Ilmiah", "Bab 2: Analisis Teks Sastra & Karakterisasi", "Bab 3: Evaluasi & Refleksi Isi Teks"],
                    quiz: {
                        question: "Gagasan utama sebuah paragraf deduktif terletak di...",
                        options: ["A. Awal Paragraf", "B. Akhir Paragraf", "C. Tengah Paragraf", "D. Luar Teks"],
                        correct: "A. Awal Paragraf",
                        explain: "Paragraf deduktif menempatkan kalimat utama di awal wacana."
                    }
                },
                {
                    id: "lit_ing",
                    name: "Literasi Bahasa Inggris",
                    tutor: "English Master Tutor",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Reading comprehension, author's attitude/tone, main ideas, inference, and vocabulary in context.",
                    trick: "💡 <strong>Skimming & Scanning:</strong> Read the question first, then scan keywords in the paragraph.",
                    bab: ["Bab 1: Main Idea & Author's Purpose", "Bab 2: Inference & Implied Meaning", "Bab 3: Tone, Mood & Vocabulary Context"],
                    quiz: {
                        question: "What is the synonym of 'rapid' in a scientific reading text?",
                        options: ["A. Slow", "B. Fast", "C. Heavy", "D. Weak"],
                        correct: "B. Fast",
                        explain: "'Rapid' means happening in a short time or at a fast pace."
                    }
                }
            ],

            // ================= KELAS 10 (FASE E) =================
            k10: [
                {
                    id: "mtk10",
                    name: "Matematika",
                    tutor: "Jerome Polin",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Eksponen, Logaritma, Barisan & Deret, Vektor, Trigonometri Dasar, dan Statistika Data.",
                    trick: "💡 <strong>Trik Logaritma:</strong> a^log(b) x b^log(c) = a^log(c). Coret nilai tengah yang sama!",
                    bab: ["Bab 1: Eksponen & Fungsi Eksponensial", "Bab 2: Logaritma & Sifat-Sifatnya", "Bab 3: Vektor & Operasi Aljabar Vektor", "Bab 4: Trigonometri Dasar (Sin, Cos, Tan)", "Bab 5: Barisan & Deret Aritmetika/Geometri"],
                    quiz: {
                        question: "Berapakah hasil dari 2^4 x 2^3?",
                        options: ["A. 2^7 (128)", "B. 2^12", "C. 2^1", "D. 64"],
                        correct: "A. 2^7 (128)",
                        explain: "Perkalian eksponen basis sama: pangkat dijumlahkan (4 + 3 = 7)."
                    }
                },
                {
                    id: "fis10",
                    name: "Fisika",
                    tutor: "Pakar Fisika Indonesia",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Hakikat Fisika, Pengukuran & Angka Penting, Kinematika Gerak (GLB, GLBB), dan Energi Terbarukan.",
                    trick: "💡 <strong>Trik GLBB:</strong> Vt = V0 + a.t | S = V0.t + 1/2.a.t^2.",
                    bab: ["Bab 1: Pengukuran, Dimensi & Angka Penting", "Bab 2: Gerak Lurus Beraturan (GLB) & GLBB", "Bab 3: Energi Terbarukan & Efisiensi Energi"],
                    quiz: {
                        question: "Satuan SI untuk Besaran Kuat Arus Listrik adalah...",
                        options: ["A. Ampere", "B. Volt", "C. Watt", "D. Joule"],
                        correct: "A. Ampere",
                        explain: "Kuat arus diukur dalam satuan Ampere (A)."
                    }
                },
                {
                    id: "kim10",
                    name: "Kimia",
                    tutor: "Pakar Kimia SMA",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Struktur Atom, Konfigurasi Elektron, Tabel Periodik Unsur, Hukum Dasar Kimia, dan Stoikiometri.",
                    trick: "💡 <strong>Hafalan Konfigurasi:</strong> s p s p s d p s d p (Si Sapi Sapi Sedap Sedap).",
                    bab: ["Bab 1: Struktur Atom & Konfigurasi Elektron", "Bab 2: Tabel Periodik & Sifat Keperiodikan", "Bab 3: Hukum Dasar Kimia & Mol (Stoikiometri)"],
                    quiz: {
                        question: "Partikel penyusun inti atom yang bermuatan positif adalah...",
                        options: ["A. Proton", "B. Neutron", "C. Elektron", "D. Foton"],
                        correct: "A. Proton",
                        explain: "Inti atom terdiri dari Proton (+) dan Neutron (0)."
                    }
                },
                {
                    id: "bio10",
                    name: "Biologi",
                    tutor: "Pakar Biologi SMA",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Keanekaragaman Hayati, Keanekaragaman Gen-Spesies-Ekosistem, Virus, Bakteri, dan Ekologi.",
                    trick: "💡 <strong>Taksonomi:</strong> Kingdom - Filum/Divisi - Kelas - Ordo - Famili - Genus - Spesies.",
                    bab: ["Bab 1: Keanekaragaman Hayati Indonesia", "Bab 2: Virus, Struktur & Bioteknologi Vaksin", "Bab 3: Ekosistem & Daur Biogeokimia"],
                    quiz: {
                        question: "Keanekaragaman warna mawar merupakan contoh keanekaragaman tingkat...",
                        options: ["A. Gen", "B. Spesies", "C. Ekosistem", "D. Komunitas"],
                        correct: "A. Gen",
                        explain: "Variasi dalam satu jenis disebabkan perbedaan susunan genetik."
                    }
                },
                {
                    id: "eko10",
                    name: "Ekonomi",
                    tutor: "Pakar Ekonomi SMA",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Kelangkaan, Skala Prioritas, Pelaku Ekonomi, Permintaan, Penawaran, dan Lembaga Keuangan.",
                    trick: "💡 <strong>Hukum Permintaan:</strong> P Naik $\rightarrow$ Q Turun (Berbanding Terbalik).",
                    bab: ["Bab 1: Kelangkaan & Skala Prioritas Kebutuhan", "Bab 2: Mekanisme Permintaan, Penawaran & Harga Pasar", "Bab 3: Bank, OJK & Lembaga Keuangan Non-Bank"],
                    quiz: {
                        question: "Inti masalah ekonomi yang dialami manusia adalah...",
                        options: ["A. Kebutuhan tidak terbatas, alat pemuas terbatas", "B. Kebutuhan terbatas, alat pemuas melimpah", "C. Uang terlalu banyak", "D. Produksi berlebihan"],
                        correct: "A. Kebutuhan tidak terbatas, alat pemuas terbatas",
                        explain: "Inti masalah ekonomi adalah kelangkaan (scarcity)."
                    }
                },
                {
                    id: "sos10",
                    name: "Sosiologi",
                    tutor: "Tutor Sosiologi",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Sosiologi sebagai Ilmu, Interaksi Sosial, Nilai & Norma Sosial, serta Sosialisasi Kepribadian.",
                    trick: "💡 <strong>Syarat Interaksi Sosial:</strong> Kontak Sosial + Komunikasi.",
                    bab: ["Bab 1: Pengantar Sosiologi & Objek Kajian", "Bab 2: Interaksi Sosial & Tindakan Sosial", "Bab 3: Nilai, Norma & Lembaga Sosial"],
                    quiz: {
                        question: "Dua syarat utama terjadinya interaksi sosial adalah...",
                        options: ["A. Kontak Sosial dan Komunikasi", "B. Asimilasi dan Akulturasi", "C. Konflik dan Persaingan", "D. Status dan Peran"],
                        correct: "A. Kontak Sosial dan Komunikasi",
                        explain: "Tanpa adanya kontak dan komunikasi, interaksi sosial tidak dapat terjadi."
                    }
                },
                {
                    id: "geo10",
                    name: "Geografi",
                    tutor: "Tutor Geografi",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Konsep Dasar Geografi, Prinsip & Pendekatan Geografi, Peta, Penginderaan Jauh, dan Litosfer.",
                    trick: "💡 <strong>10 Konsep Geografi:</strong> Jak-Ke-Ma-Di-Lo-Pa-Ni-Mor-A-Di (Lokasi, Jarak, Keterjangkauan, Morfologi, dll).",
                    bab: ["Bab 1: Konsep, Prinsip & Pendekatan Geografi", "Bab 2: Pemetaan, Penginderaan Jauh & SIG", "Bab 3: Dinamika Litosfer & Gunung Api"],
                    quiz: {
                        question: "Pendekatan geografi yang menganalisis hubungan manusia dengan lingkungannya adalah...",
                        options: ["A. Pendekatan Ekologi (Kelingkungan)", "B. Pendekatan Spasial (Keruangan)", "C. Pendekatan Kompleks Wilayah", "D. Pendekatan Regional"],
                        correct: "A. Pendekatan Ekologi (Kelingkungan)",
                        explain: "Pendekatan ekologi mengkaji interaksi organisme hidup dengan lingkungan fisiknya."
                    }
                }
            ],

            // ================= KELAS 11 IPA =================
            k11_ipa: [
                {
                    id: "mtk11_ipa",
                    name: "Matematika Lanjut 11 IPA",
                    tutor: "Jerome Polin",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Matriks, Invers, Polinomial (Suku Banyak), Persamaan Lingkaran, dan Transformasi Geometri.",
                    trick: "💡 <strong>Determinan Matriks 2x2:</strong> ad - bc. Tinggal kali silang!",
                    bab: ["Bab 1: Polinomial & Teorema Sisa", "Bab 2: Matriks, Determinan & Invers", "Bab 3: Persamaan Lingkaran & Garis Singgung", "Bab 4: Transformasi Geometri (Translasi, Rotasi, Dilatasi)"],
                    quiz: {
                        question: "Ordo dari matriks yang memiliki 2 baris dan 3 kolom adalah...",
                        options: ["A. 2x3", "B. 3x2", "C. 2x2", "D. 3x3"],
                        correct: "A. 2x3",
                        explain: "Ordo matriks ditulis dengan format (Jumlah Baris) x (Jumlah Kolom)."
                    }
                },
                {
                    id: "fis11",
                    name: "Fisika 11 IPA",
                    tutor: "Master Fisika",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Dinamika Rotasi, Kesetimbangan Benda Tegar, Fluida Statis/Dinamis, dan Termodinamika.",
                    trick: "💡 <strong>Torsi (Momen Gaya):</strong> τ = F x r x sin(θ).",
                    bab: ["Bab 1: Dinamika Rotasi & Momen Inersia", "Bab 2: Fluida Statis (Hukum Pascal & Archimedes)", "Bab 3: Fluida Dinamis (Hukum Bernoulli)", "Bab 4: Termodinamika & Mesin Carnot"],
                    quiz: {
                        question: "Besaran fisika yang menyebabkan benda berotasi adalah...",
                        options: ["A. Momen Gaya (Torsi)", "B. Gaya Murni", "C. Tekanan", "D. Daya"],
                        correct: "A. Momen Gaya (Torsi)",
                        explain: "Torsi adalah penyebab utama perubahan gerak rotasi pada benda tegar."
                    }
                },
                {
                    id: "kim11",
                    name: "Kimia 11 IPA",
                    tutor: "Pakar Kimia IPA",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Hidrokarbon, Minyak Bumi, Termokimia, Laju Reaksi, Kesetimbangan Kimia, dan Larutan Asam Basa.",
                    trick: "💡 <strong>Trik pH Asam Kuat:</strong> pH = -log[H+], di mana [H+] = a x M.",
                    bab: ["Bab 1: Senyawa Hidrokarbon (Alkana, Alkena, Alkuna)", "Bab 2: Termokimia & Perubahan Entalpi", "Bab 3: Kesetimbangan Kimia & Laju Reaksi", "Bab 4: Larutan Asam Basa & Titrasi"],
                    quiz: {
                        question: "Nilai pH untuk larutan netral pada suhu kamar 25°C adalah...",
                        options: ["A. 7", "B. 0", "C. 14", "D. 1"],
                        correct: "A. 7",
                        explain: "Larutan netral memiliki konsentrasi H+ sama dengan OH-, yaitu pH 7."
                    }
                },
                {
                    id: "bio11",
                    name: "Biologi 11 IPA",
                    tutor: "Pakar Biologi IPA",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Struktur Sel, Jaringan Tumbuhan & Hewan, Sistem Gerak, Sistem Sirkulasi Darah, dan Pencernaan.",
                    trick: "💡 <strong>Organel Sel:</strong> Mitokondria = Powerhouse (Pembangkit Energi ATP).",
                    bab: ["Bab 1: Struktur Sel & Transpor Membran", "Bab 2: Jaringan Tumbuhan & Hewan", "Bab 3: Sistem Gerak & Rangka Manusia", "Bab 4: Sistem Peredaran Darah (Sirkulasi)"],
                    quiz: {
                        question: "Organel sel yang berfungsi sebagai tempat respirasi seluler dan penghasil ATP adalah...",
                        options: ["A. Mitokondria", "B. Ribosom", "C. Lisosom", "D. Badan Golgi"],
                        correct: "A. Mitokondria",
                        explain: "Mitokondria mengubah nutrisi menjadi energi ATP melalui respirasi aerob."
                    }
                }
            ],

            // ================= KELAS 11 IPS =================
            k11_ips: [
                {
                    id: "eko11_ips",
                    name: "Ekonomi 11 IPS",
                    tutor: "Tutor Ekonomi",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Pendapatan Nasional, Ketenagakerjaan, Inflasi, serta Kebijakan Moneter & Kebijakan Fiskal.",
                    trick: "💡 <strong>Kebijakan Moneter Ketat:</strong> Naikkan Suku Bunga $\rightarrow$ Jumlah Uang Beredar Turun $\rightarrow$ Inflasi Terkendali.",
                    bab: ["Bab 1: Pendapatan Nasional (PDB, PNB, NNI)", "Bab 2: Ketenagakerjaan & Pengangguran", "Bab 3: Indeks Harga, Inflasi & Kebijakan Moneter", "Bab 4: APBN & APBD (Kebijakan Fiskal)"],
                    quiz: {
                        question: "Kenaikan harga barang secara umum dan terus menerus disebut...",
                        options: ["A. Inflasi", "B. Deflasi", "C. Resesi", "D. Devaluasi"],
                        correct: "A. Inflasi",
                        explain: "Inflasi ditandai dengan turunnya daya beli mata uang terhadap barang/jasa."
                    }
                },
                {
                    id: "sos11_ips",
                    name: "Sosiologi 11 IPS",
                    tutor: "Tutor Sosiologi",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Kelompok Sosial, Permasalahan Sosial di Masyarakat, Konflik Sosial, Integrasi, dan Reintegrasi.",
                    trick: "💡 <strong>Resolusi Konflik:</strong> Mediasi (Ada pihak ketiga netral yang memberi usulan non-binding).",
                    bab: ["Bab 1: Pembentukan Kelompok Sosial", "Bab 2: Permasalahan Sosial & Eksklusi", "Bab 3: Konflik Sosial & Kekerasan", "Bab 4: Integrasi & Reintegrasi Sosial"],
                    quiz: {
                        question: "Sikap menilai budaya orang lain berdasarkan standar budayanya sendiri disebut...",
                        options: ["A. Etnosentrisme", "B. Relativisme Budaya", "C. Akulturasi", "D. Asimilasi"],
                        correct: "A. Etnosentrisme",
                        explain: "Etnosentrisme memandang budayanya sendiri lebih superior dibanding budaya lain."
                    }
                },
                {
                    id: "geo11_ips",
                    name: "Geografi 11 IPS",
                    tutor: "Tutor Geografi",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Posisi Strategis Indonesia (Poros Maritim), Flora dan Fauna, Sumber Daya Alam, dan Kebencanaan.",
                    trick: "💡 <strong>Garis Pembatas Flora Fauna:</strong> Garis Wallace & Garis Weber membagi wilayah Asiatis, Peralihan, dan Australis.",
                    bab: ["Bab 1: Letak Indonesia & Poros Maritim Dunia", "Bab 2: Persebaran Flora & Fauna Dunia-Indonesia", "Bab 3: Pengelolaan Sumber Daya Alam", "Bab 4: Mitigasi & Adaptasi Bencana Alam"],
                    quiz: {
                        question: "Garis imajiner yang memisahkan fauna tipe Asiatis dan tipe Peralihan di Indonesia adalah...",
                        options: ["A. Garis Wallace", "B. Garis Weber", "C. Garis Khatulistiwa", "D. Garis Meridian"],
                        correct: "A. Garis Wallace",
                        explain: "Garis Wallace membentang antara Kalimantan-Sulawesi dan Bali-Lombok."
                    }
                }
            ],

            // ================= KELAS 12 IPA =================
            k12_ipa: [
                {
                    id: "mtk12_ipa",
                    name: "Matematika 12 IPA",
                    tutor: "Jerome Polin",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Limit Fungsi Trigonometri, Turunan Fungsi Trigonometri, Integral Tentu/Tak Tentu, dan Geometri Dimensi Tiga.",
                    trick: "💡 <strong>Trik Limit Trigonometri x->0:</strong> Coret sin & tan! Ambil koefisien variabel angka depannya saja.",
                    bab: ["Bab 1: Geometri Dimensi Tiga (Jarak Titik, Garis, Bidang)", "Bab 2: Limit Fungsi Trigonometri & Limit Tak Hingga", "Bab 3: Turunan Fungsi Trigonometri", "Bab 4: Integral Tentu, Tak Tentu & Luas Daerah"],
                    quiz: {
                        question: "Turunan pertama dari f(x) = sin(x) adalah...",
                        options: ["A. cos(x)", "B. -cos(x)", "C. tan(x)", "D. -sin(x)"],
                        correct: "A. cos(x)",
                        explain: "Turunan dasar dari fungsi trigonometri sin(x) adalah cos(x)."
                    }
                },
                {
                    id: "fis12",
                    name: "Fisika 12 IPA",
                    tutor: "Master Fisika 12",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Rangkaian Listrik Searah/Bolak-Balik, Medan Magnet, Induksi Elektromagnetik, dan Fisika Modern.",
                    trick: "💡 <strong>Hukum Ohm:</strong> V = I x R.",
                    bab: ["Bab 1: Rangkaian Listrik Arus Searah (DC)", "Bab 2: Medan Magnet & Gaya Lorentz", "Bab 3: Induksi Elektromagnetik (Hukum Faraday)", "Bab 4: Relativitas Khusus & Efek Fotolistrik"],
                    quiz: {
                        question: "Alat yang berfungsi mengubah energi mekanik menjadi energi listrik berdasarkan induksi elektromagnetik adalah...",
                        options: ["A. Generator (Dinamo)", "B. Motor Listrik", "C. Transformator", "D. Resistor"],
                        correct: "A. Generator (Dinamo)",
                        explain: "Generator memutar kumparan dalam medan magnet untuk menghasilkan arus listrik."
                    }
                },
                {
                    id: "kim12",
                    name: "Kimia 12 IPA",
                    tutor: "Pakar Kimia 12",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Sifat Koligatif Larutan, Reaksi Redoks, Sel Volta, Elektrolisis, dan Makromolekul (Polimer/Biokimia).",
                    trick: "💡 <strong>Sel Volta (KNAP):</strong> Katoda = Positif (Reduksi), Anoda = Negatif (Oksidasi).",
                    bab: ["Bab 1: Sifat Koligatif Larutan (ΔTb, ΔTf, π)", "Bab 2: Reaksi Redoks & Sel Elektrokimia (Volta & Elektrolisis)", "Bab 3: Unsur-Unsur Periode 3 & Gas Mulia", "Bab 4: Polimer, Karbohidrat & Protein"],
                    quiz: {
                        question: "Pada sel Volta, reaksi oksidasi terjadi pada elektroda...",
                        options: ["A. Anoda", "B. Katoda", "C. Elektrolit", "D. Jembatan Garam"],
                        correct: "A. Anoda",
                        explain: "Singkatan KRAO: Katoda Reduksi, Anoda Oksidasi."
                    }
                },
                {
                    id: "bio12",
                    name: "Biologi 12 IPA",
                    tutor: "Pakar Biologi 12",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Pertumbuhan & Perkembangan, Metabolisme Sel (Enzim, Respirasi, Fotosintesis), Genetika, dan Evolusi.",
                    trick: "💡 <strong>Respirasi Aerob:</strong> Glikolisis $\rightarrow$ Dekarboksilasi Oksidatif $\rightarrow$ Siklus Krebs $\rightarrow$ Transpor Elektron.",
                    bab: ["Bab 1: Pertumbuhan & Perkembangan Tumbuhan", "Bab 2: Metabolisme Sel (Respirasi & Fotosintesis)", "Bab 3: Substansi Genetik (DNA, RNA, Sintesis Protein)", "Bab 4: Hukum Mendel & Genetika Populasi", "Bab 5: Teori Evolusi & Bioteknologi Modern"],
                    quiz: {
                        question: "Tahap respirasi aerobik yang menghasilkan molekul ATP terbanyak adalah...",
                        options: ["A. Transpor Elektron", "B. Glikolisis", "C. Siklus Krebs", "D. Dekarboksilasi Oksidatif"],
                        correct: "A. Transpor Elektron",
                        explain: "Transpor elektron menghasilkan hingga 32-34 molekul ATP per molekul glukosa."
                    }
                }
            ],

            // ================= KELAS 12 IPS =================
            k12_ips: [
                {
                    id: "eko12_ips",
                    name: "Ekonomi 12 IPS",
                    tutor: "Tutor Akuntansi",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Akuntansi sebagai Sistem Informasi, Persamaan Dasar Akuntansi, Jurnal Umum, dan Siklus Akuntansi Perusahaan Jasa/Dagang.",
                    trick: "💡 <strong>Persamaan Akuntansi:</strong> HARTA = UTANG + MODAL.",
                    bab: ["Bab 1: Akuntansi & Persamaan Dasar Akuntansi", "Bab 2: Jurnal Umum & Buku Besar Perusahaan Jasa", "Bab 3: Jurnal Penyesuaian & Laporan Keuangan", "Bab 4: Akuntansi Perusahaan Dagang & Jurnal Khusus"],
                    quiz: {
                        question: "Rumus utama Persamaan Dasar Akuntansi adalah...",
                        options: ["A. Harta = Utang + Modal", "B. Harta = Modal - Utang", "C. Utang = Harta + Modal", "D. Pendapatan = Beban"],
                        correct: "A. Harta = Utang + Modal",
                        explain: "Setiap transaksi harus menjaga keseimbangan antara aktiva (harta) dan pasiva (utang + modal)."
                    }
                },
                {
                    id: "sos12_ips",
                    name: "Sosiologi 12 IPS",
                    tutor: "Tutor Sosiologi 12",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Perubahan Sosial, Globalisasi, Ketimpangan Sosial, Kebearifan Lokal, dan Pemberdayaan Komunitas.",
                    trick: "💡 <strong>Faktor Perubahan Sosial:</strong> Internal (Inovasi, Demografi) vs Ekstrenal (Bencana, Perang, Budaya Luar).",
                    bab: ["Bab 1: Perubahan Sosial & Dampaknya", "Bab 2: Globalisasi & Modernisasi", "Bab 3: Ketimpangan Sosial & Komunitas Lokal", "Bab 4: Evaluasi Pemberdayaan Komunitas"],
                    quiz: {
                        question: "Proses masuknya budaya luar secara halus tanpa menghilangkan budaya asli disebut...",
                        options: ["A. Akulturasi", "B. Asimilasi", "C. Difusi", "D. Invasi"],
                        correct: "A. Akulturasi",
                        explain: "Akulturasi adalah percampuran dua budaya yang menghasilkan budaya baru tanpa mengikis kebudayaan asli."
                    }
                },
                {
                    id: "geo12_ips",
                    name: "Geografi 12 IPS",
                    tutor: "Tutor Geografi 12",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Pola Keruangan Desa-Kota, Penginderaan Jauh (SIG), serta Kerjasama Negara Maju dan Berkembang.",
                    trick: "💡 <strong>Rumus Titik Henti Interaksi:</strong> TH = d / (1 + √(P_besar / P_kecil)).",
                    bab: ["Bab 1: Penataan Ruang Wilayah Desa & Kota", "Bab 2: Pemfaatan SIG & Penginderaan Jauh", "Bab 3: Kerjasama Regional & Internasional Negara Maju"],
                    quiz: {
                        question: "Komponen pemrosesan data utama pada Sistem Informasi Geografis adalah...",
                        options: ["A. Hardware & Software", "B. Peta Kertas", "C. Kompas", "D. Cuaca"],
                        correct: "A. Hardware & Software",
                        explain: "Perangkat keras dan lunak mengolah data geospasial dalam SIG."
                    }
                }
            ],

            // ================= KELAS 12 BAHASA =================
            k12_bahasa: [
                {
                    id: "sas_indo12",
                    name: "Sastra Indonesia 12",
                    tutor: "Pakar Bahasa & Sastra",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Kritik Sastra, Esai, Periodisasi Angkatan Sastra Indonesia, Resensi Karya, dan Drama.",
                    trick: "💡 <strong>Ciri Angkatan Sastra:</strong> Pujangga Baru (Nasionalisme) vs Angkatan 45 (Realitis, Ekspresif).",
                    bab: ["Bab 1: Penulisan Kritik & Esai Sastra", "Bab 2: Periodisasi & Sejarah Sastra Indonesia", "Bab 3: Drama, Teater & Musikalisasi Puisi"],
                    quiz: {
                        question: "Karangan prosa yang membahas suatu masalah dari sudut pandang pribadi penulisnya disebut...",
                        options: ["A. Esai", "B. Novel", "C. Biografi", "D. Drama"],
                        correct: "A. Esai",
                        explain: "Esai berisi tanggapan atau analisis subjektif penulis mengenai suatu fenomena."
                    }
                },
                {
                    id: "antro12",
                    name: "Antropologi 12",
                    tutor: "Pakar Antropologi",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Kebudayaan, Etnografi, Institusi Sosial, Keberagaman Agama/Kepercayaan, dan Dinamika Budaya.",
                    trick: "💡 <strong>7 Unsur Kebudayaan Universal:</strong> Bahasa, Sistem Pengetahuan, Organisasi Sosial, Peralatan Hidup, Mata Pencaharian, Kesenian, Religi.",
                    bab: ["Bab 1: Kebudayaan & Tradisi Lisan Nusantara", "Bab 2: Studi Etnografi & Penelitian Antropologi", "Bab 3: Integrasi Nasional dalam Masyarakat Majemuk"],
                    quiz: {
                        question: "Metode utama penelitian lapangan dalam ilmu antropologi adalah...",
                        options: ["A. Observasi Partisipatif (Etnografi)", "B. Eksperimen Laboratorium", "C. Survei Kuantitatif", "D. Studi Dokumen Resmi"],
                        correct: "A. Observasi Partisipatif (Etnografi)",
                        explain: "Peneliti antropologi tinggal bersama masyarakat setempat untuk mengamati budaya secara langsung."
                    }
                }
            ],

            // ================= TKA SAINTEK =================
            tka_saintek: [
                {
                    id: "tka_fisika",
                    name: "TKA Fisika",
                    tutor: "Tutor Saintek UTBK",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Soal-soal HOTS Ujian Mandiri PTN: Mekanika, Listrik Magnet, Termodinamika, dan Fisika Modern.",
                    trick: "💡 <strong>Daya Listrik:</strong> P = V x I = I^2 x R = V^2 / R.",
                    bab: ["Bab 1: Dinamika Gerak & Newton (HOTS)", "Bab 2: Rangkaian Listrik Searah & Bolak-Balik", "Bab 3: Fisika Kuantum & Efek Fotolistrik"],
                    quiz: {
                        question: "Daya listrik diukur dalam satuan...",
                        options: ["A. Watt", "B. Volt", "C. Joule", "D. Ampere"],
                        correct: "A. Watt",
                        explain: "Daya listrik diukur dalam satuan Watt (Joule/sekon)."
                    }
                },
                {
                    id: "tka_kimia",
                    name: "TKA Kimia",
                    tutor: "Tutor Kimia UTBK",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Stoikiometri Larutan, Termokimia, Kesetimbangan, Sel Elektrokimia, dan Senyawa Karbon.",
                    trick: "💡 <strong>Laju Reaksi:</strong> V = k [A]^m [B]^n.",
                    bab: ["Bab 1: Stoikiometri Larutan & Gas", "Bab 2: Kesetimbangan Kimia & Pergeseran Le Chatelier", "Bab 3: Elektrokimia & Hukum Faraday"],
                    quiz: {
                        question: "Pada reaksi eksoterm, nilai perubahan entalpi (ΔH) bernilai...",
                        options: ["A. Negatif (-)", "B. Positif (+)", "C. Nol", "D. Tak Hingga"],
                        correct: "A. Negatif (-)",
                        explain: "Reaksi eksoterm melepaskan kalor ke lingkungan sehingga ΔH < 0."
                    }
                }
            ],

            // ================= TKA SOSHUM =================
            tka_soshum: [
                {
                    id: "tka_sejarah",
                    name: "TKA Sejarah",
                    tutor: "Tutor Soshum UTBK",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Sejarah Indonesia (Pergerakan Nasional, Proklamasi, Orba, Reformasi) dan Sejarah Dunia.",
                    trick: "💡 <strong>Urutan Kronologis:</strong> Budi Utomo (1908) $\rightarrow$ Sumpah Pemuda (1928) $\rightarrow$ Proklamasi (1945).",
                    bab: ["Bab 1: Pergerakan Nasional & Sumpah Pemuda", "Bab 2: Perang Dunia I & II serta Perang Dingin", "Bab 3: Orde Baru & Gerakan Reformasi 1998"],
                    quiz: {
                        question: "Pelopor organisasi pergerakan nasional pertama di Indonesia adalah...",
                        options: ["A. Budi Utomo", "B. Sarekat Islam", "C. Indische Partij", "D. PNI"],
                        correct: "A. Budi Utomo",
                        explain: "Budi Utomo didirikan 20 Mei 1908 sebagai awal Kebangkitan Nasional."
                    }
                },
                {
                    id: "tka_ekonomi",
                    name: "TKA Ekonomi",
                    tutor: "Tutor Ekonomi UTBK",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Mikro & Makro Ekonomi, Elastisitas, Struktur Pasar (Monopoli/Oligopoli), dan Akuntansi Penyesuaian.",
                    trick: "💡 <strong>Pasar Monopoli:</strong> Hanya ada SATU penjual yang menguasai seluruh penawaran barang tanpa substitusi dekat.",
                    bab: ["Bab 1: Elastisitas Permintaan & Penawaran", "Bab 2: Struktur Pasar (Persaingan Sempurna & Monopoli)", "Bab 3: Jurnal Penyesuaian & Laporan Keuangan"],
                    quiz: {
                        question: "Struktur pasar yang hanya dikuasai oleh satu penjual tunggal disebut...",
                        options: ["A. Monopoli", "B. Oligopoli", "C. Monopsoni", "D. Persaingan Sempurna"],
                        correct: "A. Monopoli",
                        explain: "Pasar monopoli dikuasai tunggal oleh satu produsen tanpa adanya barang pengganti langsung."
                    }
                }
            ]
        };

        // KURIKULUM SWITCH
        function setCurriculum(curr, btn) {
            currentCurriculum = curr;
            document.querySelectorAll('.curr-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            loadCategorySubjects();
        }

        // LOAD MAPEL KATEGORI
        function loadCategorySubjects() {
            const cat = document.getElementById('gradeSelect').value;
            const subjects = appDatabase[cat] || [];
            const container = document.getElementById('subjectListContainer');
            
            container.innerHTML = "";

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

            if (subjects.length > 0) {
                renderMateri(subjects[0]);
            } else {
                document.getElementById('materiContainer').innerHTML = "<p style='padding:20px;'>Materi sedang dalam pembaruan.</p>";
            }
        }

        // RENDER DETAIL MATERI
        function renderMateri(sub) {
            const container = document.getElementById('materiContainer');
            
            let babListHtml = "";
            sub.bab.forEach((b) => {
                babListHtml += `
                    <div class="bab-item">
                        <span class="bab-name">${b}</span>
                        <button class="btn-play" onclick="alert('Memutar video bab: ${b}')">Tonton Video</button>
                    </div>
                `;
            });

            container.innerHTML = `
                <div class="materi-header">
                    <h2>${sub.name} (${currentCurriculum === 'merdeka' ? 'Kurikulum Merdeka' : 'Kurikulum 2013'})</h2>
                    <p>Pengajar Utama: <strong>${sub.tutor}</strong></p>
                </div>

                <div class="video-box">
                    <div class="video-wrapper">
                        <iframe src="${sub.video}" title="${sub.name}" allowfullscreen></iframe>
                    </div>

                    <div class="tabs-nav">
                        <div class="tab-btn active" onclick="switchTab(this, 'tabBab')">📺 Video & Bab</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabSummary')">📖 Rangkuman</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabTrick')">⚡ Metode Cepat</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabQuiz')">✏️ Kuis Bab</div>
                    </div>

                    <div class="tab-content active" id="tabBab">
                        <div class="bab-group">${babListHtml}</div>
                    </div>

                    <div class="tab-content" id="tabSummary">
                        <div class="summary-card">
                            <strong>Konsep Inti Pembelajaran:</strong><br>${sub.summary}
                        </div>
                    </div>

                    <div class="tab-content" id="tabTrick">
                        <div class="trick-card">
                            ${sub.trick}
                        </div>
                    </div>

                    <div class="tab-content" id="tabQuiz">
                        <div class="quiz-card">
                            <p style="font-weight:700; margin-bottom:10px;">Latihan Kuis Bab:</p>
                            <p style="margin-bottom:12px;">${sub.quiz.question}</p>
                            ${sub.quiz.options.map(opt => `
                                <div class="quiz-option" onclick="checkQuiz('${opt}', '${sub.quiz.correct}', '${sub.quiz.explain}')">${opt}</div>
                            `).join('')}
                            <div id="quizResult" style="margin-top:12px; font-weight:700;"></div>
                        </div>
                    </div>
                </div>
            `;
        }

        // SWITCH TAB METHOD
        function switchTab(btn, tabId) {
            document.querySelectorAll('.tab-btn').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            
            btn.classList.add('active');
            document.getElementById(tabId).classList.add('active');
        }

        // EVALUASI KUIS
        function checkQuiz(selected, correct, explain) {
            const res = document.getElementById('quizResult');
            if (selected === correct) {
                res.innerHTML = `<span style="color:#16a34a;">✅ Jawaban Benar! ${explain}</span>`;
            } else {
                res.innerHTML = `<span style="color:#dc2626;">❌ Kurang Tepat. Jawaban Benar: ${correct}. Pembahasan: ${explain}</span>`;
            }
        }

        // TRYOUT MODAL
        function openTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'flex'; }
        function closeTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'none'; }
        function pickTryoutAns(el) {
            document.querySelectorAll('.quiz-option').forEach(o => o.style.background = '#f8fafc');
            el.style.background = '#e0f2fe';
        }
        function submitTryout() {
            alert("Hasil Tryout Anda:\n• Skor IRT: 755 / 1000\n• Prediksi Kelulusan PTN: 91% (Sangat Tinggi)\n\nPembahasan detail telah masuk ke portal belajar!");
            closeTryoutModal();
        }

        // GEMINI AI CHATBOT
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
                            <strong>Gemini AI:</strong> Mengenai soal/pertanyaan "${text}", kuncinya adalah memahaminya langkah demi langkah melalui konsep dasar di tab Rangkuman atau Metode Cepat di menu sebelah kiri ya!
                        </div>
                    `;
                    body.scrollTop = body.scrollHeight;
                }, 700);
            }
        }

        // RUN AT START
        window.onload = () => {
            loadCategorySubjects();
        };
    </script>
</body>
</html>
    .curriculum-switch { display: flex; background: #e2e8f0; border-radius: 20px; padding: 3px; }
        .curr-btn { padding: 6px 14px; border: none; border-radius: 16px; font-size: 12px; font-weight: 700; cursor: pointer; color: #64748b; background: transparent; transition: 0.2s; }
        .curr-btn.active { background: #2563eb; color: white; }
        .btn-tryout { background: linear-gradient(135deg, #ea580c, #f97316); color: white; border: none; padding: 8px 18px; border-radius: 20px; font-weight: 700; cursor: pointer; font-size: 13px; box-shadow: 0 4px 12px rgba(234, 88, 12, 0.2); }

        /* MAIN LAYOUT */
        .main-layout { display: flex; flex: 1; overflow: hidden; }

        /* SIDEBAR */
        .sidebar { width: 320px; background: #ffffff; border-right: 1px solid #e2e8f0; display: flex; flex-direction: column; }
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
        .content-container { max-width: 900px; margin: 0 auto; }

        .materi-header { margin-bottom: 18px; }
        .materi-header h2 { font-size: 22px; color: #0f172a; font-weight: 800; }
        .materi-header p { font-size: 13px; color: #64748b; margin-top: 2px; }

        .video-box { background: white; border-radius: 14px; padding: 20px; border: 1px solid #e2e8f0; box-shadow: 0 2px 8px rgba(0,0,0,0.04); margin-bottom: 24px; }
        .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 10px; background: #000; margin-bottom: 20px; }
        .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; }

        /* TABS METHOD */
        .tabs-nav { display: flex; gap: 8px; border-bottom: 2px solid #e2e8f0; margin-bottom: 16px; }
        .tab-btn { padding: 10px 16px; font-weight: 700; font-size: 13px; color: #64748b; cursor: pointer; border-bottom: 2px solid transparent; margin-bottom: -2px; }
        .tab-btn.active { color: #2563eb; border-bottom-color: #2563eb; }

        .tab-content { display: none; }
        .tab-content.active { display: block; }

        /* LIST BAB */
        .bab-group { display: flex; flex-direction: column; gap: 10px; }
        .bab-item { display: flex; justify-content: space-between; align-items: center; padding: 12px 16px; background: #f1f5f9; border-radius: 8px; border-left: 4px solid #2563eb; }
        .bab-name { font-size: 13px; font-weight: 700; color: #334155; }
        .btn-play { background: #2563eb; color: white; border: none; padding: 6px 14px; border-radius: 6px; font-size: 12px; cursor: pointer; font-weight: 700; }

        /* BOX METODE & KUIS */
        .summary-card { background: #eff6ff; border: 1px solid #bfdbfe; padding: 16px; border-radius: 10px; font-size: 13px; line-height: 1.6; color: #1e40af; }
        .trick-card { background: #fefce8; border: 1px solid #fef08a; padding: 16px; border-radius: 10px; font-size: 13px; line-height: 1.6; color: #854d0e; }
        .quiz-card { background: #ffffff; border: 1px solid #e2e8f0; padding: 18px; border-radius: 10px; }
        .quiz-option { display: block; margin: 8px 0; padding: 10px 14px; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; cursor: pointer; font-size: 13px; transition: 0.2s; }
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
        .tryout-box { background: white; width: 90%; max-width: 750px; height: 80vh; border-radius: 14px; display: flex; flex-direction: column; overflow: hidden; }
        .tryout-top { background: #0f172a; color: white; padding: 16px 20px; display: flex; justify-content: space-between; align-items: center; }
        .tryout-timer { background: #ea580c; padding: 4px 12px; border-radius: 12px; font-weight: 800; font-size: 13px; }
        .tryout-content { flex: 1; padding: 24px; overflow-y: auto; }
        .tryout-bottom { padding: 14px 20px; background: #f1f5f9; border-top: 1px solid #e2e8f0; display: flex; justify-content: space-between; }
    </style>
</head>
<body>

    <header>
        <div class="logo">
            <span>SMArt Academy</span>
        </div>
        <div class="curriculum-switch">
            <button class="curr-btn active" onclick="setCurriculum('merdeka', this)">Kurikulum Merdeka</button>
            <button class="curr-btn" onclick="setCurriculum('k13', this)">Kurikulum 2013</button>
        </div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Tryout UTBK & TKA</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="sidebar-filter">
                <label>Pilihan Kelas / Program</label>
                <select id="gradeSelect" onchange="loadCategorySubjects()">
                    <optgroup label="Tingkat SMA">
                        <option value="k10">Kelas 10 (Fase E / MIPA & IPS)</option>
                        <option value="k11_ipa">Kelas 11 IPA (Fase F)</option>
                        <option value="k11_ips">Kelas 11 IPS (Fase F)</option>
                        <option value="k12_ipa">Kelas 12 IPA</option>
                        <option value="k12_ips">Kelas 12 IPS</option>
                        <option value="k12_bahasa">Kelas 12 Bahasa & Budaya</option>
                    </optgroup>
                    <optgroup label="Persiapan UTBK & Ujian Mandiri">
                        <option value="utbk_tps" selected>UTBK SNBT - Tes Potensi Skolastik (TPS)</option>
                        <option value="utbk_literasi">UTBK SNBT - Literasi Bahasa</option>
                        <option value="tka_saintek">TKA Saintek (Ujian Mandiri PTN)</option>
                        <option value="tka_soshum">TKA Soshum (Ujian Mandiri PTN)</option>
                    </optgroup>
                </select>
            </div>
            <div class="subject-list" id="subjectListContainer"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer"></div>
        </main>
    </div>

    <button class="gemini-btn" onclick="toggleChat()">✨ Asisten Belajar Gemini</button>
    <div class="chat-modal" id="chatWindow">
        <div class="chat-header">
            <span>Gemini AI Tutor</span>
            <span style="cursor:pointer;" onclick="toggleChat()">✖</span>
        </div>
        <div class="chat-body" id="chatBody">
            <div class="msg-ai"><strong>Gemini:</strong> Halo! Bingung dengan rumus matematika atau soal UTBK? Tanyakan padaku sekarang!</div>
        </div>
        <div class="chat-input-box">
            <input type="text" id="chatInput" placeholder="Ketik soal/pertanyaan..." onkeypress="handleChatKey(event)">
            <button onclick="sendChatMessage()">Kirim</button>
        </div>
    </div>

    <div class="tryout-overlay" id="tryoutOverlay">
        <div class="tryout-box">
            <div class="tryout-top">
                <h3>Simulasi UTBK SNBT - Penalaran Matematika</h3>
                <div class="tryout-timer">15:00</div>
            </div>
            <div class="tryout-content">
                <p style="font-weight: 700; margin-bottom: 12px;">Soal Nomor 1:</p>
                <p style="font-size: 15px; margin-bottom: 18px; line-height:1.5;">
                    Jika $f(x) = 2x + 5$ dan $g(x) = x^2 - 1$, berapakah nilai dari komposisi $(f \circ g)(3)$?
                </p>
                <div class="quiz-option" onclick="pickTryoutAns(this)">A. 21</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">B. 23</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">C. 25</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">D. 27</div>
            </div>
            <div class="tryout-bottom">
                <button style="padding: 8px 16px; border: 1px solid #cbd5e1; background: white; border-radius: 6px; cursor: pointer;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 8px 18px; background: #2563eb; color: white; border: none; border-radius: 6px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan Jawaban</button>
            </div>
        </div>
    </div>

    <script>
        let currentCurriculum = 'merdeka';

        const appDatabase = {
            // UTBK TPS
            utbk_tps: [
                {
                    id: "pk",
                    name: "Pengetahuan Kuantitatif (PK)",
                    tutor: "Jerome Polin (Eksakta Expert)",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Menguji kemampuan perhitungan aljabar dasar, geometri, teori bilangan, serta pemecahan masalah numerik cepat.",
                    trick: "💡 <strong>Metode Solusi 10 Detik:</strong> Pada soal perbandingan kuantitatif P dan Q, gunakan substitusi angka ekstrem (seperti -1, 0, 1) daripada menguraikan persamaan aljabar rumit.",
                    bab: ["Bab 1: Trik Aljabar & Persamaan Kuadrat", "Bab 2: Geometri & Pola Bangun", "Bab 3: Peluang & Kombinatorika"],
                    quiz: {
                        question: "Berapakah nilai dari 15% dari 200 ditambah 3^3?",
                        options: ["A. 57", "B. 47", "C. 37", "D. 27"],
                        correct: "A. 57",
                        explain: "15% x 200 = 30. Nilai 3^3 = 27. Hasil = 30 + 27 = 57."
                    }
                },
                {
                    id: "pu",
                    name: "Penalaran Umum (PU)",
                    tutor: "Tim Master UTBK",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Penalaran deduktif, induktif, serta kemampuan menganalisis grafik dan tabel kuantitatif.",
                    trick: "💡 <strong>Metode Logika:</strong> Semua A adalah B. Sebagian A adalah C. Kesimpulan pasti: Sebagian B adalah C.",
                    bab: ["Bab 1: Penalaran Deduktif & Silogisme", "Bab 2: Analisis Tabel & Grafik Data"],
                    quiz: {
                        question: "Semua siswa rajin belajar. Sebagian siswa lulus UTBK. Kesimpulannya?",
                        options: ["A. Semua siswa lulus UTBK", "B. Sebagian siswa rajin belajar dan lulus UTBK", "C. Tidak ada yang lulus", "D. Semua tidak rajin"],
                        correct: "B. Sebagian siswa rajin belajar dan lulus UTBK",
                        explain: "Prinsip penggabungan premis universal dan partikular."
                    }
                }
            ],

            // KELAS 10
            k10: [
                {
                    id: "mtk10",
                    name: "Matematika Kelas 10",
                    tutor: "Jerome Polin",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Eksponen, Logaritma, Vektor, Trigonometri Dasar, dan Fungsi Kuadrat.",
                    trick: "💡 <strong>Metode Cepat Logaritma:</strong> a^log(b) x b^log(c) = a^log(c). Cukup eliminasi basis yang sama di tengah!",
                    bab: ["Bab 1: Eksponen & Logaritma", "Bab 2: Vektor & Operasinya", "Bab 3: Trigonometri Dasar"],
                    quiz: {
                        question: "Berapakah nilai dari 2^4 x 2^3?",
                        options: ["A. 2^7 (128)", "B. 2^12", "C. 2^1", "D. 64"],
                        correct: "A. 2^7 (128)",
                        explain: "Perkalian eksponen basis sama: pangkat dijumlahkan (4 + 3 = 7)."
                    }
                },
                {
                    id: "fis10",
                    name: "Fisika Kelas 10",
                    tutor: "Pakar Fisika Indonesia",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Pengukuran, Vektor, Kinematika Gerak Lurus (GLB & GLBB), serta Hukum Newton.",
                    trick: "💡 <strong>Metode GLBB:</strong> Ingat rumus segitiga VT = V0 + a.t.",
                    bab: ["Bab 1: Pengukuran & Angka Penting", "Bab 2: Kinematika Gerak Lurus (GLB & GLBB)"],
                    quiz: {
                        question: "Satuan SI untuk Besaran Kuat Arus Listrik adalah...",
                        options: ["A. Ampere", "B. Volt", "C. Watt", "D. Joule"],
                        correct: "A. Ampere",
                        explain: "Kuat arus diukur dalam satuan Ampere (A)."
                    }
                },
                {
                    id: "kim10",
                    name: "Kimia Kelas 10",
                    tutor: "Pakar Kimia SMA",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Struktur Atom, Konfigurasi Elektron, Tabel Periodik Unsur, dan Hukum Dasar Kimia.",
                    trick: "💡 <strong>Cara Hafal Konfigurasi:</strong> Si Sapi Sapi Sedap Sedap (s p s p s d p s d p).",
                    bab: ["Bab 1: Struktur Atom & Periodik Unsur", "Bab 2: Hukum Dasar Kimia & Stoikiometri"],
                    quiz: {
                        question: "Partikel penyusun inti atom yang bermuatan positif adalah...",
                        options: ["A. Proton", "B. Neutron", "C. Elektron", "D. Foton"],
                        correct: "A. Proton",
                        explain: "Inti atom terdiri dari Proton (+) dan Neutron (0)."
                    }
                },
                {
                    id: "bio10",
                    name: "Biologi Kelas 10",
                    tutor: "Pakar Biologi SMA",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Keanekaragaman Hayati, Virus, Bakteri, Ekosistem, dan Perubahan Lingkungan.",
                    trick: "💡 <strong>Daya Ingat Taksonomi:</strong> Kingdom - Filum - Kelas - Bangsa - Suku - Marga - Jenis.",
                    bab: ["Bab 1: Keanekaragaman Hayati", "Bab 2: Virus & Inovasi Bioteknologi"],
                    quiz: {
                        question: "Keanekaragaman warna bunga mawar merupakan contoh keanekaragaman tingkat...",
                        options: ["A. Gen", "B. Spesies", "C. Ekosistem", "D. Komunitas"],
                        correct: "A. Gen",
                        explain: "Variasi warna dalam satu spesies mawar terjadi akibat perbedaan susunan genetik."
                    }
                },
                {
                    id: "eko10",
                    name: "Ekonomi Kelas 10",
                    tutor: "Pakar Ekonomi SMA",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Kelangkaan, Kebutuhan Manusia, Masalah Ekonomi, dan Keseimbangan Pasar.",
                    trick: "💡 <strong>Hukum Permintaan:</strong> Harga Naik (P↑) $\rightarrow$ Permintaan Turun (Q↓). Berbanding terbalik!",
                    bab: ["Bab 1: Kelangkaan & Skala Prioritas", "Bab 2: Permintaan & Penawaran"],
                    quiz: {
                        question: "Inti masalah ekonomi yang dialami manusia adalah...",
                        options: ["A. Kebutuhan tidak terbatas, alat pemuas terbatas", "B. Kebutuhan terbatas, alat pemuas melimpah", "C. Uang terlalu banyak", "D. Produksi berlebihan"],
                        correct: "A. Kebutuhan tidak terbatas, alat pemuas terbatas",
                        explain: "Inti masalah ekonomi adalah kelangkaan (scarcity)."
                    }
                }
            ],

            // KELAS 11 IPA
            k11_ipa: [
                {
                    id: "mtk11_ipa",
                    name: "Matematika Lanjut 11",
                    tutor: "Jerome Polin",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Matriks, Persamaan Lingkaran, Polinomial (Suku Banyak), dan Transformasi Geometri.",
                    trick: "💡 <strong>Determinan Matriks 2x2:</strong> ad - bc. Cukup kali silang!",
                    bab: ["Bab 1: Polinomial (Suku Banyak)", "Bab 2: Matriks & Invers"],
                    quiz: {
                        question: "Ordo dari matriks yang memiliki 2 baris dan 3 kolom adalah...",
                        options: ["A. 2x3", "B. 3x2", "C. 2x2", "D. 3x3"],
                        correct: "A. 2x3",
                        explain: "Format ordo matriks: (Jumlah Baris) x (Jumlah Kolom)."
                    }
                }
            ],

            // KELAS 11 IPS
            k11_ips: [
                {
                    id: "eko11_ips",
                    name: "Ekonomi Kelas 11",
                    tutor: "Tutor Ekonomi",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Pendapatan Nasional, Ketenagakerjaan, Inflasi, serta Kebijakan Moneter & Fiskal.",
                    trick: "💡 <strong>Kebijakan Moneter Ketat:</strong> Naikkan Suku Bunga $\rightarrow$ Jumlah Uang Beredar Turun $\rightarrow$ Inflasi Terkendali.",
                    bab: ["Bab 1: Pendapatan Nasional (PDB)", "Bab 2: Inflasi & Kebijakan Bank"],
                    quiz: {
                        question: "Kenaikan harga barang secara umum dan terus menerus disebut...",
                        options: ["A. Inflasi", "B. Deflasi", "C. Resesi", "D. Devaluasi"],
                        correct: "A. Inflasi",
                        explain: "Inflasi ditandai dengan turunnya nilai tukar mata uang terhadap barang secara terus-menerus."
                    }
                }
            ],

            // KELAS 12 IPA
            k12_ipa: [
                {
                    id: "mtk12_ipa",
                    name: "Matematika 12 IPA",
                    tutor: "Jerome Polin",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Limit Trigonometri, Turunan Fungsi Trigonometri, Integral, dan Geometri Dimensi Tiga.",
                    trick: "💡 <strong>Limit Trigonometri x->0:</strong> Coret sin dan tan! Ambil koefisien variabelnya saja.",
                    bab: ["Bab 1: Limit Fungsi Trigonometri", "Bab 2: Geometri Dimensi Tiga"],
                    quiz: {
                        question: "Turunan pertama dari f(x) = sin(x) adalah...",
                        options: ["A. cos(x)", "B. -cos(x)", "C. tan(x)", "D. -sin(x)"],
                        correct: "A. cos(x)",
                        explain: "Turunan dasar fungsi trigonometri sin(x) adalah cos(x)."
                    }
                }
            ],

            // KELAS 12 IPS
            k12_ips: [
                {
                    id: "geo12",
                    name: "Geografi Kelas 12",
                    tutor: "Tutor Geografi",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Pola Keruangan Desa-Kota, Penginderaan Jauh (SIG), dan Kerjasama Negara Maju/Berkembang.",
                    trick: "💡 <strong>Rumus Interaksi Kota (Carrothers):</strong> I = (P1 x P2) / (d)^2.",
                    bab: ["Bab 1: Tata Ruang Wilayah & Kota", "Bab 2: SIG & Penginderaan Jauh"],
                    quiz: {
                        question: "Komponen SIG yang berfungsi menganalisis data spasial adalah...",
                        options: ["A. Hardware & Software", "B. Kompas", "C. Peta Cetak", "D. Atmosfer"],
                        correct: "A. Hardware & Software",
                        explain: "Perangkat keras dan lunak dioperasikan manusia untuk mengolah data geospasial."
                    }
                }
            ],

            // UTBK LITERASI
            utbk_literasi: [
                {
                    id: "lit_indo",
                    name: "Literasi B. Indonesia",
                    tutor: "Tutor Bahasa UTBK",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Memahami bacaan kritis, menemukan ide tersirat, serta menilai validitas argumen penulisan.",
                    trick: "💡 <strong>Mencari Ide Pokok:</strong> Cek kalimat pertama dan kalimat terakhir paragraf terlebih dahulu (Deduktif/Induktif).",
                    bab: ["Bab 1: Ide Pokok & Simpulan Teks", "Bab 2: Evaluasi Argumen Penulis"],
                    quiz: {
                        question: "Gagasan utama paragraf biasanya terletak pada...",
                        options: ["A. Kalimat Utama", "B. Kalimat Penjelas Terakhir", "C. Catatan Kaki", "D. Judul Teks"],
                        correct: "A. Kalimat Utama",
                        explain: "Kalimat utama memuat pokok pikiran utama paragraf."
                    }
                }
            ],

            // TKA SAINTEK
            tka_saintek: [
                {
                    id: "tka_fis",
                    name: "TKA Fisika",
                    tutor: "Tutor Saintek",
                    video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Mekanika, Listrik Magnet, Termodinamika, Gelombang, dan Fisika Modern.",
                    trick: "💡 <strong>Daya Listrik:</strong> P = V x I = I^2 x R = V^2 / R.",
                    bab: ["Bab 1: Dinamika Gerak & Newton", "Bab 2: Rangkaian Listrik Arus Searah"],
                    quiz: {
                        question: "Daya listrik diukur dalam satuan...",
                        options: ["A. Watt", "B. Volt", "C. Joule", "D. Ampere"],
                        correct: "A. Watt",
                        explain: "Daya listrik diukur dalam satuan Watt (Joule/sekon)."
                    }
                }
            ],

            // TKA SOSHUM
            tka_soshum: [
                {
                    id: "tka_sej",
                    name: "TKA Sejarah",
                    tutor: "Tutor Soshum",
                    video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Sejarah Indonesia (Pergerakan Nasional, Proklamasi, Orba, Reformasi) dan Sejarah Dunia.",
                    trick: "💡 <strong>Urutan Kronologis:</strong> Budi Utomo (1908) $\rightarrow$ Sumpah Pemuda (1928) $\rightarrow$ Proklamasi (1945).",
                    bab: ["Bab 1: Pergerakan Nasional Indonesia", "Bab 2: Perang Dunia I & II"],
                    quiz: {
                        question: "Pelopor organisasi pergerakan nasional pertama di Indonesia adalah...",
                        options: ["A. Budi Utomo", "B. Sarekat Islam", "C. Indische Partij", "D. PNI"],
                        correct: "A. Budi Utomo",
                        explain: "Budi Utomo didirikan 20 Mei 1908 sebagai awal Kebangkitan Nasional."
                    }
                }
            ]
        };

        // KURIKULUM SWITCH
        function setCurriculum(curr, btn) {
            currentCurriculum = curr;
            document.querySelectorAll('.curr-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            loadCategorySubjects();
        }

        // LOAD MAPEL KATEGORI
        function loadCategorySubjects() {
            const cat = document.getElementById('gradeSelect').value;
            const subjects = appDatabase[cat] || [];
            const container = document.getElementById('subjectListContainer');
            
            container.innerHTML = "";

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

            if (subjects.length > 0) {
                renderMateri(subjects[0]);
            } else {
                document.getElementById('materiContainer').innerHTML = "<p>Materi belum tersedia.</p>";
            }
        }

        // RENDER DETAIL MATERI
        function renderMateri(sub) {
            const container = document.getElementById('materiContainer');
            
            let babListHtml = "";
            sub.bab.forEach((b) => {
                babListHtml += `
                    <div class="bab-item">
                        <span class="bab-name">${b}</span>
                        <button class="btn-play" onclick="alert('Memutar video bab: ${b}')">Tonton Video</button>
                    </div>
                `;
            });

            container.innerHTML = `
                <div class="materi-header">
                    <h2>${sub.name} (${currentCurriculum === 'merdeka' ? 'Kurikulum Merdeka' : 'Kurikulum 2013'})</h2>
                    <p>Pengajar Utama: <strong>${sub.tutor}</strong></p>
                </div>

                <div class="video-box">
                    <div class="video-wrapper">
                        <iframe src="${sub.video}" title="${sub.name}" allowfullscreen></iframe>
                    </div>

                    <div class="tabs-nav">
                        <div class="tab-btn active" onclick="switchTab(this, 'tabBab')">📺 Video & Bab</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabSummary')">📖 Rangkuman</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabTrick')">⚡ Metode Cepat</div>
                        <div class="tab-btn" onclick="switchTab(this, 'tabQuiz')">✏️ Kuis Bab</div>
                    </div>

                    <div class="tab-content active" id="tabBab">
                        <div class="bab-group">${babListHtml}</div>
                    </div>

                    <div class="tab-content" id="tabSummary">
                        <div class="summary-card">
                            <strong>Konsep Inti Pembelajaran:</strong><br>${sub.summary}
                        </div>
                    </div>

                    <div class="tab-content" id="tabTrick">
                        <div class="trick-card">
                            ${sub.trick}
                        </div>
                    </div>

                    <div class="tab-content" id="tabQuiz">
                        <div class="quiz-card">
                            <p style="font-weight:700; margin-bottom:10px;">Latihan Kuis Bab:</p>
                            <p style="margin-bottom:12px;">${sub.quiz.question}</p>
                            ${sub.quiz.options.map(opt => `
                                <div class="quiz-option" onclick="checkQuiz('${opt}', '${sub.quiz.correct}', '${sub.quiz.explain}')">${opt}</div>
                            `).join('')}
                            <div id="quizResult" style="margin-top:12px; font-weight:700;"></div>
                        </div>
                    </div>
                </div>
            `;
        }

        // SWITCH TAB METHOD
        function switchTab(btn, tabId) {
            document.querySelectorAll('.tab-btn').forEach(t => t.classList.remove('active'));
            document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
            
            btn.classList.add('active');
            document.getElementById(tabId).classList.add('active');
        }

        // EVALUASI KUIS
        function checkQuiz(selected, correct, explain) {
            const res = document.getElementById('quizResult');
            if (selected === correct) {
                res.innerHTML = `<span style="color:#16a34a;">✅ Jawaban Benar! ${explain}</span>`;
            } else {
                res.innerHTML = `<span style="color:#dc2626;">❌ Kurang Tepat. Jawaban Benar: ${correct}. Pembahasan: ${explain}</span>`;
            }
        }

        // TRYOUT MODAL
        function openTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'flex'; }
        function closeTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'none'; }
        function pickTryoutAns(el) {
            document.querySelectorAll('.quiz-option').forEach(o => o.style.background = '#f8fafc');
            el.style.background = '#e0f2fe';
        }
        function submitTryout() {
            alert("Hasil Tryout Anda:\n• Skor IRT: 755 / 1000\n• Prediksi Kelulusan PTN: 91% (Sangat Tinggi)\n\nPembahasan detail telah masuk ke portal belajar!");
            closeTryoutModal();
        }

        // GEMINI AI CHATBOT
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
                            <strong>Gemini AI:</strong> Mengenai soal/pertanyaan "${text}", kuncinya adalah memahaminya langkah demi langkah melalui konsep dasar di tab Rangkuman atau Metode Cepat di menu sebelah kiri ya!
                        </div>
                    `;
                    body.scrollTop = body.scrollHeight;
                }, 700);
            }
        }

        // RUN AT START
        window.onload = () => {
            loadCategorySubjects();
        };
    </script>
</body>
</html>
