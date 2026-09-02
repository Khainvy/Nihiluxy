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
