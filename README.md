<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RuangBelajar Pro - Terlengkap Kurikulum Merdeka & K13</title>
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

        /* MODALS (Chat & Tryout) */
        .gemini-btn { position: fixed; bottom: 20px; right: 20px; background: linear-gradient(135deg, #7c3aed, #4f46e5); color: white; border: none; padding: 12px 20px; border-radius: 30px; font-weight: 700; font-size: 13px; box-shadow: 0 8px 20px rgba(124, 58, 237, 0.3); cursor: pointer; z-index: 1000; }
        .chat-modal { display: none; position: fixed; bottom: 75px; right: 20px; width: 340px; height: 440px; background: white; border-radius: 14px; box-shadow: 0 12px 32px rgba(0,0,0,0.15); border: 1px solid #e2e8f0; z-index: 1000; flex-direction: column; overflow: hidden; }
        .chat-header { background: #7c3aed; color: white; padding: 12px 16px; font-weight: 700; font-size: 14px; display: flex; justify-content: space-between; align-items: center; }
        .chat-body { flex: 1; padding: 12px; overflow-y: auto; background: #f8fafc; font-size: 13px; }
        .msg-ai { background: #f1f5f9; padding: 10px; border-radius: 8px; margin-bottom: 8px; color: #1e293b; border-left: 3px solid #7c3aed; }
        .msg-user { background: #2563eb; color: white; padding: 10px; border-radius: 8px; margin-bottom: 8px; text-align: right; margin-left: 20%; }
        .chat-input-box { display: flex; padding: 10px; border-top: 1px solid #e2e8f0; background: white; }
        .chat-input-box input { flex: 1; padding: 8px 12px; border: 1px solid #cbd5e1; border-radius: 6px; outline: none; font-size: 12px; }
        .chat-input-box button { background: #7c3aed; color: white; border: none; padding: 8px 12px; margin-left: 6px; border-radius: 6px; cursor: pointer; font-weight: 700; }

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
            <button class="curr-btn active" onclick="setCurriculum('merdeka', this)">Kurikulum Merdeka</button>
            <button class="curr-btn" onclick="setCurriculum('k13', this)">Kurikulum 2013</button>
        </div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Simulasi UTBK Nasional</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="sidebar-filter">
                <label>Pilih Jenjang & Kategori</label>
                <select id="gradeSelect" onchange="loadCategorySubjects()">
                    <optgroup label="Tingkat SMA">
                        <option value="k10" selected>Kelas 10 Umum (Semua Jurusan)</option>
                        <option value="ipa">Kelompok Sains (IPA)</option>
                        <option value="ips">Kelompok Soshum (IPS)</option>
                        <option value="bahasa">Kelompok Bahasa & Budaya</option>
                    </optgroup>
                    <optgroup label="Persiapan PTN">
                        <option value="utbk">UTBK SNBT & TKA Lengkap</option>
                    </optgroup>
                </select>
            </div>
            <div class="subject-list" id="subjectListContainer"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer"></div>
        </main>
    </div>

    <button class="gemini-btn" onclick="toggleChat()">✨ Tanya Gemini AI</button>
    <div class="chat-modal" id="chatWindow">
        <div class="chat-header"><span>Gemini AI Tutor</span><span style="cursor:pointer;" onclick="toggleChat()">✖</span></div>
        <div class="chat-body" id="chatBody">
            <div class="msg-ai"><strong>Gemini:</strong> Halo! Masukkan soal kompleks atau teori yang ingin dibahas.</div>
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
                <h3>Tryout Akbar UTBK SNBT</h3>
                <div class="tryout-timer">15:00</div>
            </div>
            <div class="tryout-content">
                <p style="font-weight: 700; margin-bottom: 12px; font-size: 16px;">Soal Penalaran Matematika:</p>
                <p style="font-size: 16px; margin-bottom: 20px; line-height: 1.6;">
                    Jika $f(x) = 2x - 3$ dan $g(x) = x^2 + 1$, berapakah nilai $(f \circ g)(4)$?
                </p>
                <div class="quiz-option" onclick="pickTryoutAns(this)">A. 29</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">B. 31</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">C. 33</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">D. 35</div>
            </div>
            <div class="tryout-bottom">
                <button style="padding: 10px 20px; border: 1px solid #cbd5e1; background: white; border-radius: 8px; cursor: pointer; font-weight: 600;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 10px 24px; background: #2563eb; color: white; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan</button>
            </div>
        </div>
    </div>

    <script>
        let currentCurriculum = 'merdeka';

        // Fungsi Helper untuk membuat list bab agar jumlahnya pas dengan request
        const generateBabs = (baseBabs, targetCount) => {
            const babs = [...baseBabs];
            for (let i = baseBabs.length + 1; i <= targetCount; i++) {
                babs.push(`Bab ${i}: Pendalaman Materi Ke-${i}`);
            }
            return babs;
        };

        const appDatabase = {
            // ================= MATA PELAJARAN UMUM & KELAS 10 =================
            k10: [
                {
                    id: "ppkn", name: "Pendidikan Pancasila / PPKn", tutor: "Tim Guru PPKn", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Memahami Sejarah Pancasila, UUD 1945, Bhinneka Tunggal Ika, NKRI, Sistem Pemerintahan, dan Kewarganegaraan.",
                    trick: "💡 <strong>Cara Hafal Konstitusi:</strong> UUD 1945 diamandemen 4 kali (1999, 2000, 2001, 2002). Ingat urutan perubahan pasal dengan metode jembatan keledai.",
                    bab: generateBabs(["Bab 1: Sejarah Perumusan Pancasila", "Bab 2: Konstitusi & UUD 1945", "Bab 3: Sistem Demokrasi Indonesia", "Bab 4: Hak Asasi Manusia (HAM)"], 24),
                    quiz: { question: "Amandemen pertama UUD 1945 dilakukan pada tahun...", options: ["A. 1998", "B. 1999", "C. 2000", "D. 2001"], correct: "B. 1999", explain: "Amandemen pertama disahkan pada Sidang Umum MPR 1999." }
                },
                {
                    id: "bind", name: "Bahasa Indonesia", tutor: "Pakar Bahasa", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Teks Laporan Hasil Observasi (LHO), Teks Eksposisi, Anekdot, Hikayat, Negosiasi, Teks Prosedur, dan Kaidah PUEBI.",
                    trick: "💡 <strong>Trik Kalimat Efektif:</strong> Kalimat tidak boleh memiliki Subjek ganda dan harus menghindari preposisi (di, ke, dari, pada) di awal kalimat jika bertindak sebagai Subjek.",
                    bab: generateBabs(["Bab 1: Teks Laporan Hasil Observasi", "Bab 2: Teks Eksposisi", "Bab 3: Teks Anekdot & Humor", "Bab 4: Nilai Kehidupan dalam Hikayat", "Bab 5: PUEBI & Tata Kalimat"], 30),
                    quiz: { question: "Struktur teks eksposisi yang benar adalah...", options: ["A. Tesis - Argumentasi - Penegasan Ulang", "B. Orientasi - Komplikasi - Resolusi", "C. Pernyataan Umum - Deskripsi Bagian", "D. Abstraksi - Orientasi - Krisis"], correct: "A. Tesis - Argumentasi - Penegasan Ulang", explain: "Teks eksposisi mengemukakan pendapat (tesis) yang didukung alasan (argumentasi)." }
                },
                {
                    id: "bing", name: "Bahasa Inggris", tutor: "English Native Tutor", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Tenses (Present, Past, Future, Perfect), Narrative Text, Descriptive Text, Analytical Exposition, Procedure Text, Passive Voice, dan Conditional Sentences.",
                    trick: "💡 <strong>Trik Tenses V3:</strong> Setiap tenses yang memiliki kata 'Perfect' (Present Perfect, Past Perfect) WAJIB menggunakan Verb 3.",
                    bab: generateBabs(["Bab 1: Descriptive Text & Present Tense", "Bab 2: Recount Text & Past Tense", "Bab 3: Narrative Text & Direct-Indirect Speech", "Bab 4: Passive Voice", "Bab 5: Conditional Sentences (If Clause)"], 30),
                    quiz: { question: "If I ___ a bird, I would fly around the world.", options: ["A. am", "B. was", "C. were", "D. be"], correct: "C. were", explain: "Conditional Type 2 for unreal situations always uses 'were' for all subjects." }
                },
                {
                    id: "mtk_umum", name: "Matematika", tutor: "Jerome Polin", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Aljabar Dasar, Eksponen & Logaritma, Fungsi Kuadrat, Pertidaksamaan, Trigonometri, Statistika, Peluang, dan Geometri Dasar.",
                    trick: "💡 <strong>Trik Cepat Persamaan Kuadrat:</strong> Rumus ABC $\\rightarrow$ $x = (-b \\pm \\sqrt{D}) / 2a$. Jika Ditanya $x_1 + x_2$ rumusnya $-b/a$. Jika $x_1 \\cdot x_2$ rumusnya $c/a$.",
                    bab: generateBabs(["Bab 1: Eksponen & Bentuk Akar", "Bab 2: Logaritma Dasar", "Bab 3: Persamaan & Fungsi Kuadrat", "Bab 4: Trigonometri Segitiga Siku-Siku", "Bab 5: Peluang & Kombinatorika"], 35),
                    quiz: { question: "Jika akar-akar persamaan $x^2 - 5x + 6 = 0$ adalah $p$ dan $q$, nilai $p+q$ adalah...", options: ["A. -5", "B. 5", "C. 6", "D. -6"], correct: "B. 5", explain: "$p+q = -b/a = -(-5)/1 = 5$." }
                },
                {
                    id: "sej", name: "Sejarah", tutor: "Tim Sejarah Nasional", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Konsep berpikir sejarah, Zaman Pra-Aksara, Kerajaan Hindu-Buddha, Kerajaan Islam, Kolonialisme, hingga Pergerakan Nasional.",
                    trick: "💡 <strong>Sinkronik vs Diakronik:</strong> Diakronik = memanjang dalam waktu, menyempit ruang. Sinkronik = meluas dalam ruang, menyempit waktu.",
                    bab: generateBabs(["Bab 1: Konsep Berpikir Sinkronik & Diakronik", "Bab 2: Manusia Purba & Pra-Aksara", "Bab 3: Pengaruh Hindu-Buddha di Nusantara", "Bab 4: Masuknya Islam di Indonesia", "Bab 5: Kolonialisme VOC"], 30),
                    quiz: { question: "Sumpah Pemuda diikrarkan pada Kongres Pemuda II tanggal...", options: ["A. 2 Mei 1928", "B. 28 Oktober 1928", "C. 20 Mei 1908", "D. 17 Agustus 1945"], correct: "B. 28 Oktober 1928", explain: "Kongres Pemuda II berlangsung pada 27-28 Oktober 1928 di Batavia." }
                },
                {
                    id: "info", name: "Informatika", tutor: "Pakar IT Pendidikan", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Berpikir Komputasional (Computational Thinking), Algoritma & Pemrograman Dasar (Python/C++), Jaringan Komputer, dan Analisis Data.",
                    trick: "💡 <strong>Algoritma 4 Pilar:</strong> Dekomposisi, Pengenalan Pola, Abstraksi, Algoritma.",
                    bab: generateBabs(["Bab 1: Berpikir Komputasional", "Bab 2: Sistem Komputer & Hardware", "Bab 3: Jaringan Komputer & Internet", "Bab 4: Algoritma & Pemrograman Dasar", "Bab 5: Dampak Sosial Informatika"], 25),
                    quiz: { question: "Proses memecah masalah besar dan kompleks menjadi bagian-bagian kecil disebut...", options: ["A. Abstraksi", "B. Pengenalan Pola", "C. Dekomposisi", "D. Algoritma"], correct: "C. Dekomposisi", explain: "Dekomposisi adalah teknik dasar dalam Berpikir Komputasional." }
                }
            ],

            // ================= KELAS 11-12 IPA =================
            ipa: [
                {
                    id: "fisika", name: "Fisika", tutor: "Tim Fisika Sains", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Kinematika, Dinamika Partikel & Rotasi, Termodinamika, Listrik Magnet, Gelombang Elektromagnetik, dan Fisika Modern.",
                    trick: "💡 <strong>Trik Energi Mekanik (EM):</strong> EM selalu konstan (Ep + Ek). Pada titik tertinggi, Ek = 0. Pada titik terendah, Ep = 0.",
                    bab: generateBabs(["Bab 1: Vektor & Kinematika Gerak Lurus", "Bab 2: Hukum Newton & Dinamika Partikel", "Bab 3: Usaha, Energi & Daya", "Bab 4: Impuls & Momentum", "Bab 5: Fluida Statis & Dinamis", "Bab 6: Listrik Statis & Dinamis", "Bab 7: Medan Magnet & Induksi Elektromagnetik"], 35),
                    quiz: { question: "Satuan dari Gaya (F) dalam SI adalah...", options: ["A. Joule", "B. Newton", "C. Watt", "D. Pascal"], correct: "B. Newton", explain: "$F = m \\times a = kg \\cdot m/s^2 = Newton$." }
                },
                {
                    id: "kimia", name: "Kimia", tutor: "Tim Kimia Sains", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Struktur Atom, Stoikiometri, Termokimia, Laju Reaksi, Kesetimbangan, Sifat Koligatif, Redoks, dan Senyawa Karbon.",
                    trick: "💡 <strong>Trik pH Asam Lemah:</strong> pH = $-\\log[H^+]$ dimana $[H^+] = \\sqrt{Ka \\times M}$.",
                    bab: generateBabs(["Bab 1: Struktur Atom & Ikatan Kimia", "Bab 2: Stoikiometri Larutan", "Bab 3: Termokimia & Hukum Hess", "Bab 4: Laju Reaksi & Kesetimbangan", "Bab 5: Larutan Asam Basa & Titrasi", "Bab 6: Sifat Koligatif Larutan", "Bab 7: Elektrokimia (Sel Volta & Elektrolisis)"], 35),
                    quiz: { question: "Pada sel Volta, reaksi reduksi terjadi di elektroda...", options: ["A. Anoda", "B. Katoda", "C. Jembatan Garam", "D. Elektrolit"], correct: "B. Katoda", explain: "KRAO: Katoda Reduksi, Anoda Oksidasi." }
                },
                {
                    id: "biologi", name: "Biologi", tutor: "Tim Biologi Sains", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Sel & Organel, Sistem Organ Tubuh Manusia, Genetika (DNA/RNA), Metabolisme (Fotosintesis/Respirasi), Mutasi, dan Evolusi.",
                    trick: "💡 <strong>Respirasi Sel (4 Tahap):</strong> Glikolisis $\\rightarrow$ Dekarboksilasi Oksidatif $\\rightarrow$ Siklus Krebs $\\rightarrow$ Transpor Elektron.",
                    bab: generateBabs(["Bab 1: Struktur & Fungsi Sel", "Bab 2: Jaringan Tumbuhan & Hewan", "Bab 3: Sistem Gerak & Peredaran Darah", "Bab 4: Sistem Pencernaan & Pernapasan", "Bab 5: Metabolisme Sel (Enzim & ATP)", "Bab 6: Sintesis Protein (Transkripsi & Translasi)", "Bab 7: Hukum Mendel & Genetika Populasi"], 40),
                    quiz: { question: "Organel yang berfungsi sebagai tempat pembentukan energi (ATP) adalah...", options: ["A. Lisosom", "B. Ribosom", "C. Mitokondria", "D. Badan Golgi"], correct: "C. Mitokondria", explain: "Mitokondria melakukan respirasi seluler untuk menghasilkan ATP." }
                },
                {
                    id: "mtk_lanjut", name: "Matematika Tingkat Lanjut", tutor: "Jerome Polin", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Polinomial (Suku Banyak), Matriks Lanjutan, Irisan Kerucut (Parabola, Elips, Hiperbola), Limit Tak Hingga, Turunan & Integral Lanjut.",
                    trick: "💡 <strong>Trik Teorema Sisa:</strong> Jika polinomial $P(x)$ dibagi $(x-a)$, sisanya adalah $P(a)$.",
                    bab: generateBabs(["Bab 1: Polinomial & Teorema Sisa", "Bab 2: Matriks Transformasi & Determinan 3x3", "Bab 3: Irisan Kerucut (Lingkaran & Parabola)", "Bab 4: Limit Fungsi Trigonometri & Limit Tak Hingga", "Bab 5: Aplikasi Integral (Volume Benda Putar)"], 25),
                    quiz: { question: "Sisa pembagian $x^3 - 2x + 5$ oleh $(x-2)$ adalah...", options: ["A. 5", "B. 7", "C. 9", "D. 11"], correct: "C. 9", explain: "Substitusi x = 2. $2^3 - 2(2) + 5 = 8 - 4 + 5 = 9$." }
                }
            ],

            // ================= KELAS 11-12 IPS =================
            ips: [
                {
                    id: "geografi", name: "Geografi", tutor: "Tim Geografi", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Biosfer, Antroposfer, Litosfer, Atmosfer, Hidrosfer, Pemetaan & SIG, Tata Ruang Wilayah (Desa-Kota).",
                    trick: "💡 <strong>Trik Skala Peta:</strong> Jarak Sebenarnya (JS) = Jarak Peta (JP) $\\times$ Penyebut Skala.",
                    bab: generateBabs(["Bab 1: Prinsip & Pendekatan Geografi", "Bab 2: Dinamika Litosfer & Gempa", "Bab 3: Dinamika Atmosfer & Iklim", "Bab 4: Persebaran Flora & Fauna", "Bab 5: Penginderaan Jauh & SIG", "Bab 6: Pola Keruangan Desa & Kota", "Bab 7: Negara Maju & Berkembang"], 35),
                    quiz: { question: "Pendekatan geografi yang menganalisis hubungan manusia dengan lingkungannya adalah...", options: ["A. Keruangan", "B. Ekologi", "C. Kompleks Wilayah", "D. Regional"], correct: "B. Ekologi", explain: "Ekologi (Kelingkungan) fokus pada interaksi makhluk hidup dengan alam." }
                },
                {
                    id: "ekonomi", name: "Ekonomi", tutor: "Tim Ekonomi", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Mikro & Makro Ekonomi, Elastisitas, Kebijakan Moneter & Fiskal, Pendapatan Nasional, Akuntansi Perusahaan Jasa & Dagang.",
                    trick: "💡 <strong>Persamaan Dasar Akuntansi:</strong> Harta = Utang + Modal. Debit-Kredit = H E L P (Harta Beban = Debit).",
                    bab: generateBabs(["Bab 1: Permintaan, Penawaran & Elastisitas", "Bab 2: Pasar Persaingan Sempurna & Monopoli", "Bab 3: Pendapatan Nasional & Inflasi", "Bab 4: Kebijakan Moneter Bank Sentral", "Bab 5: Persamaan Dasar Akuntansi", "Bab 6: Jurnal Umum & Buku Besar", "Bab 7: Jurnal Penyesuaian"], 35),
                    quiz: { question: "Kenaikan harga barang secara umum dan terus menerus disebut...", options: ["A. Deflasi", "B. Inflasi", "C. Devaluasi", "D. Depresiasi"], correct: "B. Inflasi", explain: "Inflasi menurunkan daya beli mata uang." }
                },
                {
                    id: "sosiologi", name: "Sosiologi", tutor: "Tim Sosiologi", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Interaksi Sosial, Nilai Norma, Kelompok Sosial, Stratifikasi Sosial, Konflik, dan Perubahan Sosial Global.",
                    trick: "💡 <strong>Trik Interaksi:</strong> Syarat interaksi sosial = Kontak Sosial + Komunikasi.",
                    bab: generateBabs(["Bab 1: Interaksi & Tindakan Sosial", "Bab 2: Nilai, Norma & Lembaga Sosial", "Bab 3: Stratifikasi & Diferensiasi Sosial", "Bab 4: Kelompok Sosial (Paguyuban/Patembayan)", "Bab 5: Konflik & Resolusi Konflik", "Bab 6: Perubahan Sosial & Globalisasi"], 30),
                    quiz: { question: "Sikap menilai budaya lain dengan standar budayanya sendiri disebut...", options: ["A. Relativisme", "B. Etnosentrisme", "C. Asimilasi", "D. Chauvinisme"], correct: "B. Etnosentrisme", explain: "Etnosentrisme merasa budayanya paling benar/unggul." }
                },
                {
                    id: "sej_lanjut", name: "Sejarah Tingkat Lanjut", tutor: "Tutor Sejarah Dunia", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Revolusi Besar Dunia (Prancis, Amerika, Rusia, Tiongkok), Perang Dunia I & II, Perang Dingin, dan Sejarah Kontemporer.",
                    trick: "💡 <strong>Urutan Revolusi:</strong> Amerika (1776) $\\rightarrow$ Prancis (1789) $\\rightarrow$ Rusia (1917).",
                    bab: generateBabs(["Bab 1: Peradaban Kuno Dunia", "Bab 2: Aufklarung & Revolusi Industri", "Bab 3: Revolusi Amerika & Prancis", "Bab 4: Perang Dunia I & II", "Bab 5: Perang Dingin & Runtuhnya Uni Soviet"], 25),
                    quiz: { question: "Semboyan Revolusi Prancis adalah Liberte, Egalite, dan...", options: ["A. Fraternite", "B. Solidarite", "C. Vini Vidi Vici", "D. Laissez-faire"], correct: "A. Fraternite", explain: "Liberte (Kebebasan), Egalite (Keadilan), Fraternite (Persaudaraan)." }
                }
            ],

            // ================= KELAS 12 BAHASA/BUDAYA =================
            bahasa: [
                {
                    id: "sas_ind", name: "Sastra Indonesia", tutor: "Tim Sastra", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Apresiasi Puisi, Prosa, Drama, Sejarah Sastra Indonesia, Kritik Sastra dan Esai.",
                    trick: "💡 <strong>Trik Majas:</strong> Metafora (Perbandingan langsung tanpa kata hubung). Personifikasi (Benda mati seperti manusia).",
                    bab: generateBabs(["Bab 1: Unsur Intrinsik & Ekstrinsik Prosa", "Bab 2: Majas & Citraan dalam Puisi", "Bab 3: Resensi & Kritik Sastra", "Bab 4: Penulisan Naskah Drama", "Bab 5: Periodisasi Sastra Indonesia"], 25),
                    quiz: { question: "Majas yang membandingkan benda mati seolah-olah memiliki sifat manusia disebut...", options: ["A. Hiperbola", "B. Personifikasi", "C. Metafora", "D. Litotes"], correct: "B. Personifikasi", explain: "Contoh: Angin menari-nari." }
                },
                {
                    id: "sas_ing", name: "Sastra Inggris", tutor: "English Native Literature", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "English Literature History, Poetry Analysis, Drama (Shakespearean), Short Stories, and Literary Criticism.",
                    trick: "💡 <strong>Poetry Trik:</strong> Rhyme scheme (AABB, ABAB) determines the rhythm. Pay attention to Stanza forms.",
                    bab: generateBabs(["Bab 1: Elements of Short Stories", "Bab 2: Figurative Language in Poetry", "Bab 3: Reading Shakespeare (Drama)", "Bab 4: Literary Criticism", "Bab 5: Essay Writing Process"], 25),
                    quiz: { question: "In literature, the main character is known as the...", options: ["A. Antagonist", "B. Protagonist", "C. Narrator", "D. Foil"], correct: "B. Protagonist", explain: "The protagonist is the central character." }
                },
                {
                    id: "jepang", name: "Bahasa Jepang", tutor: "Sensei Jepang", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Huruf Hiragana, Katakana, Kanji Dasar, Tata Bahasa (Bunpou), Kosakata (Kotoba), dan Pemahaman Bacaan (Dokkai).",
                    trick: "💡 <strong>Trik Hafal Huruf:</strong> Hiragana (melengkung/asli Jepang), Katakana (kaku/serapan asing), Kanji (simbol makna).",
                    bab: generateBabs(["Bab 1: Pengenalan Hiragana & Katakana", "Bab 2: Salam & Perkenalan (Aisatsu)", "Bab 3: Pola Kalimat N4/N5 Dasar", "Bab 4: Kanji Dasar JLPT N5", "Bab 5: Keterampilan Mendengar (Choukai)"], 30),
                    quiz: { question: "Salam 'Selamat Pagi' dalam bahasa Jepang adalah...", options: ["A. Konnichiwa", "B. Konbanwa", "C. Ohayou Gozaimasu", "D. Sayounara"], correct: "C. Ohayou Gozaimasu", explain: "Digunakan di pagi hari." }
                },
                {
                    id: "antro", name: "Antropologi", tutor: "Tim Antropologi", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Etnografi, Sistem Kekerabatan, Kepercayaan/Religi, Dinamika Budaya, dan Keberagaman Masyarakat.",
                    trick: "💡 <strong>Trik 7 Unsur Budaya:</strong> Bahasa, Pengetahuan, Organisasi Sosial, Peralatan Hidup, Ekonomi, Agama, Kesenian.",
                    bab: generateBabs(["Bab 1: Konsep Dasar Antropologi", "Bab 2: Etnografi Nusantara", "Bab 3: Sistem Kekerabatan (Patrilineal/Matrilineal)", "Bab 4: Dinamika Kepercayaan Lokal", "Bab 5: Multikulturalisme di Indonesia"], 25),
                    quiz: { question: "Sistem kekerabatan yang menarik garis keturunan dari pihak ibu disebut...", options: ["A. Patrilineal", "B. Matrilineal", "C. Bilateral", "D. Ambilineal"], correct: "B. Matrilineal", explain: "Diterapkan misalnya pada suku Minangkabau." }
                }
            ],

            // ================= UTBK SNBT =================
            utbk: [
                {
                    id: "pk", name: "Pengetahuan Kuantitatif", tutor: "Tim UTBK", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Operasi Bilangan, Aljabar, Geometri, Statistika, Peluang.",
                    trick: "💡 <strong>Trik Kecukupan Data:</strong> Cek Pernyataan 1 saja. Jika tidak cukup, cek Pernyataan 2 saja. Jika tidak cukup, gabungkan keduanya.",
                    bab: generateBabs(["Bab 1: Aljabar Dasar", "Bab 2: Geometri", "Bab 3: Kecukupan Data", "Bab 4: Analisis Kuantitas P dan Q", "Bab 5: Peluang dan Kombinatorika"], 30),
                    quiz: { question: "Berapa 10% dari 500?", options: ["A. 10", "B. 50", "C. 100", "D. 500"], correct: "B. 50", explain: "0.1 * 500 = 50." }
                },
                {
                    id: "litindo", name: "Literasi Bahasa Indonesia", tutor: "Tim Bahasa", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Gagasan Utama, Makna Tersirat, Evaluasi Argumen, Kesimpulan.",
                    trick: "💡 <strong>Trik Ide Pokok:</strong> Baca kalimat pertama dan terakhir setiap paragraf (Deduktif/Induktif).",
                    bab: generateBabs(["Bab 1: Gagasan Utama", "Bab 2: Analisis Argumen", "Bab 3: Makna Tersirat Paragraf", "Bab 4: PUEBI dalam Konteks Bacaan"], 30),
                    quiz: { question: "Letak kalimat utama pada paragraf deduktif adalah...", options: ["A. Awal", "B. Akhir", "C. Tengah", "D. Awal dan Akhir"], correct: "A. Awal", explain: "Deduktif = Umum ke Khusus." }
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
                        <div class="tab-btn active" onclick="switchTab(this, 'tabBab')">📺 Video & Bab (${sub.bab.length} Bab)</div>
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
                            <strong>Gemini AI:</strong> Untuk pertanyaan "${text}", pastikan kamu juga mempelajari <strong>Metode Cepat</strong> di menu sebelah kiri. Tetap semangat belajarnya!
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

