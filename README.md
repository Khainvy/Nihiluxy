<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RuangMaster EdTech - Portal Belajar SMA & UTBK</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: #f8fafc; color: #0f172a; display: flex; flex-direction: column; height: 100vh; overflow: hidden; }

        /* HEADER */
        header { background: #ffffff; padding: 14px 28px; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #e2e8f0; z-index: 10; box-shadow: 0 2px 4px rgba(0,0,0,0.03); }
        .brand { font-size: 20px; font-weight: 800; color: #0284c7; display: flex; align-items: center; gap: 8px; }
        .tagline { font-size: 12px; background: #e0f2fe; color: #0369a1; padding: 4px 12px; border-radius: 20px; font-weight: 700; }
        .btn-tryout { background: linear-gradient(135deg, #f97316, #ea580c); color: white; border: none; padding: 8px 18px; border-radius: 20px; font-weight: 700; cursor: pointer; font-size: 13px; box-shadow: 0 4px 12px rgba(249, 115, 22, 0.25); transition: 0.2s; }
        .btn-tryout:hover { opacity: 0.9; transform: translateY(-1px); }

        /* LAYOUT */
        .main-layout { display: flex; flex: 1; overflow: hidden; }

        /* SIDEBAR */
        .sidebar { width: 350px; background: #ffffff; border-right: 1px solid #e2e8f0; display: flex; flex-direction: column; }
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

        /* AKORDION BAB */
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

        /* VIDEO PLAYER CONTAINER */
        .video-box-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
        .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 10px; background: #000; margin-bottom: 20px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
        .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; }

        .quiz-box { background: white; border: 1px solid #cbd5e1; padding: 20px; border-radius: 10px; }
        .quiz-question { font-size: 14px; font-weight: 600; margin-bottom: 12px; color: #0f172a; line-height: 1.5; }
        .quiz-option { margin: 8px 0; padding: 12px 14px; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; cursor: pointer; font-size: 13px; transition: 0.2s; font-weight: 500; }
        .quiz-option:hover { background: #f0fdf4; border-color: #16a34a; }
        .quiz-feedback { margin-top: 12px; padding: 12px; border-radius: 6px; font-size: 13px; font-weight: 600; display: none; }

        /* AI CHATBOT & GAUTH AI SOLVER */
        .chat-btn { position: fixed; bottom: 24px; right: 24px; background: #0284c7; color: white; border: none; padding: 12px 22px; border-radius: 30px; font-weight: 700; font-size: 13px; box-shadow: 0 8px 20px rgba(2, 132, 199, 0.35); cursor: pointer; z-index: 100; transition: transform 0.2s; }
        .chat-btn:hover { transform: scale(1.05); }
        .chat-window { display: none; position: fixed; bottom: 85px; right: 24px; width: 350px; height: 450px; background: white; border-radius: 14px; box-shadow: 0 12px 32px rgba(0,0,0,0.15); border: 1px solid #cbd5e1; flex-direction: column; overflow: hidden; z-index: 100; }
        .chat-header { background: #0284c7; color: white; padding: 14px 18px; font-weight: 700; font-size: 14px; display: flex; justify-content: space-between; align-items: center; }
        .chat-body { flex: 1; padding: 14px; overflow-y: auto; font-size: 13px; background: #f8fafc; display: flex; flex-direction: column; gap: 10px; }
        .chat-input { display: flex; padding: 10px; border-top: 1px solid #e2e8f0; background: white; }
        .chat-input input { flex: 1; padding: 8px 12px; border: 1px solid #cbd5e1; border-radius: 6px; outline: none; font-size: 12px; }
        .chat-input button { background: #0284c7; color: white; border: none; padding: 8px 14px; margin-left: 6px; border-radius: 6px; cursor: pointer; font-weight: 700; font-size: 12px; }
    </style>
</head>
<body>

    <header>
        <div class="brand">
            <span>📚 RuangMaster EdTech</span>
        </div>
        <div class="tagline">Kurikulum Terpadu (K13 + Merdeka) & Bank Soal UTBK/TKA</div>
        <button class="btn-tryout" onclick="alert('Simulasi Tryout UTBK SNBT Siap Akses!')">🎯 Tryout UTBK</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="filter-section">
                <div class="filter-group">
                    <label>Pilih Jurusan / Kelompok Program</label>
                    <select id="jenjangSelect" onchange="renderSubjects()">
                        <option value="sma_ipa" selected>SMA - IPA (Saintek Terpadu)</option>
                        <option value="sma_ips">SMA - IPS (Soshum Terpadu)</option>
                        <option value="utbk_snbt">Persiapan UTBK / TKA / SNBT</option>
                    </select>
                </div>
            </div>
            <div class="subject-list" id="subjectList"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer"></div>
        </main>
    </div>

    <!-- AI CHATBOT & GAUTH SOLVER -->
    <button class="chat-btn" onclick="toggleChat()">✨ Tanya AI Tutor (Gauth AI)</button>
    <div class="chat-window" id="chatWindow">
        <div class="chat-header"><span>Gauth AI Smart Assistant</span><span style="cursor:pointer" onclick="toggleChat()">✖</span></div>
        <div class="chat-body" id="chatBody">
            <div style="background:#e0f2fe; padding:10px; border-radius:8px; color:#0369a1;">Halo! Tuliskan soal atau topik matematika/sains yang ingin lu bedah langkah demi langkah!</div>
        </div>
        <div class="chat-input">
            <input type="text" id="chatInput" placeholder="Ketik soal atau materi..." onkeypress="if(event.key==='Enter') sendChat()">
            <button onclick="sendChat()">Kirim</button>
        </div>
    </div>

    <script>
        // BASIS DATA MATERI TERPADU LENGKAP DENGAN SLOT RUANG VIDEO
        const MASTER_DATABASE = {
            sma_ipa: [
                {
                    name: "Matematika IPA Terpadu",
                    chapters: [
                        {
                            title: "Bab 1: Eksponen, Bentuk Akar & Logaritma",
                            exp: "Materi ini menggabungkan konsep pangkat (eksponen), penyederhanaan bentuk akar, serta invers eksponen berupa logaritma sesuai standar K13 dan Kurikulum Merdeka.",
                            trick: "Metode Cepat Logaritma: Gunakan sifat perkalian menyilang a^log(b) * b^log(c) = a^log(c). Coret numerus dan basis yang sama untuk hasil instan.",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Jika 2^x = 32 dan 3^y = 81, berapakah nilai dari x + y?",
                            opts: ["A. 7", "B. 8", "C. 9", "D. 10"],
                            corr: "C. 9",
                            explain: "2^5 = 32 (x = 5) dan 3^4 = 81 (y = 4). Maka x + y = 5 + 4 = 9."
                        },
                        {
                            title: "Bab 2: Persamaan & Fungsi Kuadrat",
                            exp: "Memahami pola grafik parabola, menentukan titik puncak, diskriminan (D = b^2 - 4ac), serta sifat-sifat akar persamaan kuadrat.",
                            trick: "Trik Akar Gauth AI: Jumlah akar x1 + x2 = -b/a dan perkalian akar x1 * x2 = c/a tanpa perlu memfaktorkan bentuk kuadrat.",
                            video: "https://www.youtube.com/embed/Yt-3C1-eW-c", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Jumlah akar-akar dari persamaan kuadrat x^2 - 8x + 12 = 0 adalah...",
                            opts: ["A. 8", "B. -8", "C. 12", "D. -12"],
                            corr: "A. 8",
                            explain: "Berdasarkan rumus x1 + x2 = -b/a -> -(-8)/1 = 8."
                        },
                        {
                            title: "Bab 3: Turunan Fungsi Aljabar (Diferensial)",
                            exp: "Pengukuran laju perubahan sesaat suatu fungsi aljabar menggunakan aturan pangkat dan aturan rantai.",
                            trick: "Aturan Rantai Cepat: f(x) = (ax + b)^n -> f'(x) = n * a * (ax + b)^(n-1). Turunkan bagian luar lalu kalikan dengan turunan dalam.",
                            video: "https://www.youtube.com/embed/Gz_Z1p3p4wA", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Turunan pertama dari f(x) = (2x + 3)^3 adalah...",
                            opts: ["A. 6(2x + 3)^2", "B. 3(2x + 3)^2", "C. 2(2x + 3)^2", "D. 12(2x + 3)^2"],
                            corr: "A. 6(2x + 3)^2",
                            explain: "Turunan luar: 3(2x+3)^2. Kalikan turunan dalam (2) -> 3 * 2 * (2x+3)^2 = 6(2x+3)^2."
                        }
                    ]
                },
                {
                    name: "Fisika Mekanika & Dinamika",
                    chapters: [
                        {
                            title: "Bab 1: Kinematika Gerak Lurus (GLB & GLBB)",
                            exp: "Mempelajari posisi, kecepatan, dan percepatan benda pada lintasan lurus beraturan maupun berubah beraturan secara sistematis.",
                            trick: "Formula Bebas Waktu: Gunakan vt^2 = v0^2 + 2as ketika nilai waktu (t) tidak diberikan dalam soal.",
                            video: "https://www.youtube.com/embed/2M-vU7fK7-8", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Sebuah benda ditarik dengan gaya 30 N di atas lantai licin hingga melaju dengan percepatan 6 m/s^2. Massa benda tersebut adalah...",
                            opts: ["A. 5 kg", "B. 6 kg", "C. 180 kg", "D. 15 kg"],
                            corr: "A. 5 kg",
                            explain: "Gunakan Hukum II Newton: m = F / a = 30 / 6 = 5 kg."
                        }
                    ]
                },
                {
                    name: "Kimia Stoikiometri",
                    chapters: [
                        {
                            title: "Bab 1: Konsep Mol & Perhitungan Kimia",
                            exp: "Penentuan hubungan kuantitatif antara reaktan dan produk dalam reaksi kimia berbasis Hukum Avogadro.",
                            trick: "Jembatan Mol Wajib: Ubah semua variabel (massa gram, volume liter STP, pasokan partikel) ke dalam unit Mol terlebih dahulu.",
                            video: "https://www.youtube.com/embed/9BqM-0J-GvI", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Volume dari 0,5 mol gas O2 pada kondisi standar (STP) adalah...",
                            opts: ["A. 11,2 Liter", "B. 22,4 Liter", "C. 5,6 Liter", "D. 44,8 Liter"],
                            corr: "A. 11,2 Liter",
                            explain: "Volume STP = mol * 22,4 = 0,5 * 22,4 = 11,2 Liter."
                        }
                    ]
                }
            ],
            sma_ips: [
                {
                    name: "Ekonomi & Akuntansi",
                    chapters: [
                        {
                            title: "Bab 1: Permintaan, Penawaran & Keseimbangan Pasar",
                            exp: "Analisis pergerakan kurva permintaan dan penawaran serta penentuan titik keseimbangan harga (equilibrium).",
                            trick: "Trik Keseimbangan: Samakan nilai Qd = Qs atau Pd = Ps secara langsung tanpa mengubah koordinat.",
                            video: "https://www.youtube.com/embed/xQx9hW6j1U0", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Titik keseimbangan pasar terjadi pada saat...",
                            opts: ["A. Qd = Qs", "B. Qd > Qs", "C. Qd < Qs", "D. Harga jual mencapai nilai tertinggi"],
                            corr: "A. Qd = Qs",
                            explain: "Keseimbangan pasar terjadi saat kuantitas permintaan sama dengan kuantitas penawaran."
                        },
                        {
                            title: "Bab 2: Siklus Akuntansi Perusahaan Jasa",
                            exp: "Pencatatan transaksi transaksi keuangan mulai dari Jurnal Umum, Buku Besar, Neraca Saldo, hingga Laporan Keuangan.",
                            trick: "Saldo Normal H-E-L-P: Harta dan Beban (Expense) bertambah di Debit. Utang, Modal, dan Pendapatan bertambah di Kredit.",
                            video: "https://www.youtube.com/embed/z9zX4eW-Zcw", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Akun beban gaji yang bertambah dicatat pada posisi...",
                            opts: ["A. Debit", "B. Kredit", "C. Ikhtisar Laba/Rugi", "D. Penyesuaian"],
                            corr: "A. Debit",
                            explain: "Beban bertambah selalu dicatat di sisi Debit."
                        }
                    ]
                },
                {
                    name: "Sosiologi Akademik",
                    chapters: [
                        {
                            title: "Bab 1: Interaksi Sosial & Struktur Masyarakat",
                            exp: "Kajian hubungan timbal balik antarindividu, antarkelompok, serta pembentukan strata sosial.",
                            trick: "Syarat Interaksi Sosial: Harus memuat Kontak Sosial + Komunikasi. Tanpa salah satunya, interaksi tidak akan terjadi.",
                            video: "https://www.youtube.com/embed/FqYIq9kdshM", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Syarat utama terjadinya interaksi sosial menurut Sosiologi adalah...",
                            opts: ["A. Kontak sosial dan komunikasi", "B. Asimilasi dan akulturasi", "C. Konflik dan konsolidasi", "D. Imitasi dan identifikasi"],
                            corr: "A. Kontak sosial dan komunikasi",
                            explain: "Interaksi sosial mensyaratkan adanya kontak sosial dan komunikasi efektif."
                        }
                    ]
                }
            ],
            utbk_snbt: [
                {
                    name: "Penalaran Kuantitatif & TKA",
                    chapters: [
                        {
                            title: "Bab 1: Penalaran Aritmatika & Pola Bilangan Cepat",
                            exp: "Kumpulan teknik penyelesaian soal pola angka, deret aritmatika/geometri, serta logika kuantitatif ujian masuk PTN.",
                            trick: "Metode Digit Satuan: Perhatikan hanya angka paling akhir dari pilihan jawaban untuk memangkas waktu pengerjaan.",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg", // TEMPAT LINK VIDEO (BISA DIGANTI)
                            q: "Jika 3^x = 81 dan 2^y = 32, berapakah nilai dari x * y?",
                            opts: ["A. 20", "B. 15", "C. 25", "D. 12"],
                            corr: "A. 20",
                            explain: "x = 4 (karena 3^4 = 81) dan y = 5 (karena 2^5 = 32). Nilai x * y = 4 * 5 = 20."
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
                listContainer.innerHTML = "<p style='font-size:12px; padding:10px; color:#64748b;'>Materi sedang ditambahkan...</p>";
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
                    <p>Kurikulum Terpadu & Bank Soal Evaluasi Persiapan Akademik</p>
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
                                <span style="font-size:11px; color:#64748b;">(Ganti tautan src iframe pada kode untuk mengubah video)</span>
                            </div>
                            <div class="video-wrapper">
                                <!-- SLOT UTAMA LINK VIDEO YOUTUBE (GANTI DENGAN LINK EMBED PILIHAN LU) -->
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
                feedback.innerHTML = `❌ <strong>Kurang tepat.</strong> Jawaban benar adalah ${correct}. Pembahasan: ${explain}`;
            }
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
                    body.innerHTML += `<div style="background:#e0f2fe; padding:10px; border-radius:8px; color:#0369a1;"><strong>Gauth AI Assistant:</strong> Untuk soal tentang "${text}", gunakan trik pengerjaan cepat yang tertera di modul bab terkait!</div>`;
                    body.scrollTop = body.scrollHeight;
                }, 600);
            }
        }

        window.onload = () => { renderSubjects(); };
    </script>
</body>
</html>
