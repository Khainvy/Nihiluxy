<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RuangBelajar Pro - Materi Spesifik & Video Berbeda</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: #f1f5f9; color: #0f172a; display: flex; flex-direction: column; height: 100vh; overflow: hidden; }
        
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
        .content-area { flex: 1; overflow-y: auto; padding: 28px; background: #f8fafc; }
        .content-container { max-width: 960px; margin: 0 auto; }

        .materi-header { margin-bottom: 20px; }
        .materi-header h2 { font-size: 24px; color: #0f172a; font-weight: 800; display: flex; align-items: center; gap: 10px; }
        .materi-header p { font-size: 13px; color: #64748b; margin-top: 4px; }

        /* CHAPTER ACCORDION */
        .chapter-container { display: flex; flex-direction: column; gap: 12px; }
        .chapter-card { background: white; border: 1px solid #e2e8f0; border-radius: 12px; overflow: hidden; box-shadow: 0 1px 3px rgba(0,0,0,0.02); }
        .chapter-header { padding: 16px 20px; background: #ffffff; cursor: pointer; display: flex; justify-content: space-between; align-items: center; font-weight: 700; font-size: 15px; color: #1e293b; user-select: none; }
        .chapter-header:hover { background: #f8fafc; }
        .chapter-header .toggle-icon { font-size: 18px; font-weight: 800; color: #2563eb; transition: transform 0.2s; }
        
        .chapter-body { display: none; padding: 20px; background: #f8fafc; border-top: 1px solid #e2e8f0; }
        .chapter-card.open .chapter-body { display: block; }
        .chapter-card.open .toggle-icon { transform: rotate(45deg); }

        .explanation-box { background: #ffffff; border: 1px solid #cbd5e1; padding: 16px; border-radius: 6px; margin-bottom: 16px; font-size: 14px; line-height: 1.7; color: #334155; }
        .explanation-box h4 { margin-bottom: 8px; color: #0f172a; font-size: 15px; }

        .method-box { background: #eff6ff; border-left: 4px solid #2563eb; padding: 16px; border-radius: 6px; margin-bottom: 16px; font-size: 14px; line-height: 1.6; color: #1e40af; }
        .method-box h4 { margin-bottom: 6px; font-size: 14px; color: #1e3a8a; }

        .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 8px; background: #000; margin-bottom: 20px; }
        .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; }

        .chapter-quiz { background: #ffffff; border: 1px solid #cbd5e1; padding: 18px; border-radius: 8px; }
        .quiz-title { font-weight: 700; font-size: 14px; color: #334155; margin-bottom: 10px; }
        .quiz-question { font-size: 14px; font-weight: 600; margin-bottom: 12px; color: #0f172a; }
        .quiz-option { display: block; margin: 6px 0; padding: 10px 12px; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 6px; cursor: pointer; font-size: 13px; transition: 0.2s; font-weight: 500; }
        .quiz-option:hover { background: #f0fdf4; border-color: #22c55e; }
        .quiz-feedback { margin-top: 12px; padding: 10px; border-radius: 6px; font-size: 13px; font-weight: 600; display: none; }

        /* GEMINI AI CHATBOT & TRYOUT MODAL */
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
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Tryout Nasional SNBT</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="sidebar-filter">
                <label>Pilih Kelompok Mapel</label>
                <select id="categorySelect" onchange="loadCategorySubjects()">
                    <option value="umum" selected>Mata Pelajaran Umum (Wajib)</option>
                    <option value="ipa">Kelompok Sains (IPA)</option>
                    <option value="ips">Kelompok Soshum (IPS)</option>
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
        <div class="chat-header"><span>Gemini AI Tutor</span><span style="cursor:pointer;" onclick="toggleChat()">✖</span></div>
        <div class="chat-body" id="chatBody">
            <div class="msg-ai"><strong>Gemini:</strong> Halo! Ada materi bab atau rumus cepat yang ingin didiskusikan?</div>
        </div>
        <div class="chat-input-box">
            <input type="text" id="chatInput" placeholder="Ketik pertanyaan..." onkeypress="handleChatKey(event)">
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
                <p style="font-weight: 700; margin-bottom: 12px; font-size: 16px;">Soal Penalaran Kuantitatif:</p>
                <p style="font-size: 16px; margin-bottom: 20px; line-height: 1.6;">
                    Jika $3^x = 81$ dan $2^y = 32$, berapakah nilai dari $x + y$?
                </p>
                <div class="quiz-option" onclick="pickTryoutAns(this)">A. 7</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">B. 8</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">C. 9</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">D. 10</div>
            </div>
            <div class="tryout-bottom">
                <button style="padding: 10px 20px; border: 1px solid #cbd5e1; background: white; border-radius: 8px; cursor: pointer; font-weight: 600;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 10px 24px; background: #2563eb; color: white; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan</button>
            </div>
        </div>
    </div>

    <script>
        let currentCurriculum = 'merdeka';

        // DATABASE FULL SPESIFIK DENGAN PENJELASAN, VIDEO BERBEDA, METODE, & KUIS PER BAB
        const appDatabase = {
            umum: [
                {
                    id: "mtk_umum", name: "Matematika", tutor: "Tim Matematika Ahli",
                    chapters: [
                        {
                            title: "Bab 1: Eksponen & Bentuk Akar",
                            explanation: "Eksponen adalah bentuk perkalian berulang dari suatu bilangan yang sama. Sifat utama eksponen meliputi sifat perkalian pangkat (a^m * a^n = a^(m+n)), pembagian, serta pangkat negatif dan pecahan. Bentuk akar adalah invers dari bilangan berpangkat pecahan.",
                            trick: "Trik Pangkat Bertingkat: Selesaikan selalu mulai dari pangkat yang paling atas secara berurutan turun ke bawah.",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg",
                            quiz: { q: "Berapakah hasil dari 2^3 * 2^4?", opts: ["A. 16", "B. 32", "C. 64", "D. 128"], corr: "D. 128", exp: "Gunakan sifat pangkat: 2^(3+4) = 2^7 = 128." }
                        },
                        {
                            title: "Bab 2: Persamaan & Fungsi Kuadrat",
                            explanation: "Persamaan kuadrat memiliki bentuk umum ax^2 + bx + c = 0. Penyelesaiannya bisa melalui pemfaktoran, melengkapkan kuadrat sempurna, atau menggunakan rumus ABC. Fungsi kuadrat menghasilkan grafik berbentuk parabola.",
                            trick: "Trik Akar Cepat: Jumlah akar x1 + x2 = -b/a dan hasil kali x1 * x2 = c/a tanpa perlu mencari nilai akarnya satu per satu.",
                            video: "https://www.youtube.com/embed/Yt-3C1-eW-c",
                            quiz: { q: "Jika akar x^2 - 5x + 6 = 0 adalah p dan q, nilai p + q adalah...", opts: ["A. 3", "B. 5", "C. 6", "D. -5"], corr: "B. 5", exp: "Gunakan -b/a = -(-5)/1 = 5." }
                        },
                        {
                            title: "Bab 3: Limit Fungsi Aljabar",
                            explanation: "Limit menjelaskan nilai suatu fungsi ketika mendekati titik tertentu. Jika substitusi langsung menghasilkan nilai tak tentu (0/0), kita harus melakukan pemfaktoran, perkalian sekawan, atau turunan.",
                            trick: "Trik L'Hopital: Jika substitusi menghasilkan 0/0, turunkan pembilang dan penyebut sekali, lalu masukkan kembali nilai x.",
                            video: "https://www.youtube.com/embed/dC_P0JkU9nE",
                            quiz: { q: "Nilai dari lim (x^2 - 4) / (x - 2) untuk x mendekati 2 adalah...", opts: ["A. 2", "B. 4", "C. 0", "D. Tak hingga"], corr: "B. 4", exp: "Turunkan atas dan bawah: 2x / 1 = 2(2) = 4." }
                        }
                    ]
                },
                {
                    id: "bind", name: "Bahasa Indonesia", tutor: "Pakar Bahasa",
                    chapters: [
                        {
                            title: "Bab 1: Teks Laporan Hasil Observasi (LHO)",
                            explanation: "Teks LHO berisi penjabaran umum mengenai suatu objek berdasarkan hasil pengamatan langsung secara sistematis. Strukturnya terdiri dari pernyataan umum (klasifikasi) dan deskripsi bagian.",
                            trick: "Bedakan kalimat definisi (menggunakan kata 'adalah/merupakan') dengan kalimat deskripsi (menggambarkan sifat fisik/sifat khusus objek).",
                            video: "https://www.youtube.com/embed/FqYIq9kdshM",
                            quiz: { q: "Kalimat yang menggunakan kata 'adalah' atau 'merupakan' termasuk jenis kalimat...", opts: ["A. Deskripsi", "B. Definisi", "C. Perintah", "D. Langsung"], corr: "B. Definisi", exp: "Kata penghubung penjelas arti adalah ciri kalimat definisi." }
                        },
                        {
                            title: "Bab 2: Menemukan Ide Pokok Paragraf",
                            explanation: "Ide pokok atau gagasan utama adalah inti permasalahan yang dibahas dalam sebuah paragraf. Paragraf deduktif menaruh ide pokok di awal, sedangkan induktif di akhir.",
                            trick: "Baca kalimat pertama dan terakhir secara cermat. Kalimat yang memuat gagasan paling umum adalah kalimat utamanya.",
                            video: "https://www.youtube.com/embed/ScMzIvxBSi4",
                            quiz: { q: "Paragraf yang gagasan utamanya terletak di bagian akhir paragraf dinamakan...", opts: ["A. Deduktif", "B. Induktif", "C. Campuran", "D. Deskriptif"], corr: "B. Induktif", exp: "Induktif bersifat khusus ke umum (di akhir)." }
                        }
                    ]
                }
            ],
            ipa: [
                {
                    id: "fisika", name: "Fisika", tutor: "Tim Fisika Sains",
                    chapters: [
                        {
                            title: "Bab 1: Kinematika Gerak Lurus (GLBB)",
                            explanation: "GLBB adalah gerak benda pada lintasan garis lurus dengan percepatan (a) tetap. Kecepatan benda bisa bertambah (dipercepat) atau berkurang (diperlambat).",
                            trick: "Metode Tanpa Waktu: Jika waktu (t) tidak diketahui dalam soal, langsung gunakan rumus v_t^2 = v_0^2 + 2as.",
                            video: "https://www.youtube.com/embed/2M-vU7fK7-8",
                            quiz: { q: "Jika waktu (t) tidak diketahui pada soal GLBB, rumus paling cepat yang digunakan adalah...", opts: ["A. s = v*t", "B. v_t^2 = v_0^2 + 2as", "C. v_t = v_0 + at", "D. s = 1/2 a t^2"], corr: "B. v_t^2 = v_0^2 + 2as", exp: "Rumus ini tidak memerlukan variabel waktu (t)." }
                        },
                        {
                            title: "Bab 2: Hukum Newton tentang Gerak",
                            explanation: "Hukum I Newton berkaitan dengan kelembaman. Hukum II Newton merumuskan percepatan berbanding lurus dengan gaya (F = m * a). Hukum III Newton adalah hukum aksi-reaksi.",
                            trick: "Diagram Benda Bebas: Selalu proyeksikan gaya-gaya yang bekerja searah gerak bernilai positif dan yang berlawanan bernilai negatif.",
                            video: "https://www.youtube.com/embed/3yN-4QZ0K-M",
                            quiz: { q: "Gaya sebesar 10 N mendorong balok bermassa 2 kg di atas lantai licin. Berapa percepatannya?", opts: ["A. 2 m/s^2", "B. 5 m/s^2", "C. 10 m/s^2", "D. 20 m/s^2"], corr: "B. 5 m/s^2", exp: "a = F / m = 10 / 2 = 5 m/s^2." }
                        }
                    ]
                },
                {
                    id: "kimia", name: "Kimia", tutor: "Tim Kimia Sains",
                    chapters: [
                        {
                            title: "Bab 1: Konsep Mol & Stoikiometri",
                            explanation: "Mol adalah satuan jumlah zat dalam kimia yang bernilai setara dengan bilangan Avogadro (6.02 * 10^23 partikel). Stoikiometri mempelajari perhitungan kuantitatif dari reaktan dan produk dalam reaksi kimia.",
                            trick: "Jembatan Mol: Ubah semua satuan soal (gram, liter STP, jumlah partikel) ke dalam bentuk mol terlebih dahulu sebelum membandingkan koefisien reaksi.",
                            video: "https://www.youtube.com/embed/9BqM-0J-GvI",
                            quiz: { q: "Berapakah jumlah mol dari 11,2 liter gas oksigen (O2) pada keadaan STP?", opts: ["A. 0,25 mol", "B. 0,5 mol", "C. 1 mol", "D. 2 mol"], corr: "B. 0,5 mol", exp: "Mol = Volume / 22,4 = 11,2 / 22,4 = 0,5 mol." }
                        },
                        {
                            title: "Bab 2: Termokimia & Hukum Hess",
                            explanation: "Termokimia mempelajari perubahan panas atau entalpi (delta H) yang menyertai suatu reaksi kimia. Hukum Hess menyatakan bahwa perubahan entalpi suatu reaksi hanya bergantung pada keadaan awal dan akhir.",
                            trick: "Trik Hukum Hess: Jika reaksi dibalik, tanda delta H berubah (plus jadi minus). Jika reaksi dikalikan konstanta tertentu, delta H ikut dikalikan konstanta tersebut.",
                            video: "https://www.youtube.com/embed/Q5d-8L_vVQA",
                            quiz: { q: "Jika suatu reaksi dibalik arahnya, maka nilai perubahan entalpi (delta H) akan...", opts: ["A. Tetap sama", "B. Berlawanan tanda", "C. Dikuadratkan", "D. Dibagi dua"], corr: "B. Berlawanan tanda", exp: "Pembalikan arah reaksi mengubah tanda delta H dari positif ke negatif atau sebaliknya." }
                        }
                    ]
                }
            ],
            ips: [
                {
                    id: "ekonomi", name: "Ekonomi", tutor: "Tim Ekonomi Soshum",
                    chapters: [
                        {
                            title: "Bab 1: Permintaan, Penawaran & Harga Keseimbangan",
                            explanation: "Hukum permintaan menyatakan hubungan terbalik antara harga dan jumlah barang yang diminta. Harga keseimbangan (equilibrium) terjadi ketika jumlah barang yang diminta sama dengan jumlah yang ditawarkan (Qd = Qs).",
                            trick: "Trik Equilibrium: Samakan fungsi Qd dan Qs untuk mencari harga (P), lalu masukkan nilai P ke salah satu fungsi untuk mencari jumlah (Q).",
                            video: "https://www.youtube.com/embed/xQx9hW6j1U0",
                            quiz: { q: "Keseimbangan pasar tercapai apabila pada tingkat harga tertentu...", opts: ["A. Permintaan lebih besar dari penawaran", "B. Penawaran lebih besar dari permintaan", "C. Jumlah permintaan sama dengan jumlah penawaran", "D. Harga mencapai titik tertinggi"], corr: "C. Jumlah permintaan sama dengan jumlah penawaran", exp: "Keseimbangan pasar adalah titik temu Qd = Qs." }
                        },
                        {
                            title: "Bab 2: Siklus Akuntansi Perusahaan Jasa",
                            explanation: "Akuntansi adalah proses mencatat, menggolongkan, meringkas, dan melaporkan transaksi keuangan. Siklus dimulai dari transaksi, jurnal umum, buku besar, neraca saldo, jurnal penyesuaian, hingga laporan keuangan.",
                            trick: "Saldo Normal H-E-L-P: Harta (Asset) dan Expense (Beban) bertambah di Debit. Utang (Liability), Modal (Equity), dan Pendapatan bertambah di Kredit.",
                            video: "https://www.youtube.com/embed/z9zX4eW-Zcw",
                            quiz: { q: "Akun beban sewa yang bertambah dalam pencatatan akuntansi diletakkan di sisi...", opts: ["A. Debit", "B. Kredit", "C. Saldo awal", "D. Ikhtisar laba rugi"], corr: "A. Debit", exp: "Beban (Expense) bertambah di sisi Debit." }
                        }
                    ]
                }
            ]
        };

        // UI RENDER LOGIC
        function setCurriculum(curr, btn) {
            currentCurriculum = curr;
            document.querySelectorAll('.curr-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            loadCategorySubjects();
        }

        function loadCategorySubjects() {
            const cat = document.getElementById('categorySelect').value;
            const subjects = appDatabase[cat] || [];
            const container = document.getElementById('subjectListContainer');
            
            container.innerHTML = "";
            document.getElementById('materiContainer').innerHTML = "";

            if (subjects.length === 0) {
                container.innerHTML = "<p style='padding:15px; font-size:13px; color:#64748b;'>Kategori ini sedang diperbarui.</p>";
                return;
            }

            subjects.forEach((sub, idx) => {
                const card = document.createElement('div');
                card.className = `subject-card ${idx === 0 ? 'active' : ''}`;
                card.onclick = () => {
                    document.querySelectorAll('.subject-card').forEach(c => c.classList.remove('active'));
                    card.classList.add('active');
                    renderSubjectChapters(sub);
                };
                
                card.innerHTML = `
                    <div class="subject-title">${sub.name}</div>
                    <div class="badge-count">${sub.chapters.length} Bab</div>
                `;
                container.appendChild(card);
            });

            renderSubjectChapters(subjects[0]);
        }

        function renderSubjectChapters(sub) {
            const container = document.getElementById('materiContainer');
            
            let chaptersHtml = "";
            sub.chapters.forEach((chap, idx) => {
                chaptersHtml += `
                    <div class="chapter-card" id="chap-${idx}">
                        <div class="chapter-header" onclick="toggleChapter(${idx})">
                            <span>${chap.title}</span>
                            <span class="toggle-icon">+</span>
                        </div>
                        <div class="chapter-body">
                            <div class="explanation-box">
                                <h4>📖 Penjelasan Materi</h4>
                                <p>${chap.explanation}</p>
                            </div>
                            <div class="method-box">
                                <h4>💡 Metode Pengerjaan & Trik Cepat</h4>
                                <p>${chap.trick}</p>
                            </div>
                            <div class="video-wrapper">
                                <iframe src="${chap.video}" allowfullscreen></iframe>
                            </div>
                            <div class="chapter-quiz">
                                <div class="quiz-title">✏️ Latihan Soal Sesuai Bab:</div>
                                <div class="quiz-question">${chap.quiz.q}</div>
                                ${chap.quiz.opts.map(opt => `
                                    <div class="quiz-option" onclick="checkChapterQuiz(this, '${opt}', '${chap.quiz.corr}', '${chap.quiz.exp}')">${opt}</div>
                                `).join('')}
                                <div class="quiz-feedback"></div>
                            </div>
                        </div>
                    </div>
                `;
            });

            const currLabel = currentCurriculum === 'merdeka' ? 'Kurikulum Merdeka' : 'Kurikulum 2013';

            container.innerHTML = `
                <div class="materi-header">
                    <h2>${sub.name} <span style="font-size:13px; font-weight:600; color:#2563eb; background:#dbeafe; padding:4px 10px; border-radius:12px; margin-left:8px;">${currLabel}</span></h2>
                    <p>Pengajar: <strong>${sub.tutor}</strong> — Klik judul bab untuk membuka penjelasan materi, video, metode cepat, dan latihan soal.</p>
                </div>
                <div class="chapter-container">
                    ${chaptersHtml}
                </div>
            `;
        }

        function toggleChapter(idx) {
            const card = document.getElementById(`chap-${idx}`);
            card.classList.toggle('open');
        }

        function checkChapterQuiz(element, selected, correct, explain) {
            const quizContainer = element.closest('.chapter-quiz');
            const feedback = quizContainer.querySelector('.quiz-feedback');
            feedback.style.display = 'block';
            
            if (selected === correct) {
                feedback.style.backgroundColor = '#dcfce7';
                feedback.style.color = '#16a34a';
                feedback.innerHTML = `✅ Benar! ${explain}`;
            } else {
                feedback.style.backgroundColor = '#fee2e2';
                feedback.style.color = '#dc2626';
                feedback.innerHTML = `❌ Kurang Tepat. Jawaban benar: ${correct}. Pembahasan: ${explain}`;
            }
        }

        function openTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'flex'; }
        function closeTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'none'; }
        function pickTryoutAns(el) {
            document.querySelectorAll('.quiz-option').forEach(o => o.style.background = '#f8fafc');
            el.style.background = '#dbeafe';
        }
        function submitTryout() {
            alert("Hasil Tryout Anda Berhasil Dikirim!\n• Skor IRT: 850 / 1000\n• Prediksi Masuk PTN: 99% (Sangat Tinggi)");
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
                            <strong>Gemini AI:</strong> Untuk materi "${text}", pastikan kamu mempelajari penjelasan konsep pada kotak putih dan trik cepat pada kotak biru di bab tersebut!
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
