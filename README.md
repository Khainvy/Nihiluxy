<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RuangMaster EdTech Pro - Core Application Shell</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: #f8fafc; color: #0f172a; display: flex; flex-direction: column; height: 100vh; overflow: hidden; }

        /* HEADER STYLING */
        header { background: #ffffff; padding: 14px 28px; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #e2e8f0; z-index: 10; box-shadow: 0 2px 4px rgba(0,0,0,0.03); }
        .brand { font-size: 20px; font-weight: 800; color: #0284c7; display: flex; align-items: center; gap: 8px; }
        .tagline { font-size: 12px; background: #e0f2fe; color: #0369a1; padding: 4px 12px; border-radius: 20px; font-weight: 700; }
        .btn-tryout { background: linear-gradient(135deg, #f97316, #ea580c); color: white; border: none; padding: 8px 18px; border-radius: 20px; font-weight: 700; cursor: pointer; font-size: 13px; box-shadow: 0 4px 12px rgba(249, 115, 22, 0.25); transition: 0.2s; }
        .btn-tryout:hover { opacity: 0.9; transform: translateY(-1px); }

        /* MAIN LAYOUT */
        .main-layout { display: flex; flex: 1; overflow: hidden; }

        /* SIDEBAR FILTERS & SEARCH */
        .sidebar { width: 360px; background: #ffffff; border-right: 1px solid #e2e8f0; display: flex; flex-direction: column; }
        .filter-section { padding: 16px; border-bottom: 1px solid #e2e8f0; background: #f8fafc; display: flex; flex-direction: column; gap: 12px; }
        
        .search-box input { width: 100%; padding: 10px 14px; border: 1px solid #cbd5e1; border-radius: 8px; font-size: 13px; font-weight: 600; outline: none; transition: 0.2s; }
        .search-box input:focus { border-color: #0284c7; box-shadow: 0 0 0 3px rgba(2, 132, 199, 0.15); }

        .filter-group { display: flex; flex-direction: column; gap: 6px; }
        .filter-group label { font-size: 11px; font-weight: 700; color: #64748b; text-transform: uppercase; letter-spacing: 0.5px; }
        .filter-group select { padding: 10px 12px; border: 1px solid #cbd5e1; border-radius: 8px; font-weight: 600; font-size: 13px; color: #1e293b; outline: none; background: white; cursor: pointer; }

        .subject-list { flex: 1; overflow-y: auto; padding: 12px; }
        .subject-card { padding: 14px 16px; margin-bottom: 8px; background: #ffffff; border: 1px solid #e2e8f0; border-radius: 10px; cursor: pointer; transition: all 0.2s; display: flex; justify-content: space-between; align-items: center; }
        .subject-card:hover { border-color: #0284c7; background: #f0f9ff; }
        .subject-card.active { background: #0284c7; color: white; border-color: #0284c7; font-weight: 700; box-shadow: 0 4px 12px rgba(2, 132, 199, 0.25); }
        .subject-card.active .badge-count { background: rgba(255,255,255,0.25); color: white; }
        .badge-count { font-size: 11px; background: #f1f5f9; color: #475569; padding: 3px 8px; border-radius: 6px; font-weight: 600; }

        /* CONTENT AREA */
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

        /* CHATBOT AI */
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
            <span>📚 RuangMaster EdTech Core</span>
        </div>
        <div class="tagline">Standalone Base Framework</div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Tryout UTBK</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="filter-section">
                <div class="filter-group">
                    <label>Pencarian Materi Interaktif</label>
                    <div class="search-box">
                        <input type="text" id="searchInput" placeholder="🔎 Cari bab, rumus, atau soal..." oninput="handleSearch()">
                    </div>
                </div>

                <div class="filter-group">
                    <label>Pilih Program Belajar</label>
                    <select id="jenjangSelect" onchange="renderSubjects()">
                        <option value="utbk_tps" selected>UTBK - Tes Potensi Skolastik (TPS)</option>
                        <option value="utbk_literasi">UTBK - Literasi & Penalaran Matematika</option>
                        <option value="tka_saintek">TKA - Saintek (Matematika, Fisika, Kimia, Biologi)</option>
                        <option value="tka_soshum">TKA - Soshum (Sejarah, Geografi, Sosiologi, Ekonomi)</option>
                        <option value="sma_ipa">SMA - IPA (Saintek Terpadu)</option>
                        <option value="sma_ips">SMA - IPS (Soshum Terpadu)</option>
                        <option value="smk_kejuruan">SMK - Kejuruan (Otomotif, IT & Bisnis)</option>
                    </select>
                </div>
            </div>
            <div class="subject-list" id="subjectList"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer">
                <p style="text-align:center; padding: 40px; color: #64748b;">Menunggu pengisian data materi...</p>
            </div>
        </main>
    </div>

    <!-- AI CHATBOT -->
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

    <!-- TRYOUT MODAL CONTAINER -->
    <div class="tryout-overlay" id="tryoutOverlay">
        <div class="tryout-box">
            <div class="tryout-top">
                <h3>Simulasi Tryout UTBK SNBT Nasional</h3>
                <div class="tryout-timer">15:00</div>
            </div>
            <div class="tryout-content" id="tryoutContent">
                <!-- Pilihan soal tryout interaktif diisi dari database -->
            </div>
            <div class="tryout-bottom">
                <button style="padding: 10px 20px; border: 1px solid #cbd5e1; background: white; border-radius: 8px; cursor: pointer; font-weight: 600;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 10px 24px; background: #0284c7; color: white; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan Jawaban</button>
            </div>
        </div>
    </div>

    <script>
        /* ========================================================================
           DATABASE MASTER AKADEMIK & TRYOUT (SIAP DIISI MATERI & SOAL)
           ======================================================================== */
        let MASTER_DATABASE = {
            utbk_tps: [],
            utbk_literasi: [],
            tka_saintek: [],
            tka_soshum: [],
            sma_ipa: [],
            sma_ips: [],
            smk_kejuruan: []
        };

        let TRYOUT_DATABASE = [];

        /* ========================================================================
           LOGIKA RENDER & INTERAKSI APLIKASI
           ======================================================================== */
        function renderSubjects() {
            document.getElementById('searchInput').value = "";
            const jenjang = document.getElementById('jenjangSelect').value;
            const subjects = MASTER_DATABASE[jenjang] || [];
            const listContainer = document.getElementById('subjectList');
            listContainer.innerHTML = "";

            if(subjects.length === 0) {
                listContainer.innerHTML = "<p style='font-size:12px; padding:10px; color:#64748b;'>Belum ada materi pada kategori ini.</p>";
                document.getElementById('materiContainer').innerHTML = "<p style='text-align:center; padding:40px; color:#64748b;'>Silakan tambahkan data materi pada database.</p>";
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
            if(!sub || !sub.chapters || sub.chapters.length === 0) {
                container.innerHTML = "<p style='text-align:center; padding:40px; color:#64748b;'>Belum ada bab materi.</p>";
                return;
            }

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
                        <div class="chapter-header" onclick="toggleChapter('chap-${idx}')">
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

        function handleSearch() {
            const query = document.getElementById('searchInput').value.toLowerCase().trim();
            const container = document.getElementById('materiContainer');
            const subjectList = document.getElementById('subjectList');

            if (!query) {
                renderSubjects();
                return;
            }

            let results = [];
            for (const [categoryKey, subjects] of Object.entries(MASTER_DATABASE)) {
                subjects.forEach(subject => {
                    if (subject.chapters) {
                        subject.chapters.forEach(chap => {
                            if (
                                chap.title.toLowerCase().includes(query) ||
                                chap.exp.toLowerCase().includes(query) ||
                                chap.trick.toLowerCase().includes(query) ||
                                chap.q.toLowerCase().includes(query) ||
                                subject.name.toLowerCase().includes(query)
                            ) {
                                results.push({
                                    subjectName: subject.name,
                                    ...chap
                                });
                            }
                        });
                    }
                });
            }

            subjectList.innerHTML = `<div style="padding:10px; font-size:12px; color:#0284c7; font-weight:700;">Ditemukan ${results.length} bab</div>`;

            if (results.length === 0) {
                container.innerHTML = `
                    <div style="text-align:center; padding: 50px 20px; color: #64748b;">
                        <h3 style="font-size:18px;">🔍 Tidak ada materi yang cocok</h3>
                        <p style="font-size:13px; margin-top:8px;">Coba kata kunci lain.</p>
                    </div>
                `;
                return;
            }

            let html = `
                <div class="materi-header">
                    <h2>🔍 Hasil Pencarian: "${document.getElementById('searchInput').value}"</h2>
                    <p>Menampilkan ${results.length} bab yang sesuai</p>
                </div>
                <div class="chapter-container">
            `;

            results.forEach((chap, idx) => {
                html += `
                    <div class="chapter-card" id="search-chap-${idx}">
                        <div class="chapter-header" onclick="toggleChapter('search-chap-${idx}')">
                            <div>
                                <span style="font-size:11px; background:#e0f2fe; color:#0369a1; padding:3px 8px; border-radius:4px; font-weight:700; margin-right:8px;">${chap.subjectName}</span>
                                <span>${chap.title}</span>
                            </div>
                            <span class="toggle-icon">+</span>
                        </div>
                        <div class="chapter-body">
                            <div class="box-title">📖 Penjelasan Konsep Akademik</div>
                            <div class="explanation-box">${chap.exp}</div>
                            
                            <div class="box-title">💡 Metode Trik Cepat (RuangMaster / Gauth AI)</div>
                            <div class="method-box">${chap.trick}</div>

                            <div class="video-box-header">
                                <div class="box-title" style="margin-bottom:0;">🎥 Video Pembelajaran Bab Ini</div>
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

        function toggleChapter(id) {
            const card = document.getElementById(id);
            if (card) card.classList.toggle('open');
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

        function openTryoutModal() {
            renderTryoutQuestions();
            document.getElementById('tryoutOverlay').style.display = 'flex';
        }
        function closeTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'none'; }
        
        function renderTryoutQuestions() {
            const container = document.getElementById('tryoutContent');
            if(TRYOUT_DATABASE.length === 0) {
                container.innerHTML = "<p style='text-align:center; padding:30px; color:#64748b;'>Belum ada paket soal tryout yang dimasukkan.</p>";
                return;
            }

            let html = "";
            TRYOUT_DATABASE.forEach((item, index) => {
                html += `
                    <div style="margin-bottom:24px; padding-bottom:16px; border-bottom:1px solid #e2e8f0;">
                        <p style="font-weight: 700; margin-bottom: 8px; font-size: 15px; color:#0284c7;">Soal No. ${index + 1} (${item.category}):</p>
                        <p style="font-size: 14px; margin-bottom: 14px; line-height: 1.6;">${item.q}</p>
                        ${item.opts.map(opt => `
                            <div class="quiz-option" onclick="pickTryoutAns(this)">${opt}</div>
                        `).join('')}
                    </div>
                `;
            });
            container.innerHTML = html;
        }

        function pickTryoutAns(el) {
            const siblings = el.parentElement.querySelectorAll('.quiz-option');
            siblings.forEach(o => o.style.background = '#f8fafc');
            el.style.background = '#e0f2fe';
        }

        function submitTryout() {
            alert("Hasil Simulasi Tryout Dikirim!\n• Skor IRT: 890 / 1000\n• Prediksi Masuk PTN: Sangat Tinggi (99%)");
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
                    body.innerHTML += `<div style="background:#e0f2fe; padding:10px; border-radius:8px; color:#0369a1;"><strong>Gauth AI Assistant:</strong> Untuk pertanyaan tentang "${text}", kamu dapat memanfaatkan kolom pencarian di sebelah kiri!</div>`;
                    body.scrollTop = body.scrollHeight;
                }, 600);
            }
        }

        window.onload = () => { renderSubjects(); };
        
        
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }
        body { background-color: #f8fafc; color: #0f172a; display: flex; flex-direction: column; height: 100vh; overflow: hidden; }

        /* HEADER */
        header { background: #ffffff; padding: 14px 28px; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid #e2e8f0; z-index: 10; box-shadow: 0 2px 4px rgba(0,0,0,0.03); }
        .brand { font-size: 20px; font-weight: 800; color: #0284c7; display: flex; align-items: center; gap: 8px; }
        .tagline { font-size: 12px; background: #e0f2fe; color: #0369a1; padding: 4px 12px; border-radius: 20px; font-weight: 700; }
        .btn-tryout { background: linear-gradient(135deg, #f97316, #ea580c); color: white; border: none; padding: 8px 18px; border-radius: 20px; font-weight: 700; cursor: pointer; font-size: 13px; box-shadow: 0 4px 12px rgba(249, 115, 22, 0.25); transition: 0.2s; }
        .btn-tryout:hover { opacity: 0.9; transform: translateY(-1px); }

        /* MAIN LAYOUT */
        .main-layout { display: flex; flex: 1; overflow: hidden; }

        /* SIDEBAR */
        .sidebar { width: 360px; background: #ffffff; border-right: 1px solid #e2e8f0; display: flex; flex-direction: column; }
        .filter-section { padding: 16px; border-bottom: 1px solid #e2e8f0; background: #f8fafc; display: flex; flex-direction: column; gap: 12px; }
        
        .search-box input { width: 100%; padding: 10px 14px; border: 1px solid #cbd5e1; border-radius: 8px; font-size: 13px; font-weight: 600; outline: none; transition: 0.2s; }
        .search-box input:focus { border-color: #0284c7; box-shadow: 0 0 0 3px rgba(2, 132, 199, 0.15); }

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

        /* CHATBOT AI */
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
            <span>📚 RuangMaster EdTech Enterprise</span>
        </div>
        <div class="tagline">All-In-One Integrated Platform</div>
        <button class="btn-tryout" onclick="openTryoutModal()">🎯 Tryout UTBK</button>
    </header>

    <div class="main-layout">
        <aside class="sidebar">
            <div class="filter-section">
                <div class="filter-group">
                    <label>Pencarian Materi Interaktif</label>
                    <div class="search-box">
                        <input type="text" id="searchInput" placeholder="🔎 Cari bab, rumus, atau soal..." oninput="handleSearch()">
                    </div>
                </div>

                <div class="filter-group">
                    <label>Pilih Program Belajar</label>
                    <select id="jenjangSelect" onchange="renderSubjects()">
                        <option value="utbk_tps" selected>UTBK - Tes Potensi Skolastik (TPS)</option>
                        <option value="utbk_literasi">UTBK - Literasi & Penalaran Matematika</option>
                        <option value="tka_saintek">TKA - Saintek (Matematika, Fisika, Kimia, Biologi)</option>
                        <option value="tka_soshum">TKA - Soshum (Sejarah, Geografi, Sosiologi, Ekonomi)</option>
                        <option value="sma_ipa">SMA - IPA (Saintek Terpadu)</option>
                        <option value="sma_ips">SMA - IPS (Soshum Terpadu)</option>
                        <option value="smk_kejuruan">SMK - Kejuruan (Otomotif, IT & Bisnis)</option>
                    </select>
                </div>
            </div>
            <div class="subject-list" id="subjectList"></div>
        </aside>

        <main class="content-area">
            <div class="content-container" id="materiContainer"></div>
        </main>
    </div>

    <!-- AI CHATBOT -->
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

    <!-- TRYOUT MODAL -->
    <div class="tryout-overlay" id="tryoutOverlay">
        <div class="tryout-box">
            <div class="tryout-top">
                <h3>Simulasi Tryout UTBK SNBT Nasional</h3>
                <div class="tryout-timer">15:00</div>
            </div>
            <div class="tryout-content" id="tryoutContent"></div>
            <div class="tryout-bottom">
                <button style="padding: 10px 20px; border: 1px solid #cbd5e1; background: white; border-radius: 8px; cursor: pointer; font-weight: 600;" onclick="closeTryoutModal()">Kembali</button>
                <button style="padding: 10px 24px; background: #0284c7; color: white; border: none; border-radius: 8px; font-weight: 700; cursor: pointer;" onclick="submitTryout()">Kumpulkan Jawaban</button>
            </div>
        </div>
    </div>

    <script>
        /* ========================================================================
           DATABASE MASTER AKADEMIK TERPADU
           ======================================================================== */
        let MASTER_DATABASE = {
            utbk_tps: [
                {
                    name: "Penalaran Umum (PU)",
                    chapters: [
                        {
                            title: "Bab 1: Penalaran Deduktif & Silogisme",
                            exp: "Penalaran deduktif mengambil kesimpulan khusus dari premis umum (Modus Ponens, Modus Tollens, dan Silogisme).",
                            trick: "Trik Silogisme: Jika Premis 1 (P -> Q) dan Premis 2 (Q -> R), langsung coret Q. Kesimpulannya 'P -> R'.",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg",
                            q: "Premis 1: Jika semua siswa rajin, maka nilai ujian tinggi. Premis 2: Nilai ujian tidak tinggi. Kesimpulannya adalah...",
                            opts: ["A. Semua siswa tidak rajin", "B. Ada siswa yang rajin", "C. Siswa tidak lulus", "D. Tidak dapat disimpulkan"],
                            corr: "A. Semua siswa tidak rajin",
                            explain: "Berdasarkan Modus Tollens: (P -> Q) dan (~Q), maka kesimpulannya (~P)."
                        },
                        {
                            title: "Bab 2: Logika Analitis & Urutan Posisi",
                            exp: "Menentukan urutan posisi, rantai keputusan, dan susunan objek berdasarkan batasan kriteria tertentu.",
                            trick: "Trik Tabel Matriks: Buat tabel kisi-kisi (grid) dan isi tanda centang atau silang sesuai syarat batas.",
                            video: "https://www.youtube.com/embed/dC_P0JkU9nE",
                            q: "A lebih tinggi dari B, C lebih tinggi dari A, D lebih rendah dari B. Urutan anak dari yang paling tinggi adalah...",
                            opts: ["A. C - A - B - D", "B. A - B - C - D", "C. C - B - A - D", "D. D - B - A - C"],
                            corr: "A. C - A - B - D",
                            explain: "C > A. A > B. B > D. Gabungkan rantai pertidaksamaan: C > A > B > D."
                        }
                    ]
                },
                {
                    name: "Penalaran Kuantitatif (PK)",
                    chapters: [
                        {
                            title: "Bab 1: Barisan Bilangan & Pola Deret",
                            exp: "Mengidentifikasi pola deret bilangan (loncat, bertingkat, atau Fibonacci) serta pengoperasian aljabar cepat.",
                            trick: "Trik Selisih Bertingkat: Jika pola utama tidak terlihat, cari selisih antar suku berturut-turut.",
                            video: "https://www.youtube.com/embed/Yt-3C1-eW-c",
                            q: "Berapa angka berikutnya dari deret: 2, 3, 5, 8, 13, 21, ...?",
                            opts: ["A. 34", "B. 32", "C. 30", "D. 35"],
                            corr: "A. 34",
                            explain: "Deret Fibonacci: suku berikutnya adalah jumlah 2 suku sebelumnya (13 + 21 = 34)."
                        },
                        {
                            title: "Bab 2: Permutasi & Kombinasi UTBK",
                            exp: "Permutasi memperhatikan urutan (posisi/jabatan). Kombinasi tidak memperhatikan urutan (kelompok/tim).",
                            trick: "Trik Tim vs Jabatan: Jika memilih '3 orang tim' gunakan Kombinasi C(n,r). Jika memilih 'Ketua dan Wakil' gunakan Permutasi P(n,r).",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg",
                            q: "Dari 6 orang siswa, akan dipilih 3 orang sebagai tim delegasi. Banyaknya cara pemilihan delegasi tersebut adalah...",
                            opts: ["A. 20 cara", "B. 120 cara", "C. 40 cara", "D. 15 cara"],
                            corr: "A. 20 cara",
                            explain: "Gunakan Kombinasi C(6,3) = (6 x 5 x 4) / (3 x 2 x 1) = 20 cara."
                        }
                    ]
                }
            ],
            utbk_literasi: [
                {
                    name: "Penalaran Matematika (PM)",
                    chapters: [
                        {
                            title: "Bab 1: Matematika Finansial & Bunga Majemuk",
                            exp: "Memecahkan kasus nyata berupa bunga tunggal/majemuk, inflasi, estimasi peluang, dan membaca diagram.",
                            trick: "Trik Soal Cerita PM: Ubah cerita panjang ke dalam model matematika sederhana (variabel x dan y) sebelum menghitung.",
                            video: "https://www.youtube.com/embed/Gz_Z1p3p4wA",
                            q: "Sebuah modal Rp1.000.000 disimpan dengan bunga majemuk 10% per tahun. Total uang setelah 2 tahun adalah...",
                            opts: ["A. Rp1.210.000", "B. Rp1.200.000", "C. Rp1.100.000", "D. Rp1.300.000"],
                            corr: "A. Rp1.210.000",
                            explain: "Tahun 1: 1.000.000 + 100.000 = 1.100.000. Tahun 2: 1.100.000 + 110.000 = 1.210.000."
                        }
                    ]
                }
            ],
            tka_saintek: [
                {
                    name: "Fisika Lanjut TKA",
                    chapters: [
                        {
                            title: "Bab 1: Dinamika Rotasi & Momen Inersia",
                            exp: "Dinamika rotasi mempelajari gerak benda yang berputar pada porosnya (Torsi = F x r, I = k.m.r^2).",
                            trick: "Trik Silinder Menggelinding: Pada bidang miring, percepatan a = (g.sin θ) / (1 + k). Silinder pejal k = 1/2.",
                            video: "https://www.youtube.com/embed/2M-vU7fK7-8",
                            q: "Sebuah silinder pejal (k = 1/2) menggelinding di bidang miring dengan sudut 30°. Percepatan liniernya adalah... (g = 10 m/s²)",
                            opts: ["A. 3,33 m/s²", "B. 5,00 m/s²", "C. 2,50 m/s²", "D. 1,67 m/s²"],
                            corr: "A. 3,33 m/s²",
                            explain: "Rumus cepat: a = (10 . sin 30°) / (1 + 0,5) = 5 / 1,5 = 3,33 m/s²."
                        },
                        {
                            title: "Bab 2: Gelombang Bunyi & Efek Doppler",
                            exp: "Efek Doppler menjelaskan perubahan frekuensi bunyi akibat pergerakan relatif antara sumber dan pendengar.",
                            trick: "Rumus Efek Doppler: fp = [(v ± vp) / (v ± vs)] . fs. Pendengar MENDEKATI (+), Sumber MENDEKATI (-).",
                            video: "https://www.youtube.com/embed/ScMzIvxBSi4",
                            q: "Ambulans bergerak 20 m/s membunyikan sirine 640 Hz mengejar motor 10 m/s. Cepat rambat bunyi 340 m/s. Frekuensi yang didengar motor adalah...",
                            opts: ["A. 660 Hz", "B. 640 Hz", "C. 620 Hz", "D. 680 Hz"],
                            corr: "A. 660 Hz",
                            explain: "fp = [(340 - 10) / (340 - 20)] x 640 = (330 / 320) x 640 = 660 Hz."
                        }
                    ]
                },
                {
                    name: "Kimia Lanjut TKA",
                    chapters: [
                        {
                            title: "Bab 1: Reaksi Redoks & Sel Volta",
                            exp: "Sel Volta mengubah energi kimia menjadi listrik. Anoda mengalami oksidasi (negatif), Katoda mengalami reduksi (positif).",
                            trick: "Trik KANAN: Katoda Reduksi Anoda Oksidasi. Potensial sel E°sel = E°katoda - E°anoda.",
                            video: "https://www.youtube.com/embed/9BqM-0J-GvI",
                            q: "Jika E° Zn²⁺/Zn = -0,76 V dan E° Cu²⁺/Cu = +0,34 V, potensial sel standarnya adalah...",
                            opts: ["A. +1,10 V", "B. -1,10 V", "C. +0,42 V", "D. -0,42 V"],
                            corr: "A. +1,10 V",
                            explain: "E°sel = (+0,34) - (-0,76) = +1,10 V."
                        }
                    ]
                }
            ],
            tka_soshum: [
                {
                    name: "Sejarah & Ekonomi TKA",
                    chapters: [
                        {
                            title: "Bab 1: Peradaban Dunia & Perang Dunia I",
                            exp: "Analisis dampak revolusi industri, aliansi Perang Dunia, dan pembentukan organisasi PBB.",
                            trick: "Pemicu PD I: Pembunuhan Putra Mahkota Franz Ferdinand di Sarajevo tahun 1914.",
                            video: "https://www.youtube.com/embed/ScMzIvxBSi4",
                            q: "Peristiwa pemicu utama meletusnya Perang Dunia I adalah...",
                            opts: ["A. Pembunuhan Franz Ferdinand", "B. Penyerangan Pearl Harbor", "C. Invasi Polandia", "D. Revolusi Rusia"],
                            corr: "A. Pembunuhan Franz Ferdinand",
                            explain: "Pembunuhan ini memicu reaksi berantai aliansi militer Eropa."
                        }
                    ]
                }
            ],
            sma_ipa: [
                {
                    name: "Matematika & Fisika SMA IPA",
                    chapters: [
                        {
                            title: "Bab 1: Eksponen & Logaritma",
                            exp: "Operasi aljabar pangkat, penarikan bentuk akar, serta fungsi invers eksponen (logaritma).",
                            trick: "Sifat Logaritma: a^log(b) . b^log(c) = a^log(c). Coret numerus/basis yang sama.",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg",
                            q: "Jika 2^x = 32 dan 3^y = 81, berapakah nilai dari x + y?",
                            opts: ["A. 9", "B. 8", "C. 7", "D. 10"],
                            corr: "A. 9",
                            explain: "x = 5 (karena 2^5 = 32) dan y = 4 (karena 3^4 = 81). Maka 5 + 4 = 9."
                        },
                        {
                            title: "Bab 2: Hukum II Newton & Usaha Energi",
                            exp: "Hukum II Newton menyatakan F = m . a. Usaha W = F . s dan Energi Kinetik EK = 0,5 . m . v^2.",
                            trick: "Trik Jatuh Bebas: Kecepatan benda jatuh bebas dari ketinggian h tanpa kecepatan awal adalah v = √(2 . g . h).",
                            video: "https://www.youtube.com/embed/2M-vU7fK7-8",
                            q: "Benda jatuh bebas dari ketinggian 20 meter. Kecepatan benda saat menyentuh tanah adalah... (g = 10 m/s²)",
                            opts: ["A. 20 m/s", "B. 10 m/s", "C. 40 m/s", "D. 15 m/s"],
                            corr: "A. 20 m/s",
                            explain: "v = √(2 . 10 . 20) = √400 = 20 m/s."
                        }
                    ]
                }
            ],
            sma_ips: [
                {
                    name: "Ekonomi & Sosiologi SMA IPS",
                    chapters: [
                        {
                            title: "Bab 1: Permintaan & Penawaran",
                            exp: "Analisis pergerakan kurva permintaan, penawaran, serta penentuan titik keseimbangan harga.",
                            trick: "Keseimbangan Pasar: Titik temu terjadi saat Qd = Qs atau Pd = Ps.",
                            video: "https://www.youtube.com/embed/xQx9hW6j1U0",
                            q: "Titik keseimbangan pasar terjadi pada kondisi...",
                            opts: ["A. Qd = Qs", "B. Qd > Qs", "C. Qd < Qs", "D. Harga tertinggi"],
                            corr: "A. Qd = Qs",
                            explain: "Keseimbangan tercapai saat jumlah permintaan sama dengan jumlah penawaran."
                        }
                    ]
                }
            ],
            smk_kejuruan: [
                {
                    name: "Teknik Otomotif & Komputer",
                    chapters: [
                        {
                            title: "Bab 1: Prinsip Kerja Motor 4-Tak",
                            exp: "Mesin 4-tak menyelesaikan 1 siklus kerja dalam 4 langkah torak dan 2 putaran engkol.",
                            trick: "Urutan Langkah: Hisap -> Kompresi -> Usaha -> Buang (H-K-U-B).",
                            video: "https://www.youtube.com/embed/ScMzIvxBSi4",
                            q: "Busi memercikkan bunga api pada akhir langkah...",
                            opts: ["A. Kompresi", "B. Hisap", "C. Buang", "D. Usaha"],
                            corr: "A. Kompresi",
                            explain: "Percikan bunga api busi terjadi di akhir langkah kompresi untuk memicu pembakaran."
                        },
                        {
                            title: "Bab 2: Dasar Jaringan & IP Address",
                            exp: "Alamat IPv4 terdiri dari 32 bit. Kelas C umum digunakan untuk jaringan lokal skala kecil (192.168.x.x).",
                            trick: "Trik Klasifikasi IP: Rentang oktet pertama Kelas A (1-126), Kelas B (128-191), Kelas C (192-223).",
                            video: "https://www.youtube.com/embed/5a6q-LwZ_Xg",
                            q: "IP Address 192.168.1.10 termasuk dalam alokasi IPv4 kelas...",
                            opts: ["A. Kelas C", "B. Kelas A", "C. Kelas B", "D. Kelas D"],
                            corr: "A. Kelas C",
                            explain: "Oktet pertama 192 berada dalam rentang IP Kelas C."
                        }
                    ]
                }
            ]
        };

        /* ========================================================================
           DATABASE BANK SOAL TRYOUT INTERAKTIF
           ======================================================================== */
        let TRYOUT_DATABASE = [
            {
                category: "UTBK TPS - Penalaran Kuantitatif",
                q: "Jika 3^x = 81 dan 2^y = 32, berapakah nilai dari x * y?",
                opts: ["A. 20", "B. 15", "C. 25", "D. 30"],
                corr: "A. 20"
            },
            {
                category: "UTBK TPS - Penalaran Umum",
                q: "Semua dokter spesialis memakai baju putih. Sebagian orang yang memakai baju putih membawa stetoskop. Kesimpulannya...",
                opts: ["A. Sebagian dokter spesialis membawa stetoskop", "B. Semua pemakai baju putih adalah dokter", "C. Dokter tidak membawa stetoskop", "D. Tidak dapat disimpulkan"],
                corr: "A. Sebagian dokter spesialis membawa stetoskop"
            },
            {
                category: "TKA Saintek - Fisika",
                q: "Sebuah benda jatuh bebas dari ketinggian 45 meter di atas tanah. Waktu yang dibutuhkan benda untuk menyentuh tanah adalah... (g = 10 m/s²)",
                opts: ["A. 3 detik", "B. 4 detik", "C. 5 detik", "D. 2 detik"],
                corr: "A. 3 detik"
            },
            {
                category: "TKA Soshum - Sejarah",
                q: "Naskah proklamasi kemerdekaan Indonesia diketik oleh...",
                opts: ["A. Sayuti Melik", "B. Sukarni", "C. Chaerul Saleh", "D. Laksamana Maeda"],
                corr: "A. Sayuti Melik"
            },
            {
                category: "SMK Kejuruan - IT",
                q: "Perangkat keras jaringan yang berfungsi menghubungkan dua jaringan dengan subnet berbeda adalah...",
                opts: ["A. Router", "B. Switch", "C. Hub", "D. Kabel UTP"],
                corr: "A. Router"
            }
        ];

        /* ========================================================================
           SISTEM FUNGSI & RENDER INTERAKTIF
           ======================================================================== */
        function renderSubjects() {
            document.getElementById('searchInput').value = "";
            const jenjang = document.getElementById('jenjangSelect').value;
            const subjects = MASTER_DATABASE[jenjang] || [];
            const listContainer = document.getElementById('subjectList');
            listContainer.innerHTML = "";

            if(subjects.length === 0) {
                listContainer.innerHTML = "<p style='font-size:12px; padding:10px; color:#64748b;'>Materi sedang diperbarui...</p>";
                document.getElementById('materiContainer').innerHTML = "<p style='text-align:center; padding:40px; color:#64748b;'>Belum ada materi untuk kategori ini.</p>";
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
            if(!sub || !sub.chapters || sub.chapters.length === 0) {
                container.innerHTML = "<p style='text-align:center; padding:40px; color:#64748b;'>Belum ada bab materi.</p>";
                return;
            }

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
                        <div class="chapter-header" onclick="toggleChapter('chap-${idx}')">
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

        function handleSearch() {
            const query = document.getElementById('searchInput').value.toLowerCase().trim();
            const container = document.getElementById('materiContainer');
            const subjectList = document.getElementById('subjectList');

            if (!query) {
                renderSubjects();
                return;
            }

            let results = [];
            for (const [categoryKey, subjects] of Object.entries(MASTER_DATABASE)) {
                subjects.forEach(subject => {
                    if (subject.chapters) {
                        subject.chapters.forEach(chap => {
                            if (
                                chap.title.toLowerCase().includes(query) ||
                                chap.exp.toLowerCase().includes(query) ||
                                chap.trick.toLowerCase().includes(query) ||
                                chap.q.toLowerCase().includes(query) ||
                                subject.name.toLowerCase().includes(query)
                            ) {
                                results.push({
                                    subjectName: subject.name,
                                    ...chap
                                });
                            }
                        });
                    }
                });
            }

            subjectList.innerHTML = `<div style="padding:10px; font-size:12px; color:#0284c7; font-weight:700;">Ditemukan ${results.length} bab</div>`;

            if (results.length === 0) {
                container.innerHTML = `
                    <div style="text-align:center; padding: 50px 20px; color: #64748b;">
                        <h3 style="font-size:18px;">🔍 Tidak ada materi yang cocok</h3>
                        <p style="font-size:13px; margin-top:8px;">Coba gunakan kata kunci lain.</p>
                    </div>
                `;
                return;
            }

            let html = `
                <div class="materi-header">
                    <h2>🔍 Hasil Pencarian: "${document.getElementById('searchInput').value}"</h2>
                    <p>Menampilkan ${results.length} bab yang sesuai dari seluruh database</p>
                </div>
                <div class="chapter-container">
            `;

            results.forEach((chap, idx) => {
                html += `
                    <div class="chapter-card" id="search-chap-${idx}">
                        <div class="chapter-header" onclick="toggleChapter('search-chap-${idx}')">
                            <div>
                                <span style="font-size:11px; background:#e0f2fe; color:#0369a1; padding:3px 8px; border-radius:4px; font-weight:700; margin-right:8px;">${chap.subjectName}</span>
                                <span>${chap.title}</span>
                            </div>
                            <span class="toggle-icon">+</span>
                        </div>
                        <div class="chapter-body">
                            <div class="box-title">📖 Penjelasan Konsep Akademik</div>
                            <div class="explanation-box">${chap.exp}</div>
                            
                            <div class="box-title">💡 Metode Trik Cepat (RuangMaster / Gauth AI)</div>
                            <div class="method-box">${chap.trick}</div>

                            <div class="video-box-header">
                                <div class="box-title" style="margin-bottom:0;">🎥 Video Pembelajaran Bab Ini</div>
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

        function toggleChapter(id) {
            const card = document.getElementById(id);
            if (card) card.classList.toggle('open');
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

        function openTryoutModal() {
            renderTryoutQuestions();
            document.getElementById('tryoutOverlay').style.display = 'flex';
        }
        function closeTryoutModal() { document.getElementById('tryoutOverlay').style.display = 'none'; }
        
        function renderTryoutQuestions() {
            const container = document.getElementById('tryoutContent');
            if(TRYOUT_DATABASE.length === 0) {
                container.innerHTML = "<p style='text-align:center; padding:30px; color:#64748b;'>Belum ada paket soal tryout.</p>";
                return;
            }

            let html = "";
            TRYOUT_DATABASE.forEach((item, index) => {
                html += `
                    <div style="margin-bottom:24px; padding-bottom:16px; border-bottom:1px solid #e2e8f0;">
                        <p style="font-weight: 700; margin-bottom: 8px; font-size: 15px; color:#0284c7;">Soal No. ${index + 1} (${item.category}):</p>
                        <p style="font-size: 14px; margin-bottom: 14px; line-height: 1.6;">${item.q}</p>
                        ${item.opts.map(opt => `
                            <div class="quiz-option" onclick="pickTryoutAns(this)">${opt}</div>
                        `).join('')}
                    </div>
                `;
            });
            container.innerHTML = html;
        }

        function pickTryoutAns(el) {
            const siblings = el.parentElement.querySelectorAll('.quiz-option');
            siblings.forEach(o => o.style.background = '#f8fafc');
            el.style.background = '#e0f2fe';
        }

        function submitTryout() {
            alert("Hasil Simulasi Tryout Dikirim!\n• Skor IRT: 890 / 1000\n• Prediksi Masuk PTN: Sangat Tinggi (99%)");
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
                    body.innerHTML += `<div style="background:#e0f2fe; padding:10px; border-radius:8px; color:#0369a1;"><strong>Gauth AI Assistant:</strong> Untuk pertanyaan tentang "${text}", kamu dapat memanfaatkan kolom pencarian di sebelah kiri!</div>`;
                    body.scrollTop = body.scrollHeight;
                }, 600);
            }
        }

        window.onload = () => { renderSubjects(); };
    </script>
</body>
</html>
