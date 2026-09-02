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

        /* LIST BAB (Dengan batas maksimal tinggi agar bisa di-scroll jika bab sangat banyak) */
        .bab-group { display: flex; flex-direction: column; gap: 10px; max-height: 400px; overflow-y: auto; padding-right: 5px; }
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
            <button class="curr-btn active" onclick="setCurriculum('merdeka', this)">Kurikulum Merdeka</button>
            <button class="curr-btn" onclick="setCurriculum('k13', this)">Kurikulum 2013</button>
        </div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Tryout Nasional SNBT</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="sidebar-filter">
                <label>Pilih Kategori Pelajaran</label>
                <select id="categorySelect" onchange="loadCategorySubjects()">
                    <option value="umum" selected>Mata Pelajaran Umum</option>
                    <option value="ipa">Kelompok Sains (IPA)</option>
                    <option value="ips">Kelompok Soshum (IPS)</option>
                    <option value="bahasa">Kelompok Bahasa & Budaya</option>
                    <option value="utbk">Persiapan UTBK & SNBT</option>
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
            <div class="msg-ai"><strong>Gemini:</strong> Halo! Ada bab pelajaran atau soal yang membuatmu bingung? Tanyakan padaku!</div>
        </div>
        <div class="chat-input-box">
            <input type="text" id="chatInput" placeholder="Ketik soal/teori..." onkeypress="handleChatKey(event)">
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
                    Suatu modal diinvestasikan senilai Rp50.000.000 dengan bunga majemuk 10% per tahun. Berapakah nilai investasi tersebut pada akhir tahun kedua?
                </p>
                <div class="quiz-option" onclick="pickTryoutAns(this)">A. Rp55.000.000</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">B. Rp60.000.000</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">C. Rp60.500.000</div>
                <div class="quiz-option" onclick="pickTryoutAns(this)">D. Rp65.000.000</div>
            </div>
            <div class="tryout-bottom">
                <button style="padding: 10px 20px; border: 1px solid #cbd5e1; background: white; border-radius: 8px; cursor: pointer; font-weight: 600;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 10px 24px; background: #2563eb; color: white; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan</button>
            </div>
        </div>
    </div>

    <script>
        let currentCurriculum = 'merdeka';

        // DATABASE LENGKAP 18 MATA PELAJARAN
        const appDatabase = {
            
            // ================= MATA PELAJARAN UMUM =================
            umum: [
                {
                    id: "ppkn", name: "Pendidikan Pancasila / PPKn", tutor: "Tim Guru PPKn", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Memahami Sejarah Pancasila, UUD 1945, Demokrasi, Ketahanan Nasional, HAM, Sistem Hukum, Pemerintahan Daerah dan Pusat, serta Peran Ormas.",
                    trick: "💡 <strong>Trik Hafal Hak dan Kewajiban:</strong> Hak = Sesuatu yang mutlak menjadi milik kita (contoh: hak hidup). Kewajiban = Sesuatu yang harus dilakukan dengan tanggung jawab (contoh: bayar pajak).",
                    bab: [
                        "1. Nilai-Nilai Pancasila dalam Praktik Penyelenggaraan Negara", "2. Ketentuan UUD 1945 dalam Kehidupan Berbangsa", "3. Kewenangan Lembaga-Lembaga Negara", "4. Hubungan Struktural dan Fungsional Pemerintah Pusat dan Daerah",
                        "5. Integrasi Nasional dalam Bingkai Bhinneka Tunggal Ika", "6. Ancaman terhadap Negara dan Upaya Penyelesaiannya", "7. Wawasan Nusantara dalam Konteks NKRI", "8. Kasus Pelanggaran HAM dalam Perspektif Pancasila",
                        "9. Sistem dan Dinamika Demokrasi Pancasila", "10. Sistem Hukum dan Peradilan di Indonesia", "11. Dinamika Peran Indonesia dalam Perdamaian Dunia", "12. Ketahanan Nasional dan Bela Negara",
                        "13. Hak dan Kewajiban Warga Negara", "14. Perlindungan dan Penegakan Hukum di Indonesia", "15. Pengaruh Kemajuan Iptek terhadap NKRI", "16. Dinamika Persatuan dan Kesatuan Bangsa",
                        "17. Identitas Nasional dan Multikulturalisme", "18. Gotong Royong dalam Kehidupan Berbangsa", "19. Etika Demokrasi dan Kebebasan Berpendapat", "20. Desentralisasi dan Otonomi Daerah",
                        "21. Tata Kelola Pemerintahan yang Baik (Good Governance)", "22. Peran Partai Politik dalam Sistem Demokrasi", "23. Demokrasi Lokal dan Pemilihan Umum", "24. Peran Pemuda dalam Menjaga Keutuhan NKRI",
                        "25. Peran Organisasi Masyarakat (Ormas) dalam Pembangunan", "26. Hubungan Internasional dalam Perspektif Pancasila"
                    ],
                    quiz: { question: "Lembaga negara yang memiliki kewenangan menguji undang-undang terhadap UUD 1945 adalah...", options: ["A. Mahkamah Agung (MA)", "B. Mahkamah Konstitusi (MK)", "C. Komisi Yudisial (KY)", "D. DPR"], correct: "B. Mahkamah Konstitusi (MK)", explain: "Kewenangan judicial review UU terhadap UUD 1945 adalah milik Mahkamah Konstitusi." }
                },
                {
                    id: "bind", name: "Bahasa Indonesia", tutor: "Pakar Bahasa", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Mempelajari berbagai jenis teks (LHO, Eksposisi, Anekdot, Hikayat, Cerpen, Karya Ilmiah, Editorial), struktur tata bahasa, dan kaidah kebahasaan PUEBI.",
                    trick: "💡 <strong>Trik Menentukan Ide Pokok:</strong> Ide pokok adalah kalimat utama. Lihat awal (Deduktif), akhir (Induktif), atau keduanya (Campuran).",
                    bab: [
                        "1. Menyusun Teks Laporan Hasil Observasi", "2. Mengembangkan Pendapat dalam Teks Eksposisi", "3. Menyampaikan Ide Melalui Teks Anekdot", "4. Melestarikan Nilai Kearifan Lokal Melalui Hikayat",
                        "5. Membuat Kesepakatan Melalui Teks Negosiasi", "6. Berdebat dengan Cerdas dan Santun", "7. Menyusun Biografi Tokoh Inspiratif", "8. Mendalami Puisi Baru dan Kontemporer",
                        "9. Mengonstruksi Teks Prosedur", "10. Menganalisis Teks Eksplanasi", "11. Mengelola Informasi dalam Ceramah", "12. Menulis Cerita Pendek (Cerpen)", "13. Mempersiapkan Proposal Kegiatan dan Penelitian",
                        "14. Merancang Karya Tulis Ilmiah", "15. Menilai Karya Melalui Resensi", "16. Bermain Drama dan Teater", "17. Menulis Surat Lamaran Pekerjaan", "18. Menganalisis Teks Cerita Sejarah",
                        "19. Menyusun Teks Editorial/Tajuk Rencana", "20. Menikmati Novel Teks Fiksi", "21. Menyajikan Artikel Opini", "22. Mengkritisi Karya Melalui Kritik dan Esai", "23. Menyusun Surat Dinas dan Surat Niaga",
                        "24. Membedah Buku Nonfiksi", "25. Menganalisis Kebahasaan Teks Iklan, Slogan, dan Poster", "26. Menulis Teks Berita berdasarkan Fakta", "27. Menyusun Teks Pidato Persuasif",
                        "28. Menelaah Teks Ulasan (Review)", "29. Mengembangkan Teks Diskusi", "30. Menggali Nilai Moral dalam Fabel dan Legenda", "31. Menelaah Karakteristik Teks Monolog",
                        "32. Menganalisis Kritik Sastra Feminis dalam Karya Fiksi", "33. Mengonversi Teks Cerita Sejarah Menjadi Bentuk Drama", "34. Menulis Esai Pribadi Berdasarkan Pengalaman"
                    ],
                    quiz: { question: "Teks yang berisi pendapat pribadi redaksi terhadap suatu isu aktual disebut...", options: ["A. Teks Eksplanasi", "B. Teks Editorial/Tajuk Rencana", "C. Teks Anekdot", "D. Teks Deskripsi"], correct: "B. Teks Editorial/Tajuk Rencana", explain: "Editorial mewakili pandangan redaksi media massa terhadap suatu isu." }
                },
                {
                    id: "bing", name: "Bahasa Inggris", tutor: "English Native", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Menguasai berbagai teks bahasa Inggris (Narrative, Recount, Report, Exposition), Grammar (Tenses, Passive Voice, Conditional, Clauses), serta percakapan harian.",
                    trick: "💡 <strong>Trik Conditional Sentences:</strong> Type 1 = Future (will + V1). Type 2 = Unreal Present (would + V1 / were). Type 3 = Unreal Past (would have + V3).",
                    bab: [
                        "1. Talking About Self (Introduction)", "2. Congratulating and Complimenting Others", "3. Expressing Intentions", "4. Descriptive Text: Historical Places", "5. Announcement Text",
                        "6. Recount Text: Historical Events", "7. Narrative Text: Legends and Myths", "8. Expressing Past and Future Actions", "9. Suggestions and Offers", "10. Opinions and Thoughts",
                        "11. Formal Invitations", "12. Analytical Exposition Text", "13. Passive Voice (Present & Past)", "14. Personal Letters", "15. Cause and Effect Relationships",
                        "16. Explanation Text: Natural Phenomena", "17. Conditional Sentences (Type 1, 2, 3)", "18. Factual Report Text", "19. Discussion Text: Pros and Cons", "20. Application Letter and Resume",
                        "21. Job Interview Expressions", "22. News Item Text", "23. Captions and Visual Information", "24. Hortatory Exposition Text", "25. Review Text (Movies and Books)",
                        "26. Modals in the Past (Should have, Could have)", "27. Adjective Clauses and Relative Pronouns", "28. Direct and Indirect Speech", "29. Song Lyrics Analysis and Moral Values",
                        "30. English Proverbs and Riddles", "31. Understanding Brochures, Leaflets, and Banners", "32. Writing a Formal Report", "33. Mastering Debate and Argumentation", "34. English Idioms in Daily Contexts"
                    ],
                    quiz: { question: "If it rains tomorrow, I ___ at home.", options: ["A. stay", "B. will stay", "C. would stay", "D. stayed"], correct: "B. will stay", explain: "Conditional Type 1 (Possible condition in future) uses 'will + Verb 1'." }
                },
                {
                    id: "mtk_umum", name: "Matematika", tutor: "Jerome Polin", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Total 65 Bab mencakup Aljabar, Fungsi, Geometri, Trigonometri, Matriks, Limit, Turunan, Integral, dan Statistika Dasar.",
                    trick: "💡 <strong>Trik Cepat Persamaan Kuadrat:</strong> Rumus cepat mencari jumlah akar ($x_1+x_2 = -b/a$) dan hasil kali akar ($x_1\\cdot x_2 = c/a$).",
                    bab: [
                        "1. Bilangan Real dan Sifat-sifatnya", "2. Eksponen Dasar dan Sifat-sifat Pangkat", "3. Bentuk Akar dan Merasionalkan Penyebut", "4. Logaritma Dasar", "5. Sifat-sifat Logaritma Lanjut",
                        "6. Persamaan Linear Satu Variabel", "7. Pertidaksamaan Linear Satu Variabel", "8. Persamaan Nilai Mutlak", "9. Pertidaksamaan Nilai Mutlak", "10. Sistem Persamaan Linear Dua Variabel (SPLDV)",
                        "11. Sistem Persamaan Linear Tiga Variabel (SPLTV)", "12. Sistem Pertidaksamaan Linear Dua Variabel", "13. Persamaan Kuadrat Dasar", "14. Akar-akar Persamaan Kuadrat", "15. Sifat-sifat Akar Persamaan Kuadrat",
                        "16. Pertidaksamaan Kuadrat", "17. Sistem Persamaan Linear dan Kuadrat", "18. Relasi Himpunan", "19. Fungsi Dasar dan Pemetaan", "20. Fungsi Linear dan Grafiknya",
                        "21. Fungsi Kuadrat dan Grafiknya", "22. Fungsi Rasional", "23. Fungsi Irasional", "24. Fungsi Eksponensial", "25. Fungsi Logaritma", "26. Aljabar Fungsi", "27. Fungsi Komposisi",
                        "28. Sifat-sifat Komposisi Fungsi", "29. Fungsi Invers", "30. Komposisi Fungsi Invers", "31. Rasio Trigonometri Segitiga Siku-Siku", "32. Sudut Berelasi di Berbagai Kuadran",
                        "33. Aturan Sinus", "34. Aturan Cosinus", "35. Luas Segitiga dengan Trigonometri", "36. Grafik Fungsi Sinus dan Cosinus", "37. Grafik Fungsi Tangen", "38. Persamaan Trigonometri Sederhana",
                        "39. Induksi Matematika Dasar", "40. Penerapan Induksi pada Keterbagian", "41. Program Linear: Model Matematika", "42. Program Linear: Nilai Optimum", "43. Matriks: Ordo dan Elemen",
                        "44. Operasi Penjumlahan dan Pengurangan Matriks", "45. Perkalian Skalar dan Matriks", "46. Determinan Matriks 2x2 dan 3x3", "47. Invers Matriks 2x2 dan 3x3", "48. Transformasi Geometri: Translasi",
                        "49. Transformasi Geometri: Refleksi", "50. Transformasi Geometri: Rotasi", "51. Transformasi Geometri: Dilatasi", "52. Komposisi Transformasi Berbasis Matriks", "53. Barisan dan Deret Aritmetika",
                        "54. Barisan dan Deret Geometri", "55. Deret Geometri Tak Hingga", "56. Limit Fungsi Aljabar Mendekati Suatu Nilai", "57. Limit Fungsi Aljabar Menuju Tak Hingga", "58. Turunan Pertama Fungsi Aljabar",
                        "59. Aplikasi Turunan: Persamaan Garis Singgung", "60. Aplikasi Turunan: Kemonotonan dan Nilai Ekstrim", "61. Integral Tak Tentu Fungsi Aljabar", "62. Integral Tentu Fungsi Aljabar",
                        "63. Penyajian Data Tunggal dan Kelompok", "64. Pemusatan dan Penyebaran Data (Statistika Dasar)", "65. Kaidah Pencacahan dan Peluang Kejadian"
                    ],
                    quiz: { question: "Nilai dari $\\lim_{x \\to 2} (3x^2 - x + 5)$ adalah...", options: ["A. 13", "B. 15", "C. 17", "D. 19"], correct: "B. 15", explain: "Substitusi langsung: $3(2)^2 - 2 + 5 = 12 - 2 + 5 = 15$." }
                },
                {
                    id: "sej", name: "Sejarah", tutor: "Tim Sejarah", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Konsep Berpikir Sejarah, Praaksara, Masa Kerajaan, Kolonialisme, Pergerakan Nasional, Proklamasi, Orde Baru, hingga Reformasi.",
                    trick: "💡 <strong>Trik Konsep Waktu:</strong> Diakronik = memanjang waktu/kronologis. Sinkronik = meluas ruang (menganalisis keadaan sosial/ekonomi pada waktu tertentu).",
                    bab: [
                        "1. Konsep Berpikir Sinkronik dan Diakronik", "2. Konsep Perubahan dan Keberlanjutan dalam Sejarah", "3. Kehidupan Manusia Purba di Nusantara dan Dunia", "4. Asal-usul Nenek Moyang Bangsa Indonesia",
                        "5. Kebudayaan Zaman Praaksara (Batu dan Logam)", "6. Masuknya Pengaruh Agama dan Kebudayaan Hindu-Buddha", "7. Kerajaan-Kerajaan Hindu-Buddha di Nusantara", "8. Masuk dan Berkembangnya Islam di Nusantara",
                        "9. Kerajaan-Kerajaan Islam di Indonesia", "10. Akulturasi Kebudayaan Nusantara, Hindu-Buddha, dan Islam", "11. Penjelajahan Samudra dan Kedatangan Bangsa Eropa", "12. Kekuasaan VOC di Nusantara",
                        "13. Pemerintahan Hindia Belanda dan Tanam Paksa", "14. Perlawanan Rakyat Daerah Terhadap Kolonialisme", "15. Lahirnya Pergerakan Nasional dan Politik Etis", "16. Organisasi Pergerakan Nasional",
                        "17. Sumpah Pemuda dan Makna Kebangsaan", "18. Masa Pendudukan Jepang di Indonesia", "19. Peristiwa Rengasdengklok dan Proklamasi", "20. Perjuangan Fisik Mempertahankan Kemerdekaan",
                        "21. Perjuangan Diplomasi Mempertahankan Kemerdekaan", "22. Pemberontakan dan Ancaman Disintegrasi Bangsa", "23. Sistem Demokrasi Liberal di Indonesia", "24. Sistem Demokrasi Terpimpin di Indonesia",
                        "25. Lahirnya Orde Baru dan Kebijakan Pembangunan", "26. Runtuhnya Orde Baru dan Lahirnya Reformasi", "27. Perkembangan Politik dan Ekonomi Masa Reformasi", "28. Peran Indonesia dalam Perdamaian Dunia"
                    ],
                    quiz: { question: "Perjanjian yang mengharuskan Belanda mengakui kedaulatan RI atas Jawa, Sumatra, dan Madura adalah...", options: ["A. Perjanjian Renville", "B. Perjanjian Linggarjati", "C. Perjanjian Roem-Royen", "D. KMB"], correct: "B. Perjanjian Linggarjati", explain: "Disepakati tahun 1946 secara de facto." }
                },
                {
                    id: "info", name: "Informatika", tutor: "Pakar IT Pendidikan", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Berpikir Komputasional, Algoritma Pemrograman, Jaringan Komputer, Pengolahan Data, dan Dampak Sosial Informatika.",
                    trick: "💡 <strong>4 Pilar CT:</strong> Dekomposisi (pecah masalah), Pengenalan Pola (cari kesamaan), Abstraksi (buang hal tak penting), Algoritma (langkah-langkah).",
                    bab: [
                        "1. Berpikir Komputasional: Dekomposisi dan Abstraksi", "2. Pengenalan Pola dan Perancangan Algoritma", "3. Sejarah Perkembangan Komputer", "4. Perangkat Keras (Hardware) dan Perangkat Lunak (Software)",
                        "5. Sistem Operasi dan Interaksi Manusia dengan Komputer", "6. Jaringan Komputer Lokal (LAN) dan Topologi Jaringan", "7. Jaringan Internet dan Keamanan Siber (Cyber Security)", "8. Manajemen File dan Basis Data Sederhana",
                        "9. Pengolah Kata Tingkat Lanjut", "10. Pengolah Angka (Spreadsheet) dan Fungsi Logika", "11. Perangkat Lunak Presentasi dan Desain Visual", "12. Pengantar Pemrograman Visual (Scratch/Blockly)",
                        "13. Bahasa Pemrograman Tekstual Dasar", "14. Tipe Data, Variabel, dan Operator", "15. Struktur Kontrol Percabangan", "16. Struktur Kontrol Perulangan", "17. Fungsi dan Prosedur dalam Pemrograman",
                        "18. Analisis dan Visualisasi Data", "19. Algoritma Pencarian (Searching)", "20. Algoritma Pengurutan (Sorting)", "21. Etika Kewargaan Digital", "22. Hak Kekayaan Intelektual (HAKI) Perangkat Lunak",
                        "23. Dampak Sosial Kecerdasan Buatan (AI)", "24. Internet of Things (IoT) dan Big Data", "25. Proyek Informatika Terpadu (STEM)"
                    ],
                    quiz: { question: "Fungsi yang digunakan pada Spreadsheet untuk menjumlahkan data dengan kriteria tertentu adalah...", options: ["A. SUM", "B. AVERAGE", "C. SUMIF", "D. COUNT"], correct: "C. SUMIF", explain: "SUM menjumlahkan, sedangkan SUMIF menjumlahkan dengan kondisi/kriteria tertentu." }
                }
            ],

            // ================= KELAS IPA (SAINS) =================
            ipa: [
                {
                    id: "fisika", name: "Fisika", tutor: "Tim Fisika Sains", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Kinematika, Dinamika Partikel & Rotasi, Termodinamika, Fluida, Listrik Magnet, Gelombang, dan Fisika Modern.",
                    trick: "💡 <strong>Hukum Pascal:</strong> Tekanan zat cair di ruang tertutup diteruskan ke segala arah sama besar ($F_1/A_1 = F_2/A_2$).",
                    bab: [
                        "1. Hakikat Fisika dan Metode Ilmiah", "2. Besaran, Satuan, dan Dimensi", "3. Pengukuran dan Angka Penting", "4. Vektor (Penjumlahan dan Penguraian)", "5. Kinematika: Gerak Lurus Beraturan (GLB)",
                        "6. Kinematika: Gerak Lurus Berubah Beraturan (GLBB)", "7. Gerak Parabola", "8. Gerak Melingkar Beraturan", "9. Dinamika Partikel: Hukum Newton tentang Gerak", "10. Gaya Gesek dan Aplikasi Hukum Newton",
                        "11. Hukum Newton tentang Gravitasi", "12. Usaha dan Energi", "13. Hukum Kekekalan Energi Mekanik", "14. Momentum, Impuls, dan Tumbukan", "15. Dinamika Rotasi dan Momen Inersia",
                        "16. Kesetimbangan Benda Tegar", "17. Elastisitas dan Hukum Hooke", "18. Fluida Statis", "19. Fluida Dinamis (Hukum Bernoulli)", "20. Suhu, Pemuaian, dan Kalor", "21. Asas Black dan Perpindahan Kalor",
                        "22. Teori Kinetik Gas Ideal", "23. Termodinamika dan Mesin Carnot", "24. Karakteristik Gelombang Mekanik", "25. Gelombang Berjalan dan Gelombang Stasioner", "26. Gelombang Bunyi (Efek Doppler, Pipa Organa)",
                        "27. Gelombang Cahaya", "28. Alat Optik (Mata, Lup, Mikroskop, Teleskop)", "29. Pemanasan Global dan Efek Rumah Kaca", "30. Listrik Statis", "31. Kapasitor dan Dielektrik",
                        "32. Rangkaian Listrik Arus Searah (DC)", "33. Medan Magnetik dan Hukum Biot-Savart", "34. Gaya Lorentz", "35. Induksi Elektromagnetik", "36. Rangkaian Arus Bolak-Balik (AC)",
                        "37. Teori Relativitas Khusus", "38. Efek Fotolistrik dan Dualisme Gelombang-Partikel", "39. Fisika Inti dan Radioaktivitas Lanjut"
                    ],
                    quiz: { question: "Sebuah benda bermassa 2 kg jatuh bebas dari ketinggian 10 m (g = 10 m/s^2). Energi Kinetik saat mencapai tanah adalah...", options: ["A. 100 J", "B. 200 J", "C. 300 J", "D. 400 J"], correct: "B. 200 J", explain: "Berdasarkan Hukum Kekekalan Energi Mekanik, Ek di tanah = Ep di awal = mgh = 2*10*10 = 200 Joule." }
                },
                {
                    id: "kimia", name: "Kimia", tutor: "Tim Kimia Sains", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Struktur Atom, Ikatan Kimia, Stoikiometri, Termokimia, Laju & Kesetimbangan Reaksi, Asam Basa, Redoks, dan Senyawa Karbon.",
                    trick: "💡 <strong>Trik Hidrolisis & Penyangga:</strong> Jika Sisa Asam Kuat/Basa Kuat -> Hidrolisis. Jika Sisa Asam Lemah/Basa Lemah -> Penyangga (Buffer).",
                    bab: [
                        "1. Hakikat Ilmu Kimia dan Keselamatan Kerja", "2. Struktur Atom dan Partikel Dasar", "3. Model Atom Bohr dan Mekanika Kuantum", "4. Konfigurasi Elektron dan Bilangan Kuantum", "5. Sistem Periodik Unsur",
                        "6. Ikatan Ion dan Ikatan Kovalen", "7. Ikatan Logam dan Gaya Antarmolekul", "8. Bentuk Molekul (VSEPR dan Hibridisasi)", "9. Tata Nama Senyawa Sederhana", "10. Persamaan Reaksi Kimia",
                        "11. Hukum-Hukum Dasar Kimia", "12. Konsep Mol dan Stoikiometri", "13. Daya Hantar Listrik Larutan", "14. Reaksi Reduksi-Oksidasi (Redoks) Dasar", "15. Kekhasan Atom Karbon dan Tata Nama Alkana, Alkena, Alkuna",
                        "16. Isomeri Hidrokarbon", "17. Minyak Bumi dan Petrokimia", "18. Termokimia (Entalpi dan Hukum Hess)", "19. Kalorimetri dan Energi Ikatan", "20. Laju Reaksi dan Faktor yang Memengaruhi",
                        "21. Persamaan Laju Reaksi dan Orde Reaksi", "22. Kesetimbangan Kimia", "23. Pergeseran Kesetimbangan (Asas Le Chatelier)", "24. Teori Asam dan Basa", "25. Derajat Keasaman (pH)", "26. Titrasi Asam-Basa",
                        "27. Larutan Penyangga (Buffer)", "28. Hidrolisis Garam", "29. Kelarutan dan Hasil Kali Kelarutan (Ksp)", "30. Sistem Koloid", "31. Sifat Koligatif Larutan", "32. Penyetaraan Reaksi Redoks Lanjut",
                        "33. Sel Volta dan Potensial Sel", "34. Sel Elektrolisis dan Hukum Faraday", "35. Kimia Unsur (Golongan Utama dan Transisi)", "36. Kimia Hijau (Green Chemistry) dan Prinsip Keberlanjutan"
                    ],
                    quiz: { question: "Proses pemisahan minyak bumi menjadi fraksi-fraksinya menggunakan prinsip...", options: ["A. Destilasi Bertingkat", "B. Kromatografi", "C. Ekstraksi", "D. Kristalisasi"], correct: "A. Destilasi Bertingkat", explain: "Minyak bumi dipisahkan berdasarkan perbedaan titik didih (destilasi fraksional/bertingkat)." }
                },
                {
                    id: "biologi", name: "Biologi", tutor: "Tim Biologi Sains", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Sel, Jaringan Tumbuhan & Hewan, Anatomi Manusia, Metabolisme Sel, Genetika, Evolusi, dan Ekologi.",
                    trick: "💡 <strong>Trik Respirasi Aerob:</strong> G-D-K-T (Glikolisis, DO, Krebs, Transpor Elektron). ATP Terbanyak ada di Transpor Elektron.",
                    bab: [
                        "1. Ruang Lingkup Biologi dan Metode Ilmiah", "2. Tingkat Organisasi Kehidupan", "3. Keanekaragaman Hayati di Indonesia", "4. Klasifikasi Makhluk Hidup (Taksonomi)", "5. Virus: Struktur, Replikasi, dan Peranannya",
                        "6. Archaebacteria dan Eubacteria", "7. Protista Mirip Jamur, Tumbuhan, dan Hewan", "8. Fungi (Jamur)", "9. Tumbuhan Lumut (Bryophyta) dan Paku (Pteridophyta)", "10. Tumbuhan Berbiji (Spermatophyta)",
                        "11. Invertebrata: Porifera hingga Echinodermata", "12. Vertebrata: Pisces hingga Mammalia", "13. Ekologi: Komponen Ekosistem", "14. Aliran Energi, Rantai Makanan, dan Jaring Makanan", "15. Daur Biogeokimia",
                        "16. Perubahan Lingkungan dan Pelestarian Ekosistem", "17. Struktur dan Fungsi Sel", "18. Organel Sel Tumbuhan dan Hewan", "19. Transpor Membran Sel", "20. Jaringan pada Tumbuhan",
                        "21. Jaringan pada Hewan", "22. Sistem Gerak (Rangka dan Otot)", "23. Sistem Peredaran Darah Manusia", "24. Sistem Limfatik dan Kekebalan Tubuh Dasar", "25. Sistem Pencernaan Makanan",
                        "26. Sistem Pernapasan Manusia dan Hewan", "27. Sistem Ekskresi Manusia", "28. Sistem Saraf Pusat dan Tepi", "29. Organ Indera", "30. Sistem Endokrin (Hormon)",
                        "31. Sistem Reproduksi Pria dan Wanita", "32. Siklus Menstruasi, Kehamilan, dan Kontrasepsi", "33. Sistem Imun dan Imunisasi", "34. Pertumbuhan dan Perkembangan", "35. Enzim dan Sifat-sifatnya",
                        "36. Respirasi Seluler (Aerob dan Anaerob)", "37. Fotosintesis dan Kemosintesis", "38. Substansi Genetik (Kromosom, DNA, RNA, Sintesis Protein)", "39. Pembelahan Sel (Mitosis dan Meiosis)", "40. Pewarisan Sifat (Hukum Mendel dan Penyimpangan Semu)",
                        "41. Mutasi, Evolusi, dan Bioetika (Kloning & Bioteknologi Modern)"
                    ],
                    quiz: { question: "Basa nitrogen pada RNA yang tidak ada pada DNA adalah...", options: ["A. Sitosin", "B. Guanin", "C. Adenin", "D. Urasil"], correct: "D. Urasil", explain: "Pada RNA, Timin (T) digantikan oleh Urasil (U)." }
                },
                {
                    id: "mtk_lanjut", name: "Matematika Tingkat Lanjut", tutor: "Jerome Polin", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Polinomial, Matriks Geometri, Irisan Kerucut, Eksponen/Logaritma Lanjut, Limit Trigonometri, Turunan & Integral Trigonometri Lanjut.",
                    trick: "💡 <strong>Trik Limit Menuju Tak Hingga:</strong> Bentuk $\\frac{ax^n}{px^m}$. Jika n=m, hasilnya $a/p$. Jika n>m hasilnya $\\infty$.",
                    bab: [
                        "1. Operasi Aljabar pada Polinomial (Suku Banyak)", "2. Teorema Sisa pada Polinomial", "3. Teorema Faktor pada Polinomial", "4. Persamaan Polinomial dan Akar-akarnya", "5. Matriks Lanjut: Sifat Determinan Geometris",
                        "6. Sistem Persamaan Linear dengan Aturan Cramer", "7. Matriks Transformasi Geometri Ordo 2x2", "8. Komposisi Transformasi Geometri Berbasis Matriks", "9. Irisan Kerucut: Persamaan Lingkaran", "10. Garis Singgung Lingkaran",
                        "11. Irisan Kerucut: Parabola", "12. Garis Singgung Parabola", "13. Irisan Kerucut: Elips", "14. Garis Singgung Elips", "15. Irisan Kerucut: Hiperbola", "16. Garis Singgung Hiperbola",
                        "17. Fungsi Eksponensial dan Logaritma Lanjut", "18. Persamaan dan Pertidaksamaan Eksponensial", "19. Persamaan dan Pertidaksamaan Logaritma", "20. Limit Fungsi Trigonometri", "21. Asimtot Datar, Tegak, dan Miring Kurva Aljabar",
                        "22. Limit Menuju Tak Hingga Fungsi Trigonometri", "23. Turunan Pertama dan Kedua Fungsi Trigonometri", "24. Titik Stasioner dan Kemonotonan Kurva Trigonometri", "25. Aplikasi Turunan Trigonometri (Gerak Harmonik)",
                        "26. Vektor Ruang dan Proyeksi Ortogonal", "27. Integral Tak Tentu Fungsi Trigonometri", "28. Integral Tentu Fungsi Trigonometri", "29. Teknik Integrasi: Substitusi dan Parsial", "30. Aplikasi Integral: Luas Daerah dan Volume Benda Putar"
                    ],
                    quiz: { question: "Teorema Sisa menyatakan bahwa sisa pembagian fungsi polinomial f(x) oleh (x - k) adalah...", options: ["A. f(k)", "B. f(-k)", "C. f'(k)", "D. 0"], correct: "A. f(k)", explain: "Sesuai definisi Teorema Sisa, nilai sisa adalah nilai fungsi pada x=k." }
                }
            ],

            // ================= KELAS IPS (SOSHUM) =================
            ips: [
                {
                    id: "geografi", name: "Geografi", tutor: "Tim Geografi", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Pengetahuan Dasar Geografi, Dinamika Bumi, Biosfer, Antroposfer, SDA, Bencana Alam, Tata Ruang, dan Interaksi Desa-Kota.",
                    trick: "💡 <strong>Teori Konsentris:</strong> Pemukiman kumuh/pekerja pabrik terletak dekat dengan zona transisi/pusat industri, sedangkan kalangan elite hidup di pinggiran (suburban) untuk menghindari polusi.",
                    bab: [
                        "1. Pengetahuan Dasar Geografi", "2. Peta dan Pemetaan Topografi", "3. Penginderaan Jauh dan Interpretasi Citra", "4. Sistem Informasi Geografis (SIG)", "5. Langkah-Langkah Penelitian Geografi",
                        "6. Pembentukan Bumi dan Tata Surya", "7. Sejarah Perkembangan Muka Bumi (Teori Lempeng Tektonik)", "8. Litosfer: Siklus Batuan dan Tenaga Endogen", "9. Vulkanisme, Seisme, dan Dampaknya", "10. Tenaga Eksogen: Pelapukan, Erosi, dan Sedimentasi",
                        "11. Pedosfer: Proses Pembentukan Tanah dan Konservasi", "12. Atmosfer: Cuaca, Iklim, dan Klasifikasi Iklim", "13. Gejala Cuaca dan Perubahan Iklim Global", "14. Hidrosfer: Siklus Air dan Perairan Darat", "15. Perairan Laut dan Morfologi Dasar Laut",
                        "16. Biosfer: Faktor Persebaran Flora dan Fauna", "17. Bioma Dunia dan Persebaran Flora Fauna Indonesia", "18. Konservasi Flora dan Fauna di Indonesia", "19. Antroposfer: Kuantitas Penduduk dan Sensus", "20. Komposisi dan Piramida Penduduk",
                        "21. Dinamika Mobilitas dan Migrasi Penduduk", "22. Kualitas Penduduk dan Indeks Pembangunan Manusia", "23. Klasifikasi Sumber Daya Alam (SDA) di Indonesia", "24. Potensi Pertanian, Kehutanan, Pertambangan, dan Kelautan", "25. Analisis Mengenai Dampak Lingkungan (AMDAL)",
                        "26. Ketahanan Pangan Nasional dan Energi Terbarukan", "27. Jenis-Jenis Bencana Alam di Indonesia", "28. Mitigasi dan Adaptasi Bencana Alam", "29. Konsep Wilayah dan Perwilayahan", "30. Kutub Pertumbuhan dan Pusat Pertumbuhan di Indonesia",
                        "31. Struktur Keruangan dan Perkembangan Desa", "32. Struktur Keruangan dan Perkembangan Kota", "33. Pola Interaksi Keruangan Desa dan Kota", "34. Dampak Interaksi Desa-Kota", "35. Indikator dan Sebaran Negara Maju - Negara Berkembang"
                    ],
                    quiz: { question: "Alat untuk merekam gelombang seismik dari gempa bumi disebut...", options: ["A. Barometer", "B. Seismograf", "C. Anemometer", "D. Higrometer"], correct: "B. Seismograf", explain: "Seismograf merekam kekuatan dan durasi gempa bumi." }
                },
                {
                    id: "ekonomi", name: "Ekonomi", tutor: "Tim Ekonomi Soshum", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Konsep Dasar Ilmu Ekonomi, Pasar & Elastisitas, Kebijakan Moneter Fiskal, Pendapatan Nasional, APBN, Ketenagakerjaan, hingga Siklus Akuntansi.",
                    trick: "💡 <strong>Trik Jurnal Umum:</strong> H E L P -> Harta & Beban (+) di Debit. Kewajiban (Utang), Ekuitas (Modal), Pendapatan (+) di Kredit.",
                    bab: [
                        "1. Konsep Dasar Ilmu Ekonomi dan Kelangkaan", "2. Biaya Peluang (Opportunity Cost) dan Skala Prioritas", "3. Sistem Ekonomi", "4. Peran Pelaku Ekonomi", "5. Model Diagram Interaksi Pelaku Ekonomi (Circular Flow)",
                        "6. Konsep Permintaan dan Penawaran", "7. Harga Keseimbangan Pasar", "8. Elastisitas Permintaan dan Penawaran", "9. Struktur Pasar: Pasar Persaingan Sempurna", "10. Struktur Pasar: Monopoli, Oligopoli, Monopolistik",
                        "11. Lembaga Jasa Keuangan (Perbankan dan LKBB)", "12. Otoritas Jasa Keuangan (OJK)", "13. Bank Sentral dan Sistem Pembayaran", "14. Alat Pembayaran Tunai dan Nontunai", "15. Konsep Manajemen",
                        "16. Koperasi dan Sisa Hasil Usaha (SHU)", "17. Pendapatan Nasional (PDB, PNB, NNP, NNI)", "18. Metode Penghitungan Pendapatan Nasional", "19. Pertumbuhan Ekonomi dan Teori Pertumbuhan", "20. Pembangunan Ekonomi dan Indikator Keberhasilan",
                        "21. Ketenagakerjaan: Angkatan Kerja dan Pengangguran", "22. Indeks Harga dan Inflasi", "23. Kebijakan Moneter", "24. Kebijakan Fiskal", "25. APBN dan APBD", "26. Jenis-Jenis Pajak di Indonesia",
                        "27. Perdagangan Internasional", "28. Neraca Pembayaran dan Devisa", "29. Akuntansi sebagai Sistem Informasi", "30. Persamaan Dasar Akuntansi", "31. Jurnal Umum dan Buku Besar (Perusahaan Jasa)",
                        "32. Jurnal Penyesuaian dan Kertas Kerja", "33. Laporan Keuangan Perusahaan Jasa", "34. Jurnal Khusus Perusahaan Dagang", "35. Harga Pokok Penjualan (HPP)", "36. Ekonomi Digital, E-Commerce, dan Fintech"
                    ],
                    quiz: { question: "Jika jumlah uang beredar di masyarakat terlalu banyak, bank sentral akan melakukan...", options: ["A. Menurunkan suku bunga", "B. Menaikkan suku bunga (Diskonto)", "C. Membeli surat berharga", "D. Menurunkan pajak"], correct: "B. Menaikkan suku bunga (Diskonto)", explain: "Menaikkan suku bunga memicu orang menabung dan mengurangi uang beredar." }
                },
                {
                    id: "sosiologi", name: "Sosiologi", tutor: "Tim Sosiologi", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Interaksi Sosial, Diferensiasi, Stratifikasi, Konflik Sosial, Integrasi, Mobilitas, Perubahan Sosial, dan Globalisasi.",
                    trick: "💡 <strong>Trik Stratifikasi vs Diferensiasi:</strong> Stratifikasi (Vertikal/Tingkatan: Kekayaan, Pendidikan). Diferensiasi (Horizontal/Sejajar: Agama, Ras, Suku).",
                    bab: [
                        "1. Sosiologi sebagai Ilmu Pengetahuan", "2. Objek Kajian dan Realitas Sosial", "3. Nilai dan Norma Sosial", "4. Interaksi Sosial: Syarat dan Bentuknya", "5. Tindakan Sosial dan Proses Sosialisasi",
                        "6. Pembentukan Kepribadian dan Agen Sosialisasi", "7. Perilaku Menyimpang (Deviasi Sosial)", "8. Pengendalian Sosial", "9. Struktur Sosial dan Diferensiasi Sosial", "10. Stratifikasi Sosial (Pelapisan Masyarakat)",
                        "11. Mobilitas Sosial: Bentuk dan Saluran", "12. Konsep dan Klasifikasi Kelompok Sosial", "13. Dinamika Kelompok Sosial", "14. Masyarakat Multikultural", "15. Konflik Sosial: Faktor Penyebab dan Bentuknya",
                        "16. Kekerasan dan Dampak Konflik Sosial", "17. Resolusi Konflik (Mediasi, Arbitrase, Konsiliasi)", "18. Integrasi dan Reintegrasi Sosial", "19. Perubahan Sosial: Teori dan Bentuknya", "20. Faktor Pendorong dan Penghambat Perubahan Sosial",
                        "21. Modernisasi dan Ciri Masyarakat Modern", "22. Globalisasi: Dampak Positif dan Negatif", "23. Ketimpangan Sosial sebagai Dampak Globalisasi", "24. Kearifan Lokal dalam Mengatasi Ketimpangan Sosial",
                        "25. Penelitian Sosial: Metode Kualitatif dan Kuantitatif", "26. Penyusunan Instrumen dan Pengumpulan Data", "27. Pemberdayaan Komunitas Berbasis Kearifan Lokal"
                    ],
                    quiz: { question: "Proses percampuran dua budaya menjadi satu budaya baru tanpa menghilangkan unsur budaya asli disebut...", options: ["A. Asimilasi", "B. Akulturasi", "C. Amalgamasi", "D. Akomodasi"], correct: "B. Akulturasi", explain: "Akulturasi memadukan kebudayaan tanpa menghilangkan identitas kebudayaan asli." }
                },
                {
                    id: "sej_lanjut", name: "Sejarah Tingkat Lanjut", tutor: "Tim Sejarah Lanjut", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Peradaban Kuno Dunia, Abad Pertengahan Eropa, Revolusi Besar (Prancis, Amerika, Rusia), Perang Dunia, dan Sejarah Kontemporer.",
                    trick: "💡 <strong>Zaman Pencerahan (Aufklärung):</strong> Era dimana logika dan rasio manusia digunakan seluas-luasnya untuk mendobrak dogma gereja (Abad Kegelapan).",
                    bab: [
                        "1. Metodologi Penelitian Sejarah", "2. Historiografi Tradisional, Kolonial, dan Modern", "3. Peradaban Kuno Lembah Sungai Nil", "4. Peradaban Kuno Mesopotamia", "5. Peradaban Kuno Lembah Sungai Indus dan Tiongkok",
                        "6. Peradaban Kuno Yunani dan Romawi", "7. Peradaban Kuno Amerika (Inca, Maya, Aztec)", "8. Abad Kegelapan (Dark Ages) di Eropa", "9. Renaisans dan Humanisme", "10. Merkantilisme dan Kapitalisme Awal",
                        "11. Gerakan Reformasi Gereja", "12. Abad Pencerahan (Aufklärung)", "13. Revolusi Industri di Inggris", "14. Revolusi Amerika", "15. Revolusi Prancis", "16. Revolusi Rusia", "17. Revolusi Tiongkok",
                        "18. Perkembangan Paham-Paham Besar", "19. Kebangkitan Nasionalisme Asia-Afrika", "20. Perang Dunia I: Latar Belakang dan Jalannya Perang", "21. Dampak Perang Dunia I dan Liga Bangsa-Bangsa",
                        "22. Perang Dunia II: Latar Belakang dan Negara Terlibat", "23. Dampak Perang Dunia II dan PBB", "24. Perang Dingin dan Perebutan Hegemoni Global", "25. Sejarah Kontemporer: Runtuhnya Uni Soviet dan Yugoslavia",
                        "26. Sejarah Konflik Timur Tengah Terpilih", "27. Sejarah Perkembangan HAM secara Global", "28. Sejarah Krisis Ekonomi Global Berpengaruh Besar"
                    ],
                    quiz: { question: "Revolusi industri pertama kali terjadi di negara...", options: ["A. Prancis", "B. Amerika Serikat", "C. Inggris", "D. Rusia"], correct: "C. Inggris", explain: "Dimulai dari industri tekstil dengan ditemukannya mesin uap oleh James Watt di Inggris." }
                }
            ],

            // ================= KELAS BAHASA & BUDAYA =================
            bahasa: [
                {
                    id: "sas_ind", name: "Sastra Indonesia", tutor: "Pakar Sastra", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Genre Sastra, Analisis Puisi & Prosa, Sejarah Angkatan Sastra Indonesia, Kritik Sastra, Esai, dan Ekranisasi.",
                    trick: "💡 <strong>Trik Membedakan Angkatan:</strong> Balai Pustaka (adat/Siti Nurbaya). Pujangga Baru (nasionalisme). Angkatan 45 (realistis/Chairil Anwar).",
                    bab: [
                        "1. Konsep Dasar Kesastraan dan Genre Sastra", "2. Unsur Intrinsik dan Ekstrinsik Prosa Fiksi", "3. Menganalisis Cerpen Berdasarkan Aliran Sastra", "4. Unsur-Unsur Pembangun Puisi (Fisik dan Batin)",
                        "5. Jenis-Jenis Puisi Lama (Pantun, Gurindam, Syair)", "6. Karakteristik Puisi Baru dan Kontemporer", "7. Diksi, Majas, dan Citraan dalam Puisi", "8. Struktur dan Unsur Pementasan Drama", "9. Menulis dan Menyadur Naskah Drama",
                        "10. Sejarah Sastra Indonesia: Angkatan Balai Pustaka", "11. Sejarah Sastra Indonesia: Pujangga Baru", "12. Sejarah Sastra Indonesia: Angkatan 45 dan 66", "13. Sejarah Sastra Indonesia: Era 80-an hingga Reformasi",
                        "14. Aliran Sastra Realisme, Romantisme, dan Surealisme", "15. Hakikat Kritik Sastra", "16. Jenis dan Pendekatan dalam Kritik Sastra", "17. Menulis Kritik Sastra terhadap Karya Fenomenal", "18. Hakikat dan Sistematika Esai Sastra",
                        "19. Menganalisis Nilai Sosial dan Budaya dalam Novel", "20. Menganalisis Novel Terjemahan (Sastra Dunia)", "21. Musikalisasi Puisi dan Teknik Deklamasi", "22. Menulis Cerpen Berdasarkan Pengalaman Empiris",
                        "23. Ekranisasi: Transformasi Novel Menjadi Film", "24. Pengantar Sastra Siber (Cyber Literature)", "25. Penerbitan dan Industri Sastra di Indonesia"
                    ],
                    quiz: { question: "Proses pengubahan atau transformasi novel menjadi sebuah film layar lebar disebut...", options: ["A. Akulturasi", "B. Adopsi", "C. Ekranisasi", "D. Plagiasi"], correct: "C. Ekranisasi", explain: "Ekranisasi adalah pelayarputihan atau pemindahan bentuk sastra (novel) ke dalam medium film." }
                },
                {
                    id: "sas_ing", name: "Sastra Inggris", tutor: "English Native", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "English Poetry, Drama (Shakespeare), Novels, History of English Literature (Renaissance to Victorian), Literary Criticism.",
                    trick: "💡 <strong>Trik Analisis Karakter:</strong> Protagonist (Karakter utama), Antagonist (Lawan), Foil (Karakter yang menonjolkan sifat karakter utama lewat kontras).",
                    bab: [
                        "1. Introduction to English Literature and Genres", "2. Elements of Poetry (Stanza, Rhyme, Meter)", "3. Figurative Language in English Poetry", "4. Analyzing Classical English Poems", "5. Elements of a Short Story",
                        "6. Analyzing English Short Stories", "7. Elements of a Novel", "8. Reading and Analyzing Modern English Novels", "9. Elements of Drama and Theater", "10. Introduction to Shakespearean Plays",
                        "11. History of English Literature: The Renaissance Era", "12. The Victorian Era in English Literature", "13. American Literature Overview", "14. Literary Devices: Foreshadowing, Flashback, Irony", "15. Point of View in English Fiction",
                        "16. English Proverbs and Idioms in Literature", "17. Moral Values and Characterization", "18. Analyzing English Song Lyrics as Poetry", "19. Writing a Book Review", "20. Writing a Film Review",
                        "21. Basic Literary Criticism (Feminism, Marxism, Psychoanalysis)", "22. Creative Writing: Crafting an English Poem", "23. Creative Writing: Developing a Short Narrative", "24. Performing an English Monologue", "25. Translation and Adaptation in Literature"
                    ],
                    quiz: { question: "Which literary device involves giving human characteristics to non-human things?", options: ["A. Simile", "B. Metaphor", "C. Personification", "D. Hyperbole"], correct: "C. Personification", explain: "Example: The wind whispered through the trees." }
                },
                {
                    id: "jepang", name: "Bahasa Jepang", tutor: "Sensei Jepang", video: "https://www.youtube.com/embed/ScMzIvxBSi4?rel=0&modestbranding=1",
                    summary: "Hiragana, Katakana, Kanji Dasar, Tata Bahasa Jepang (Bunpou), Kosa Kata (Kotoba), dan Percakapan Sehari-hari (Kaiwa).",
                    trick: "💡 <strong>Trik Hiragana vs Katakana:</strong> Hiragana (garis melengkung, untuk kata asli Jepang). Katakana (garis kaku/lurus, untuk kata serapan asing).",
                    bab: [
                        "1. Pengenalan Huruf Hiragana", "2. Pengenalan Huruf Katakana dan Aturan Penulisan", "3. Aisatsu (Salam Pertemuan dan Perpisahan)", "4. Jikoshoukai (Memperkenalkan Diri Sendiri)", "5. Kazoku (Anggota Keluarga dan Sebutannya)",
                        "6. Angka, Tanggal, Hari, dan Bulan", "7. Jikan (Menyatakan Waktu dan Jam)", "8. Kata Tunjuk Benda (Kore, Sore, Are)", "9. Kata Tunjuk Tempat (Koko, Soko, Asoko)", "10. Keikatsudou (Aktivitas Sehari-hari)",
                        "11. Penggolongan Kata Kerja (Grup I, II, dan III)", "12. Bentuk Kata Kerja Sopan (~masu, ~masen)", "13. Bentuk Kata Kerja Lampau (~mashita, ~masen deshita)", "14. Partikel Dasar (Wa, Ga, O, Ni, De, To, Mo, Ka)",
                        "15. Gakkou (Kehidupan Sekolah dan Mata Pelajaran)", "16. Kata Sifat Akhiran ~i (I-Keiyoushi)", "17. Kata Sifat Akhiran ~na (Na-Keiyoushi)", "18. Basho to Ichi (Letak dan Posisi Benda)", "19. Shumi (Hobi dan Kegemaran)",
                        "20. Ryokou (Pariwisata dan Transportasi)", "21. Tabemono to Nomimono (Makanan, Minuman)", "22. Belanja dan Menanyakan Harga Benda", "23. Menyatakan Keinginan (~tai dan Hoshii)", "24. Mengajak Seseorang (~mashou dan ~masen ka)",
                        "25. Bentuk Perintah Sopan (~te kudasai)", "26. Menyatakan Izin dan Larangan (~te mo ii desu / ~te wa ikemasen)", "27. Bentuk Kamus (Jishokei) dan Kemampuan (Dekimasu)", "28. Bentuk Nai (Bentuk Negatif Pendek)",
                        "29. Pengenalan Kanji Dasar (Level N5 - Bagian 1)", "30. Pengenalan Kanji Dasar (Level N5 - Bagian 2)"
                    ],
                    quiz: { question: "Apa arti dari 'Arigatou Gozaimasu'?", options: ["A. Selamat Pagi", "B. Terima Kasih", "C. Permisi", "D. Sampai Jumpa"], correct: "B. Terima Kasih", explain: "Arigatou Gozaimasu adalah ucapan terima kasih formal dalam Bahasa Jepang." }
                },
                {
                    id: "antro", name: "Antropologi", tutor: "Tim Antropologi", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Etnografi, Wujud Kebudayaan, Religi, Sistem Kekerabatan, Masyarakat Multikultural, dan Dinamika Budaya.",
                    trick: "💡 <strong>Wujud Kebudayaan (J.J. Honigmann):</strong> 1) Ide (Gagasan/Nilai), 2) Aktivitas (Tindakan/Pola interaksi), 3) Artefak (Karya fisik).",
                    bab: [
                        "1. Konsep Dasar Antropologi (Fisik dan Budaya)", "2. Sejarah Perkembangan Antropologi sebagai Ilmu", "3. Etnografi: Metode Penelitian Lapangan", "4. Menyusun Deskripsi Etnografi Nusantara", "5. Wujud Kebudayaan (Ide, Aktivitas, Artefak)",
                        "6. Tujuh Unsur Kebudayaan Universal", "7. Peran Bahasa dalam Berkebudayaan", "8. Tradisi Lisan dan Cerita Rakyat Nusantara", "9. Sistem Pengetahuan Tradisional Masyarakat Lokal", "10. Organisasi Sosial dan Sistem Kekerabatan",
                        "11. Peralatan Hidup dan Teknologi Tradisional", "12. Sistem Mata Pencaharian Hidup Berbasis Budaya", "13. Sistem Religi dan Kepercayaan Lokal di Indonesia", "14. Dinamika Seni dan Kesenian Tradisional", "15. Proses Belajar Kebudayaan (Sosialisasi, Enkulturasi)",
                        "16. Dinamika Masyarakat: Asimilasi dan Akulturasi", "17. Difusi Budaya dan Inovasi", "18. Pembentukan Identitas Budaya Lokal dan Nasional", "19. Masyarakat Multikultural dan Kesetaraan Budaya", "20. Etnosentrisme, Primordialisme, dan Relativisme Budaya",
                        "21. Dampak Globalisasi terhadap Budaya Lokal", "22. Pergeseran Nilai Budaya di Era Digital", "23. Upaya Pelestarian dan Pewarisan Budaya", "24. Peran Museum dan Cagar Budaya dalam Edukasi", "25. Kebijakan Kebudayaan Nasional di Indonesia"
                    ],
                    quiz: { question: "Proses penyerapan budaya luar tanpa menghilangkan identitas budaya aslinya disebut...", options: ["A. Asimilasi", "B. Akulturasi", "C. Enkulturasi", "D. Amalgamasi"], correct: "B. Akulturasi", explain: "Akulturasi memadukan kebudayaan tanpa menghilangkan identitas kebudayaan asli." }
                }
            ],

            // ================= UTBK SNBT & TKA =================
            utbk: [
                {
                    id: "pk", name: "Pengetahuan Kuantitatif & Penalaran Matematika", tutor: "Tim UTBK", video: "https://www.youtube.com/embed/FqYIq9kdshM?rel=0&modestbranding=1",
                    summary: "Kombinasi materi Penalaran Matematika berbasis konteks literasi dan Pengetahuan Kuantitatif aljabar, teori bilangan, serta kecukupan data.",
                    trick: "💡 <strong>Trik Hubungan P dan Q:</strong> Jika tidak menemukan rumus pasti, coba masukkan 3 angka sakti: 0, 1, dan bilangan negatif. Jika hasil berubah-ubah, jawab 'Hubungan tidak dapat ditentukan'.",
                    bab: ["Bab 1: Aljabar Dasar & Persamaan Linear/Kuadrat", "Bab 2: Geometri & Pola Bangun", "Bab 3: Soal Cerita Penalaran Matematika (Kecepatan, Waktu, Jarak)", "Bab 4: Statistika, Peluang & Kombinatorika", "Bab 5: Analisis Kecukupan Data (Pernyataan 1 & 2)"],
                    quiz: { question: "Berapa 25% dari 160?", options: ["A. 20", "B. 30", "C. 40", "D. 50"], correct: "C. 40", explain: "25% sama dengan 1/4. Maka 1/4 * 160 = 40." }
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
            const cat = document.getElementById('categorySelect').value;
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
            alert("Hasil Tryout Anda:\n• Skor IRT: 785 / 1000\n• Prediksi Kelulusan PTN: 94% (Sangat Tinggi)\n\nPembahasan detail telah masuk ke portal belajar!");
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
                            <strong>Gemini AI:</strong> Mengenai topik "${text}", kamu bisa mencari referensi mendalam di tab <strong>Rangkuman Lengkap</strong> pada materi yang sedang kamu pilih di menu kiri.
                        </div>
                    `;
                    body.scrollTop = body.scrollHeight;
                }, 700);
            }
        }

        // Initialize App
        window.onload = () => { loadCategorySubjects(); };
    </script>
</body>
</html>
