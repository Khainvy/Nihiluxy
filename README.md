<!DOCTYPE html>
<html lang="id" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nihiluxxy AI Pro v8.0 - Ultimate Megamodule Engine SMA & UTBK SNBT 2026</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#f5f3ff', 100: '#ede9fe', 200: '#ddd6fe', 300: '#c4b5fd',
                            400: '#a78bfa', 500: '#8b5cf6', 600: '#7c3aed', 700: '#6d28d9',
                            800: '#5b21b6', 900: '#4c1d95', 950: '#2e1065',
                        }
                    },
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                        mono: ['JetBrains Mono', 'monospace'],
                    },
                    animation: {
                        'pulse-glow': 'pulseGlow 2.5s infinite alternate',
                        'float': 'float 4s ease-in-out infinite',
                    },
                    keyframes: {
                        pulseGlow: {
                            '0%': { boxShadow: '0 0 15px rgba(139, 92, 246, 0.25), 0 0 30px rgba(99, 102, 241, 0.15)' },
                            '100%': { boxShadow: '0 0 35px rgba(168, 85, 247, 0.55), 0 0 60px rgba(236, 72, 153, 0.3)' }
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0px)' },
                            '50%': { transform: 'translateY(-8px)' }
                        }
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        body { 
            font-family: 'Plus Jakarta Sans', sans-serif; 
            background-color: #04060d;
            background-image: 
                radial-gradient(at 0% 0%, rgba(124, 58, 237, 0.22) 0px, transparent 50%),
                radial-gradient(at 100% 0%, rgba(99, 102, 241, 0.22) 0px, transparent 50%),
                radial-gradient(at 50% 100%, rgba(236, 72, 153, 0.18) 0px, transparent 50%);
            background-attachment: fixed;
        }
        .gradient-brand { background: linear-gradient(135deg, #070a14 0%, #12162b 45%, #231c3e 100%); }
        .gradient-accent { background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 50%, #ec4899 100%); }
        .glass-header { background: rgba(4, 6, 13, 0.9); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); }
        .glass-card { background: rgba(15, 20, 35, 0.6); backdrop-filter: blur(16px); -webkit-backdrop-filter: blur(16px); border: 1px solid rgba(255, 255, 255, 0.09); }
        .glass-modal { background: rgba(6, 8, 18, 0.97); backdrop-filter: blur(28px); -webkit-backdrop-filter: blur(28px); border: 1px solid rgba(139, 92, 246, 0.45); }
        
        .custom-scrollbar::-webkit-scrollbar { width: 6px; height: 6px; }
        .custom-scrollbar::-webkit-scrollbar-track { background: rgba(9, 13, 24, 0.8); }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: rgba(139, 92, 246, 0.45); border-radius: 9999px; }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover { background: rgba(139, 92, 246, 0.8); }
    </style>
</head>
<body class="bg-[#04060d] text-slate-100 min-h-screen flex flex-col selection:bg-purple-500 selection:text-white custom-scrollbar relative">

    <!-- Top Announcement & AI Status Bar -->
    <div class="bg-gradient-to-r from-purple-950 via-slate-950 to-indigo-950 text-xs py-2 px-4 font-medium border-b border-purple-500/20 text-purple-200 flex justify-between items-center z-50">
        <div class="flex items-center gap-2">
            <span class="inline-flex items-center px-2.5 py-0.5 rounded-full text-[10px] font-black bg-purple-500/20 text-purple-300 border border-purple-500/40 shadow-sm">
                ⚡ Nihiluxxy AI Pro v8.0 Megamodule Engine
            </span>
            <span class="hidden sm:inline text-slate-300">Modul Bimbingan Belajar Ultra-Lengkap (135 Bab Penuh) & Bank Soal UTBK SNBT 2026</span>
        </div>
        <div class="flex items-center gap-4 text-[11px] font-semibold text-purple-300">
            <span class="hidden md:flex items-center gap-1.5 font-mono text-emerald-400">
                <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span> Multi-Solver Deep Engine Active
            </span>
            <span class="text-slate-700 hidden md:inline">•</span>
            <span id="live-clock" class="font-mono text-purple-200 font-bold">--:--:-- WIB</span>
        </div>
    </div>

    <!-- Header Navigation Bar -->
    <header class="sticky top-0 z-40 glass-header border-b border-slate-800/80 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between gap-4">
            
            <!-- Brand Logo -->
            <div class="flex items-center gap-3 cursor-pointer group" onclick="switchView('home')">
                <div class="w-11 h-11 rounded-2xl gradient-accent flex items-center justify-center text-white font-black text-xl shadow-lg shadow-purple-500/30 group-hover:scale-105 transition duration-300 animate-pulse-glow">
                    <i data-lucide="sparkles" class="w-6 h-6"></i>
                </div>
                <div class="flex flex-col">
                    <div class="flex items-center gap-1.5">
                        <span class="text-2xl font-black tracking-tight text-white group-hover:text-purple-300 transition">Nihiluxxy</span>
                        <span class="text-[9px] font-black px-1.5 py-0.5 rounded-md bg-gradient-to-r from-purple-500 to-pink-500 text-white uppercase tracking-wider">AI PRO v8.0</span>
                    </div>
                    <span class="text-[9px] uppercase tracking-widest text-purple-400 font-extrabold -mt-1">Super Megamodule Engine</span>
                </div>
            </div>

            <!-- Global Search Desktop -->
            <div class="hidden lg:flex items-center flex-1 max-w-md mx-6">
                <div class="relative w-full">
                    <i data-lucide="search" class="w-4 h-4 absolute left-3.5 top-1/2 -translate-y-1/2 text-slate-400"></i>
                    <input type="text" id="global-search" oninput="handleGlobalSearch(this.value)" placeholder="Cari bab & konsep (misal: Vieta, Bernoulli, Glikolisis, Hardy-Weinberg)..." class="w-full bg-slate-900/90 border border-slate-700/80 rounded-2xl pl-10 pr-12 py-2 text-xs text-slate-200 focus:outline-none focus:border-purple-500 focus:ring-1 focus:ring-purple-500 transition shadow-inner">
                    <kbd class="hidden sm:inline-block absolute right-3 top-1/2 -translate-y-1/2 text-[9px] bg-slate-800 border border-slate-700 px-1.5 py-0.5 rounded text-slate-400 font-mono font-bold">⌘K</kbd>
                    <div id="search-results-popover" class="hidden absolute left-0 right-0 top-12 bg-slate-900/95 border border-purple-500/30 rounded-2xl shadow-2xl p-2 z-50 max-h-80 overflow-y-auto custom-scrollbar backdrop-blur-xl"></div>
                </div>
            </div>

            <!-- Navigation Desktop -->
            <nav class="hidden md:flex items-center gap-1 bg-slate-900/90 p-1.5 rounded-2xl border border-slate-800 text-xs font-semibold">
                <button onclick="switchView('home')" id="nav-home" class="px-3.5 py-2 rounded-xl text-white bg-purple-600 transition flex items-center gap-1.5 font-bold shadow-md shadow-purple-600/30">
                    <i data-lucide="home" class="w-4 h-4"></i> Beranda
                </button>
                <button onclick="switchView('materi')" id="nav-materi" class="px-3.5 py-2 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="book-open" class="w-4 h-4"></i> Modul Elite
                </button>
                <button onclick="switchView('visualizer')" id="nav-visualizer" class="px-3.5 py-2 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="line-chart" class="w-4 h-4 text-emerald-400"></i> Graph AI
                </button>
                <button onclick="switchView('kalkulator')" id="nav-kalkulator" class="px-3.5 py-2 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="calculator" class="w-4 h-4 text-cyan-400"></i> Hitung AI
                </button>
                <button onclick="switchView('utbk')" id="nav-utbk" class="px-3.5 py-2 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="award" class="w-4 h-4 text-amber-400"></i> UTBK
                </button>
                <button onclick="switchView('flashcards')" id="nav-flashcards" class="px-3.5 py-2 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="brain" class="w-4 h-4 text-pink-400"></i> Kartu
                </button>
                <button onclick="switchView('riwayat')" id="nav-riwayat" class="px-3.5 py-2 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="history" class="w-4 h-4 text-purple-400"></i> Riwayat
                </button>
            </nav>

            <!-- AI Quick Trigger Header Button -->
            <div class="flex items-center gap-3">
                <button onclick="toggleAiModal()" class="px-4 py-2.5 rounded-2xl bg-gradient-to-r from-purple-600 via-indigo-600 to-pink-600 hover:from-purple-500 hover:to-pink-500 text-white font-extrabold text-xs flex items-center gap-2 shadow-lg shadow-purple-500/25 border border-purple-400/40 transition transform hover:scale-105 active:scale-95">
                    <i data-lucide="bot" class="w-4 h-4 text-purple-100 animate-bounce"></i>
                    <span class="hidden sm:inline">AI Super Tutor</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Content Dynamic Render Container -->
    <main id="app-content" class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <!-- Rendered dynamically by JS Engine -->
    </main>

    <!-- Floating AI Tutor Trigger Widget -->
    <div class="fixed bottom-20 md:bottom-8 right-6 z-40">
        <button onclick="toggleAiModal()" class="group relative flex items-center justify-center w-14 h-14 rounded-full gradient-accent text-white shadow-2xl shadow-purple-500/50 hover:scale-110 active:scale-95 transition-all duration-300 border-2 border-white/20">
            <i data-lucide="sparkles" class="w-7 h-7"></i>
            <span class="absolute -top-1 -right-1 w-4 h-4 rounded-full bg-emerald-400 border-2 border-slate-950 animate-ping"></span>
            <span class="absolute -top-1 -right-1 w-4 h-4 rounded-full bg-emerald-400 border-2 border-slate-950"></span>
            <div class="absolute right-16 top-1/2 -translate-y-1/2 hidden group-hover:flex items-center px-3.5 py-1.5 bg-slate-900 border border-purple-500/50 rounded-xl text-xs font-bold text-white whitespace-nowrap shadow-2xl backdrop-blur-md">
                <span>Tanyakan AI Super Tutor ⚡</span>
            </div>
        </button>
    </div>

    <!-- AI Tutor Interactive Chat Drawer Modal -->
    <div id="ai-tutor-modal" class="fixed inset-0 z-50 hidden flex items-center justify-center p-3 sm:p-6 bg-slate-950/80 backdrop-blur-md transition-opacity">
        <div class="glass-modal w-full max-w-3xl rounded-3xl overflow-hidden shadow-2xl flex flex-col h-[88vh] border border-purple-500/40">
            
            <!-- AI Modal Header -->
            <div class="p-4 sm:p-5 bg-gradient-to-r from-purple-950 via-slate-900 to-indigo-950 border-b border-purple-500/30 flex items-center justify-between">
                <div class="flex items-center gap-3">
                    <div class="w-11 h-11 rounded-2xl gradient-accent flex items-center justify-center text-white font-bold shadow-lg shadow-purple-500/30">
                        <i data-lucide="bot" class="w-6 h-6"></i>
                    </div>
                    <div>
                        <div class="flex items-center gap-2">
                            <h3 class="font-black text-white text-base">Nihiluxxy AI Super Tutor v8.0</h3>
                            <span class="text-[9px] px-2 py-0.5 rounded-full bg-emerald-500/20 text-emerald-300 border border-emerald-500/40 font-mono font-bold">Deep Concept Engine</span>
                        </div>
                        <p class="text-[11px] text-purple-300">Pakar Matematika, Fisika, Kimia, Biologi, Geografi, Ekonomi, Sosiologi, Sejarah & UTBK SNBT 2026</p>
                    </div>
                </div>
                <button onclick="toggleAiModal()" class="w-9 h-9 rounded-xl bg-slate-800/80 hover:bg-slate-700 text-slate-400 hover:text-white flex items-center justify-center transition">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>

            <!-- AI Quick Action Chips Bar -->
            <div class="p-3 bg-slate-900/90 border-b border-slate-800 flex gap-2 overflow-x-auto custom-scrollbar text-xs">
                <button onclick="injectAiPrompt('Tolong jelaskan secara mendalam tentang rumus Vieta dan cara menurunkan rumus jumlah kuadrat akar-akar!')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="calculator" class="w-3.5 h-3.5 text-blue-400"></i> Rumus Vieta
                </button>
                <button onclick="injectAiPrompt('Bagaimana cara cepat membedakan larutan buffer dan hidrolisis garam dari soal campuran asam-basa?')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="flask-conical" class="w-3.5 h-3.5 text-pink-400"></i> Buffer vs Hidrolisis
                </button>
                <button onclick="injectAiPrompt('Paparkan alur 4 tahap respirasi aerob seluler beserta lokasi dan jumlah ATP yang dihasilkan!')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="dna" class="w-3.5 h-3.5 text-emerald-400"></i> Respirasi Aerob
                </button>
                <button onclick="injectAiPrompt('Jelaskan prinsip Hukum Bernoulli dan aplikasinya pada gaya angkat pesawat terbang!')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="zap" class="w-3.5 h-3.5 text-amber-400"></i> Hukum Bernoulli
                </button>
            </div>

            <!-- AI Chat Body Container -->
            <div id="ai-chat-body" class="flex-1 p-4 sm:p-6 overflow-y-auto custom-scrollbar space-y-4 bg-slate-950/60">
                <div class="flex gap-3 items-start">
                    <div class="w-9 h-9 rounded-xl gradient-accent flex-shrink-0 flex items-center justify-center text-white text-xs font-bold shadow-md">AI</div>
                    <div class="bg-slate-900/90 border border-purple-500/30 p-4 sm:p-5 rounded-2xl text-xs sm:text-sm text-slate-200 max-w-xl leading-relaxed shadow-xl">
                        <p class="font-bold text-purple-300 text-sm mb-1">Selamat datang di Nihiluxxy AI Super Tutor v8.0 Megamodule Edition! 🚀</p>
                        <p>Ketik soal dari 135 bab mata pelajaran SMA atau UTBK SNBT. Engine AI akan mengurai konsep hingga akar-akarnya, menyajikan derivasi rumus, dan memberikan langkah penyelesaian terperinci!</p>
                    </div>
                </div>
            </div>

            <!-- AI Input Box Area -->
            <div class="p-3 sm:p-4 bg-slate-900 border-t border-slate-800 flex items-center gap-2">
                <textarea id="ai-user-input" rows="1" onkeydown="handleAiKeyDown(event)" placeholder="Ketik pertanyaan atau salin soal di sini (misal: 'Jelaskan cara mencari integral substitusi sin³ x cos x dx')..." class="flex-1 bg-slate-950 border border-slate-700/80 rounded-2xl px-4 py-3 text-xs sm:text-sm text-slate-100 focus:outline-none focus:border-purple-500 custom-scrollbar resize-none"></textarea>
                <button onclick="sendAiQuery()" class="w-12 h-12 rounded-2xl gradient-accent text-white flex items-center justify-center hover:opacity-95 transition shadow-lg shadow-purple-500/25 flex-shrink-0">
                    <i data-lucide="send" class="w-5 h-5"></i>
                </button>
            </div>
        </div>
    </div>

    <!-- Mobile Navigation Bottom Bar -->
    <div class="md:hidden fixed bottom-0 left-0 right-0 glass-header border-t border-slate-800/80 flex justify-around py-2.5 text-[10px] font-semibold text-slate-400 z-30 backdrop-blur-lg">
        <button onclick="switchView('home')" id="mob-home" class="flex flex-col items-center gap-1 text-purple-400 font-bold">
            <i data-lucide="home" class="w-5 h-5"></i> Beranda
        </button>
        <button onclick="switchView('materi')" id="mob-materi" class="flex flex-col items-center gap-1">
            <i data-lucide="book-open" class="w-5 h-5"></i> Modul
        </button>
        <button onclick="switchView('visualizer')" id="mob-visualizer" class="flex flex-col items-center gap-1">
            <i data-lucide="line-chart" class="w-5 h-5"></i> Grafik
        </button>
        <button onclick="switchView('kalkulator')" id="mob-kalkulator" class="flex flex-col items-center gap-1">
            <i data-lucide="calculator" class="w-5 h-5"></i> Hitung
        </button>
        <button onclick="switchView('utbk')" id="mob-utbk" class="flex flex-col items-center gap-1">
            <i data-lucide="award" class="w-5 h-5"></i> UTBK
        </button>
        <button onclick="switchView('flashcards')" id="mob-flashcards" class="flex flex-col items-center gap-1">
            <i data-lucide="brain" class="w-5 h-5"></i> Kartu
        </button>
    </div>

    <!-- Application Footer -->
    <footer class="mt-auto border-t border-slate-800/80 bg-slate-950/80 py-8 text-xs text-slate-400 relative z-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center gap-4">
            <div class="flex items-center gap-2">
                <div class="w-6 h-6 rounded-lg gradient-accent flex items-center justify-center text-white text-xs font-bold">N</div>
                <span class="font-extrabold text-slate-200">Nihiluxxy AI Platform Megamodule Edition 2026 (v8.0)</span>
                <span class="text-slate-600">|</span>
                <span>Hak Cipta &copy; 2026. Kurikulum Merdeka & K13 Terverifikasi.</span>
            </div>
            <div class="flex gap-6 text-slate-400">
                <a href="#" onclick="toggleAiModal()" class="hover:text-purple-400 transition flex items-center gap-1">
                    <i data-lucide="bot" class="w-3.5 h-3.5 text-purple-400"></i> AI Assistant
                </a>
                <a href="#" class="hover:text-purple-400 transition">Panduan HOTS</a>
                <a href="#" class="hover:text-purple-400 transition">Kebijakan Privasi</a>
            </div>
        </div>
    </footer>

    <!-- JS Application Engine -->
    <script>
        // Realtime Clock
        setInterval(() => {
            const now = new Date();
            const timeStr = now.toLocaleTimeString('id-ID') + ' WIB';
            const clockEl = document.getElementById('live-clock');
            if (clockEl) clockEl.innerText = timeStr;
        }, 1000);

        // Keyboard Shortcut ⌘K / Ctrl+K
        document.addEventListener('keydown', (e) => {
            if ((e.metaKey || e.ctrlKey) && e.key === 'k') {
                e.preventDefault();
                document.getElementById('global-search')?.focus();
            }
        });

        // Core Application State
        const state = {
            activeView: 'home',
            selectedKurikulum: 'Merdeka',
            selectedSubject: 'mat',
            attempts: JSON.parse(localStorage.getItem('nihiluxxy_v8_attempts') || '[]'),
            userNotes: JSON.parse(localStorage.getItem('nihiluxxy_v8_notes') || '{}'),
            currentSimAnswers: {},
            activeSimKey: null,
            simTimerInterval: null,
            simTimeLeft: 0,
            currentFlashcardIdx: 0,
            flashcardFilter: 'semua'
        };

        // Fully Expanded Database Engine - 15 Deep-Dive Chapters Per Subject (135 Total Chapters)
        const db = {
            mapel: [
                { id: 'mat', nama: 'Matematika Wajib & Lanjut', icon: 'calculator', color: 'from-blue-600 to-cyan-500', k13: 'Kelas 10-12 IPA/IPS', merdeka: 'Fase E & F (15 Bab Terperinci Modul Bintang)' },
                { id: 'fis', nama: 'Fisika Lanjut', icon: 'zap', color: 'from-indigo-600 to-blue-500', k13: 'Kelas 10-12 IPA', merdeka: 'Fase F (15 Bab Terperinci Modul Bintang)' },
                { id: 'kim', nama: 'Kimia Lanjut', icon: 'flask-conical', color: 'from-purple-600 to-pink-500', k13: 'Kelas 10-12 IPA', merdeka: 'Fase F (15 Bab Terperinci Modul Bintang)' },
                { id: 'bio', nama: 'Biologi Lanjut', icon: 'dna', color: 'from-emerald-600 to-teal-500', k13: 'Kelas 10-12 IPA', merdeka: 'Fase F (15 Bab Terperinci Modul Bintang)' },
                { id: 'geo', nama: 'Geografi Lanjut', icon: 'globe', color: 'from-teal-600 to-emerald-500', k13: 'Kelas 10-12 IPS', merdeka: 'Fase F (15 Bab Terperinci Modul Bintang)' },
                { id: 'eko', nama: 'Ekonomi & Akuntansi', icon: 'trending-up', color: 'from-amber-600 to-yellow-500', k13: 'Kelas 10-12 IPS', merdeka: 'Fase F (15 Bab Terperinci Modul Bintang)' },
                { id: 'sos', nama: 'Sosiologi Lanjut', icon: 'users', color: 'from-rose-600 to-red-500', k13: 'Kelas 10-12 IPS', merdeka: 'Fase F (15 Bab Terperinci Modul Bintang)' },
                { id: 'sej', nama: 'Sejarah Indonesia & Dunia', icon: 'landmark', color: 'from-red-600 to-orange-500', k13: 'Kelas 10-12 Wajib/Peminatan', merdeka: 'Fase E & F (15 Bab Terperinci Modul Bintang)' },
                { id: 'lit', nama: 'Literasi Bahasa & Penalaran', icon: 'book-marked', color: 'from-orange-600 to-amber-500', k13: 'Wajib Semua Jurusan', merdeka: 'Fase E & F (15 Bab Terperinci Modul Bintang)' }
            ],
            flashcards: [
                { mapel: 'Matematika', pertanyaan: 'Apakah turunan pertama dari f(x) = axⁿ menurut aturan turunan dasar?', jawaban: 'f\'(x) = a · n · xⁿ⁻¹.' },
                { mapel: 'Matematika', pertanyaan: 'Berapakah rumus integral tentu ∫ xⁿ dx untuk n ≠ -1?', jawaban: '∫ xⁿ dx = [1 / (n + 1)] · xⁿ⁺¹ + C.' },
                { mapel: 'Matematika', pertanyaan: 'Apakah syarat utama dua vektor u dan v saling tegak lurus (ortogonal)?', jawaban: 'Hasil perkalian titiknya sama dengan nol: u · v = 0.' },
                { mapel: 'Fisika', pertanyaan: 'Apakah Hukum Kirchhoff II tentang tegangan dalam sebuah loop tertutup?', jawaban: 'Jumlah perubahan potensial (ΣE + Σ(I·R)) dalam loop tertutup adalah nol.' },
                { mapel: 'Fisika', pertanyaan: 'Bagaimana rumus frekuensi resonansi pada rangkaian RLC seri?', jawaban: 'f = 1 / (2π √(L·C)).' },
                { mapel: 'Kimia', pertanyaan: 'Bagaimana rumus orde reaksi laju V = k [A]ᵐ [B]ⁿ?', jawaban: 'Laju reaksi berbanding lurus dengan konsentrasi reaktan pangkat ordenya.' },
                { mapel: 'Kimia', pertanyaan: 'Apakah rumus menghitung pH larutan hidrolisis garam dari asam lemah dan basa kuat?', jawaban: '[OH⁻] = √( (Kw / Ka) × M_garam ).' },
                { mapel: 'Biologi', pertanyaan: 'Di manakah lokasi terjadinya tahap glikolisis pada respirasi aerob sel?', jawaban: 'Di dalam Sitosol (Sitoplasma) sel.' },
                { mapel: 'Geografi', pertanyaan: 'Apakah rumus menentukan skala peta jika diketahui jarak di peta (d) dan jarak sebenarnya (D)?', jawaban: 'Skala = d / D.' },
                { mapel: 'Ekonomi', pertanyaan: 'Apakah rumus mencari Break Even Point (BEP) unit dalam akuntansi manajemen?', jawaban: 'BEP Unit = Biaya Tetap Total / (Harga per Unit - Biaya Variabel per Unit).' }
            ],
            materiDetails: {
                'mat': [
                    {
                        title: 'Bab 1: Eksponen, Bentuk Akar & Logaritma Lanjut',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Eksponen menggambarkan perkalian berulang basis $a^n = a \times a \times \dots \times a$. Logaritma merupakan invers langsung dari fungsi eksponensial ($a^y = x \iff \text{^a}\log x = y$). Sifat-sifat logaritma diturunkan langsung dari hukum eksponen. Bentuk akar ($\sqrt[n]{a^m} = a^{m/n}$) digunakan untuk menyederhanakan pecahan irasional melalui teknik merasionalkan penyebut (dikalikan sekawan).',
                        visual: 'ᵃlog(b·c) = ᵃlog b + ᵃlog c  |  ᵃlog(b/c) = ᵃlog b - ᵃlog c  |  ᵃlog bⁿ = n · ᵃlog b  |  ᵃlog b · ᵇlog c = ᵃlog c',
                        tips: '<strong>Trik Bimbel Elite:</strong> Jika menemukan persamaan eksponen $a^{f(x)} = a^{g(x)}$, samakan pangkatnya $f(x) = g(x)$ (syarat $a>0, a \neq 1$). Jika basis mengandung variabel $h(x)^{f(x)} = h(x)^{g(x)}$, uji 4 kondisi: (1) $f(x)=g(x)$, (2) $h(x)=1$, (3) $h(x)=0$ (dengan $f(x),g(x)>0$), (4) $h(x)=-1$ (dengan $f(x),g(x)$ sama-sama genap/ganjil).',
                        contohSoal: '<strong>Soal 1:</strong> Jika diketahui $\text{^a}\log b + \text{^a}\log b^2 = 12$, hitunglah nilai dari $\text{^a}\log(a \cdot b)$.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Gunakan sifat pangkat logaritma: $\text{^a}\log b^2 = 2 \cdot \text{^a}\log b$.<br>2. Substitusi ke persamaan: $\text{^a}\log b + 2 \cdot \text{^a}\log b = 12 \implies 3 \cdot \text{^a}\log b = 12 \implies \text{^a}\log b = 4$.<br>3. Hitung $\text{^a}\log(a \cdot b) = \text{^a}\log a + \text{^a}\log b = 1 + 4 = \mathbf{5}$.<br><br><strong>Soal 2 (HOTS):</strong> Tentukan himpunan penyelesaian dari $\text{^2}\log^2 x - \text{^2}\log x^3 + 2 = 0$.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Ubah $\text{^2}\log x^3 = 3 \cdot \text{^2}\log x$. Persamaan menjadi $(\text{^2}\log x)^2 - 3(\text{^2}\log x) + 2 = 0$.<br>2. Misalkan $y = \text{^2}\log x \implies y^2 - 3y + 2 = 0 \implies (y-1)(y-2) = 0$.<br>3. Untuk $y=1 \implies \text{^2}\log x = 1 \implies x = 2$. Untuk $y=2 \implies \text{^2}\log x = 2 \implies x = 4$.<br>4. HP = $\mathbf{\{2, 4\}}$.'
                    },
                    {
                        title: 'Bab 2: Persamaan & Fungsi Kuadrat serta Rumus Vieta',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Persamaan kuadrat $ax^2 + bx + c = 0$ memiliki titik balik parabola di $x_p = -b/(2a)$ dan $y_p = -D/(4a)$. Diskriminan $D = b^2 - 4ac$ menentukan jumlah akar real. Rumus Vieta diturunkan dari faktorisasi $a(x-x_1)(x-x_2) = ax^2 - a(x_1+x_2)x + a x_1 x_2$, sehingga diperoleh $x_1+x_2 = -b/a$ dan $x_1 x_2 = c/a$.',
                        visual: 'Vieta: x₁ + x₂ = -b/a  |  x₁ · x₂ = c/a  |  x₁ - x₂ = √D / a  |  Puncak Parabola: (-b / 2a , -D / 4a)',
                        tips: 'Gunakan identitas aljabar Vieta untuk menghemat waktu tanpa mencari akar secara eksplisit:<br>• $x_1^2 + x_2^2 = (x_1+x_2)^2 - 2 x_1 x_2$<br>• $x_1^3 + x_2^3 = (x_1+x_2)^3 - 3 x_1 x_2 (x_1+x_2)$<br>• $\frac{1}{x_1} + \frac{1}{x_2} = \frac{x_1+x_2}{x_1 x_2}$',
                        contohSoal: '<strong>Soal 1:</strong> Jika $x^2 - (k + 2)x + 16 = 0$ memiliki dua akar kembar positif, tentukan nilai $k$.<br><strong>Langkah Penyelesaian:</strong><br>1. Syarat akar kembar: $D = 0 \implies (-(k+2))^2 - 4(1)(16) = 0 \implies (k+2)^2 = 64$.<br>2. Maka $k+2 = 8 \implies k = 6$ atau $k+2 = -8 \implies k = -10$.<br>3. Uji syarat akar positif: $x_1+x_2 = k+2 > 0 \implies 6+2 = 8 > 0$ (Memenuhi). Jadi $k = \mathbf{6}$.<br><br><strong>Soal 2 (HOTS):</strong> Akar-akar $2x^2 - 6x + 1 = 0$ adalah $\alpha$ dan $\beta$. Buat persamaan kuadrat baru yang akar-akarnya $(2\alpha + 1)$ dan $(2\beta + 1)$.<br><strong>Langkah Penyelesaian:</strong><br>1. Dari persamaan awal: $\alpha + \beta = 6/2 = 3$, $\alpha \beta = 1/2$.<br>2. Jumlah akar baru $S = (2\alpha+1) + (2\beta+1) = 2(\alpha+\beta) + 2 = 2(3) + 2 = 8$.<br>3. Hasil kali akar baru $P = (2\alpha+1)(2\beta+1) = 4\alpha\beta + 2(\alpha+\beta) + 1 = 4(1/2) + 2(3) + 1 = 2 + 6 + 1 = 9$.<br>4. Persamaan kuadrat baru: $x^2 - Sx + P = 0 \implies \mathbf{x^2 - 8x + 9 = 0}$.'
                    },
                    {
                        title: 'Bab 3: Trigonometri Analitik & Identitas Jumlah Sudut',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Trigonometri analitik menghubungkan fungsi rasional sudut siku-siku dengan koordinat kartesius lingkaran satuan ($x = r \cos \theta, y = r \sin \theta$). Rumus jumlah dan selisih sudut diperoleh dari rumus jarak vektor koordinat pada lingkaran satuan.',
                        visual: 'sin(A ± B) = sin A cos B ± cos A sin B  |  cos(A ± B) = cos A cos B ∓ sin A sin B  |  tan(A ± B) = (tan A ± tan B) / (1 ∓ tan A tan B)',
                        tips: 'Ingat sudut ganda: $\sin 2A = 2 \sin A \cos A$ dan $\cos 2A = \cos^2 A - \sin^2 A = 2\cos^2 A - 1 = 1 - 2\sin^2 A$. Uji Aturan Kosinus $c^2 = a^2 + b^2 - 2ab \cos C$ jika diketahui dua sisi dan satu sudut apit.',
                        contohSoal: '<strong>Soal 1:</strong> Segitiga ABC memiliki $a = 4\text{ cm}$, $b = 6\text{ cm}$, dan sudut $C = 60^\circ$. Hitung panjang sisi $c$.<br><strong>Langkah Penyelesaian:</strong><br>1. $c^2 = a^2 + b^2 - 2ab \cos C = 4^2 + 6^2 - 2(4)(6) \cos 60^\circ$.<br>2. $c^2 = 16 + 36 - 48(0,5) = 52 - 24 = 28 \implies c = \sqrt{28} = \mathbf{2\sqrt{7}\text{ cm}}$.<br><br><strong>Soal 2 (HOTS):</strong> Hitung nilai pasti dari $\cos 15^\circ$.<br><strong>Langkah Penyelesaian:</strong><br>1. Ubah $\cos 15^\circ = \cos(45^\circ - 30^\circ) = \cos 45^\circ \cos 30^\circ + \sin 45^\circ \sin 30^\circ$.<br>2. $= (\frac{1}{2}\sqrt{2})(\frac{1}{2}\sqrt{3}) + (\frac{1}{2}\sqrt{2})(\frac{1}{2}) = \frac{1}{4}\sqrt{6} + \frac{1}{4}\sqrt{2} = \mathbf{\frac{1}{4}(\sqrt{6} + \sqrt{2})}$.'
                    },
                    {
                        title: 'Bab 4: Vektor pada R² & R³ serta Proyeksi Ortogonal',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Vektor merepresentasikan besaran yang memiliki panjang (magnitudo) dan arah. Perkalian titik (dot product) $\vec{u} \cdot \vec{v} = |\vec{u}| |\vec{v}| \cos \theta$ mengukur sejauh mana dua vektor berada pada arah yang sama. Jika $\vec{u} \cdot \vec{v} = 0$, maka kedua vektor tegak lurus ($\theta = 90^\circ$).',
                        visual: 'Dua Vektor Tegak Lurus: u · v = 0  |  Proyeksi Skalar: |p| = (u · v) / |v|  |  Proyeksi Vektor: p = [ (u · v) / |v|² ] · v',
                        tips: 'Proyeksi skalar menghasilkan bilangan real (panjang), sedangkan proyeksi vektor menghasilkan komponen vektor baru yang sejajar dengan vektor alas.',
                        contohSoal: '<strong>Soal 1:</strong> Diketahui $\vec{u} = (2, -1)$ dan $\vec{v} = (x, 4)$. Jika $\vec{u} \perp \vec{v}$, berapa $x$? <br><strong>Langkah Penyelesaian:</strong><br>1. Syarat tegak lurus: $\vec{u} \cdot \vec{v} = 0 \implies (2)(x) + (-1)(4) = 0 \implies 2x - 4 = 0 \implies \mathbf{x = 2}$.<br><br><strong>Soal 2 (HOTS):</strong> Vektor $\vec{a} = (1, 2, 2)$ diproyeksikan secara ortogonal pada $\vec{b} = (2, -2, 1)$. Tentukan vektor proyeksinya.<br><strong>Langkah Penyelesaian:</strong><br>1. Hitung $\vec{a} \cdot \vec{b} = (1)(2) + (2)(-2) + (2)(1) = 2 - 4 + 2 = 0$.<br>2. Karena $\vec{a} \cdot \vec{b} = 0$, maka proyeksi vektornya adalah $\mathbf{\vec{0} = (0, 0, 0)}$.'
                    },
                    {
                        title: 'Bab 5: Matriks, Determinan & Invers Operasi Baris',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Matriks adalah susunan kuantitas berbentuk persegi panjang. Invers matriks $A^{-1}$ memenuhi $A \cdot A^{-1} = I$. Determinan mengukur faktor skala transformasi linear dari matriks tersebut.',
                        visual: 'det(A · B) = det(A) · det(B)  |  det(A⁻¹) = 1 / det(A)  |  det(k·A_2x2) = k²·det(A)',
                        tips: 'Jika $\det(A) = 0$, matriks dinamakan matriks singular (tidak memiliki invers).',
                        contohSoal: '<strong>Soal 1:</strong> Jika $\det(A) = 5$ dan $\det(B) = 2$, berapakah determinan dari $3 A^{-1} \cdot B$ untuk matriks berordo $2 \times 2$? <br><strong>Langkah Penyelesaian:</strong><br>1. $\det(3 A^{-1} B) = 3^2 \cdot \det(A^{-1}) \cdot \det(B) = 9 \cdot (1/5) \cdot 2 = \mathbf{18/5 = 3,6}$.'
                    },
                    {
                        title: 'Bab 6: Barisan & Deret Aritmatika, Geometri & Tak Hingga',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Barisan aritmatika memiliki beda tetap $b = U_n - U_{n-1}$, sedangkan barisan geometri memiliki rasio tetap $r = U_n / U_{n-1}$. Deret geometri tak hingga konvergen jika $|r| < 1$, dengan jumlah $S_\infty = \frac{a}{1 - r}$.',
                        visual: 'Aritmatika: U_n = a + (n-1)b  |  Geometri: U_n = a·rⁿ⁻¹  |  Tak Hingga Konvergen: S_∞ = a / (1 - r)',
                        tips: 'Jumlah $n$ suku pertama deret aritmatika dapat langsung dicari dengan $S_n = \frac{n}{2}(a + U_n)$.',
                        contohSoal: '<strong>Soal 1:</strong> Deret geometri tak hingga memiliki $a = 12$ dan $S_\infty = 18$. Hitung rasionya.<br><strong>Langkah Penyelesaian:</strong><br>1. $S_\infty = \frac{a}{1-r} \implies 18 = \frac{12}{1-r} \implies 1-r = \frac{12}{18} = \frac{2}{3} \implies r = 1 - \frac{2}{3} = \mathbf{1/3}$.'
                    },
                    {
                        title: 'Bab 7: Limit Fungsi Aljabar, Trigonometri & Aturan L\'Hopital',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Limit menentukan perilaku nilai $f(x)$ saat $x$ mendekati titik tertentu $c$. Untuk bentuk tak tentu $\frac{0}{0}$ atau $\frac{\infty}{\infty}$, gunakan aturan L\'Hopital $\lim_{x \to c} \frac{f(x)}{g(x)} = \lim_{x \to c} \frac{f\'(x)}{g\'(x)}$.',
                        visual: 'lim (x→0) (sin ax / bx) = a/b  |  lim (x→0) (tan ax / bx) = a/b  |  L\'Hopital: f\'(x)/g\'(x)',
                        tips: 'Limit trigonometri dasar: $\lim_{x \to 0} \frac{1 - \cos ax}{x^2} = \frac{1}{2} a^2$. Gunakan ini untuk menyelesaikan soal limit trigonometri secara instan!',
                        contohSoal: '<strong>Soal 1:</strong> Hitung $\lim_{x \to 0} \frac{1 - \cos 4x}{x \sin 2x}$.<br><strong>Langkah Penyelesaian:</strong><br>1. Gunakan trik cepat: pembilang $1 - \cos 4x \approx \frac{1}{2}(4)^2 x^2 = 8x^2$.<br>2. Penyebut $x \sin 2x \approx 2x^2$.<br>3. Limit $= \frac{8x^2}{2x^2} = \mathbf{4}$.'
                    },
                    {
                        title: 'Bab 8: Turunan Fungsi, Garis Singgung & Titik Stasioner',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Turunan $f\'(x) = \lim_{h \to 0} \frac{f(x+h)-f(x)}{h}$ merepresentasikan laju perubahan seketika dan gradien garis singgung kurva di titik $(x_1, y_1)$ dengan $m = f\'(x_1)$. Titik stasioner dicapai saat $f\'(x) = 0$.',
                        visual: 'Aturan Rantai: d/dx [f(g(x))] = f\'(g(x)) · g\'(x)  |  Stasioner: f\'(x) = 0',
                        tips: 'Kurva fungsi selalu naik pada interval $f\'(x) > 0$ dan selalu turun pada interval $f\'(x) < 0$. Uji turunan kedua $f\'\'(x_0)$ untuk menentukan jenis stasioner (minimum jika $>0$, maksimum jika $<0$).',
                        contohSoal: '<strong>Soal 1:</strong> Tentukan nilai minimum fungsi $f(x) = x^3 - 3x^2 + 5$.<br><strong>Langkah Penyelesaian:</strong><br>1. $f\'(x) = 3x^2 - 6x = 0 \implies 3x(x - 2) = 0 \implies x = 0$ atau $x = 2$.<br>2. Uji turunan kedua $f\'\'(x) = 6x - 6$. Untuk $x=2 \implies f\'\'(2) = 6 > 0$ (Minimum).<br>3. Nilai minimum $= f(2) = 2^3 - 3(2)^2 + 5 = 8 - 12 + 5 = \mathbf{1}$.'
                    },
                    {
                        title: 'Bab 9: Integral Tentu, Luas Daerah & Benda Putar',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Derivasi Matematis:</strong> Integral merupakan antiturunan (Teorema Dasar Kalkulus). Integral tentu $\int_a^b f(x) dx = F(b) - F(a)$ mengukur akumulasi luas di bawah kurva.',
                        visual: 'Luas Parabola & Garis: L = (D √D) / (6 a²)  |  Volume Rotasi Sumbu-X: V = π ∫ y² dx',
                        tips: 'Gunakan rumus instan $L = \frac{D\sqrt{D}}{6a^2}$ untuk mencari luas daerah yang dibatasi oleh parabola $y = ax^2+bx+c$ dan garis!',
                        contohSoal: '<strong>Soal 1:</strong> Hitung luas daerah yang dibatasi oleh $y = x^2 - 4x$ dan sumbu-X.<br><strong>Langkah Penyelesaian:</strong><br>1. $a = 1, b = -4, c = 0 \implies D = (-4)^2 - 4(1)(0) = 16$.<br>2. Luas $= \frac{16 \cdot \sqrt{16}}{6(1)^2} = \frac{16 \cdot 4}{6} = \frac{64}{6} = \mathbf{32/3\text{ satuan luas}}$.'
                    },
                    {
                        title: 'Bab 10: Polinomial, Metode Horner & Teorema Sisa',
                        kurikulum: 'K13 & Merdeka (Fase F Lanjut)',
                        summary: '<strong>Akar Konsep & Algoritma:</strong> Polinomial $P(x) = a_n x^n + \dots + a_0$ dibagi $(x - k)$ dapat ditulis $P(x) = (x - k)Q(x) + S$. Menurut Teorema Sisa, sisa pembagian sama dengan nilai suku banyak $S = P(k)$. Menurut Teorema Faktor, $(x - k)$ adalah faktor jika $P(k) = 0$.',
                        visual: 'Teorema Sisa: P(k) = Sisa  |  Teorema Faktor: P(k) = 0 ⇔ (x - k) adalah faktor',
                        tips: 'Gunakan Skema Horner untuk mempercepat perhitungan pembagian dan pemfaktoran polinomial derajat tinggi!',
                        contohSoal: '<strong>Soal 1:</strong> Jika $P(x) = 2x^3 - x^2 + ax - 4$ dibagi $(x - 2)$ bersisa 10, tentukan $a$.<br><strong>Langkah Penyelesaian:</strong><br>1. $P(2) = 10 \implies 2(2)^3 - (2)^2 + a(2) - 4 = 10 \implies 16 - 4 + 2a - 4 = 10 \implies 8 + 2a = 10 \implies \mathbf{a = 1}$.'
                    },
                    {
                        title: 'Bab 11: Kombinatorika, Permutasi, Kombinasi & Peluang',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Teori Peluang:</strong> Permutasi $P(n,r) = \frac{n!}{(n-r)!}$ memperhitungkan urutan susunan, sedangkan Kombinasi $C(n,r) = \frac{n!}{r!(n-r)!}$ tidak memperhitungkan urutan. Peluang kejadian $P(A) = \frac{n(A)}{n(S)}$.',
                        visual: 'Permutasi (Ada Jabatan/Urutan) vs Kombinasi (Acak/Tim)  |  P(A ∪ B) = P(A) + P(B) - P(A ∩ B)',
                        tips: 'Jika soal menyebutkan pembentukan pengurus (Ketua, Sekretaris), gunakan **Permutasi**. Jika pembentukan tim acak, gunakan **Kombinasi**.',
                        contohSoal: '<strong>Soal 1:</strong> Dari 7 kandidat, akan dipilih 3 orang anggota delegasi. Berapa banyak cara pemilihan?<br><strong>Langkah Penyelesaian:</strong><br>1. Karena urutan tidak penting, gunakan Kombinasi: $C(7,3) = \frac{7!}{3!4!} = \frac{7 \cdot 6 \cdot 5}{3 \cdot 2 \cdot 1} = \mathbf{35\text{ cara}}$.'
                    },
                    {
                        title: 'Bab 12: Geometri Analitik Lingkaran & Garis Singgung',
                        kurikulum: 'K13 & Merdeka (Fase F Lanjut)',
                        summary: '<strong>Akar Konsep Geometri:</strong> Persamaan lingkaran berpusat $(a,b)$ ber-jari-jari $r$ adalah $(x-a)^2 + (y-b)^2 = r^2$. Bentuk umum $x^2 + y^2 + Ax + By + C = 0$ memiliki pusat $(-A/2, -B/2)$ dan jari-jari $r = \sqrt{\frac{A^2}{4} + \frac{B^2}{4} - C}$.',
                        visual: 'Garis Singgung Bergradien m: y - b = m(x - a) ± r √(1 + m²)',
                        tips: 'Jarak titik $(x_1, y_1)$ ke garis $Ax + By + C = 0$ adalah $d = \frac{|Ax_1 + By_1 + C|}{\sqrt{A^2 + B^2}}$.',
                        contohSoal: '<strong>Soal 1:</strong> Tentukan pusat dan jari-jari lingkaran $x^2 + y^2 - 6x + 8y = 0$.<br><strong>Langkah Penyelesaian:</strong><br>1. Pusat $= (-(-6)/2, -8/2) = \mathbf{(3, -4)}$.<br>2. Jari-jari $r = \sqrt{3^2 + (-4)^2 - 0} = \sqrt{9+16} = \mathbf{5}$.'
                    },
                    {
                        title: 'Bab 13: Fungsi Komposisi & Fungsi Invers',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Akar Konsep Pemetaan:</strong> Fungsi komposisi $(f \circ g)(x) = f(g(x))$ memetakan himpunan domain $g$ ke daerah hasil $f$. Fungsi invers $f^{-1}(x)$ membalik pemetaan $y = f(x) \iff x = f^{-1}(y)$.',
                        visual: 'Invers Fungsi Rasional: f(x) = (ax + b)/(cx + d) ⇒ f⁻¹(x) = (-dx + b)/(cx - a)',
                        tips: 'Tukar posisi koefisien $a$ dan $d$ lalu kalikan $-1$ untuk mencari invers fungsi rasional secara instan!',
                        contohSoal: '<strong>Soal 1:</strong> Jika $f(x) = \frac{2x + 5}{3x - 4}$, tentukan $f^{-1}(x)$.<br><strong>Langkah Penyelesaian:</strong><br>1. Gunakan trik cepat: $a=2, b=5, c=3, d=-4 \implies f^{-1}(x) = \mathbf{\frac{4x + 5}{3x - 2}}$.'
                    },
                    {
                        title: 'Bab 14: Program Linear & Uji Titik Pojok Optimum',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Optimasi:</strong> Program linear menentukan nilai optimum (maksimum/minimum) dari fungsi objektif $Z = ax + by$ di bawah daerah himpunan penyelesaian sistem pertidaksamaan linear.',
                        visual: 'Metode Titik Pojok (Corner Point Method)  |  Garis Selidik: ax + by = k',
                        tips: 'Nilai optimum SELALU terletak pada salah satu titik sudut (pojok) daerah penyelesaian!',
                        contohSoal: '<strong>Soal 1:</strong> Tentukan nilai maksimum $Z = 5x + 2y$ pada titik-titik pojok daerah penyelesaian $(0,0), (4,0), (2,3), (0,5)$.<br><strong>Langkah Penyelesaian:</strong><br>1. Evaluasi: $Z(0,0)=0, Z(4,0)=20, Z(2,3)=5(2)+2(3)=16, Z(0,5)=10$.<br>2. Nilai maksimum $= \mathbf{20}$ pada titik $(4,0)$.'
                    },
                    {
                        title: 'Bab 15: Dimensi Tiga (Jarak & Sudut dalam Ruang)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Geometri Ruang:</strong> Analisis posisi titik, garis, dan bidang pada bangun tiga dimensi menggunakan proyeksi tegak lurus dan Teorema Pythagoras.',
                        visual: 'Diagonal Sisi Kubus = s√2  |  Diagonal Ruang Kubus = s√3  |  Jarak Titik ke Garis via Proyeksi Tegak Lurus',
                        tips: 'Jarak titik sudut kubus ke diagonal ruang yang tidak melaluinya adalah $\frac{1}{3} s \sqrt{6}$.',
                        contohSoal: '<strong>Soal 1:</strong> Kubus ABCD.EFGH memiliki rusuk $6\text{ cm}$. Hitung jarak titik A ke garis CF.<br><strong>Langkah Penyelesaian:</strong><br>1. Segitiga ACF adalah segitiga sama sisi dengan panjang sisi $s\sqrt{2} = 6\sqrt{2}\text{ cm}$.<br>2. Tingginya $= \frac{\text{sisi}}{2} \sqrt{3} = \frac{6\sqrt{2}}{2} \sqrt{3} = \mathbf{3\sqrt{6}\text{ cm}}$.'
                    }
                ],
                'fis': [
                    {
                        title: 'Bab 1: Kinematika Gerak Lurus & Parabola',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Derivasi Fisika:</strong> Kinematika mengkaji posisi, kecepatan, dan percepatan benda tanpa meninjau gaya penyebabnya. Gerak Parabola merupakan superposisi dua gerak independen yang saling tegak lurus: Gerak Lurus Beraturan (GLB) pada sumbu mendatar $X$ ($v_x = v_0 \cos \theta$) dan Gerak Lurus Berubah Beraturan (GLBB) pada sumbu vertikal $Y$ ($v_y = v_0 \sin \theta - gt$).',
                        visual: 'H_max = (v₀² sin² θ) / 2g  |  X_max = (v₀² sin 2θ) / g  |  t_puncak = (v₀ sin θ) / g',
                        tips: '<strong>Trik Cepat Fisika:</strong> Pada titik tertinggi lintasan parabola, kecepatan vertikal $v_y = 0$, tetapi kecepatan total benda TIDAK NOL, melainkan $v = v_x = v_0 \cos \theta$.',
                        contohSoal: '<strong>Soal 1:</strong> Ditembakkan peluru $v_0 = 20\text{ m/s}$ sudut $30^\circ$ ($g = 10\text{ m/s}^2$). Hitung ketinggian maksimumnya.<br><strong>Langkah Penyelesaian:</strong><br>1. $H_{\text{max}} = \frac{v_0^2 \sin^2 \theta}{2g} = \frac{20^2 \cdot (\sin 30^\circ)^2}{2(10)} = \frac{400 \cdot (0,5)^2}{20} = \frac{400 \cdot 0,25}{20} = \mathbf{5\text{ meter}}$.<br><br><strong>Soal 2 (HOTS):</strong> Berapakah jangkauan horisontal terjauh ($X_{\text{max}}$) jika peluru tersebut ditembakkan dengan sudut elevasi $45^\circ$? <br><strong>Langkah Penyelesaian:</strong><br>1. $X_{\text{max}} = \frac{v_0^2 \sin(2\theta)}{g} = \frac{20^2 \cdot \sin(90^\circ)}{10} = \frac{400 \cdot 1}{10} = \mathbf{40\text{ meter}}$.'
                    },
                    {
                        title: 'Bab 2: Hukum-Hukum Newton & Dinamika Gerak',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Derivasi Fisika:</strong> Dinamika mengkaji pengaruh gaya terhadap gerak benda. Hukum I Newton ($\Sigma \vec{F} = 0$) menyatakan kelembaman (inersia). Hukum II Newton ($\Sigma \vec{F} = m \vec{a}$) menyatakan hubungan sebab-akibat antara gaya netral dan percepatan massa. Hukum III Newton ($\vec{F}_{\text{aksi}} = -\vec{F}_{\text{reaksi}}$) menyatakan sifat pasangan gaya interaksi.',
                        visual: 'Gaya Gesek: f_g = μ · N  |  Komponen Bidang Miring: F = m·g sin θ  |  N = m·g cos θ',
                        tips: 'Gaya normal $N$ pada bidang miring selalu sebesar $m g \cos \theta$, bukan $m g$!',
                        contohSoal: '<strong>Soal 1:</strong> Balok $m = 4\text{ kg}$ berada pada bidang miring licin $30^\circ$ ($g = 10\text{ m/s}^2$). Hitung percepatannya.<br><strong>Langkah Penyelesaian:</strong><br>1. Komponen gaya sejajar bidang: $F = m g \sin 30^\circ$.<br>2. Menurut Hukum II Newton: $a = \frac{F}{m} = g \sin 30^\circ = 10 \cdot 0,5 = \mathbf{5\text{ m/s}^2}$.'
                    },
                    {
                        title: 'Bab 3: Usaha, Energi & Hukum Kekekalan Energi Mekanik',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Energi:</strong> Usaha $W = \vec{F} \cdot \vec{s} = F s \cos \theta$ adalah transfer energi. Energi Mekanik $EM = EP + EK$ bersifat kekal pada sistem tertutup tanpa gaya gesek non-konservatif.',
                        visual: 'Usaha W = ΔEK = ΔEP  |  Hukum Kekekalan Energi Mekanik: EP₁ + EK₁ = EP₂ + EK₂',
                        tips: 'Pada gerak jatuh bebas tanpa kecepatan awal dari ketinggian $h$, $v = \sqrt{2gh}$.',
                        contohSoal: '<strong>Soal 1:</strong> Benda $1\text{ kg}$ jatuh dari ketinggian $20\text{ m}$ ($g = 10\text{ m/s}^2$). Hitung energi kinetiknya saat ketinggian $5\text{ m}$.<br><strong>Langkah Penyelesaian:</strong><br>1. $\Delta EP = m g \Delta h = 1 \cdot 10 \cdot (20 - 5) = 150\text{ J}$.<br>2. Menurut kekekalan energi: $EK_{\text{akhir}} = \Delta EP = \mathbf{150\text{ Joule}}$.'
                    },
                    {
                        title: 'Bab 4: Impuls, Momentum & Tumbukan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Momentum:</strong> Momentum $\vec{p} = m \vec{v}$ mengukur kesukaran menghentikan benda bergerak. Impuls $\vec{I} = \vec{F} \Delta t = \Delta \vec{p}$ adalah perubahan momentum. Hukum Kekekalan Momentum berlaku jika $\Sigma \vec{F}_{\text{eksternal}} = 0$.',
                        visual: 'Impuls I = F · Δt = m(v₂ - v₁)  |  Koefisien Restitusi e = -(v₂\' - v₁\') / (v₂ - v₁)',
                        tips: 'Pada tumbukan tidak lenting sama sekali ($e = 0$), kedua benda bergabung dan bergerak dengan kecepatan akhir yang sama ($v_1\' = v_2\'$).',
                        contohSoal: '<strong>Soal 1:</strong> Bola A ($2\text{ kg}, 4\text{ m/s}$) menumbuk bola B ($3\text{ kg}$, diam) dan menyatu. Hitung kecepatan akhirnya.<br><strong>Langkah Penyelesaian:</strong><br>1. $(2 \cdot 4) + (3 \cdot 0) = (2 + 3) v\' \implies 8 = 5 v\' \implies v\' = \mathbf{1,6\text{ m/s}}$.'
                    },
                    {
                        title: 'Bab 5: Gerak Harmonis Sederhana & Ayunan Bandul',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Getaran:</strong> GHS adalah gerak bolak-balik periodik di sekitar titik setimbang akibat gaya pemulih yang berbanding lurus dengan simpangan ($F = -k x$).',
                        visual: 'Periode Pegas: T = 2π √(m/k)  |  Periode Bandul: T = 2π √(L/g)',
                        tips: 'Periode ayunan bandul sederhana HANYA bergantung pada panjang tali $L$ dan gravitasi $g$, tidak terpengaruh massa bandul!',
                        contohSoal: '<strong>Soal 1:</strong> Panjang tali bandul $0,98\text{ m}$ ($g = 9,8\text{ m/s}^2$). Hitung periodenya.<br><strong>Langkah Penyelesaian:</strong><br>1. $T = 2\pi \sqrt{\frac{0,98}{9,8}} = 2\pi \sqrt{0,1} \approx \mathbf{0,628\text{ detik}}$.'
                    },
                    {
                        title: 'Bab 6: Dinamika Rotasi & Kesetimbangan Benda Tegar',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Rotasi:</strong> Rotasi dipengaruhi oleh Momen Gaya (Torsi $\tau = F r \sin \theta$) dan Momen Inersia ($I = \sum m r^2$). Syarat kesetimbangan benda tegar: $\Sigma \vec{F} = 0$ dan $\Sigma \vec{\tau} = 0$.',
                        visual: 'Hukum II Rotasi: Στ = I · α  |  Momentum Sudut: L = I · ω (Kekal jika Στ = 0)',
                        tips: 'Batang homogen diputar di pusat: $I = \frac{1}{12} m L^2$. Batang diputar di ujung: $I = \frac{1}{3} m L^2$.',
                        contohSoal: '<strong>Soal 1:</strong> Momen gaya $20\text{ Nm}$ bekerja pada roda $I = 4\text{ kg m}^2$. Hitung percepatan sudutnya.<br><strong>Langkah Penyelesaian:</strong><br>1. $\alpha = \frac{\tau}{I} = \frac{20}{4} = \mathbf{5\text{ rad/s}^2}$.'
                    },
                    {
                        title: 'Bab 7: Fluida Statis: Hukum Pascal & Archimedes',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Fluida Diam:</strong> Tekanan hidrostatis $P = \rho g h$ bekerja secara seragam ke segala arah. Hukum Pascal menyatakan tekanan yang diberikan pada zat cair diteruskan sama besar. Hukum Archimedes menyatakan gaya apung $F_a = \rho_{\text{fluida}} V_{\text{celup}} g$.',
                        visual: 'Hukum Pascal: F₁ / A₁ = F₂ / A₂  |  Gaya Apung: F_a = ρ · V · g',
                        tips: 'Benda terapung memiliki gaya apung $F_a$ yang tepat sama dengan berat total benda $W$.',
                        contohSoal: '<strong>Soal 1:</strong> Dongkrak hidrolik $A_1 = 10\text{ cm}^2$ dan $A_2 = 200\text{ cm}^2$. Jika $F_1 = 50\text{ N}$, berapa $F_2$? <br><strong>Langkah Penyelesaian:</strong><br>1. $F_2 = \frac{A_2}{A_1} \cdot F_1 = \frac{200}{10} \cdot 50 = 20 \cdot 50 = \mathbf{1000\text{ N}}$.'
                    },
                    {
                        title: 'Bab 8: Fluida Dinamis & Persamaan Kontinuitas - Bernoulli',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Fluida Bergerak:</strong> Fluida ideal tidak kompresibel dan tanpa viskositas. Persamaan Kontinuitas $A_1 v_1 = A_2 v_2$ menyatakan kekekalan debit ($Q = A v$). Hukum Bernoulli $P + \frac{1}{2}\rho v^2 + \rho g h = \text{konstan}$ menyatakan kekekalan energi fluida.',
                        visual: 'Kontinuitas: A₁ v₁ = A₂ v₂  |  Bernoulli: P + ½ ρ v² + ρ g h = Konstan',
                        tips: 'Makin kecil penampang pipa, makin besar kelajuan fluida, dan makin kecil tekanan statis fluida tersebut!',
                        contohSoal: '<strong>Soal 1:</strong> Pipa $A_1 = 8\text{ cm}^2$ ($v_1 = 2\text{ m/s}$) menyempit ke $A_2 = 2\text{ cm}^2$. Hitung $v_2$.<br><strong>Langkah Penyelesaian:</strong><br>1. $v_2 = \frac{A_1}{A_2} \cdot v_1 = \frac{8}{2} \cdot 2 = \mathbf{8\text{ m/s}}$.'
                    },
                    {
                        title: 'Bab 9: Termodinamika & Mesin Carnot',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kalor & Usaha:</strong> Hukum I Termodinamika $Q = \Delta U + W$ adalah kekekalan energi. Mesin Carnot adalah mesin kalor reversibel ideal dengan efisiensi maksimum $\eta = (1 - \frac{T_2}{T_1}) \times 100\%$.',
                        visual: 'Efisiensi Carnot: η = (1 - T₂ / T₁) × 100%  (Wajib Suhu Kelvin: T_K = T_C + 273)',
                        tips: 'Selalu ubah satuan suhu ke Kelvin ($K$) sebelum dimasukkan ke dalam rumus termodinamika!',
                        contohSoal: '<strong>Soal 1:</strong> Mesin Carnot bekerja antara $T_1 = 600\text{ K}$ dan $T_2 = 300\text{ K}$. Hitung efisiensinya.<br><strong>Langkah Penyelesaian:</strong><br>1. $\eta = (1 - \frac{300}{600}) \times 100\% = (1 - 0,5) \times 100\% = \mathbf{50\%}$.'
                    },
                    {
                        title: 'Bab 10: Gelombang Bunyi & Efek Doppler Lanjut',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Gelombang:</strong> Bunyi adalah gelombang mekanik longitudinal. Efek Doppler menjelaskan pergeseran frekuensi terdengar $f_p$ akibat gerak relatif antara sumber dan pendengar: $f_p = \frac{v \pm v_p}{v \pm v_s} f_s$.',
                        visual: 'f_p = [(v ± v_p) / (v ± v_s)] · f_s  |  Intensitas Bunyi: TI = 10 log(I / I₀)',
                        tips: 'Pendengar Mendekat ($+v_p$), Sumber Mendekat ($-v_s$). Pendengar Menjauh ($-v_p$), Sumber Menjauh ($+v_s$).',
                        contohSoal: '<strong>Soal 1:</strong> Ambulans ($f_s = 640\text{ Hz}$) mendekati pendengar diam ($v = 340\text{ m/s}, v_s = 20\text{ m/s}$). Hitung $f_p$.<br><strong>Langkah Penyelesaian:</strong><br>1. $f_p = \frac{340 + 0}{340 - 20} \cdot 640 = \frac{340}{320} \cdot 640 = \mathbf{680\text{ Hz}}$.'
                    },
                    {
                        title: 'Bab 11: Listrik Searah (DC) & Hukum Kirchhoff',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Arus Listrik:</strong> Hukum Ohm $V = I R$. Hukum I Kirchhoff (arus masuk node = arus keluar). Hukum II Kirchhoff ($\Sigma E + \Sigma (I R) = 0$) menyatakan kekekalan energi dalam loop tertutup.',
                        visual: 'Seri: R_total = R₁ + R₂  |  Paralel: 1/R_total = 1/R₁ + 1/R₂',
                        tips: 'Hambatan paralel selalu menghasilkan hambatan pengganti yang lebih kecil dari nilai hambatan terkecilnya.',
                        contohSoal: '<strong>Soal 1:</strong> $R_1 = 3\,\Omega$ dan $R_2 = 6\,\Omega$ diparalelkan pada baterai $12\text{ V}$. Hitung arus total.<br><strong>Langkah Penyelesaian:</strong><br>1. $R_p = \frac{3 \cdot 6}{3 + 6} = 2\,\Omega$.<br>2. Arus $I = \frac{V}{R_p} = \frac{12}{2} = \mathbf{6\text{ Ampere}}$.'
                    },
                    {
                        title: 'Bab 12: Listrik Statis, Medan Listrik & Kapasitor',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Muatan Listrik:</strong> Hukum Coulomb $F = k \frac{q_1 q_2}{r^2}$. Medan listrik $E = k \frac{q}{r^2}$. Kapasitor menyimpan muatan $Q = C V$ dan energi $W = \frac{1}{2} C V^2$.',
                        visual: 'Hukum Coulomb: F = k (q₁ q₂) / r²  |  Kapasitansi keping sejajar: C = ε₀ A / d',
                        tips: 'Jika jarak $r$ antara dua muatan diperbesar 2 kali, gaya Coulomb berkurang menjadi $\frac{1}{4}$ kali semula!',
                        contohSoal: '<strong>Soal 1:</strong> Muatan $q_1 = 2\,\mu\text{C}$ dan $q_2 = 3\,\mu\text{C}$ berjarak $0,3\text{ m}$ ($k = 9 \times 10^9$). Hitung gaya $F$.<br><strong>Langkah Penyelesaian:</strong><br>1. $F = \frac{9 \times 10^9 \cdot (2 \times 10^{-6}) \cdot (3 \times 10^{-6})}{(0,3)^2} = \frac{0,054}{0,09} = \mathbf{0,6\text{ N}}$.'
                    },
                    {
                        title: 'Bab 13: Medan Magnet & Induksi Elektromagnetik Faraday',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Magnetisme:</strong> Arus listrik menimbulkan medan magnet $B$. Muatan bergerak dalam medan magnet mengalami Gaya Lorentz $F = B I L \sin \theta$. Perubahan fluks magnetik menimbulkan GGL Induksi $E = -N \frac{\Delta \Phi}{\Delta t}$ (Hukum Faraday).',
                        visual: 'Gaya Lorentz: F = B · I · L sin θ  |  GGL Induksi Faraday: E = -N (ΔΦ / Δt)',
                        tips: 'Gunakan Aturan Tangan Kanan: Ibu jari = Arus ($I$), Jari-jari = Medan Magnet ($B$), Telapak tangan = Gaya Lorentz ($F$).',
                        contohSoal: '<strong>Soal 1:</strong> Kawat $L = 2\text{ m}$ berarus $I = 5\text{ A}$ dalam medan $B = 0,4\text{ T}$ tegak lurus. Hitung $F$.<br><strong>Langkah Penyelesaian:</strong><br>1. $F = B I L \sin 90^\circ = 0,4 \cdot 5 \cdot 2 \cdot 1 = \mathbf{4\text{ N}}$.'
                    },
                    {
                        title: 'Bab 14: Rangkaian Listrik Bolak-Balik (AC) & Resonansi RLC',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Arus AC:</strong> Tegangan dan arus AC bervariasi secara sinusoidal. Impedansi total $Z = \sqrt{R^2 + (X_L - X_C)^2}$. Resonansi terjadi saat $X_L = X_C$, menghasilkan frekuensi resonansi $f = \frac{1}{2\pi \sqrt{L C}}$.',
                        visual: 'Impedansi: Z = √(R² + (X_L - X_C)²)  |  Frekuensi Resonansi: f = 1 / (2π √(LC))',
                        tips: 'Saat terjadi resonansi RLC, hambatan total bernilai minimum ($Z = R$) dan arus listrik bernilai maksimum!',
                        contohSoal: '<strong>Soal 1:</strong> Rangkaian RLC memiliki $R = 30\,\Omega, X_L = 80\,\Omega, X_C = 40\,\Omega$. Hitung $Z$.<br><strong>Langkah Penyelesaian:</strong><br>1. $Z = \sqrt{30^2 + (80 - 40)^2} = \sqrt{900 + 1600} = \sqrt{2500} = \mathbf{50\,\Omega}$.'
                    },
                    {
                        title: 'Bab 15: Fisika Modern, Efek Fotolistrik & Relativitas',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kuantum & Relativitas:</strong> Cahaya memiliki dualisme gelombang-partikel. Efek fotolistrik membuktikan cahaya sebagai paket energi foton $E = h f$. Teori Relativitas Khusus Einstein membatasi kecepatan maksimum universal pada $c$.',
                        visual: 'Energi Foton: E = h · f  |  Relativitas Massa: m = m₀ / √(1 - v²/c²)  |  E = m c²',
                        tips: 'Efek fotolistrik HANYA terjadi jika frekuensi foton memancar melebihi frekuensi ambang ($f > f_0$) logam target!',
                        contohSoal: '<strong>Soal 1:</strong> Hitung energi foton dengan frekuensi $5 \times 10^{14}\text{ Hz}$ ($h = 6,63 \times 10^{-34}\text{ J s}$).<br><strong>Langkah Penyelesaian:</strong><br>1. $E = h f = 6,63 \times 10^{-34} \cdot (5 \times 10^{14}) = \mathbf{3,315 \times 10^{-19}\text{ Joule}}$.'
                    }
                ],
                'kim': [
                    {
                        title: 'Bab 1: Struktur Atom, Konfigurasi spdf & Sistem Periodik',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Teori Kuantum:</strong> Atom terdiri dari inti (proton + neutron) dan awan elektron. Konfigurasi elektron subkulit ditentukan berdasarkan mekanika kuantum melalui 3 aturan dasar: (1) Prinsip Aufbau (pengisian dari tingkat energi terendah), (2) Kaidah Hund (elektron mengisi orbital sejajar sebelum berpasangan), dan (3) Larangan Pauli (tidak ada 2 elektron dengan 4 bilangan kuantum yang sama).',
                        visual: 'Subkulit: s(2), p(6), d(10), f(14)  |  Golongan = Jumlah Elektron Valensi  |  Periode = Kulit Utama Terbesar (n)',
                        tips: 'Untuk unsur transisi blok-$d$, golongan ditentukan dari jumlah elektron di subkulit $(n)s + (n-1)d$. Jika totalnya 8, 9, 10 $\implies$ Golongan VIII B. Jika 11 $\implies$ I B. Jika 12 $\implies$ II B.',
                        contohSoal: '<strong>Soal 1:</strong> Tentukan letak golongan dan periode dari unsur $_{26}\text{Fe}$.<br><strong>Langkah Penyelesaian:</strong><br>1. Konfigurasi $_{26}\text{Fe} = [\text{Ar}]\, 4s^2\, 3d^6$.<br>2. Kulit terbesar $n=4 \implies \mathbf{\text{Periode 4}}$.<br>3. Elektron valensi $4s^2 + 3d^6 = 8 \implies \mathbf{\text{Golongan VIII B}}$.'
                    },
                    {
                        title: 'Bab 2: Ikatan Kimia, Bentuk Molekul VSEPR & Kepolaran',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Ikatan:</strong> Atom berikatan untuk mencapai konfigurasi stabil oktet (8 elektron valensi). Ikatan ionik terjadi melalui serah terima elektron. Ikatan kovalen terjadi via pemakaian bersama elektron. Geometri molekul ditentukan oleh Tolakan Pasangan Elektron Valensi (VSEPR).',
                        visual: 'AX₂ = Linear  |  AX₃ = Trigonal Planar  |  AX₄ = Tetrahedral  |  AX₂E₂ = Bengkok (V)',
                        tips: 'Molekul simetris tanpa Pasangan Elektron Bebas (PEB) pada atom pusat bersifat **Nonpolar**.',
                        contohSoal: '<strong>Soal 1:</strong> Tentukan tipe geometri molekul $\text{CH}_4$ (Atom pusat C punya 4 elektron valensi berikatan dengan 4 H).<br><strong>Langkah Penyelesaian:</strong><br>1. Pasangan terikat $X = 4$. PEB $E = \frac{4-4}{2} = 0$. Tipe $\text{AX}_4 = \mathbf{\text{Tetrahedral}}$.'
                    },
                    {
                        title: 'Bab 3: Stoikiometri, Konsep Mol & Pereaksi Pembatas',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kuantitatif Kimia:</strong> Mol adalah satuan jumlah zat ($n = m / M_r$). Stoikiometri menghubungkan mol reaktan dan produk berdasarkan koefisien reaksi setara.',
                        visual: 'n = m / Mr  |  V_STP (0°C, 1atm) = n × 22,4 L  |  Molaritas M = n / V(L)',
                        tips: 'Bagi jumlah mol masing-masing reaktan dengan koefisien reaksinya. Nilai terkecil menjadi **Pereaksi Pembatas** yang menentukan jumlah produk!',
                        contohSoal: '<strong>Soal 1:</strong> Berapakah volume dari $0,25\text{ mol}$ gas $\text{O}_2$ pada keadaan STP?<br><strong>Langkah Penyelesaian:</strong><br>1. $V = n \times 22,4 = 0,25 \times 22,4 = \mathbf{5,6\text{ Liter}}$.'
                    },
                    {
                        title: 'Bab 4: Termokimia, Entalpi & Hukum Hess',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kalor Kimia:</strong> Termokimia mengukur perubahan entalpi $\Delta H$. Reaksi eksoterm melepaskan kalor ($\Delta H < 0$). Reaksi endoterm menyerap kalor ($\Delta H > 0$). Hukum Hess menyatakan $\Delta H$ hanya bergantung pada keadaan awal dan akhir.',
                        visual: 'ΔH_reaksi = Σ ΔH°f(produk) - Σ ΔH°f(pereaksi)  |  Hukum Hess: ΔH total = ΔH₁ + ΔH₂',
                        tips: 'Jika suatu persamaan reaksi dibalik, tanda $\Delta H$ harus dibalik (+ menjadi -). Jika koefisien dikali $n$, nilai $\Delta H$ juga dikali $n$.',
                        contohSoal: '<strong>Soal 1:</strong> $\Delta H^\circ_f \text{ CO}_2 = -393,5\text{ kJ/mol}$. Hitung kalor yang dilepas saat membakar $12\text{ gram}$ Karbon ($A_r = 12$).<br><strong>Langkah Penyelesaian:</strong><br>1. $\text{mol C} = 12/12 = 1\text{ mol}$. Kalor dilepas $= \mathbf{393,5\text{ kJ}}$.'
                    },
                    {
                        title: 'Bab 5: Laju Reaksi, Teori Tumbukan & Orde Reaksi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kinetika Kimia:</strong> Laju reaksi $V = k [\text{A}]^m [\text{B}]^n$ diukur dari berkurangnya konsentrasi reaktan per detik. Katalis mempercepat laju reaksi dengan cara menyediakan jalur alternatif ber-Energi Aktivasi ($E_a$) lebih rendah.',
                        visual: 'Persamaan Laju: V = k [A]ᵐ [B]ⁿ  |  Orde Total = m + n',
                        tips: 'Jika konsentrasi dinaikkan $x$ kali menyebabkan laju naik $y$ kali, ordenya $m$ memenuhi $x^m = y$.',
                        contohSoal: '<strong>Soal 1:</strong> Jika konsentrasi A dinaikkan 2 kali membuat laju naik 4 kali, berapa orde reaksi terhadap A?<br><strong>Langkah Penyelesaian:</strong><br>1. $2^m = 4 \implies m = \mathbf{2\text{ (Orde 2)}}$.'
                    },
                    {
                        title: 'Bab 6: Kesetimbangan Kimia & Asas Le Chatelier',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kesetimbangan Dinamis:</strong> Kesetimbangan terjadi saat laju reaksi maju sama dengan laju reaksi balik. Asas Le Chatelier: jika sistem kesetimbangan diberi aksi, sistem akan bergeser meminimalkan pengaruh aksi tersebut.',
                        visual: 'K_c = [Produk]ⁿ / [Reaktan]ᵐ  (Hanya fasa Gas g dan Larutan aq)',
                        tips: 'Jika suhu DITAIKKAN, kesetimbangan selalu bergeser ke arah reaksi **Endoterm** ($\Delta H$ positif).',
                        contohSoal: '<strong>Soal 1:</strong> Reaksi $\text{N}_2 + 3\text{H}_2 \rightleftharpoons 2\text{NH}_3$ ($\Delta H = -92\text{ kJ}$). Agar produk $\text{NH}_3$ bertambah, suhu harus?<br><strong>Langkah Penyelesaian:</strong> Reaksi pembentukan $\text{NH}_3$ eksoterm, maka suhu harus **Diturunkan**.'
                    },
                    {
                        title: 'Bab 7: Larutan Asam-Basa, Derajat pH & Indikator',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Asam Basa:</strong> Menurut Arrhenius, asam menghasilkan $\text{H}^+$ dan basa menghasilkan $\text{OH}^-$. Nilai $\text{pH} = -\log[\text{H}^+]$. Asam kuat terionisasi sempurna ($\alpha = 1$), asam lemah terionisasi sebagian ($K_a$).',
                        visual: 'Asam Kuat: [H⁺] = M × valensi  |  Asam Lemah: [H⁺] = √(K_a × M)',
                        tips: 'Pada suhu $25^\circ\text{C}$, $\text{pH} + \text{pOH} = 14$.',
                        contohSoal: '<strong>Soal 1:</strong> Hitung pH larutan $\text{CH}_3\text{COOH } 0,1\text{ M}$ ($K_a = 10^{-5}$).<br><strong>Langkah Penyelesaian:</strong><br>1. $[\text{H}^+] = \sqrt{10^{-5} \cdot 0,1} = \sqrt{10^{-6}} = 10^{-3}\text{ M}$.<br>2. $\text{pH} = -\log(10^{-3}) = \mathbf{3}$.'
                    },
                    {
                        title: 'Bab 8: Larutan Penyangga (Buffer) & Kapasitas Penyangga',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Buffer:</strong> Larutan buffer mampu mempertahankan nilai pH dari penambahan sedikit asam, basa, atau pengenceran. Terdiri dari campuran asam lemah + basa konjugasinya.',
                        visual: 'Buffer Asam: [H⁺] = K_a × (mol Asam Lemah / mol Basa Konjugasi)',
                        tips: 'Jika reaksi antara asam lemah dan basa kuat menyisakan **SISA ASAM LEMAH**, maka terbentuk larutan buffer!',
                        contohSoal: '<strong>Soal 1:</strong> $0,1\text{ mol CH}_3\text{COOH}$ ($K_a = 10^{-5}$) dicampur dengan $0,01\text{ mol CH}_3\text{COONa}$. Hitung pH.<br><strong>Langkah Penyelesaian:</strong><br>1. $[\text{H}^+] = 10^{-5} \cdot \frac{0,1}{0,01} = 10^{-4}\text{ M} \implies \text{pH} = -\log(10^{-4}) = \mathbf{4}$.'
                    },
                    {
                        title: 'Bab 9: Hidrolisis Garam & Sifat Asam-Basa Garam',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Hidrolisis:</strong> Hidrolisis adalah reaksi kation/anion garam dengan air. Garam dari asam lemah + basa kuat mengalami hidrolisis sebagian bersifat basa ($\text{pH} > 7$).',
                        visual: 'Garam Basa: [OH⁻] = √( (K_w / K_a) × M_garam )',
                        tips: 'Garam dari asam kuat dan basa kuat TIDAK mengalami hidrolisis ($\text{pH} = 7$ netral).',
                        contohSoal: '<strong>Soal 1:</strong> Hitung $[\text{OH}^-]$ larutan $\text{CH}_3\text{COONa } 0,1\text{ M}$ ($K_w = 10^{-14}, K_a = 10^{-5}$).<br><strong>Langkah Penyelesaian:</strong><br>1. $[\text{OH}^-] = \sqrt{\frac{10^{-14}}{10^{-5}} \cdot 0,1} = \sqrt{10^{-10}} = \mathbf{10^{-5}\text{ M}}$.'
                    },
                    {
                        title: 'Bab 10: Kelarutan & Hasil Kali Kelarutan (Ksp)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Ksp:</strong> $K_{sp}$ adalah konstanta kesetimbangan larutan jenuh dari garam yang sukar larut. Jika $Q_{sp} > K_{sp}$, terjadi endapan.',
                        visual: 'Garam AX₂ ⇌ A²⁺ + 2X⁻  ⇒  Ksp = 4s³',
                        tips: 'Penambahan ion sejenis akan menggeser kesetimbangan ke kiri dan MENURUNKAN kelarutan zat.',
                        contohSoal: '<strong>Soal 1:</strong> Kelarutan $\text{AgCl}$ dalam air $= 10^{-5}\text{ M}$. Hitung $K_{sp} \text{ AgCl}$.<br><strong>Langkah Penyelesaian:</strong><br>1. $K_{sp} = s \cdot s = (10^{-5})^2 = \mathbf{10^{-10}}$.'
                    },
                    {
                        title: 'Bab 11: Sifat Koligatif Larutan & Hukum Raoult',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Koligatif:</strong> Sifat koligatif HANYA bergantung pada jumlah partikel zat terlarut, tidak bergantung pada jenisnya. Meliputi: penurunan tekanan uap, kenaikan titik didih, penurunan titik beku, dan tekanan osmotik.',
                        visual: 'ΔTb = m · Kb · i  |  ΔTf = m · Kf · i  |  Tekanan Osmotik: π = M · R · T · i',
                        tips: 'Untuk larutan elektrolit, selalu sertakan faktor van\'t Hoff $i = 1 + (n - 1)\alpha$!',
                        contohSoal: '<strong>Soal 1:</strong> Hitung $\Delta T_b$ larutan $1\text{ mol}$ glukosa non-elektrolit dalam $1\text{ kg}$ air ($K_b = 0,52^\circ\text{C/m}$).<br><strong>Langkah Penyelesaian:</strong><br>1. $\Delta T_b = m \cdot K_b \cdot 1 = 1 \cdot 0,52 = \mathbf{0,52^\circ\text{C}}$.'
                    },
                    {
                        title: 'Bab 12: Reaksi Redoks & Penyetaraan Bilangan Oksidasi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Redoks:</strong> Oksidasi adalah kenaikan biloks (pelepasan elektron). Reduksi adalah penurunan biloks (penerimaan elektron). Oksidator adalah zat yang mengalami reduksi.',
                        visual: 'Oksidator (Mengalami Reduksi)  |  Reduktor (Mengalami Oksidasi)',
                        tips: 'Bilangan oksidasi unsur bebas (seperti $\text{O}_2, \text{Fe}, \text{H}_2$) selalu bernilai nol ($0$)!',
                        contohSoal: '<strong>Soal 1:</strong> Tentukan biloks Mangan ($\text{Mn}$) dalam senyawa $\text{KMnO}_4$.<br><strong>Langkah Penyelesaian:</strong><br>1. (+1) + Mn + 4(-2) = 0 ⇒ 1 + Mn - 8 = 0 ⇒ $\mathbf{\text{Mn} = +7}$.'
                    },
                    {
                        title: 'Bab 13: Sel Volta, Deret Volta & Korosi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Sel Volta:</strong> Sel Volta mengubah energi kimia spontan menjadi energi listrik. Katode (reduksi, $+$) dan Anode (oksidasi, $-$). Potensial sel $E^\circ_{\text{sel}} = E^\circ_{\text{katode}} - E^\circ_{\text{anode}}$.',
                        visual: 'Jembatan Keledai KRAO: Katode Reduksi, Anode Oksidasi  |  E°sel = E°katode - E°anode',
                        tips: 'Logam dengan $E^\circ$ lebih positif berada di katode dan bertindak sebagai oksidator.',
                        contohSoal: '<strong>Soal 1:</strong> $E^\circ \text{Zn}^{2+}/\text{Zn} = -0,76\text{ V}, E^\circ \text{Cu}^{2+}/\text{Cu} = +0,34\text{ V}$. Hitung $E^\circ_{\text{sel}}$.<br><strong>Langkah Penyelesaian:</strong><br>1. $E^\circ_{\text{sel}} = +0,34 - (-0,76) = \mathbf{+1,10\text{ Volt}}$.'
                    },
                    {
                        title: 'Bab 14: Sel Elektrolisis & Hukum Faraday I - II',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Elektrolisis:</strong> Sel elektrolisis menggunakan energi listrik untuk menjalankan reaksi redoks tidak spontan. Hukum Faraday I: massa zat terendap $W = \frac{e \cdot I \cdot t}{96500}$.',
                        visual: 'W = (e · I · t) / 96500  |  Massa Ekuivalen e = Ar / Valensi',
                        tips: 'Di katode, kation logam aktif Golongan IA, IIA, Al, Mn pada larutan tidak tereduksi, melainkan air ($\text{H}_2\text{O}$) yang tereduksi menjadi gas $\text{H}_2$!',
                        contohSoal: '<strong>Soal 1:</strong> Hitung massa Cu ($A_r = 63,5$, valensi 2) terendap jika arus $10\text{ A}$ mengalir $965\text{ detik}$.<br><strong>Langkah Penyelesaian:</strong><br>1. $W = \frac{(63,5/2) \cdot 10 \cdot 965}{96500} = 31,75 \cdot 0,1 = \mathbf{3,175\text{ gram}}$.'
                    },
                    {
                        title: 'Bab 15: Kimia Organik, Tata Nama Alkana & Gugus Fungsi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kimia Karbon:</strong> Hidrokarbon terbagi atas alkana, alkena, dan alkuna. Gugus fungsi menentukan sifat spesifik: Alkohol ($-\text{OH}$), Eter ($-\text{O}-$), Aldehid ($-\text{CHO}$), Keton ($-\text{CO}-$), Asam Karboksilat ($-\text{COOH}$), Ester ($-\text{COO}-$).',
                        visual: 'Alkohol & Eter (Isomer Fungsi C_n H_2n+2 O)  |  Asam Karboksilat & Ester (Isomer Fungsi C_n H_2n O₂)',
                        tips: 'Uji Fehling/Tollens digunakan untuk membedakan Aldehid (positif mengendap) dan Keton (negatif).',
                        contohSoal: '<strong>Soal 1:</strong> Senyawa $\text{CH}_3-\text{COOH}$ tergolong ke dalam gugus fungsi apakah?<br><strong>Langkah Penyelesaian:</strong> Tergolong **Asam Karboksilat**.'
                    }
                ],
                'bio': [
                    {
                        title: 'Bab 1: Organel Sel, Struktur Membran & Transpor',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep & Biokimia Membran:</strong> Sel dilapisi oleh membran plasma berstruktur *Fluid Mosaic Model* (lapisan ganda fosfolipid dengan protein integral dan perifer). Transpor pasif (difusi & osmosis) bergerak spontan sesuai gradien konsentrasi tanpa energi ATP. Transpor aktif (pompa $\text{Na}^+/\text{K}^+$, endositosis, eksositosis) melawan gradien konsentrasi dan memerlukan ATP.',
                        visual: 'Osmosis: Pelarut (Air) dari Hipotonis (Encer) → Hipertonis (Pekat)  |  Sel Hewan di Hipertonis = Krenasi  |  Sel Tumbuhan = Plasmolisis',
                        tips: 'Sel tumbuhan tidak mengalami lisis/pecah di larutan hipotonis karena ditahan oleh struktur dinding sel berbahan selulosa yang memiliki tekanan turgor tinggi.',
                        contohSoal: '<strong>Soal 1:</strong> Mengapa eritrosit pecah (hemolisis) saat diletakkan di dalam aquades (air murni)?<br><strong>Langkah Penyelesaian:</strong><br>1. Aquades bersifat hipotonis dibanding sitoplasma eritrosit.<br>2. Air masuk secara osmosis ke dalam sel hingga membran plasma yang elastis melebihi batas batas toleransinya dan pecah ($\mathbf{\text{Hemolisis}}$).'
                    },
                    {
                        title: 'Bab 2: Biokimia Enzim & Bioenergetika Sel',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kinetika Enzim:</strong> Enzim adalah biokatalisator protein yang mempercepat reaksi biokimia dengan cara menurunkan energi aktivasi ($E_a$). Bekerja spesifik berdasarkan teori *Lock and Key* dan *Induced Fit*.',
                        visual: 'Faktor Enzim: Suhu Optima, pH, Konsentrasi Substrat, Inhibitor Kompetitif vs Non-Kompetitif',
                        tips: 'Inhibitor kompetitif dapat diatasi dengan MENAMBAH konsentrasi substrat hingga melimpah.',
                        contohSoal: '<strong>Soal 1:</strong> Apa yang terjadi jika enzim dipanaskan di atas suhu $60^\circ\text{C}$?<br><strong>Langkah Penyelesaian:</strong> Enzim mengalami **Denaturasi** (kerusakan struktur tersier protein).'
                    },
                    {
                        title: 'Bab 3: Katabolisme Karbohidrat: Respirasi Aerob & Anaerob',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Respirasi Sel:</strong> Respirasi aerob memecah 1 molekul glukosa menjadi $\text{CO}_2, \text{H}_2\text{O}$, dan $36-38\text{ ATP}$ melalui 4 tahap: (1) Glikolisis (Sitosol), (2) Dekarboksilasi Oksidatif (Matriks Mitokondria), (3) Siklus Krebs (Matriks Mitokondria), dan (4) Transpor Elektron (Krista Mitokondria).',
                        visual: 'Glikolisis (Sitosol) → DO & Krebs (Matriks Mitokondria) → Transpor Elektron (Krista)',
                        tips: 'Akseptor elektron terakhir pada rantai transpor elektron respirasi aerob adalah molekul **Oksigen ($\text{O}_2$)**.',
                        contohSoal: '<strong>Soal 1:</strong> Di manakah tempat berlangsungnya Siklus Krebs dalam sel hewan?<br><strong>Langkah Penyelesaian:</strong> Berlangsung di dalam **Matriks Mitokondria**.'
                    },
                    {
                        title: 'Bab 4: Anabolisme: Fotosintesis Reaksi Terang & Gelap',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Bioenergetika Tumbuhan:</strong> Fotosintesis mengubah energi foton cahaya menjadi energi kimia glukosa. Reaksi Terang (Tilakoid) menghasilkan ATP, NADPH, dan $\text{O}_2$. Reaksi Gelap/Siklus Calvin (Stroma) mengikat $\text{CO}_2$ menjadi gula.',
                        visual: 'Reaksi Terang (Grana/Tilakoid) + Reaksi Gelap (Stroma Kloroplas)',
                        tips: 'Fotolisis air ($\text{H}_2\text{O} \to 2\text{H}^+ + 2e^- + \frac{1}{2}\text{O}_2$) terjadi pada **Reaksi Terang** di Fotosistem II.',
                        contohSoal: '<strong>Soal 1:</strong> Di manakah tempat terjadinya sintesis glukosa dalam kloroplas?<br><strong>Langkah Penyelesaian:</strong> Berlangsung di dalam **Stroma** (Reaksi Gelap).'
                    },
                    {
                        title: 'Bab 5: Genetik, Struktur DNA, RNA & Sintesis Protein',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Ekspresi Gen:</strong> DNA berbentuk heliks ganda tersusun atas nukleotida (Gula Deoksiribosa, Fosfat, Basa Nitrogen). Sintesis protein terdiri atas Transkripsi (DNA $\to$ mRNA di inti sel) dan Translasi (mRNA $\to$ Asam Amino di ribosom).',
                        visual: 'Pasangan Basa DNA: Adenin-Timin (2 Ikatan H), Guanin-Sitosin (3 Ikatan H)  |  RNA: Timin diganti Urasil',
                        tips: 'Rantai mRNA komplementer dibentuk dari rantai cetakan DNA Antisense (Template).',
                        contohSoal: '<strong>Soal 1:</strong> Tentukan urutan mRNA dari cetakan DNA antisense 3\'-TAC GGC-5\'.<br><strong>Langkah Penyelesaian:</strong> mRNA = 5\'-**AUG CCG**-3\'.'
                    },
                    {
                        title: 'Bab 6: Pembelahan Sel: Mitosis, Meiosis & Gametogenesis',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pembelahan Sel:</strong> Mitosis menghasilkan 2 sel anakan diploid ($2n$) identik untuk pertumbuhan. Meiosis menghasilkan 4 sel anakan haploid ($n$) bermutasi untuk pembentukan sel kelamin (gamet).',
                        visual: 'Tahapan: Profase → Metafase (Kromosom di Equator) → Anafase (Kromatid Berpisah) → Telofase',
                        tips: 'Pindah silang (*crossing over*) genetik yang memicu variasi keturunan terjadi pada fase **Profase I Meiosis I**.',
                        contohSoal: '<strong>Soal 1:</strong> Pada fase manakah kromosom berjejer di bidang pembelahan sel?<br><strong>Langkah Penyelesaian:</strong> Terjadi pada fase **Metafase**.'
                    },
                    {
                        title: 'Bab 7: Hukum Mendel & Persilangan Monohibrid - Dihibrid',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Genetika Mendel:</strong> Hukum I Mendel (Segregasi Bebas) dan Hukum II Mendel (Asortasi Bebas). Rasio fenotip F2 monohibrid dominan-resesif $= 3 : 1$. Rasio dihibrid heterozigot $= 9 : 3 : 3 : 1$.',
                        visual: 'Persilangan Dihibrid Heterozigot (AaBb × AaBb) ⇒ Rasio Fenotip 9 : 3 : 3 : 1',
                        tips: 'Jumlah macam gamet dari suatu genotip dapat dihitung dengan rumus $2^n$ di mana $n$ adalah jumlah pasangan heterozigot.',
                        contohSoal: '<strong>Soal 1:</strong> Berapa macam gamet yang dihasilkan dari individu bergenotip AaBbCcDD?<br><strong>Langkah Penyelesaian:</strong> Pasangan heterozigot ada 3 (Aa, Bb, Cc). Jumlah gamet $= 2^3 = \mathbf{8\text{ macam}}$.'
                    },
                    {
                        title: 'Bab 8: Penyimpangan Semu Hukum Mendel & Hereditas',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Interaksi Gen:</strong> Modifikasi rasio klasik Mendel $9:3:3:1$ akibat interaksi alel. Meliputi: Atavisme ($9:3:3:1$), Kriptomeri ($9:3:4$), Epistasis-Hipostasis ($12:3:1$), dan Polimeri ($15:1$).',
                        visual: 'Epistasis Dominan = 12 : 3 : 1  |  Kriptomeri = 9 : 3 : 4  |  Polimeri = 15 : 1',
                        tips: 'Pada epistasis dominan, keberadaan satu gen dominan epistasis akan menutup ekspresi gen hipostatis lainnya.',
                        contohSoal: '<strong>Soal 1:</strong> Persilangan kriptomeri bunga Linaria maroccana merah (Aabb) dan putih (aaBB) menghasilkan F1 ungu (AaBb). Rasio F2 fenotipnya adalah?<br><strong>Langkah Penyelesaian:</strong> Rasionya Ungu : Merah : Putih $= \mathbf{9 : 3 : 4}$.'
                    },
                    {
                        title: 'Bab 9: Pola Hereditas Manusia & Golongan Darah ABO',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pewarisan Sifat:</strong> Pewarisan terikat kromosom seks X (Buta Warna, Hemofilia) dan autosom (Albinisme, Golongan Darah ABO/Rhesus).',
                        visual: 'Golongan Darah ABO: Iᴬ, Iᴮ (Kodominan), Iᴼ (Resesif)  |  Hemofilia: Xᴴ, Xʰ',
                        tips: 'Pria tidak bisa menjadi *carrier* (pembawa) penyakit hemofilia atau buta warna. Pria hanya bisa normal ($X^H Y$) atau sakit ($X^h Y$).',
                        contohSoal: '<strong>Soal 1:</strong> Pasangan A heterozigot ($I^A I^O$) dan B heterozigot ($I^B I^O$) dapat memiliki anak bergolongan darah?<br><strong>Langkah Penyelesaian:</strong> Anak dapat bergolongan darah **A, B, AB, atau O** (semua mungkin).'
                    },
                    {
                        title: 'Bab 10: Mutasi Gen & Mutasi Kromosom (Aneuploidi)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Perubahan Genetik:</strong> Mutasi adalah perubahan materi genetik. Mutasi gen (substitusi, substitusi nonsens/misens). Mutasi kromosom (delesi, duplikasi, inversi, translokasi, aneuploidi).',
                        visual: 'Sindrom Down = Trisomi Kromosom Nomor 21 (47, XX/XY +21)',
                        tips: 'Sindrom Turner memiliki karyotipe $45, XO$ (Monosomi kromosom seks X).',
                        contohSoal: '<strong>Soal 1:</strong> Apakah penyebab mutasi pada penderita Sindrom Klinefelter ($47, XXY$)?<br><strong>Langkah Penyelesaian:</strong> Akibat peristiwa *Nondisjunction* (gagal berpisah) kromosom seks saat pembentukan gamet.'
                    },
                    {
                        title: 'Bab 11: Teori Evolusi, Seleksi Alam & Hukum Hardy-Weinberg',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Evolusi Populasi:</strong> Evolusi adalah perubahan frekuensi alel populasi dari generasi ke generasi. Teori Darwin menekankan Seleksi Alam. Hukum Hardy-Weinberg: $p + q = 1$ dan $p^2 + 2pq + q^2 = 1$.',
                        visual: 'Hardy-Weinberg: p + q = 1  |  p² (Homozigot Dominan) + 2pq (Heterozigot) + q² (Homozigot Resesif) = 1',
                        tips: 'Selalu hitung nilai frekuensi alel resesif $q = \sqrt{q^2}$ terlebih dahulu dari persentase fenotip resesif!',
                        contohSoal: '<strong>Soal 1:</strong> Dalam populasi, $16\%$ penduduk albino ($q^2 = 0,16$). Hitung frekuensi alel resesif $q$.<br><strong>Langkah Penyelesaian:</strong><br>1. $q = \sqrt{0,16} = \mathbf{0,4}$.'
                    },
                    {
                        title: 'Bab 12: Bioteknologi Konvensional & Modern',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Rekayasa Hayati:</strong> Bioteknologi konvensional memanfaatkan mikroorganisme secara langsung (fermentasi). Bioteknologi modern memanfaatkan rekayasa genetika (DNA rekombinan, kloning, antibodi monoklonal).',
                        visual: 'Bioteknologi Modern: Pembuatan Insulin dengan Plasmid Bakteri E. coli',
                        tips: 'Pembuatan antibodi monoklonal menggunakan teknik **Hibridoma** (peleburan sel kanker dan sel limfosit B).',
                        contohSoal: '<strong>Soal 1:</strong> Jamur yang berperan dalam pembuatan tempe dari kedelai adalah?<br><strong>Langkah Penyelesaian:</strong> **Rhizopus oryzae**.'
                    },
                    {
                        title: 'Bab 13: Sistem Koordinasi: Saraf, Hormon & Indra',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Integrasi Tubuh:</strong> Sistem saraf mengatur respon cepat via sinyal impuls kelistrikan neuron. Sistem endokrin mengatur respon lambat via hormon darah. Otak besar (berpikir), Otak kecil (keseimbangan).',
                        visual: 'Alur Gerak Refleks: Reseptor → Neuron Sensorik → Sumsum Tulang Belakang → Neuron Motorik → Efektor',
                        tips: 'Hormon Insulin menurunkan kadar gula darah, sedangkan hormon Glukagon menaikkan kadar gula darah.',
                        contohSoal: '<strong>Soal 1:</strong> Bagian otak manakah yang berfungsi sebagai pusat koordinasi keseimbangan tubuh?<br><strong>Langkah Penyelesaian:</strong> Otak Kecil (**Cerebellum**).'
                    },
                    {
                        title: 'Bab 14: Ekosistem, Daur Biogeokimia & Suksesi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Ekologi:</strong> Interaksi komponen biotik dan abiotik. Daur biogeokimia (Nitrogen, Karbon, Air, Fosfor). Nitrifikasi: Amonium $\to$ Nitrit (Nitrosomonas) $\to$ Nitrat (Nitrobacter).',
                        visual: 'Nitrifikasi: Amonium → Nitrit (Nitrosomonas) → Nitrat (Nitrobacter)',
                        tips: 'Tumbuhan menyerap nitrogen dari dalam tanah utama dalam bentuk senyawa **Nitrat ($\text{NO}_3^-$)**.',
                        contohSoal: '<strong>Soal 1:</strong> Bakteri pada bintil akar tanaman kacang-kacangan yang mengikat nitrogen bebas adalah?<br><strong>Langkah Penyelesaian:</strong> **Rhizobium leguminosarum**.'
                    },
                    {
                        title: 'Bab 15: Imunologi & Sistem Pertahanan Tubuh',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Imunitas:</strong> Pertahanan non-spesifik (kulit, mukosa, fagositosis) dan spesifik (Limfosit B membentuk antibodi humoral, Limfosit T menyerang sel terinfeksi).',
                        visual: 'Limfosit B (Imunitas Humoral / Antibodi) vs Limfosit T (Imunitas Seluler)',
                        tips: 'Vaksinasi memberikan kekebalan **Aktif Buatan** dengan merangsang pembentukan sel memori spesifik.',
                        contohSoal: '<strong>Soal 1:</strong> Sel manakah yang secara spesifik memproduksi molekul antibodi?<br><strong>Langkah Penyelesaian:</strong> **Sel Plasma (Turunan Limfosit B)**.'
                    }
                ],
                'geo': [
                    {
                        title: 'Bab 1: Konsep Dasar & 4 Prinsip Utama Geografi',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Geospasial:</strong> Geografi adalah ilmu yang mempelajari persamaan dan perbedaan fenomena geosfer dengan sudut pandang kelingkungan dan kewilayahan. 4 Prinsip Geografi: (1) Persebaran/Distribusi, (2) Interelasi (keterkaitan sebab-akibat), (3) Deskripsi (penjelasan data/peta), dan (4) Korologi (perpaduan 3 prinsip).',
                        visual: 'Interelasi = Ada hubungan sebab-akibat (Misal: Penebangan hutan → Erosi banjir)',
                        tips: 'Jika soal menanyakan hubungan timbal balik antar 2 fenomena alami/sosial, kuncinya selalu **Prinsip Interelasi**.',
                        contohSoal: '<strong>Soal 1:</strong> Banjir di Jakarta terjadi akibat alih fungsi lahan hutan menjadi permukiman di kawasan Puncak Bogor. Prinsip geografi yang relevan adalah?<br><strong>Langkah Penyelesaian:</strong> Menggunakan **Prinsip Interelasi** karena menghubungkan fenomena hilir (banjir) dengan penyebab di hulu.'
                    },
                    {
                        title: 'Bab 2: Pemetaan, Skala & Sistem Informasi Geografis (SIG)',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Kartografi & SIG:</strong> Peta adalah gambaran permukaan bumi pada bidang datar yang diperkecil skala. Kontur Interval $CI = \frac{1}{2000} \times \text{Penyebut Skala}$. SIG mengolah data spasial via *Overlay* (tumpang tindih peta) dan *Buffering*.',
                        visual: 'Skala = Jarak Peta / Jarak Sebenarnya  |  CI = (1 / 2.000) × Penyebut Skala Utama',
                        tips: 'Makin besar penyebut angka skala, makin kecil cakupan detail geografis yang ditampilkan pada peta tersebut.',
                        contohSoal: '<strong>Soal 1:</strong> Jarak kota A-B pada peta $4\text{ cm}$, jarak sebenarnya $2\text{ km}$. Berapa skala petanya?<br><strong>Langkah Penyelesaian:</strong><br>1. Skala $= \frac{4\text{ cm}}{200.000\text{ cm}} = \frac{1}{50.000} \implies \mathbf{1 : 50.000}$.'
                    },
                    {
                        title: 'Bab 3: Penginderaan Jauh & Interpretasi Citra Satelit',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Akar Konsep Remote Sensing:</strong> Penginderaan jauh merekam objek bumi dari jarak jauh tanpa kontak langsung. 8 Unsur Interpretasi Citra: Rona/Warna, Bentuk, Ukuran, Tekstur, Pola, Bayangan, Situs, dan Asosiasi.',
                        visual: 'Unsur Utama Interpretasi: Rona (Tingkat Kecerahan) & Asosiasi (Keterkaitan Ciri Objek)',
                        tips: 'Lapangan bola sepak dikenali paling cepat dari bentuk persegi panjang dan asosiasi berupa gawang di kedua ujungnya.',
                        contohSoal: '<strong>Soal 1:</strong> Objek permukiman kumuh pada citra penginderaan jauh tampak bertekstur kasar dan pola tidak teratur. Unsur interpretasinya?<br><strong>Langkah Penyelesaian:</strong> Mengenali objek berdasarkan **Tekstur dan Pola**.'
                    },
                    {
                        title: 'Bab 4: Litosfer: Batuan, Tektonisme & Vulkanisme',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Lapisan Batuan:</strong> Litosfer adalah kulit bumi padat. Batuan beku, sedimen, metamorf. Pergerakan lempeng tektonik: Divergen (menjauh), Konvergen (tumbukan subduksi), Transform (geser).',
                        visual: 'Divergen (Menjauh)  |  Konvergen (Subduksi Tumbukan)  |  Transform (Sesar Geser)',
                        tips: 'Palung laut dan gunung api aktif terbentuk di sepanjang batas pergerakan lempeng **Konvergen** (Subduksi).',
                        contohSoal: '<strong>Soal 1:</strong> Pegunungan Himalaya terbentuk akibat jenis pergerakan lempeng tektonik apakah?<br><strong>Langkah Penyelesaian:</strong> Pergerakan **Konvergen (Tumbukan Lempeng Benua-Benua)**.'
                    },
                    {
                        title: 'Bab 5: Seismisitas & Bencana Gempa Bumi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kebencanaan Gempa:</strong> Gempa disebabkan pelepasan energi tektonik. Hiposentrum (pusat gempa di dalam bumi), Episentrum (pusat gempa di permukaan). Jarak episentrum dihitung dengan Rumus Laska: $\Delta = [(S - P) - 1\text{\'}] \times 1000\text{ km}$.',
                        visual: 'Rumus Laska: Δ = [ (S - P) - 1\' ] × 1.000 km  (S = Gelombang Sekunder, P = Primer)',
                        tips: 'Waktu $1\text{\'}$ dalam rumus Laska menyimbolkan $1\text{ menit}$.',
                        contohSoal: '<strong>Soal 1:</strong> Gelombang P tercatat $02.14\'00"$, gelombang S tercatat $02.17\'30"$. Hitung jarak episentrum $\Delta$.<br><strong>Langkah Penyelesaian:</strong><br>1. $(S - P) = 3\'30"$.<br>2. $\Delta = [(3\'30") - 1\text{\'}] \times 1000 = 2,5 \times 1000 = \mathbf{2500\text{ km}}$.'
                    },
                    {
                        title: 'Bab 6: Pedosfer: Pembentukan & Konservasi Tanah',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pelapukan Tanah:</strong> Pedosfer adalah lapisan tanah hasil pelapukan batuan induk. Profil tanah (Horizon O, A, B, C, R). Konservasi tanah mekanik (terasering), vegetatif (reboisasi, *contour plowing*).',
                        visual: 'Horizon O (Humus) → A (Topsoil) → B (Subsoil) → C (Batuan Lapuk) → R (Bedrock)',
                        tips: 'Terasering pada lereng curam sangat efektif menahan laju erosi dan tanah longsor.',
                        contohSoal: '<strong>Soal 1:</strong> Penanaman tanaman sejajar garis ketinggian tanah dinamakan teknik?<br><strong>Langkah Penyelesaian:</strong> **Contour Plowing**.'
                    },
                    {
                        title: 'Bab 7: Atmosfer: Cuaca, Iklim & Unsur Klimatologi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Udara & Iklim:</strong> Lapisan atmosfer (Troposfer, Stratosfer, Mesosfer, Termosfer). Menurut Hukum Moksche, setiap naik $100\text{ meter}$, suhu udara turun rata-rata $0,6^\circ\text{C}$.',
                        visual: 'Troposfer (Fenomena Cuaca)  |  Stratosfer (Lapisan Ozon)  |  Mesosfer (Penghancur Meteor)',
                        tips: 'Semua fenomena cuaca (hujan, awan, angin, petir) HANYA terjadi di lapisan **Troposfer**.',
                        contohSoal: '<strong>Soal 1:</strong> Suhu pantai ($0\text{ m}$) $27^\circ\text{C}$. Berapa suhu kota A di ketinggian $1.000\text{ meter}$?<br><strong>Langkah Penyelesaian:</strong><br>1. Penurunan $= \frac{1000}{100} \times 0,6 = 6^\circ\text{C}$.<br>2. Suhu $= 27 - 6 = \mathbf{21^\circ\text{C}}$.'
                    },
                    {
                        title: 'Bab 8: Hidrosfer: Siklus Air & Perairan Darat - Laut',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Daur Air:</strong> Siklus hidrologi (Evaporasi, Transpirasi, Kondensasi, Presipitasi, Infiltrasi). Zona laut berdasarkan kedalaman: Litoral, Neritik ($<200\text{ m}$), Batial, Abisal.',
                        visual: 'Zona Neritik (Kedalaman < 200 m, Terang Sinar Matahari, Paling Banyak Ikan & Terumbu Karang)',
                        tips: 'Zona Neritik paling kaya biota laut karena sinar matahari masih mampu menembus dasar perairan secara optimal.',
                        contohSoal: '<strong>Soal 1:</strong> Zona laut tempat hidup mayoritas terumbu karang dan ikan adalah?<br><strong>Langkah Penyelesaian:</strong> **Zona Neritik**.'
                    },
                    {
                        title: 'Bab 9: Biosfer: Bioma Dunia & Persebaran Flora-Fauna',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Ekosistem Dunia:</strong> Bioma dunia (Hutan Hujan Tropis, Taiga, Tundra, Savana, Gurun). Garis Wallace dan Weber membagi wilayah fauna Indonesia (Asiatis, Peralihan, Australis).',
                        visual: 'Asiatis (Harimau, Gajah) | Garis Wallace | Peralihan (Anoa, Komodo) | Garis Weber | Australis (Cenderawasih)',
                        tips: 'Anoa, Komodo, dan Babi Rusa adalah fauna khas endemik kawasan **Peralihan (Wallacea)**.',
                        contohSoal: '<strong>Soal 1:</strong> Fauna cenderawasih dan kakatua raja termasuk ke dalam tipe fauna?<br><strong>Langkah Penyelesaian:</strong> Tipe **Australis**.'
                    },
                    {
                        title: 'Bab 10: Antroposfer: Dinamika Penduduk & Proyeksi Demografi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Demografi:</strong> Kependudukan dianalisis dari Natalitas, Mortalitas, dan Migrasi. Piramida Penduduk: Muda (Ekspansif), Stasioner, Tua (Konstruktif). *Dependency Ratio* $= \frac{\text{Non-Produktif}}{\text{Produktif (15-64 thn)}} \times 100$.',
                        visual: 'Dependency Ratio = (Penduduk Usia Non-Produktif / Penduduk Usia Produktif) × 100',
                        tips: 'Bonus Demografi terjadi saat proporsi penduduk usia produktif ($15-64\text{ tahun}$) melimpah tinggi melebihi $60\%$.',
                        contohSoal: '<strong>Soal 1:</strong> Piramida penduduk berbentuk kerucut dengan alas lebar menunjukkan pertumbuhan penduduk?<br><strong>Langkah Penyelesaian:</strong> Pertumbuhan penduduk usia muda yang tinggi (**Piramida Ekspansif**).'
                    },
                    {
                        title: 'Bab 11: Geografi Desa & Kota serta Interaksi Spasial',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Interaksi Keruangan:</strong> Desa sebagai penyedia bahan mentah, kota sebagai pusat pelayanan. Teori Titik Henti (*Break-off Point*) menentukan lokasi ideal fasilitas pelayanan umum: $D_{TH} = \frac{d_{AB}}{1 + \sqrt{P_B / P_A}}$ ($P_A < P_B$).',
                        visual: 'Teori Titik Henti: D_TH = d_AB / (1 + √(P_B / P_A))',
                        tips: '$P_A$ pada rumus titik henti SELALU melambangkan jumlah penduduk kota yang lebih kecil!',
                        contohSoal: '<strong>Soal 1:</strong> Jarak A-B $= 30\text{ km}$. Penduduk A $= 10.000$, B $= 40.000$. Hitung titik henti dari A.<br><strong>Langkah Penyelesaian:</strong><br>1. $D_{TH} = \frac{30}{1 + \sqrt{40.000/10.000}} = \frac{30}{1 + \sqrt{4}} = \frac{30}{3} = \mathbf{10\text{ km dari Kota A}}$.'
                    },
                    {
                        title: 'Bab 12: Wilayah, Perwilayahan & Pusat Pertumbuhan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Tata Ruang:</strong> Wilayah Formal (homogen) dan Fungsional (heterogen dinamis). Teori Tempat Sentral Christaller: $K=3$ (Pasar Optimum), $K=4$ (Lalu Lintas Optimum), $K=7$ (Administrasi Optimum).',
                        visual: 'K=3 (Pasar Optimum)  |  K=4 (Lalu Lintas Optimum)  |  K=7 (Administrasi Optimum)',
                        tips: 'Hierarki $K=4$ melayani situasi arus lalu lintas dan transportasi yang optimum.',
                        contohSoal: '<strong>Soal 1:</strong> Tempat sentral hierarki K=7 menurut Christaller berfokus pada optimum sektor?<br><strong>Langkah Penyelesaian:</strong> Sektor **Pemerintahan / Administrasi Optimum**.'
                    },
                    {
                        title: 'Bab 13: Indonesia Sebagai Poros Maritim Dunia',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Akar Konsep Geopolitik Kelautan:</strong> Indonesia terletak strategis di antara 2 samudera dan 2 benua. Alur Laut Kepulauan Indonesia (ALKI I, II, III) mengendalikan pelayaran internasional.',
                        visual: 'ALKI I (Selat Sunda) | ALKI II (Selat Lombok) | ALKI III (Selat Ombai-Wetar)',
                        tips: 'ALKI II melintasi Selat Lombok, Selat Makassar, hingga Laut Sulawesi.',
                        contohSoal: '<strong>Soal 1:</strong> Selat Sunda termasuk ke dalam jalur alur laut kepulauan nomor?<br><strong>Langkah Penyelesaian:</strong> **ALKI I**.'
                    },
                    {
                        title: 'Bab 14: Mitigasi & Adaptasi Bencana Alam',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Akar Konsep Manajemen Bencana:</strong> Tahapan bencana: Pra-bencana (Mitigasi/Kesiapsiagaan), Saat Bencana (Tanggap Darurat), Pasca-bencana (Rehabilitasi/Rekonstruksi). Mitigasi Struktural vs Non-Struktural.',
                        visual: 'Mitigasi Fisik / Bangunan Tahan Gempa (Struktural) vs Edukasi / Simulasi (Non-Struktural)',
                        tips: 'Pembangunan tembok penahan gelombang pantai tergolong Mitigasi **Struktural**.',
                        contohSoal: '<strong>Soal 1:</strong> Penanaman hutan mangrove di pantai merupakan mitigasi bencana secara?<br><strong>Langkah Penyelesaian:</strong> Mitigasi **Struktural Vegetatif** penahan tsunami dan abrasi.'
                    },
                    {
                        title: 'Bab 15: Pembangunan Berkelanjutan & Kerjasama Internasional',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Ekologi Berkelanjutan:</strong> Pembangunan berkelanjutan (SDGs) memenuhi kebutuhan masa kini tanpa mengorbankan generasi mendatang. Kajian AMDAL wajib untuk proyek berdampak luas.',
                        visual: 'AMDAL (Analisis Mengenai Dampak Lingkungan) Wajib Bagi Proyek Berdampak Luas',
                        tips: 'Prinsip *eco-efficiency* bertujuan memanfaatkan sumber daya secara hemat dan ramah lingkungan.',
                        contohSoal: '<strong>Soal 1:</strong> Dokumen kajian lingkungan hidup wajib bagi pabrik kimia besar dinamakan?<br><strong>Langkah Penyelesaian:</strong> **AMDAL**.'
                    }
                ],
                'eko': [
                    {
                        title: 'Bab 1: Kelangkaan & Biaya Peluang (Opportunity Cost)',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Ekonomi:</strong> Masalah dasar ekonomi timbul dari ketidakseimbangan antara kebutuhan manusia yang tak terbatas dengan sumber daya yang terbatas (*scarcity*). Biaya Peluang adalah nilai barang/jasa atau kesempatan terbaik yang dikorbankan karena memilih suatu alternatif keputusan.',
                        visual: 'Biaya Peluang = Nilai Alternatif Terbaik Yang TIDAK Dipilih (Bukan Total Penjumlahan)',
                        tips: 'Jika ada lebih dari 2 pilihan yang dikorbankan, Biaya Peluang adalah **opsi dengan nilai ekonomi tertinggi** dari opsi yang dilepas.',
                        contohSoal: '<strong>Soal 1:</strong> Budi memiliki opsi bekerja di Perusahaan A (gaji Rp4 jt), Perusahaan B (gaji Rp5 jt), atau kuliah. Jika Budi memilih kuliah, berapa biaya peluangnya?<br><strong>Langkah Penyelesaian:</strong> Pilihan tertinggi yang dikorbankan adalah gaji Perusahaan B sebesar **Rp5.000.000**.'
                    },
                    {
                        title: 'Bab 2: Keseimbangan Pasar, Permintaan & Penawaran',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Mekanisme Pasar:</strong> Keseimbangan pasar dicapai saat $Q_d = Q_s$. Hukum Permintaan: jika $P$ naik, $Q_d$ turun. Hukum Penawaran: jika $P$ naik, $Q_s$ naik.',
                        visual: 'Keseimbangan Pasar: Q_d = Q_s  |  Harga Keseimbangan P_E & Kuantitas Q_E',
                        tips: 'Perubahan HARGA BARANG ITU SENDIRI menyebabkan pergerakan DI SEPANJANG KURVA, bukan pergeseran kurva!',
                        contohSoal: '<strong>Soal 1:</strong> $Q_d = 20 - 2P$ dan $Q_s = -4 + 2P$. Hitung harga $P$ keseimbangan.<br><strong>Langkah Penyelesaian:</strong><br>1. $20 - 2P = -4 + 2P \implies 4P = 24 \implies \mathbf{P = 6}$.'
                    },
                    {
                        title: 'Bab 3: Elastisitas Harga Permintaan & Penawaran',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Kepekaan Pasar:</strong> Koefisien elastisitas $E = \frac{\%\Delta Q}{\%\Delta P} = \frac{\Delta Q}{\Delta P} \cdot \frac{P}{Q}$. $E > 1$ (Elastis), $E < 1$ (Inelastis), $E = 1$ (Unitary).',
                        visual: 'E = (ΔQ / ΔP) × (P / Q)  |  Elastis (E > 1) vs Inelastis (E < 1)',
                        tips: 'Barang kebutuhan pokok (beras, garam) selalu bersifat **Inelastis ($E < 1$)**.',
                        contohSoal: '<strong>Soal 1:</strong> Harga naik $10\%$ menyebabkan jumlah barang diminta turun $20\%$. Hitung $E$.<br><strong>Langkah Penyelesaian:</strong><br>1. $E = \frac{20\%}{10\%} = \mathbf{2\text{ (Elastis)}}$.'
                    },
                    {
                        title: 'Bab 4: Biaya Produksi, Penerimaan & Laba Maksimum',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Mikroekonomi:</strong> Total Biaya $TC = TFC + TVC$. Penerimaan Total $TR = P \times Q$. Laba maksimum dicapai saat Penerimaan Marjinal sama dengan Biaya Marjinal ($MR = MC$).',
                        visual: 'Laba Maksimum Syarat Mutlak: MR = MC  |  TC = TFC + TVC',
                        tips: 'Selama $MR > MC$, produsen masih bisa menambah keuntungan dengan cara meningkatkan jumlah output produksi.',
                        contohSoal: '<strong>Soal 1:</strong> Kondisi optimum bagi produsen untuk mencapai keuntungan paling maksimal adalah?<br><strong>Langkah Penyelesaian:</strong> Terjadi saat **MR = MC**.'
                    },
                    {
                        title: 'Bab 5: Struktur Pasar: Persaingan Sempurna & Monopoli',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Industri:</strong> Pasar Persaingan Sempurna (banyak penjual, barang homogen, *price taker*, $P = MR = AR$). Pasar Monopoli (satu penjual, *price maker*, *barrier to entry* tinggi).',
                        visual: 'Persaingan Sempurna (P = MR = AR) vs Monopoli (Single Seller)',
                        tips: 'Pasar yang didominasi oleh beberapa produsen besar (seperti industri semen, rokok, seluler) tergolong **Oligopoli**.',
                        contohSoal: '<strong>Soal 1:</strong> Kurva permintaan yang dihadapi perusahaan pada Pasar Persaingan Sempurna berbentuk?<br><strong>Langkah Penyelesaian:</strong> Berbentuk **Garis Lurus Horizontal** (Elastis Sempurna).'
                    },
                    {
                        title: 'Bab 6: Pendapatan Nasional (PDB, PNB & Pendapatan Per Kapita)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Makroekonomi:</strong> PDB mengukur total output di wilayah geografis negara. PNB $= \text{PDB} + \text{Pendapatan Neto Luar Negeri}$. Pendapatan Per Kapita $= \frac{\text{PNB}}{\text{Jumlah Penduduk}}$.',
                        visual: 'PNB = PDB + Pendapatan Neto Luar Negeri  |  Per Kapita = PNB / Jumlah Penduduk',
                        tips: 'Gaji TKI Indonesia yang bekerja di Malaysia dihitung dalam **PNB Indonesia**, bukan PDB Indonesia!',
                        contohSoal: '<strong>Soal 1:</strong> Gaji tenaga kerja asing yang bekerja di dalam negeri masuk dalam komputasi?<br><strong>Langkah Penyelesaian:</strong> Masuk dalam **PDB Indonesia**.'
                    },
                    {
                        title: 'Bab 7: Kebijakan Moneter, Bank Sentral & Kebijakan Fiskal',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Stabilisasi Ekonomi:</strong> Kebijakan Moneter (Bank Indonesia) mengontrol jumlah uang beredar via Suku Bunga (BI Rate), Operasi Pasar Terbuka (Jual/Beli SBI), dan Giro Wajib Minimum. Kebijakan Fiskal (Pemerintah) via Pajak dan APBN.',
                        visual: 'Atasi Inflasi: Uang Ketat (Naikkan Suku Bunga, Jual Surat Berharga SBI, Naikkan Cadangan Kas)',
                        tips: 'Untuk mengatasi lonjakan inflasi tinggi, Bank Sentral menerapkan kebijakan uang ketat (*tight money policy*).',
                        contohSoal: '<strong>Soal 1:</strong> Instrumen moneter dengan menaikkan tingkat suku bunga bank dinamakan?<br><strong>Langkah Penyelesaian:</strong> Kebijakan **Diskonto**.'
                    },
                    {
                        title: 'Bab 8: Inflasi, Indeks Harga Konsumen (IHK) & Pengangguran',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Gangguan Makro:</strong> Inflasi adalah kenaikan harga secara umum dan terus-menerus. Laju Inflasi $= \frac{IHK_t - IHK_{t-1}}{IHK_{t-1}} \times 100\%$. Pengangguran Friksional, Struktural, dan Siklis.',
                        visual: 'Laju Inflasi = [ (IHK_t - IHK_t-1) / IHK_t-1 ] × 100%',
                        tips: 'Pengangguran akibat alih teknologi mesin otomatisasi pabrik tergolong Pengangguran **Struktural**.',
                        contohSoal: '<strong>Soal 1:</strong> IHK bulan lalu $110$, bulan ini $121$. Hitung laju inflasinya.<br><strong>Langkah Penyelesaian:</strong><br>1. Inflasi $= \frac{121 - 110}{110} \times 100\% = \frac{11}{110} \times 100\% = \mathbf{10\%}$.'
                    },
                    {
                        title: 'Bab 9: Perdagangan Internasional, Kurs & Neraca Pembayaran',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Ekonomi Dunia:</strong> Teori Keunggulan Mutlak (Adam Smith) & Komparatif (David Ricardo). Neraca Pembayaran mencatat transaksi ekspor-impor dan lalu lintas modal luar negeri.',
                        visual: 'Neraca Perdagangan = Total Nilai Ekspor Barang - Total Nilai Impor Barang',
                        tips: 'Jika nilai Ekspor barang lebih besar dari Impor, neraca perdagangan mengalami status **Surplus**.',
                        contohSoal: '<strong>Soal 1:</strong> Keunggulan memproduksi barang dengan biaya kesempatan (*opportunity cost*) paling rendah dinamakan?<br><strong>Langkah Penyelesaian:</strong> Keunggulan **Komparatif**.'
                    },
                    {
                        title: 'Bab 10: Persamaan Dasar Akuntansi & Analisis Transaksi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pembukuan:</strong> Akuntansi adalah sistem informasi keuangan. Persamaan Dasar Akuntansi: $\text{Aset (Harta)} = \text{Liabilitas (Utang)} + \text{Ekuitas (Modal)}$.',
                        visual: 'ASET (Harta) = LIABILITAS (Utang) + EKUITAS (Modal)',
                        tips: 'Pembelian perlengkapan usaha secara KREDIT akan menambah akun Aset (Perlengkapan) dan Utang Usaha.',
                        contohSoal: '<strong>Soal 1:</strong> Diterima pendapatan jasa secara tunai $Rp2.000.000$. Pengaruhnya pada persamaan dasar?<br><strong>Langkah Penyelesaian:</strong> Kas (Aset) bertambah Rp2 jt, Modal bertambah Rp2 jt.'
                    },
                    {
                        title: 'Bab 11: Jurnal Umum & Mekanisme Debet-Kredit',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pencatatan Transaksi:</strong> Jurnal umum mencatat transaksi secara kronologis. Aturan Saldo Normal: Harta & Beban bertambah di **Debet**; Utang, Modal, & Pendapatan bertambah di **Kredit**.',
                        visual: 'Harta & Beban (+) Debet  |  Utang, Modal, Pendapatan (+) Kredit',
                        tips: 'Jumlah kolom Debet dan Kredit pada jurnal umum Wajib SELALU seimbang (*balanced*)!',
                        contohSoal: '<strong>Soal 1:</strong> Membeli peralatan kantor $Rp5.000.000$ secara tunai. Jurnal umumnya adalah?<br><strong>Langkah Penyelesaian:</strong> Debet: Peralatan Rp5 jt, Kredit: Kas Rp5 jt.'
                    },
                    {
                        title: 'Bab 12: Buku Besar & Neraca Saldo Sebelum Penyesuaian',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pengelompokan Akun:</strong> *Posting* adalah proses memindahkan catatan ayat jurnal umum ke dalam buku besar masing-masing akun untuk mengagregasi saldo akhir.',
                        visual: 'Posting Jurnal Umum → Buku Besar (T-Account) → Neraca Saldo',
                        tips: 'Proses memindahkan angka catatan dari jurnal umum ke akun buku besar dinamakan **Posting**.',
                        contohSoal: '<strong>Soal 1:</strong> Apa fungsi utama dari penyusunan Neraca Saldo di akhir periode?<br><strong>Langkah Penyelesaian:</strong> Menguji kesamaan total saldo Debet dan Kredit dari seluruh akun buku besar.'
                    },
                    {
                        title: 'Bab 13: Jurnal Penyesuaian (AJP) Perusahaan Jasa & Dagang',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Penyesuaian Akhir:</strong> AJP dibuat di akhir periode untuk meng-update saldo akun nominal dan riil agar mencerminkan kondisi sebenarnya (penyusutan aset, beban terutang, perlengkapan terpakai).',
                        visual: 'AJP Perlengkapan Terpakai: Debet Beban Perlengkapan | Kredit Perlengkapan',
                        tips: 'Nilai perlengkapan yang ditulis pada AJP adalah sebesar nilai perlengkapan yang **TELAH TERPAKAI**!',
                        contohSoal: '<strong>Soal 1:</strong> Saldo Perlengkapan $Rp1.000.000$. Sisa akhir periode $Rp300.000$. AJP beban perlengkapan?<br><strong>Langkah Penyelesaian:</strong> Terpakai $= 1\text{jt} - 300\text{rb} = 700\text{rb}$. Jurnal: Debet Beban Perlengkapan Rp700rb, Kredit Perlengkapan Rp700rb.'
                    },
                    {
                        title: 'Bab 14: Kertas Kerja (Neraca Lajur) & Laporan Keuangan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pelaporan Keuangan:</strong> Kertas kerja mempermudah penyusunan 4 Laporan Keuangan Utama: Laporan Laba Rugi, Laporan Perubahan Ekuitas, Neraca Posisi Keuangan, dan Laporan Arus Kas.',
                        visual: 'Laba Bersih = Total Pendapatan - Total Beban  |  Laporan Laba Rugi',
                        tips: 'Akun Nominal (Pendapatan dan Beban) dilaporkan masuk ke dalam Laporan **Laba Rugi**.',
                        contohSoal: '<strong>Soal 1:</strong> Pendapatan $Rp10.000.000$, Beban $Rp6.000.000$, Prive $Rp1.000.000$. Hitung laba bersih perusahaan.<br><strong>Langkah Penyelesaian:</strong> Laba Bersih $= 10\text{jt} - 6\text{jt} = \mathbf{Rp4.000.000}$ (Prive tidak mengurangi laba).'
                    },
                    {
                        title: 'Bab 15: Jurnal Penutup & Saldo Setelah Penutupan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Penutupan Buku:</strong> Jurnal penutup menolkan saldo akun sementara (nominal) pada akhir periode ke akun Ikhtisar Laba Rugi agar siap digunakan untuk periode akuntansi berikutnya.',
                        visual: 'Menutup Pendapatan: Debet Pendapatan | Kredit Ikhtisar Laba Rugi',
                        tips: 'Akun Riil (Harta, Utang, Modal) TIDAK DITUTUP dan saldonya dibawa terus ke periode berikutnya.',
                        contohSoal: '<strong>Soal 1:</strong> Akun manakah yang wajib ditutup pada akhir periode akuntansi?<br><strong>Langkah Penyelesaian:</strong> Akun nominal yaitu **Pendapatan dan Beban**.'
                    }
                ],
                'sos': [
                    {
                        title: 'Bab 1: Hakikat Sosiologi & 4 Ciri Ilmiah Sosiologi',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Sosiologi:</strong> Sosiologi adalah ilmu positif yang mempelajari struktur sosial dan proses sosial dalam masyarakat. 4 Ciri Ilmiah Sosiologi: (1) Empiris (berdasarkan observasi riil), (2) Teoritis (menyusun abstraksi dari hasil pengamatan), (3) Kumulatif (mengembangkan teori lama), dan (4) Non-Etis (objektif, tidak menilai baik-buruk moral fakta).',
                        visual: 'Non-Etis = Peneliti mengkaji fakta kejahatan tanpa menyalahkan atau menghakimi moral pelaku',
                        tips: 'Jika ada pernyataan "peneliti tidak menghakimi moral subjek", jawabannya pasti **Non-Etis**.',
                        contohSoal: '<strong>Soal 1:</strong> Sosiolog mengkaji penyebab tawuran remaja tanpa menghujat para pelaku secara moral. Ciri sosiologi tersebut adalah?<br><strong>Langkah Penyelesaian:</strong> Menunjukkan ciri **Non-Etis**.'
                    },
                    {
                        title: 'Bab 2: Interaksi Sosial, Syarat & Faktor pendorong',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Hubungan Sosial:</strong> Syarat terjadinya interaksi sosial: Kontak Sosial dan Komunikasi. Faktor pendorong: Imitasi (meniru luar), Sugesti (pengaruh pandangan), Identifikasi (meniru penuh identik), Simpati, dan Empati (aksi nyata pertolongan).',
                        visual: 'Imitasi (Meniru luar) vs Identifikasi (Meniru identik penuh)  |  Empati (Aksi Nyata)',
                        tips: 'Empati selalu melibatkan **tindakan nyata pertolongan**, sedangkan simpati sebatas perasaan iba.',
                        contohSoal: '<strong>Soal 1:</strong> Seorang penggemar merubah total penampilan dan gaya hidupnya agar persis idola. Faktornya?<br><strong>Langkah Penyelesaian:</strong> Faktor **Identifikasi**.'
                    },
                    {
                        title: 'Bab 3: Nilai & Norma Sosial dalam Masyarakat',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Patokan Perilaku:</strong> Nilai adalah sesuatu yang dianggap ideal. Tingkatan norma dari sanksi terringan ke terberat: Cara (*Usage*), Kebiasaan (*Folkways*), Tata Kelakuan (*Mores*), Adat Istiadat (*Customs*).',
                        visual: 'Cara (Usage) → Kebiasaan (Folkways) → Tata Kelakuan (Mores) → Adat (Customs)',
                        tips: 'Pelanggaran terhadap Adat Istiatat mendapat sanksi terberat berupa pengucilan sosial atau hukum adat.',
                        contohSoal: '<strong>Soal 1:</strong> Mengunyah makanan dengan bersuara keras melanggar tingkatan norma sosial apakah?<br><strong>Langkah Penyelesaian:</strong> Melanggar norma **Cara (Usage)**.'
                    },
                    {
                        title: 'Bab 4: Sosialisasi & Agen Pembentuk Kepribadian',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Pembentukan Diri:</strong> Sosialisasi adalah proses mempelajari nilai dan peran budaya. Tahapan Mead: *Preparatory Stage*, *Play Stage*, *Game Stage*, dan *Generalized Other*. Agen: Keluarga, Sekolah, Peer Group, Media.',
                        visual: 'Generalized Other = Mampu menjalankan peran di tengah masyarakat luas',
                        tips: 'Sosialisasi primer pertama terjadi di lingkungan internal keluarga.',
                        contohSoal: '<strong>Soal 1:</strong> Anak mulai menirukan peran orang dewasa tanpa memahami maksudnya pada tahap?<br><strong>Langkah Penyelesaian:</strong> **Play Stage**.'
                    },
                    {
                        title: 'Bab 5: Perilaku Menyimpang & Teori Anomie Merton',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Penyimpangan:</strong> Penyimpangan timbul akibat sosialisasi tidak sempurna. Teori Anomie Merton membagi 5 adaptasi: Konformitas, Inovasi (terima tujuan, tolak cara legal), Ritualisme, Retretisme, Pemberontakan.',
                        visual: 'Inovasi Merton = Menerima Tujuan Sukses Budaya, Tetapi Menolak Cara Legal (Misal: Korupsi)',
                        tips: 'Koruptor yang mengejar kekayaan dengan jalan melanggar hukum tergolong bentuk adaptasi **Inovasi**.',
                        contohSoal: '<strong>Soal 1:</strong> Karyawan bekerja hanya formalitas rutin tanpa peduli target sukses tergolong adaptasi?<br><strong>Langkah Penyelesaian:</strong> Bentuk adaptasi **Ritualisme**.'
                    },
                    {
                        title: 'Bab 6: Struktur Sosial & Stratifikasi Sosial (Pelapisan)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Hirarki Sosial:</strong> Stratifikasi (vertikal/bertingkat) dan Diferensiasi (horizontal/setara). Sifat stratifikasi: Terbuka (berdasarkan prestasi), Tertutup (berdasarkan kasta/kelahiran), dan Campuran.',
                        visual: 'Stratifikasi Tertutup (Kasta Bali/India) vs Terbuka (Prestasi Ekonomi)',
                        tips: 'Sistem kasta tradisional di Bali/India tergolong stratifikasi sosial **Tertutup**.',
                        contohSoal: '<strong>Soal 1:</strong> Pelapisan sosial berdasarkan kasta keturunan tergolong bersifat?<br><strong>Langkah Penyelesaian:</strong> Stratifikasi sosial **Tertutup**.'
                    },
                    {
                        title: 'Bab 7: Diferensiasi Sosial & Multikulturalisme',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Keragaman Horizontal:</strong> Pengelompokan masyarakat tanpa hierarki (Ras, Etnis, Agama, Gender). Konsolidasi sosial (penguatan internal) dan Interseksi sosial (persilangan keanggotaan).',
                        visual: 'Interseksi Sosial = Persilangan keanggotaan dalam kelompok sosial yang berbeda',
                        tips: 'Sikap toleransi dan kesetaraan merupakan kunci keharmonisan masyarakat multikultural.',
                        contohSoal: '<strong>Soal 1:</strong> Persilangan keanggotaan masyarakat berdasarkan suku bangsa dan agama dinamakan?<br><strong>Langkah Penyelesaian:</strong> **Interseksi Sosial**.'
                    },
                    {
                        title: 'Bab 8: Konflik Sosial & Resolusi Akomodasi Konflik',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Dinamika Konflik:</strong> Konflik timbul karena perbedaan kepentingan. Akomodasi penyelesaian: Mediasi (pihak ke-3 netral penasihat), Arbitrase (pihak ke-3 pengambil keputusan mengikat), Ajudikasi (pengadilan).',
                        visual: 'Mediasi (Pihak 3 Penasihat) vs Arbitrase (Pihak 3 Pemutus Mengikat) vs Ajudikasi (Pengadilan)',
                        tips: 'Penyelesaian sengketa melalui lembaga peradilan hukum dinamakan **Ajudikasi**.',
                        contohSoal: '<strong>Soal 1:</strong> Penyelesaian sengketa lahan di meja hijau pengadilan dinamakan bentuk akomodasi?<br><strong>Langkah Penyelesaian:</strong> **Ajudikasi**.'
                    },
                    {
                        title: 'Bab 9: Mobilitas Sosial & Saluran-Salurannya',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Perpindahan Status:</strong> Mobilitas sosial adalah perubahan posisi individu/kelompok secara vertikal (naik/turun) atau horizontal. Saluran utama: Pendidikan, Organisasi Politik, Ekonomi, Militer.',
                        visual: 'Pendidikan = Saluran Utama Mobilitas Sosial Vertikal Naik (Social Elevator)',
                        tips: 'Lembaga pendidikan sering dijuluki sebagai *social elevator* paling efektif dalam mobilitas sosial vertikal.',
                        contohSoal: '<strong>Soal 1:</strong> Saluran mobilitas sosial paling efektif yang sering disebut social elevator adalah?<br><strong>Langkah Penyelesaian:</strong> Saluran lembaga **Pendidikan**.'
                    },
                    {
                        title: 'Bab 10: Perubahan Sosial & Teori-Teori Perubahan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Perubahan Masyarakat:</strong> Perubahan struktur dan fungsi sosial. Teori Siklus (perubahan berulang seperti roda), Teori Linier/Evolusi (perkembangan berurutan tahap demi tahap), Teori Konflik.',
                        visual: 'Teori Siklus (Perubahan Berulang) vs Teori Linier (Perkembangan Maju Berurutan)',
                        tips: 'Penyebab internal perubahan sosial: perubahan jumlah penduduk, penemuan baru (*discovery/invention*), konflik internal.',
                        contohSoal: '<strong>Soal 1:</strong> Peradaban manusia berkembang dari primitif menuju modern secara berurutan dijelaskan teori?<br><strong>Langkah Penyelesaian:</strong> **Teori Linier / Evolusi**.'
                    },
                    {
                        title: 'Bab 11: Modernisasi, Globalisasi & Sekularisasi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Integrasi Dunia:</strong> Globalisasi menghilangkan batas antarnegara. Dampak negatif: *Cultural Lag* (ketimpangan pertumbuhan budaya material dan non-material), Konsumerisme, Hedonisme.',
                        visual: 'Cultural Lag = Ketimpangan antara kemajuan teknologi material & kesiapan mental non-material',
                        tips: 'Masyarakat menerima smartphone canggih namun mentalitas menyebarkan hoax menunjukkan fenomena ***Cultural Lag***.',
                        contohSoal: '<strong>Soal 1:</strong> Ketimpangan antara perkembangan teknologi canggih dan hukum penataannya dinamakan?<br><strong>Langkah Penyelesaian:</strong> **Cultural Lag**.'
                    },
                    {
                        title: 'Bab 12: Lembaga Sosial & Fungsi Manfaatnya',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Institusi Masyarakat:</strong> Sistem norma terorganisir untuk memenuhi kebutuhan dasar. Lembaga Keluarga, Agama, Ekonomi, Politik, Pendidikan. Fungsi manifes (disadari) vs laten (tersembunyi).',
                        visual: 'Fungsi Manifes (Disadari & Diharapkan) vs Fungsi Laten (Tersembunyi)',
                        tips: 'Fungsi keluarga dalam memberikan kasih sayang dan perlindungan emosional dinamakan fungsi **Afeksi**.',
                        contohSoal: '<strong>Soal 1:</strong> Fungsi keluarga dalam memberikan rasa aman dan kasih sayang dinamakan fungsi?<br><strong>Langkah Penyelesaian:</strong> Fungsi **Afeksi**.'
                    },
                    {
                        title: 'Bab 13: Penelitian Sosial: Metode Kualitatif & Kuantitatif',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Metodologi Riset:</strong> Penelitian Kuantitatif (data angka, kuesioner angket, analisis statistik). Penelitian Kualitatif (data kata deskriptif, wawancara mendalam, pengamatan partisipatif).',
                        visual: 'Kuantitatif (Angka & Statistik) vs Kualitatif (Deskripsi Kata & Motif)',
                        tips: 'Teknik *Random Sampling* (sampel acak) digunakan pada pendekatan kuantitatif.',
                        contohSoal: '<strong>Soal 1:</strong> Penelitian yang berfokus menguraikan riwayat hidup dan motif mendalam subjek adalah?<br><strong>Langkah Penyelesaian:</strong> Penelitian pendekatan **Kualitatif**.'
                    },
                    {
                        title: 'Bab 14: Masalah Sosial, Kemiskinan & Ketimpangan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Patologi Sosial:</strong> Masalah sosial timbul saat kondisi riil tidak sesuai ekspektasi norma masyarakat. Kemiskinan Absolut vs Relatif. Ketimpangan diukur dengan Indeks Gini ($0 - 1$).',
                        visual: 'Indeks Gini Mendekati 1 = Ketimpangan Distribusi Pendapatan Sangat Tinggi',
                        tips: 'Kemiskinan Absolut terjadi saat seseorang tidak mampu memenuhi kebutuhan fisik minimum (makan/papan).',
                        contohSoal: '<strong>Soal 1:</strong> Koefisien Indeks Gini mendekati angka 1 menunjukkan tingkat ketimpangan?<br><strong>Langkah Penyelesaian:</strong> Ketimpangan pendapatan yang **Sangat Tinggi**.'
                    },
                    {
                        title: 'Bab 15: Pemberdayaan Masyarakat & Kearifan Lokal',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kemandirian Warga:</strong> Pemberdayaan bertujuan meningkatkan kemandirian masyarakat berbasis kearifan lokal (*local wisdom*) sebagai mekanisme adaptasi lingkungan.',
                        visual: 'Kearifan Lokal = Pengetahuan Tradisional Adaptif Mengelola Lingkungan (Misal: Subak Bali)',
                        tips: 'Sistem pengairan pertanian Subak di Bali merupakan contoh kearifan lokal yang diakui dunia.',
                        contohSoal: '<strong>Soal 1:</strong> Sistem irigasi pertanian tradisional Subak di Bali tergolong bentuk?<br><strong>Langkah Penyelesaian:</strong> **Kearifan Lokal (Local Wisdom)**.'
                    }
                ],
                'sej': [
                    {
                        title: 'Bab 1: Hakikat Ilmu Sejarah, Diakronik & Sinkronik',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Metodologi Sejarah:</strong> Sejarah merekonstruksi peristiwa masa lalu secara kritis. Cara berpikir Diakronik memanjang dalam waktu dan menyempit dalam ruang (kronologis berurutan waktu). Cara berpikir Sinkronik meluas dalam ruang dan menyempit dalam waktu (mengkaji struktur peristiwa secara mendalam di suatu waktu tertentu).',
                        visual: 'Diakronik (Kronologis Waktu) vs Sinkronik (Analisis Mendalam Struktur Ruang)',
                        tips: 'Kritik Sumber terdiri dari Kritik Ekstern (menguji keaslian fisik dokumen) dan Kritik Intern (menguji kredibilitas isi naskah).',
                        contohSoal: '<strong>Soal 1:</strong> Mengkaji kondisi sosial-ekonomi masyarakat Jakarta pada masa Proklamasi 1945 secara mendalam merupakan pendekatan?<br><strong>Langkah Penyelesaian:</strong> Pendekatan **Sinkronik**.'
                    },
                    {
                        title: 'Bab 2: Manusia Purba & Kehidupan Praaksara Nusantara',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Akar Konsep Kehidupan Awal:</strong> Manusia purba Nusantara (*Meganthropus, Pithecanthropus, Homo*). Periodisasi kebudayaan: Paleolitikum, Mesolitikum (*Kjokkenmoddinger*), Neolitikum (Beliung persegi), Megalitikum.',
                        visual: 'Neolitikum = Revolusi Kebudayaan dari Food Gathering ke Food Producing',
                        tips: '*Kjokkenmoddinger* adalah fosil bukit sampah dapur kerang/siput pada zaman Mesolitikum.',
                        contohSoal: '<strong>Soal 1:</strong> Revolusi kebudayaan perubahan pola hidup dari berpindah (*nomaden*) menjadi menetap terjadi pada masa?<br><strong>Langkah Penyelesaian:</strong> Masa **Neolitikum**.'
                    },
                    {
                        title: 'Bab 3: Kerajaan-Kerajaan Hindu-Buddha di Indonesia',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pengaruh India:</strong> Masuknya Hindu-Buddha (Teori Brahmana, Ksatria, Waisya, Arus Balik). Kerajaan Kutai (Prasasti Yupa), Tarumanegara, Sriwijaya (Maritim-Buddha), Mataram Kuno, Majapahit.',
                        visual: 'Majapahit = Sumpah Palapa Patih Gajah Mada Menyatukan Nusantara',
                        tips: 'Prasasti Yupa dari Kerajaan Kutai ditulis menggunakan huruf **Pallawa** dan bahasa **Sanskerta**.',
                        contohSoal: '<strong>Soal 1:</strong> Kerajaan maritim dan pusat agama Buddha terbesar di Asia Tenggara pada abad ke-7 adalah?<br><strong>Langkah Penyelesaian:</strong> Kerajaan **Sriwijaya**.'
                    },
                    {
                        title: 'Bab 4: Kerajaan-Kerajaan Islam & Akulturasi Budaya',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Akulturasi Islam:</strong> Islamisasi via perdagangan, pernikahan, tasawuf, dan kesenian. Kerajaan Samudera Pasai, Demak, Mataram Islam, Gowa-Tallo, Ternate-Tidore. Akulturasi masjid atap tumpang.',
                        visual: 'Akulturasi Masjid Menara Kudus = Bentuk Menara Mirip Candi Hindu',
                        tips: 'Atap masjid berbentuk tumpang bertingkat ganjil merupakan akulturasi budaya Islam dan Hindu-Buddha.',
                        contohSoal: '<strong>Soal 1:</strong> Kerajaan Islam pertama di pulau Jawa adalah Kerajaan?<br><strong>Langkah Penyelesaian:</strong> Kerajaan **Demak**.'
                    },
                    {
                        title: 'Bab 5: Kolonialisme Barat & Perlawanan Daerah',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Penjajahan Eropa:</strong> Penjelajahan Samudera (*Gold, Glory, Gospel*). VOC (Monopoli, Hak Ekstirpasi). Tanam Paksa *Cultuurstelsel* (Van den Bosch). Perlawanan Diponegoro, Pattimura, Aceh.',
                        visual: 'VOC Hancur 1799 akibat Korupsi & Utang Besar  |  Politik Etis (Trias Van Deventer)',
                        tips: 'Politik Etis terdiri dari 3 program utama: Edukasi, Irigasi, dan Transmigrasi (Emigrasi).',
                        contohSoal: '<strong>Soal 1:</strong> Tokoh Belanda penggagas Politik Etis Trias Van Deventer adalah?<br><strong>Langkah Penyelesaian:</strong> **Conrad Theodor van Deventer**.'
                    },
                    {
                        title: 'Bab 6: Pergerakan Nasional & Sumpah Pemuda 1928',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kebangkitan Nasional:</strong> Pendidikan Politik Etis melahirkan golongan terpelajar. Budi Utomo (1908), Sarekat Islam, Indische Partij. Kongres Pemuda II (28 Oktober 1928) lahirkan Sumpah Pemuda.',
                        visual: 'Sumpah Pemuda 28 Oktober 1928: Satu Nusa, Satu Bangsa, Satu Bahasa Indonesia',
                        tips: '*Indische Partij* adalah organisasi pergerakan politik radikal pertama yang menyuarakan kemerdekaan Indonesia.',
                        contohSoal: '<strong>Soal 1:</strong> Organisasi pergerakan nasional pertama di Indonesia yang berdiri 20 Mei 1908 adalah?<br><strong>Langkah Penyelesaian:</strong> **Budi Utomo**.'
                    },
                    {
                        title: 'Bab 7: Pendudukan Jepang di Indonesia (1942-1945)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Perang Pasifik:</strong> Propaganda Jepang (3A). Organisasi militer/semimiliter (PETA, Heiho, Seinendan). Kerja paksa Romusha. Pelatihan militer PETA menjadi cikal bakal TNI.',
                        visual: 'PETA (Pembela Tanah Air) = Cikal Bakal Pembentukan TNI',
                        tips: 'Pemberontakan tentara PETA melawan Jepang di Blitar dipimpin oleh **Supriyadi** pada Februari 1945.',
                        contohSoal: '<strong>Soal 1:</strong> Siapakah pemuda yang memimpin pemberontakan PETA di Blitar?<br><strong>Langkah Penyelesaian:</strong> **Supriyadi**.'
                    },
                    {
                        title: 'Bab 8: Proklamasi Kemerdekaan & Peristiwa Rengasdengklok',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Detik-Detik Proklamasi:</strong> Peristiwa Rengasdengklok (16 Ags 1945) mengamankan Soekarno-Hatta dari pengaruh Jepang. Perumusan naskah di rumah Laksamana Maeda. Pembacaan teks 17 Agustus 1945.',
                        visual: 'Rengasdengklok → Rumah Laksamana Maeda → Jalan Pegangsaan Timur No. 56',
                        tips: 'Naskah Proklamasi Kemerdekaan diketik oleh **Sayuti Melik** dengan perubahan beberapa kata.',
                        contohSoal: '<strong>Soal 1:</strong> Tokoh yang mengetik naskah otentik Proklamasi Kemerdekaan Indonesia adalah?<br><strong>Langkah Penyelesaian:</strong> **Sayuti Melik**.'
                    },
                    {
                        title: 'Bab 9: Perjuangan Mempertahankan Kemerdekaan (Diplomasi & Fisik)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Pertahanan Negara:</strong> Perjuangan fisik (Surabaya, Bandung Lautan Api, Agresi Militer). Perjuangan diplomasi (Linggajati, Renville, Roem-Royen, Konferensi Meja Bundar/KMB 1949).',
                        visual: 'KMB (Konferensi Meja Bundar 1949) = Pengakuan Kedaulatan Indonesia oleh Belanda',
                        tips: 'Peristiwa Bandung Lautan Api bertujuan mencegah Sekutu menguasai fasilitas militer strategis.',
                        contohSoal: '<strong>Soal 1:</strong> Konferensi diplomasi internasional yang menghasilkan pengakuan kedaulatan Indonesia oleh Belanda?<br><strong>Langkah Penyelesaian:</strong> **Konferensi Meja Bundar (KMB)**.'
                    },
                    {
                        title: 'Bab 10: Demokrasi Liberal & Pemilu Pertama 1955',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Parlementer:</strong> Sistem parlementer banyak partai. Pergantian kabinet cepat (Natsir, Sukiman, Wilopo, Ali Sastroamidjojo, Burhanuddin Harahap). Pemilu 1955 memilih DPR dan Konstituante.',
                        visual: 'Pemilu 1955 = Pemilu Paling Demokratis Memilih Anggota DPR & Konstituante',
                        tips: '4 Partai Pemenang Pemilu 1955: PNI, Masyumi, NU, dan PKI.',
                        contohSoal: '<strong>Soal 1:</strong> Kabinet yang berhasil menyelenggarakan Pemilu pertama tahun 1955 adalah?<br><strong>Langkah Penyelesaian:</strong> Kabinet **Burhanuddin Harahap**.'
                    },
                    {
                        title: 'Bab 11: Demokrasi Terpimpin & Dekrit Presiden 5 Juli 1959',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Kekuasaan Terpusat:</strong> Dekrit Presiden 5 Juli 1959 kembali ke UUD 1945 dan membubarkan Konstituante. Konsep Nasakom. Politik Mercusuar dan pembebasan Irian Barat.',
                        visual: 'Dekrit Presiden 5 Juli 1959: Kembali ke UUD 1945 & Pembubaran Konstituante',
                        tips: 'Politik Mercusuar menghasilkan proyek megah seperti GBK, Monas, Patung Selamat Datang, dan Hotel Indonesia.',
                        contohSoal: '<strong>Soal 1:</strong> Apakah isi utama Dekrit Presiden 5 Juli 1959?<br><strong>Langkah Penyelesaian:</strong> Pembubaran Konstituante dan **kembali berlakunya UUD 1945**.'
                    },
                    {
                        title: 'Bab 12: Orde Baru: Dualisme Kepemimpinan & Pembangunan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Stabilitas Politik:</strong> Peralihan kekuasaan pasca G30S/PKI via Supersemar 11 Maret 1966. Dwifungsi ABRI. Pembangunan ekonomi lima tahun (Repelita).',
                        visual: 'Supersemar 11 Maret 1966 = Penyerahan Mandat Pengamanan Kepada Soeharto',
                        tips: 'Dwifungsi ABRI menempatkan militer dalam ranah pertahanan negara sekaligus politik pemerintahan.',
                        contohSoal: '<strong>Soal 1:</strong> Surat perintah 11 Maret 1966 yang menjadi tonggak awal lahirnya Orde Baru dinamakan?<br><strong>Langkah Penyelesaian:</strong> Surat **Supersemar**.'
                    },
                    {
                        title: 'Bab 13: Reformasi 1998 & Jatuhnya Pemerintahan Orde Baru',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Gerakan Mahasiswa:</strong> Krisis moneter 1997 memicu aksi demonstrasi mahasiswa 1998. Pengunduran diri Presiden Soeharto 21 Mei 1998 digantikan BJ Habibie.',
                        visual: '21 Mei 1998 = Soeharto Mundur, B.J. Habibie Dilantik Jadi Presiden ke-3',
                        tips: '6 Agenda Reformasi: Adili Soeharto, Amandemen UUD 1945, Otonomi Daerah, Hapus Dwifungsi ABRI, Supremasi Hukum, Pelaksanaan Demokrasi.',
                        contohSoal: '<strong>Soal 1:</strong> Siapakah Presiden yang menggantikan Soeharto saat menyatakan mundur 21 Mei 1998?<br><strong>Langkah Penyelesaian:</strong> **B.J. Habibie**.'
                    },
                    {
                        title: 'Bab 14: Perang Dingin & Organisasi Internasional (KAA, ASEAN)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Politik Luar Negeri:</strong> Persaingan Blok Barat (USA) dan Blok Timur (USSR). Politik Bebas Aktif Indonesia. Konferensi Asia Afrika (KAA 1955), Gerakan Non-Blok (GNB), pendirian ASEAN 1967.',
                        visual: 'Deklarasi Bangkok (8 Agustus 1967) = Berdirinya Organisasi ASEAN',
                        tips: 'KAA di Bandung melahirkan **Dasa Sila Bandung** sebagai prinsip hubungan internasional.',
                        contohSoal: '<strong>Soal 1:</strong> Deklarasi pendirian ASEAN tahun 1967 ditandatangani di kota?<br><strong>Langkah Penyelesaian:</strong> **Bangkok, Thailand**.'
                    },
                    {
                        title: 'Bab 15: Perang Dunia I - II & Organisasi Perdamaian LBB - PBB',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Akar Konsep Konflik Global:</strong> PD I (Sebab khusus: Pembunuhan Franz Ferdinand). PD II (Sebab khusus: Serangan Jerman ke Polandia 1939). Pendirian LBB lalu PBB (24 Oktober 1945).',
                        visual: 'PBB Didirikan 24 Oktober 1945 di San Francisco | 5 Anggota Tetap Hak Veto',
                        tips: '5 Anggota Tetap Dewan Keamanan PBB pemegang Hak Veto: USA, Inggris, Prancis, Rusia, dan China.',
                        contohSoal: '<strong>Soal 1:</strong> Sebutkan peristiwa sebab khusus meletusnya Perang Dunia II di Eropa!<br><strong>Langkah Penyelesaian:</strong> Invasi militer **Jerman ke Polandia pada 1 September 1939**.'
                    }
                ],
                'lit': [
                    {
                        title: 'Bab 1: Penalaran Logis: Modus Ponens, Tollens & Silogisme',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Logika Formal:</strong> Penalaran deduktif menarik kesimpulan yang sahih (valid) dari premis-premis mayor dan minor. Aturan utama: (1) Modus Ponens ($P \implies Q, P \vdash Q$), (2) Modus Tollens ($P \implies Q, \sim Q \vdash \sim P$), dan (3) Silogisme ($P \implies Q, Q \implies R \vdash P \implies R$).',
                        visual: 'Ponens: P→Q, P ⇒ Q  |  Tollens: P→Q, ~Q ⇒ ~P  |  Silogisme: P→Q, Q→R ⇒ P→R',
                        tips: 'Jebakan UTBK SNBT: Pernyataan $P \implies Q$ **TIDAK SAMA** dengan $\sim P \implies \sim Q$ atau $Q \implies P$. Inversi dan konversi TIDAK EKUIVALEN!',
                        contohSoal: '<strong>Soal 1:</strong> Premis 1: Jika Budi belajar, maka ia lulus. Premis 2: Budi tidak lulus. Kesimpulan?<br><strong>Langkah Penyelesaian:</strong> Menurut Modus Tollens, kesimpulannya adalah **Budi tidak belajar**.'
                    },
                    {
                        title: 'Bab 2: Penalaran Analitis & Urutan Posisi Kompleks',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Matriks Posisi:</strong> Penalaran analitis menguji kemampuan menyusun urutan, jadwal, atau posisi berdasarkan sekumpulan syarat batasan logika.',
                        visual: 'Metode Baris Urutan Posisi Absolut & Relatif',
                        tips: 'Selalu cari dan tempatkan syarat logika yang memberikan **posisi absolut mutlak** terlebih dahulu!',
                        contohSoal: '<strong>Soal 1:</strong> A lebih tinggi dari B, C lebih tinggi dari A. Siapakah yang paling tinggi?<br><strong>Langkah Penyelesaian:</strong> Urutan tinggi: C > A > B. Paling tinggi adalah **C**.'
                    },
                    {
                        title: 'Bab 3: Penalaran Kuantitatif: Pola Barisan & Deret Angka',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Pola Deret:</strong> Mengidentifikasi pola deret bilangan: tingkat satu, tingkat dua, larik berselang-seling, atau operasi aritmatika bertingkat.',
                        visual: 'Pola Beda Bertingkat atau Pola Larik Selang-Seling',
                        tips: 'Jika pola angka naik-turun berulang secara bergantian, kemungkinan besar merupakan deret berselang 2 atau 3 langkah!',
                        contohSoal: '<strong>Soal 1:</strong> $3, 6, 12, 21, 33, \dots$ Berapakah angka selanjutnya?<br><strong>Langkah Penyelesaian:</strong><br>1. Pola selisih: $+3, +6, +9, +12 \implies$ selisih berikut $+15$.<br>2. Angka berikutnya $= 33 + 15 = \mathbf{48}$.'
                    },
                    {
                        title: 'Bab 4: Pemahaman Bacaan: Ide Pokok & Kalimat Utama',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Analisis Teks:</strong> Ide pokok adalah gagasan inti pembahasan dalam suatu paragraf. Paragraf Deduktif (ide di awal), Induktif (ide di akhir), Campuran.',
                        visual: 'Gagasan Utama = Topik Utama Paragraf + Pandangan Penulis',
                        tips: 'Kalimat utama bersifat umum dan dijelaskan oleh kalimat-kalimat pengembang berikutnya.',
                        contohSoal: '<strong>Soal 1:</strong> Di manakah letak ide pokok pada paragraf bertipe deduktif?<br><strong>Langkah Penyelesaian:</strong> Terletak pada **Awal Paragraf**.'
                    },
                    {
                        title: 'Bab 5: Penggunaan EBI: Ejaan, Tanda Baca & Kata Baku',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Akar Konsep Kebebasabahasaan:</strong> Kaidah Bahasa Indonesia baku: penulisan huruf kapital, kata serapan baku, pemakaian tanda koma (,), dan titik koma (;).',
                        visual: 'Kata Baku: Apotek (bukan Apotik), Praktik (bukan Praktek), Efektif',
                        tips: 'Penulisan gelar akademis selalu diapit dan dipisahkan oleh tanda koma, misal: Budi, S.Pd.',
                        contohSoal: '<strong>Soal 1:</strong> Manakah bentuk kata baku yang benar: Apotik atau Apotek?<br><strong>Langkah Penyelesaian:</strong> Bentuk baku sesuai KBBI adalah **Apotek**.'
                    },
                    {
                        title: 'Bab 6: Analisis Makna Kata: Konotatif, Denotatif & Kontekstual',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Semantik:</strong> Denotatif adalah makna lugas sebenarnya sesuai kamus. Konotatif adalah makna kiasan/tambahan. Makna kontekstual bergantung pada kalimat.',
                        visual: 'Denotatif (Makna Sebenarnya) vs Konotatif (Makna Kiasan Tambahan)',
                        tips: 'Perhatikan hubungan konteks asosiasi kata di dalam keseluruhan kalimat.',
                        contohSoal: '<strong>Soal 1:</strong> Ungkapan "panjang tangan" dalam arti suka mencuri tergolong makna?<br><strong>Langkah Penyelesaian:</strong> Tergolong makna **Konotatif**.'
                    },
                    {
                        title: 'Bab 7: Penalaran Gambar & Spasial (Figural)',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Visual Spasial:</strong> Menganalisis rotasi, pencerminan, analogi gambar, atau kelanjutan pola perubahan bentuk 2D/3D.',
                        visual: 'Rotasi Searah Jarum Jam 90° / 180° / Pencerminan Vektor',
                        tips: 'Fokus pada satu elemen kecill khusus dalam gambar lalu ikuti pergerakan rotasinya!',
                        contohSoal: '<strong>Soal 1:</strong> Bentuk yang diputar 90 derajat searah jarum jam akan menghadap ke?<br><strong>Langkah Penyelesaian:</strong> Sisi atas berpindah menghadap ke **Sisi Kanan**.'
                    },
                    {
                        title: 'Bab 8: Kalimat Efektif & Kehematan Kata',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Tata Kalimat:</strong> Kalimat efektif memenuhi syarat: kesepadanan struktur, keparalelan bentuk, kehematan kata, dan kelogisan penalaran.',
                        visual: 'Hindari Pleonasme: "sangat indah sekali" (Salah) → "sangat indah" (Benar)',
                        tips: 'Subjek kalimat tidak boleh didahului oleh kata depan (seperti "Dalam...", "Bagi...", "Untuk...").',
                        contohSoal: '<strong>Soal 1:</strong> Perbaiki kalimat pleonasme: "Hadirin para bapak-bapak sekalian".<br><strong>Langkah Penyelesaian:</strong> Kalimat efektif: "**Hadirin sekalian**" atau "**Para bapak**".'
                    },
                    {
                        title: 'Bab 9: Pemahaman Paragraf: Hubungan Antarkalimat',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Kohesi Teks:</strong> Menganalisis keterkaitan logis antarkalimat: hubungan penjelas, pertentangan, sebab-akibat, penegasan, atau contoh.',
                        visual: 'Konjungsi Antarkalimat: Namun, Oleh karena itu, Dengan demikian',
                        tips: 'Kata konjungsi "Namun" digunakan di awal kalimat untuk menyatakan pertentangan dengan kalimat sebelumnya.',
                        contohSoal: '<strong>Soal 1:</strong> Kata sambung untuk menunjukkan hubungan akibat di awal kalimat?<br><strong>Langkah Penyelesaian:</strong> Menggunakan konjungsi **"Oleh karena itu,"**.'
                    },
                    {
                        title: 'Bab 10: Teks Argumentasi: Inferensi & Simpulan Implisit',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Penalaran Kritis:</strong> Menarik simpulan tersirat (*inferensi*) yang tidak tertulis secara eksplisit berdasarkan bukti faktual paragraf.',
                        visual: 'Inferensi Sah = Harus Didukung Bukti Langsung dalam Teks Paragraf',
                        tips: 'Jangan memilih jawaban simpulan yang mengandung kata-kata ekstrem tanpa bukti kuat!',
                        contohSoal: '<strong>Soal 1:</strong> Apakah syarat utama kesimpulan implisit paragraf dapat dinyatakan sah?<br><strong>Langkah Penyelesaian:</strong> Harus sepenuhnya **didukung oleh fakta dalam teks**.'
                    },
                    {
                        title: 'Bab 11: Literasi Bahasa Inggris: Main Idea & Author\'s Attitude',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Literasi Inggris:</strong> Memahami teks akademik Bahasa Inggris: *Main Idea*, *Author\'s Tone* (*Critical, Neutral, Optimistic*), *Synonyms in Context*.',
                        visual: 'Tone: Critical, Informative, Objective, Persuasive, Skeptical',
                        tips: 'Lakukan *skimming* pada paragraf pertama dan terakhir untuk menemukan *topic sentence*.',
                        contohSoal: '<strong>Soal 1:</strong> What is the main purpose of an informative text in English literacy?<br><strong>Langkah Penyelesaian:</strong> To **provide factual information to the readers**.'
                    },
                    {
                        title: 'Bab 12: Literasi Bahasa Inggris: Inference & Vocabulary',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Pemahaman Konteks:</strong> Menarik kesimpulan tersirat dalam bacaan Bahasa Inggris serta menentukan padanan kata teknis akademik.',
                        visual: 'Inference Questions: "It can be inferred from paragraph 2 that..."',
                        tips: 'Gunakan kalimat sebelum dan sesudah kata asing untuk menebak arti secara kontekstual.',
                        contohSoal: '<strong>Soal 1:</strong> Synonym of the word "substantial" in academic context?<br><strong>Langkah Penyelesaian:</strong> Synonym: **Significant / Considerable**.'
                    },
                    {
                        title: 'Bab 13: Penalaran Matematika Sederhana & Diagram Venn',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Himpunan:</strong> Soal cerita aplikasi himpunan dan diagram Venn pada permasalahan sehari-hari: $n(A \cup B) = n(A) + n(B) - n(A \cap B)$.',
                        visual: 'Diagram Venn: n(A ∪ B) = n(A) + n(B) - n(A ∩ B)',
                        tips: 'Isi bagian irisan $n(A \cap B)$ terlebih dahulu di tengah diagram Venn!',
                        contohSoal: '<strong>Soal 1:</strong> Dari 30 siswa, 20 suka Mat, 15 suka Fis, 10 suka keduanya. Berapa tidak suka keduanya?<br><strong>Langkah Penyelesaian:</strong><br>1. Suka setidaknya satu $= 20 + 15 - 10 = 25$.<br>2. Tidak suka keduanya $= 30 - 25 = \mathbf{5\text{ siswa}}$.'
                    },
                    {
                        title: 'Bab 14: Analisis Tabel, Grafik & Data Statistik UTBK',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Interpretasi Data:</strong> Membaca dan menyimpulkan tren data kuantitatif dalam bentuk tabel, diagram batang, atau grafik garis. Persentase Kenaikan $= \frac{\text{Data Baru} - \text{Data Lama}}{\text{Data Lama}} \times 100\%$.',
                        visual: 'Persentase Kenaikan = [ (Data Baru - Data Lama) / Data Lama ] × 100%',
                        tips: 'Perhatikan skala pada sumbu X dan sumbu Y sebelum melakukan penghitungan angka!',
                        contohSoal: '<strong>Soal 1:</strong> Penjualan naik dari 100 ke 150 unit. Berapa persen kenaikannya?<br><strong>Langkah Penyelesaian:</strong> Kenaikan $= \frac{150 - 100}{100} \times 100\% = \mathbf{50\%}$.'
                    },
                    {
                        title: 'Bab 15: Pemecahan Masalah Studi Kasus Kebijakan Publik',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Akar Konsep Studi Kasus:</strong> Menguji penalaran logis kritis dalam menilai solusi paling efektif dari permasalahan dilema sosial atau ekonomi.',
                        visual: 'Pilih Solusi Paling Rasional, Berdampak Luas & Minim Risiko Negatif',
                        tips: 'Gunakan prinsip kepatuhan hukum dan efisiensi biaya saat memilih opsi solusi terbaik.',
                        contohSoal: '<strong>Soal 1:</strong> Kriteria utama memilih solusi terbaik dari kasus dilema publik?<br><strong>Langkah Penyelesaian:</strong> Memilih solusi yang **paling rasional, minim dampak negatif, dan sesuai hukum**.'
                    }
                ]
            },
            simulasiBank: {
                'utbk-pk': {
                    title: 'UTBK SNBT - Pengetahuan Kuantitatif (PK)',
                    durasiMinutes: 10,
                    soal: [
                        {
                            id: 'pk_q1',
                            pertanyaan: 'Diketahui persamaan kuadrat x² - (k + 2)x + 16 = 0 memiliki dua akar real positif yang sama (kembar). Nilai k yang memenuhi adalah...',
                            pilihan: ['A. 6 atau -10', 'B. 6 saja', 'C. 8 atau -8', 'D. 10 saja', 'E. -6 saja'],
                            kunci: 'B. 6 saja',
                            solusiLengkap: '1. Syarat kembar: D = b² - 4ac = 0 ⇒ (-(k+2))² - 64 = 0 ⇒ k+2 = ±8 ⇒ k = 6 atau -10.<br>2. Syarat akar positif: x₁+x₂ = k+2 > 0 ⇒ 6+2 = 8 > 0 (Memenuhi k=6).'
                        },
                        {
                            id: 'pk_q2',
                            pertanyaan: 'Jika 3ⁿ⁺¹ + 3ⁿ = 36, maka nilai dari 2ⁿ adalah...',
                            pilihan: ['A. 2', 'B. 4', 'C. 8', 'D. 16', 'E. 32'],
                            kunci: 'B. 4',
                            solusiLengkap: '3ⁿ(3 + 1) = 36 ⇒ 3ⁿ(4) = 36 ⇒ 3ⁿ = 9 ⇒ n = 2. Maka 2ⁿ = 2² = 4.'
                        }
                    ]
                }
            }
        };

        // UI View Switcher Engine
        function switchView(viewName) {
            state.activeView = viewName;

            ['home', 'materi', 'visualizer', 'kalkulator', 'utbk', 'flashcards', 'riwayat'].forEach(v => {
                const el = document.getElementById(`nav-${v}`);
                if (el) {
                    el.className = v === viewName 
                        ? "px-3.5 py-2 rounded-xl text-white bg-purple-600 font-bold shadow-md shadow-purple-600/30 transition flex items-center gap-1.5"
                        : "px-3.5 py-2 rounded-xl text-slate-300 hover:text-white font-medium transition flex items-center gap-1.5";
                }

                const mobEl = document.getElementById(`mob-${v}`);
                if (mobEl) {
                    mobEl.className = v === viewName 
                        ? "flex flex-col items-center gap-1 text-purple-400 font-bold"
                        : "flex flex-col items-center gap-1 text-slate-400 font-medium";
                }
            });

            const content = document.getElementById('app-content');
            if (viewName === 'home') content.innerHTML = renderHome();
            else if (viewName === 'materi') content.innerHTML = renderMateriScreen();
            else if (viewName === 'visualizer') {
                content.innerHTML = renderVisualizerScreen();
                initGraphCanvas();
            }
            else if (viewName === 'kalkulator') content.innerHTML = renderKalkulatorScreen();
            else if (viewName === 'utbk') content.innerHTML = renderUTBKScreen();
            else if (viewName === 'flashcards') content.innerHTML = renderFlashcardScreen();
            else if (viewName === 'riwayat') {
                content.innerHTML = renderRiwayatScreen();
                if (state.attempts.length > 0) openDetailRiwayat(state.attempts.length - 1);
            }

            lucide.createIcons();
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Search Engine
        function handleGlobalSearch(query) {
            const popover = document.getElementById('search-results-popover');
            if (!query || query.trim().length < 2) {
                popover.classList.add('hidden');
                return;
            }

            const q = query.toLowerCase().trim();
            let matches = [];

            db.mapel.forEach(m => {
                const list = db.materiDetails[m.id] || [];
                list.forEach(mat => {
                    if (mat.title.toLowerCase().includes(q) || mat.summary.toLowerCase().includes(q)) {
                        matches.push({ mapelId: m.id, mapelNama: m.nama, title: mat.title });
                    }
                });
            });

            if (matches.length === 0) {
                popover.innerHTML = `<div class="p-3 text-xs text-slate-400 text-center">Tidak ditemukan materi dengan kata kunci "${query}"</div>`;
            } else {
                popover.innerHTML = matches.map(res => `
                    <div onclick="selectSearchResult('${res.mapelId}')" class="p-3 hover:bg-slate-800/80 rounded-xl cursor-pointer transition border-b border-slate-800/60 last:border-0">
                        <span class="text-[10px] font-bold text-purple-400 uppercase tracking-wider block">${res.mapelNama}</span>
                        <span class="text-xs text-white font-semibold block mt-0.5">${res.title}</span>
                    </div>
                `).join('');
            }
            popover.classList.remove('hidden');
        }

        function selectSearchResult(mapelId) {
            document.getElementById('search-results-popover').classList.add('hidden');
            document.getElementById('global-search').value = '';
            state.selectedSubject = mapelId;
            switchView('materi');
            openDetailMapel(mapelId);
        }

        // Render Home View
        function renderHome() {
            return `
                <div class="relative rounded-3xl gradient-brand p-8 sm:p-12 overflow-hidden border border-purple-500/30 shadow-2xl mb-12">
                    <div class="absolute -right-20 -bottom-20 w-96 h-96 bg-purple-600/20 rounded-full blur-3xl pointer-events-none"></div>
                    <div class="relative z-10 max-w-3xl">
                        <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-purple-500/10 border border-purple-500/30 text-purple-300 text-xs font-semibold mb-6">
                            <i data-lucide="sparkles" class="w-4 h-4 text-purple-400"></i>
                            <span>Nihiluxxy AI Pro v8.0 • Megamodule Engine Edition</span>
                        </div>
                        <h1 class="text-3xl sm:text-5xl font-black text-white tracking-tight mb-4 leading-tight">
                            Kuasai Seluruh Konsep SMA & Taklukkan <span class="bg-clip-text text-transparent gradient-accent">UTBK SNBT 2026</span>.
                        </h1>
                        <p class="text-slate-300 text-xs sm:text-sm mb-8 leading-relaxed">
                            Modul Bimbel Elite 135 Bab Penuh, derivasi rumus mendalam, analogi visual intuitif, visualizer grafik interaktif, serta **Nihiluxxy AI Tutor v8.0** yang mengupas materi hingga akar-akarnya!
                        </p>
                        <div class="flex flex-wrap gap-4">
                            <button onclick="switchView('materi')" class="gradient-accent text-white font-extrabold px-6 py-3.5 rounded-2xl shadow-lg shadow-purple-500/25 hover:opacity-95 transition flex items-center gap-2 text-xs sm:text-sm">
                                <i data-lucide="book-open" class="w-4 h-4"></i> Pelajari 135 Modul Terperinci
                            </button>
                            <button onclick="switchView('visualizer')" class="bg-slate-900/90 border border-emerald-500/40 text-emerald-200 font-extrabold px-6 py-3.5 rounded-2xl hover:bg-slate-800 transition flex items-center gap-2 text-xs sm:text-sm">
                                <i data-lucide="line-chart" class="w-4 h-4 text-emerald-400"></i> Simulasikan Grafik Fungsi
                            </button>
                        </div>
                    </div>
                </div>

                <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-12">
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-purple-400 font-mono">135 Bab</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">Modul Terperinci Penuh</span>
                    </div>
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-emerald-400 font-mono">100%</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">K13 & Merdeka Active</span>
                    </div>
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-amber-400 font-mono">HOTS</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">Pembahasan Akar Konsep</span>
                    </div>
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-cyan-400 font-mono">2026</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">Megamodule Engine v8.0</span>
                    </div>
                </div>

                <!-- Subject Grid -->
                <div class="mb-12">
                    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 mb-6">
                        <div>
                            <h2 class="text-2xl font-black text-white tracking-tight">Mata Pelajaran SMA (Bimbel Elite Standard)</h2>
                            <p class="text-slate-400 text-xs sm:text-sm">Pilih kurikulum untuk menyesuaikan target pembelajaran</p>
                        </div>
                        <div class="bg-slate-900/90 p-1 rounded-2xl border border-slate-800 flex gap-1 text-xs font-bold">
                            <button onclick="setKurikulum('Merdeka')" class="px-4 py-2 rounded-xl transition ${state.selectedKurikulum === 'Merdeka' ? 'bg-purple-600 text-white shadow-md' : 'text-slate-400 hover:text-white'}">Kurikulum Merdeka</button>
                            <button onclick="setKurikulum('K13')" class="px-4 py-2 rounded-xl transition ${state.selectedKurikulum === 'K13' ? 'bg-purple-600 text-white shadow-md' : 'text-slate-400 hover:text-white'}">Kurikulum 2013</button>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
                        ${db.mapel.map(m => `
                            <div class="glass-card border border-slate-800 hover:border-purple-500/60 p-5 rounded-2xl transition duration-300 hover:-translate-y-1 group cursor-pointer shadow-lg relative overflow-hidden" onclick="openDetailMapel('${m.id}')">
                                <div class="w-12 h-12 rounded-2xl bg-gradient-to-br ${m.color} flex items-center justify-center text-white mb-4 shadow-lg group-hover:scale-110 transition duration-300">
                                    <i data-lucide="${m.icon}"></i>
                                </div>
                                <h3 class="font-extrabold text-white text-base mb-1 group-hover:text-purple-300 transition">${m.nama}</h3>
                                <p class="text-[11px] text-purple-400 font-semibold mb-4 leading-tight">
                                    ${state.selectedKurikulum === 'Merdeka' ? m.merdeka : m.k13}
                                </p>
                                <div class="flex items-center justify-between text-xs text-slate-400 pt-3 border-t border-slate-800/80">
                                    <span class="font-bold text-[11px]">Buka Modul Belajar</span>
                                    <i data-lucide="arrow-right" class="w-4 h-4 text-purple-400 group-hover:translate-x-1 transition"></i>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                </div>
            `;
        }

        function setKurikulum(k) {
            state.selectedKurikulum = k;
            switchView('home');
        }

        // Render Modul Materi Screen with Notes Feature
        function renderMateriScreen() {
            return `
                <div class="mb-8">
                    <h1 class="text-3xl font-black text-white tracking-tight">Modul Pembelajaran SMA (Kupas Tuntas Akar Konsep)</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Penjelasan mendalam, derivasi matematis, analogi intuitif, rumus visual, dan contoh soal HOTS berantai.</p>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                    <div class="lg:col-span-4 space-y-3">
                        <h3 class="text-xs uppercase tracking-wider font-extrabold text-purple-400 px-1">Pilih Mata Pelajaran</h3>
                        ${db.mapel.map(m => `
                            <button onclick="openDetailMapel('${m.id}')" id="mapel-btn-${m.id}" class="w-full text-left p-4 rounded-2xl bg-slate-900/60 border border-slate-800 hover:bg-slate-800 hover:border-purple-500/50 transition flex items-center gap-3.5 group">
                                <div class="w-10 h-10 rounded-xl bg-gradient-to-br ${m.color} flex items-center justify-center text-white font-bold text-xs shadow-md group-hover:scale-105 transition">
                                    <i data-lucide="${m.icon}" class="w-5 h-5"></i>
                                </div>
                                <div class="flex flex-col">
                                    <span class="font-extrabold text-sm text-slate-200 group-hover:text-purple-300 transition">${m.nama}</span>
                                    <span class="text-[10px] text-slate-500 font-medium">15 Bab Terperinci Penuh</span>
                                </div>
                            </button>
                        `).join('')}
                    </div>
                    <div id="materi-reader" class="lg:col-span-8 glass-card border border-slate-800 rounded-3xl p-6 sm:p-8 shadow-2xl">
                        <!-- Injected by JS -->
                    </div>
                </div>
            `;
        }

        function openDetailMapel(mapelId) {
            state.selectedSubject = mapelId;
            if (state.activeView !== 'materi') switchView('materi');

            db.mapel.forEach(m => {
                const btn = document.getElementById(`mapel-btn-${m.id}`);
                if (btn) {
                    btn.className = m.id === mapelId
                        ? "w-full text-left p-4 rounded-2xl bg-slate-800 border border-purple-500/80 flex items-center gap-3.5 group shadow-lg"
                        : "w-full text-left p-4 rounded-2xl bg-slate-900/60 border border-slate-800 hover:bg-slate-800 transition flex items-center gap-3.5 group";
                }
            });

            const mapel = db.mapel.find(m => m.id === mapelId);
            const materiList = db.materiDetails[mapelId] || [];
            const savedNote = state.userNotes[mapelId] || '';

            const reader = document.getElementById('materi-reader');
            if (reader) {
                reader.innerHTML = `
                    <div class="flex items-center justify-between pb-6 border-b border-slate-800 mb-8">
                        <div class="flex items-center gap-4">
                            <div class="w-12 h-12 rounded-2xl bg-gradient-to-br ${mapel.color} flex items-center justify-center text-white font-bold shadow-lg">
                                <i data-lucide="${mapel.icon}"></i>
                            </div>
                            <div>
                                <h2 class="text-2xl font-black text-white tracking-tight">${mapel.nama}</h2>
                                <p class="text-xs text-purple-400 font-extrabold mt-0.5">Materi Terperinci Kurikulum Merdeka & K13 (15 Bab Penuh)</p>
                            </div>
                        </div>
                        <button onclick="askAiAboutSubject('${mapel.nama}')" class="px-3.5 py-2 rounded-xl bg-purple-600/20 border border-purple-500/40 text-purple-300 hover:bg-purple-600 hover:text-white transition text-xs font-bold flex items-center gap-1.5">
                            <i data-lucide="bot" class="w-4 h-4"></i> Tanya AI
                        </button>
                    </div>

                    <!-- Personal Interactive Note Area -->
                    <div class="bg-slate-900/90 border border-purple-500/30 p-5 rounded-2xl mb-8 shadow-md">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-xs font-extrabold text-purple-300 flex items-center gap-1.5">
                                <i data-lucide="notebook-pen" class="w-4 h-4 text-purple-400"></i> Catatan Ringkas Pribadi (${mapel.nama})
                            </span>
                            <button onclick="saveUserNote('${mapelId}')" class="px-3 py-1 bg-purple-600 hover:bg-purple-500 text-white rounded-lg text-[10px] font-bold transition">
                                Simpan Catatan
                            </button>
                        </div>
                        <textarea id="user-note-input" rows="3" placeholder="Tuliskan rumus cepat atau ringkasan pribadi kamu untuk bab ini di sini..." class="w-full bg-slate-950 border border-slate-700/80 rounded-xl p-3 text-xs text-slate-100 focus:outline-none focus:border-purple-500 custom-scrollbar">${savedNote}</textarea>
                    </div>

                    <div class="space-y-6">
                        ${materiList.map((mat, idx) => `
                            <div class="bg-slate-900/90 border border-slate-800 p-6 rounded-2xl shadow-md">
                                <div class="flex items-center justify-between mb-3">
                                    <span class="text-[10px] font-extrabold uppercase bg-purple-500/20 text-purple-300 px-3 py-1 rounded-full border border-purple-500/30">${mat.kurikulum}</span>
                                    <span class="text-xs text-slate-500 font-mono">Modul Terperinci #${idx + 1}</span>
                                </div>
                                <h3 class="text-lg font-extrabold text-white mb-3">${mat.title}</h3>
                                <div class="text-slate-300 text-xs sm:text-sm mb-4 leading-relaxed">${mat.summary}</div>
                                
                                <div class="bg-slate-950 p-4 rounded-xl font-mono text-xs text-purple-300 mb-4 border border-slate-800 text-center overflow-x-auto">
                                    ${mat.visual}
                                </div>

                                <div class="bg-amber-500/10 border-l-4 border-amber-500 p-4 rounded-r-xl text-xs text-amber-200 mb-4 leading-relaxed">
                                    ${mat.tips}
                                </div>

                                <div class="bg-slate-950/80 border border-slate-800 p-4 rounded-xl text-xs text-slate-300 leading-relaxed mb-4">
                                    <span class="text-emerald-400 font-extrabold block mb-2">📝 Pembahasan Soal HOTS & Akar Konsep:</span>
                                    ${mat.contohSoal}
                                </div>

                                <button onclick="askAiAboutTopic('${mat.title}')" class="w-full py-2.5 bg-slate-800 hover:bg-purple-900/40 border border-slate-700 hover:border-purple-500/50 text-purple-300 text-xs font-bold rounded-xl transition flex items-center justify-center gap-2">
                                    <i data-lucide="sparkles" class="w-3.5 h-3.5"></i> Minta AI Bedah Lebih Dalam Bab Ini
                                </button>
                            </div>
                        `).join('')}
                    </div>
                `;
                lucide.createIcons();
            }
        }

        function saveUserNote(mapelId) {
            const input = document.getElementById('user-note-input');
            if (input) {
                state.userNotes[mapelId] = input.value;
                localStorage.setItem('nihiluxxy_v8_notes', JSON.stringify(state.userNotes));
                alert('Catatan pribadi kamu berhasil disimpan!');
            }
        }

        // Render Canvas Interactive Graph Visualizer Screen
        function renderVisualizerScreen() {
            return `
                <div class="mb-8">
                    <h1 class="text-3xl font-black text-white tracking-tight">AI Graph & Math Visualizer (Interactive Canvas)</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Simulasikan kurva parabola $f(x) = ax^2 + bx + c$ secara otomatis untuk memahami pengaruh diskriminan dan titik puncak.</p>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                    <div class="lg:col-span-5 glass-card border border-purple-500/30 p-6 rounded-3xl shadow-xl">
                        <h3 class="font-extrabold text-white text-base mb-4 flex items-center gap-2">
                            <i data-lucide="sliders" class="w-5 h-5 text-purple-400"></i> Kontrol Parameter Parabola
                        </h3>

                        <div class="space-y-5 text-xs font-semibold">
                            <div>
                                <div class="flex justify-between mb-1 text-slate-300">
                                    <span>Nilai a (Arah Kurva): <span id="val-a" class="text-purple-400 font-mono font-bold">1</span></span>
                                </div>
                                <input type="range" id="slider-a" min="-5" max="5" step="0.5" value="1" oninput="updateGraphCanvas()" class="w-full accent-purple-500">
                            </div>

                            <div>
                                <div class="flex justify-between mb-1 text-slate-300">
                                    <span>Nilai b (Pergeseran Puncak): <span id="val-b" class="text-purple-400 font-mono font-bold">-2</span></span>
                                </div>
                                <input type="range" id="slider-b" min="-10" max="10" step="1" value="-2" oninput="updateGraphCanvas()" class="w-full accent-purple-500">
                            </div>

                            <div>
                                <div class="flex justify-between mb-1 text-slate-300">
                                    <span>Nilai c (Titik Potong Sumbu Y): <span id="val-c" class="text-purple-400 font-mono font-bold">-3</span></span>
                                </div>
                                <input type="range" id="slider-c" min="-10" max="10" step="1" value="-3" oninput="updateGraphCanvas()" class="w-full accent-purple-500">
                            </div>
                        </div>

                        <div id="graph-analysis-box" class="mt-6 p-4 rounded-2xl bg-slate-950 border border-slate-800 text-xs font-mono text-slate-300 space-y-1.5">
                            <!-- Injected by JS -->
                        </div>
                    </div>

                    <div class="lg:col-span-7 glass-card border border-slate-800 p-6 rounded-3xl flex flex-col justify-center items-center shadow-xl">
                        <canvas id="graphCanvas" width="500" height="400" class="w-full max-w-lg bg-slate-950 border border-slate-800 rounded-2xl shadow-inner"></canvas>
                        <span class="text-[10px] text-slate-500 font-mono mt-3">Visualisasi Grafik Kartesius Canvas HTML5 Real-Time</span>
                    </div>
                </div>
            `;
        }

        function initGraphCanvas() {
            setTimeout(updateGraphCanvas, 50);
        }

        function updateGraphCanvas() {
            const sliderA = document.getElementById('slider-a');
            const sliderB = document.getElementById('slider-b');
            const sliderC = document.getElementById('slider-c');
            const canvas = document.getElementById('graphCanvas');
            if (!sliderA || !sliderB || !sliderC || !canvas) return;

            const a = parseFloat(sliderA.value);
            const b = parseFloat(sliderB.value);
            const c = parseFloat(sliderC.value);

            document.getElementById('val-a').innerText = a;
            document.getElementById('val-b').innerText = b;
            document.getElementById('val-c').innerText = c;

            // Analysis Calculation
            const D = b * b - 4 * a * c;
            const xp = a !== 0 ? -b / (2 * a) : 0;
            const yp = a !== 0 ? -D / (4 * a) : c;

            const analysisBox = document.getElementById('graph-analysis-box');
            if (analysisBox) {
                analysisBox.innerHTML = `
                    <div class="text-emerald-400 font-bold mb-1">📊 Analisis Matematika Grafik:</div>
                    <div>Persamaan: f(x) = ${a}x² ${b >= 0 ? '+ '+b : b}x ${c >= 0 ? '+ '+c : c}</div>
                    <div>Diskriminan D = ${D} (${D > 0 ? 'D > 0: 2 Akar Real' : D === 0 ? 'D = 0: 1 Akar Kembar' : 'D < 0: Imajiner'})</div>
                    <div>Titik Puncak Parabola: (${xp.toFixed(2)}, ${yp.toFixed(2)})</div>
                    <div>Bentuk: ${a > 0 ? 'Terbuka Ke Atas (Minimum)' : a < 0 ? 'Terbuka Ke Bawah (Maksimum)' : 'Garis Lurus'}</div>
                `;
            }

            const ctx = canvas.getContext('2d');
            const width = canvas.width;
            const height = canvas.height;
            const cx = width / 2;
            const cy = height / 2;
            const scale = 20; // 20px per unit

            ctx.clearRect(0, 0, width, height);

            // Draw Grid Lines
            ctx.strokeStyle = '#1e293b';
            ctx.lineWidth = 1;
            for (let x = 0; x < width; x += scale) {
                ctx.beginPath(); ctx.moveTo(x, 0); ctx.lineTo(x, height); ctx.stroke();
            }
            for (let y = 0; y < height; y += scale) {
                ctx.beginPath(); ctx.moveTo(0, y); ctx.lineTo(width, y); ctx.stroke();
            }

            // Draw Main Axes X and Y
            ctx.strokeStyle = '#64748b';
            ctx.lineWidth = 2;
            ctx.beginPath(); ctx.moveTo(0, cy); ctx.lineTo(width, cy); ctx.stroke();
            ctx.beginPath(); ctx.moveTo(cx, 0); ctx.lineTo(cx, height); ctx.stroke();

            // Draw Parabola Curve
            ctx.strokeStyle = '#a855f7';
            ctx.lineWidth = 3;
            ctx.beginPath();

            let firstPoint = true;
            for (let px = 0; px <= width; px += 2) {
                const x = (px - cx) / scale;
                const y = a * x * x + b * x + c;
                const py = cy - y * scale;

                if (firstPoint) {
                    ctx.moveTo(px, py);
                    firstPoint = false;
                } else {
                    ctx.lineTo(px, py);
                }
            }
            ctx.stroke();

            // Draw Vertex Point
            if (a !== 0) {
                const vpx = cx + xp * scale;
                const vpy = cy - yp * scale;
                ctx.fillStyle = '#ec4899';
                ctx.beginPath();
                ctx.arc(vpx, vpy, 5, 0, 2 * Math.PI);
                ctx.fill();
            }
        }

        // Render Kalkulator Screen
        function renderKalkulatorScreen() {
            return `
                <div class="mb-8">
                    <h1 class="text-3xl font-black text-white tracking-tight">Kalkulator AI Matematika & Sains Multi-Solver</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Hitung otomatis persamaan kuadrat, determinan matriks, kombinasi, pH larutan, gas ideal, dan gerak parabola.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    
                    <!-- 1. Persamaan Kuadrat -->
                    <div class="glass-card border border-purple-500/30 p-6 rounded-3xl shadow-xl">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="p-2.5 rounded-xl bg-purple-500/20 text-purple-300">
                                <i data-lucide="function-square" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-extrabold text-white text-sm">Persamaan Kuadrat (ax² + bx + c = 0)</h3>
                        </div>
                        <div class="grid grid-cols-3 gap-2 mb-4">
                            <input type="number" id="calc-a" placeholder="a" value="1" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="calc-b" placeholder="b" value="-5" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="calc-c" placeholder="c" value="6" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                        </div>
                        <button onclick="calculateQuad()" class="w-full py-2 bg-purple-600 hover:bg-purple-500 text-white font-extrabold text-xs rounded-xl transition mb-4 shadow-md">
                            Hitung Akar & Vieta
                        </button>
                        <div id="calc-quad-res" class="bg-slate-950/80 border border-slate-800 p-3 rounded-xl text-xs font-mono text-purple-300">
                            Hasil akan muncul di sini...
                        </div>
                    </div>

                    <!-- 2. Fisika: Hukum Gas Ideal PV = nRT -->
                    <div class="glass-card border border-amber-500/30 p-6 rounded-3xl shadow-xl">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="p-2.5 rounded-xl bg-amber-500/20 text-amber-300">
                                <i data-lucide="flame" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-extrabold text-white text-sm">Gas Ideal (Tekanan P = nRT / V)</h3>
                        </div>
                        <div class="grid grid-cols-3 gap-2 mb-4">
                            <input type="number" id="gas-n" placeholder="n (mol)" value="1" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="gas-t" placeholder="T (°C)" value="27" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="gas-v" placeholder="V (Liter)" value="22.4" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                        </div>
                        <button onclick="calculateGasIdeal()" class="w-full py-2 bg-amber-600 hover:bg-amber-500 text-white font-extrabold text-xs rounded-xl transition mb-4 shadow-md">
                            Hitung Tekanan P (atm)
                        </button>
                        <div id="calc-gas-res" class="bg-slate-950/80 border border-slate-800 p-3 rounded-xl text-xs font-mono text-amber-300">
                            Hasil gas ideal di sini...
                        </div>
                    </div>

                    <!-- 3. Permutasi & Kombinasi -->
                    <div class="glass-card border border-emerald-500/30 p-6 rounded-3xl shadow-xl">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="p-2.5 rounded-xl bg-emerald-500/20 text-emerald-300">
                                <i data-lucide="dices" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-extrabold text-white text-sm">Permutasi P(n,r) & Kombinasi C(n,r)</h3>
                        </div>
                        <div class="grid grid-cols-2 gap-2 mb-4">
                            <input type="number" id="comb-n" placeholder="n (total)" value="6" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="comb-r" placeholder="r (dipilih)" value="3" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                        </div>
                        <button onclick="calculateComb()" class="w-full py-2 bg-emerald-600 hover:bg-emerald-500 text-white font-extrabold text-xs rounded-xl transition mb-4 shadow-md">
                            Hitung Peluang & Cara
                        </button>
                        <div id="calc-comb-res" class="bg-slate-950/80 border border-slate-800 p-3 rounded-xl text-xs font-mono text-emerald-300">
                            Hasil kombinasi di sini...
                        </div>
                    </div>

                </div>
            `;
        }

        // Calculation Logics
        function calculateQuad() {
            const a = parseFloat(document.getElementById('calc-a').value);
            const b = parseFloat(document.getElementById('calc-b').value);
            const c = parseFloat(document.getElementById('calc-c').value);
            const res = document.getElementById('calc-quad-res');

            if (isNaN(a) || isNaN(b) || isNaN(c) || a === 0) {
                res.innerHTML = "Nilai 'a' tidak boleh nol!";
                return;
            }

            const D = b * b - 4 * a * c;
            const x_sum = -b / a;
            const x_prod = c / a;

            let text = `D = ${D} | x₁+x₂ = ${x_sum} | x₁·x₂ = ${x_prod}<br>`;
            if (D > 0) {
                const x1 = (-b + Math.sqrt(D)) / (2 * a);
                const x2 = (-b - Math.sqrt(D)) / (2 * a);
                text += `Akar Real: x₁ = ${x1.toFixed(2)}, x₂ = ${x2.toFixed(2)}`;
            } else if (D === 0) {
                const x = -b / (2 * a);
                text += `Akar Kembar: x₁ = x₂ = ${x.toFixed(2)}`;
            } else {
                text += `Akar Imajiner (D < 0)`;
            }
            res.innerHTML = text;
        }

        function calculateGasIdeal() {
            const n = parseFloat(document.getElementById('gas-n').value);
            const tC = parseFloat(document.getElementById('gas-t').value);
            const v = parseFloat(document.getElementById('gas-v').value);
            const res = document.getElementById('calc-gas-res');

            if (isNaN(n) || isNaN(tC) || isNaN(v) || v <= 0) {
                res.innerHTML = "Volume harus lebih dari nol!";
                return;
            }

            const R = 0.08206; // L atm / mol K
            const TK = tC + 273.15;
            const P = (n * R * TK) / v;

            res.innerHTML = `Suhu T = ${TK.toFixed(2)} K<br><strong>Tekanan Gas P = ${P.toFixed(3)} atm</strong>`;
        }

        function factorial(n) {
            if (n < 0) return 0;
            if (n === 0 || n === 1) return 1;
            let val = 1;
            for (let i = 2; i <= n; i++) val *= i;
            return val;
        }

        function calculateComb() {
            const n = parseInt(document.getElementById('comb-n').value);
            const r = parseInt(document.getElementById('comb-r').value);
            const res = document.getElementById('calc-comb-res');

            if (isNaN(n) || isNaN(r) || r > n || n < 0 || r < 0) {
                res.innerHTML = "Syarat: 0 ≤ r ≤ n";
                return;
            }

            const P = factorial(n) / factorial(n - r);
            const C = P / factorial(r);

            res.innerHTML = `P(${n},${r}) = ${P} cara<br>C(${n},${r}) = ${C} cara`;
        }

        // Render UTBK Simulation Screen
        function renderUTBKScreen() {
            return `
                <div class="mb-8">
                    <h1 class="text-3xl font-black text-white tracking-tight">Simulasi TKA & UTBK SNBT 2026</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Uji pemahaman dengan timer real-time interaktif, penilaian otomatis, & pembahasan akar konsep.</p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="glass-card border border-slate-800 p-6 rounded-3xl flex flex-col justify-between shadow-xl">
                        <div>
                            <div class="w-12 h-12 rounded-2xl bg-amber-500/20 border border-amber-500/30 text-amber-400 flex items-center justify-center mb-4 font-black">
                                <i data-lucide="calculator" class="w-6 h-6"></i>
                            </div>
                            <span class="text-[10px] uppercase font-extrabold text-amber-400 bg-amber-500/10 px-2.5 py-1 rounded-md border border-amber-500/20">SNBT Standard</span>
                            <h3 class="text-xl font-extrabold text-white mt-3 mb-1">UTBK - Pengetahuan Kuantitatif (PK)</h3>
                            <p class="text-slate-400 text-xs mb-6 leading-relaxed">Uji pemahaman aljabar, kalkulus, logaritma, & geometri HOTS.</p>
                        </div>
                        <button onclick="startSimulasi('utbk-pk')" class="w-full py-3.5 bg-amber-500 hover:bg-amber-400 text-slate-950 font-black text-xs rounded-xl transition shadow-lg shadow-amber-500/20 flex items-center justify-center gap-2">
                            <i data-lucide="play" class="w-4 h-4 fill-current"></i> Mulai Tes (10 Menit)
                        </button>
                    </div>
                </div>
            `;
        }

        function startSimulasi(simKey) {
            state.activeSimKey = simKey;
            state.currentSimAnswers = {};
            const currentSim = db.simulasiBank[simKey];
            
            state.simTimeLeft = (currentSim.durasiMinutes || 10) * 60;

            const app = document.getElementById('app-content');
            app.innerHTML = `
                <div class="max-w-3xl mx-auto glass-card border border-purple-500/30 p-6 sm:p-8 rounded-3xl shadow-2xl relative">
                    <div class="sticky top-24 z-30 bg-slate-900/95 border border-purple-500/40 p-4 rounded-2xl mb-6 backdrop-blur-xl flex items-center justify-between shadow-xl">
                        <div>
                            <span class="text-[10px] font-extrabold text-purple-400 tracking-wider uppercase block">Simulasi Berjalan</span>
                            <h2 class="text-sm sm:text-base font-black text-white">${currentSim.title}</h2>
                        </div>
                        <div class="flex items-center gap-3">
                            <div class="bg-slate-950 border border-slate-700 px-3.5 py-1.5 rounded-xl text-center">
                                <span class="text-[9px] text-slate-400 uppercase font-extrabold block">Sisa Waktu</span>
                                <span id="sim-timer-display" class="text-xs sm:text-sm font-black text-amber-400 font-mono">10:00</span>
                            </div>
                        </div>
                    </div>

                    <div id="quiz-container" class="space-y-8">
                        ${currentSim.soal.map((q, idx) => `
                            <div class="bg-slate-900/90 p-6 rounded-2xl border border-slate-800">
                                <div class="flex items-center justify-between mb-3">
                                    <span class="text-xs font-bold text-purple-400 font-mono">Soal #${idx + 1}</span>
                                    <span class="text-[10px] text-slate-500 font-semibold">Tipe: Pilihan Ganda HOTS</span>
                                </div>
                                <p class="text-sm sm:text-base text-slate-100 font-medium mb-5 leading-relaxed">${q.pertanyaan}</p>
                                <div class="space-y-3">
                                    ${q.pilihan.map(opt => `
                                        <label class="flex items-center p-3.5 rounded-xl border border-slate-800 hover:bg-slate-800/80 hover:border-purple-500/50 transition cursor-pointer group">
                                            <input type="radio" name="question_${q.id}" value="${opt}" onchange="recordAnswer('${q.id}', '${opt}')" class="w-4 h-4 text-purple-600 focus:ring-purple-500 bg-slate-900 border-slate-700">
                                            <span class="ml-3.5 text-xs sm:text-sm text-slate-300 font-medium group-hover:text-white transition">${opt}</span>
                                        </label>
                                    `).join('')}
                                </div>
                            </div>
                        `).join('')}
                    </div>

                    <div class="mt-8 pt-6 border-t border-slate-800 flex justify-between items-center">
                        <button onclick="stopTimerAndExit()" class="px-5 py-2.5 border border-slate-800 text-slate-400 hover:text-white hover:bg-slate-800 text-xs font-extrabold rounded-xl transition">Batal</button>
                        <button onclick="submitSimulasi('${simKey}')" class="px-6 py-3.5 gradient-accent text-white font-black text-xs rounded-xl shadow-lg shadow-purple-500/25 hover:opacity-95 transition flex items-center gap-2">
                            <i data-lucide="check-circle" class="w-4 h-4"></i> Selesaikan Tes
                        </button>
                    </div>
                </div>
            `;
            lucide.createIcons();
            window.scrollTo({ top: 0, behavior: 'smooth' });

            clearInterval(state.simTimerInterval);
            state.simTimerInterval = setInterval(() => {
                state.simTimeLeft--;
                const mins = Math.floor(state.simTimeLeft / 60);
                const secs = state.simTimeLeft % 60;
                const display = `${mins.toString().padStart(2, '0')}:${secs.toString().padStart(2, '0')}`;
                
                const timerEl = document.getElementById('sim-timer-display');
                if (timerEl) {
                    timerEl.innerText = display;
                    if (state.simTimeLeft <= 60) timerEl.className = "text-xs sm:text-sm font-black text-rose-500 animate-pulse font-mono";
                }

                if (state.simTimeLeft <= 0) {
                    clearInterval(state.simTimerInterval);
                    alert('Waktu habis! Jawaban otomatis tersimpan.');
                    submitSimulasi(simKey);
                }
            }, 1000);
        }

        function recordAnswer(qId, val) {
            state.currentSimAnswers[qId] = val;
        }

        function stopTimerAndExit() {
            clearInterval(state.simTimerInterval);
            switchView('utbk');
        }

        function submitSimulasi(simKey) {
            clearInterval(state.simTimerInterval);
            const sim = db.simulasiBank[simKey];
            let benarCount = 0;
            const total = sim.soal.length;

            const reviewDetails = sim.soal.map(q => {
                const userAns = state.currentSimAnswers[q.id] || 'Tidak Dijawab';
                const isCorrect = userAns === q.kunci;
                if (isCorrect) benarCount++;
                return {
                    pertanyaan: q.pertanyaan,
                    jawabanUser: userAns,
                    kunci: q.kunci,
                    isCorrect: isCorrect,
                    solusi: q.solusiLengkap
                };
            });

            const score = Math.round((benarCount / total) * 100);
            const now = new Date();
            const dateStr = now.toLocaleDateString('id-ID', { day: 'numeric', month: 'short', year: 'numeric', hour: '2-digit', minute: '2-digit' }) + ' WIB';

            const attemptRecord = {
                id: 'att_' + Date.now(),
                judulSimulasi: sim.title,
                tanggal: dateStr,
                skor: score,
                benar: benarCount,
                totalSoal: total,
                detail: reviewDetails
            };

            state.attempts.push(attemptRecord);
            localStorage.setItem('nihiluxxy_v8_attempts', JSON.stringify(state.attempts));

            switchView('riwayat');
            openDetailRiwayat(state.attempts.length - 1);
        }

        // Flashcards View
        function renderFlashcardScreen() {
            let cards = db.flashcards;
            if (state.flashcardFilter && state.flashcardFilter !== 'semua') {
                cards = db.flashcards.filter(c => c.mapel.toLowerCase().includes(state.flashcardFilter.toLowerCase()));
            }
            if (cards.length === 0) cards = db.flashcards;
            if (state.currentFlashcardIdx >= cards.length) state.currentFlashcardIdx = 0;

            const card = cards[state.currentFlashcardIdx];

            return `
                <div class="mb-8 text-center max-w-2xl mx-auto">
                    <span class="text-xs font-extrabold uppercase tracking-widest text-emerald-400 bg-emerald-500/10 px-3 py-1 rounded-full border border-emerald-500/20 mb-2 inline-block">Flashcards Intuitif</span>
                    <h1 class="text-3xl font-black text-white tracking-tight">Latihan Cepat Hafalan & Konsep</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Uji ingatan intuitif Anda sebelum menghadapi ujian asli.</p>

                    <div class="flex flex-wrap justify-center gap-2 mt-4 text-xs font-semibold">
                        <button onclick="setFlashcardFilter('semua')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'semua' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Semua</button>
                        <button onclick="setFlashcardFilter('matematika')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'matematika' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Matematika</button>
                        <button onclick="setFlashcardFilter('fisika')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'fisika' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Fisika</button>
                        <button onclick="setFlashcardFilter('kimia')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'kimia' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Kimia</button>
                    </div>
                </div>

                <div class="max-w-xl mx-auto">
                    <div id="flashcard-box" onclick="flipFlashcard()" class="glass-card border border-purple-500/40 rounded-3xl p-8 sm:p-12 min-h-[280px] flex flex-col justify-between items-center text-center cursor-pointer shadow-2xl transition-all duration-300 transform hover:scale-[1.02]">
                        <span class="text-[10px] font-black uppercase text-purple-400 font-mono tracking-widest">${card.mapel} • Klik Kartu Membalik</span>
                        
                        <div id="flashcard-content" class="my-auto py-4 w-full">
                            <p class="text-base sm:text-lg font-bold text-white leading-relaxed">${card.pertanyaan}</p>
                        </div>

                        <span class="text-[11px] text-slate-500 font-bold">Kartu ${state.currentFlashcardIdx + 1} dari ${cards.length}</span>
                    </div>

                    <div class="flex justify-between items-center mt-6">
                        <button onclick="prevFlashcard()" class="px-5 py-2.5 bg-slate-900 border border-slate-800 text-slate-300 hover:text-white rounded-xl text-xs font-bold transition flex items-center gap-1.5">
                            <i data-lucide="arrow-left" class="w-4 h-4"></i> Sebelumnya
                        </button>
                        <button onclick="nextFlashcard()" class="px-5 py-2.5 bg-purple-600 hover:bg-purple-500 text-white rounded-xl text-xs font-bold transition flex items-center gap-1.5 shadow-lg shadow-purple-600/25">
                            Selanjutnya <i data-lucide="arrow-right" class="w-4 h-4"></i>
                        </button>
                    </div>
                </div>
            `;
        }

        let isCardFlipped = false;
        function flipFlashcard() {
            let cards = db.flashcards;
            if (state.flashcardFilter && state.flashcardFilter !== 'semua') {
                cards = db.flashcards.filter(c => c.mapel.toLowerCase().includes(state.flashcardFilter.toLowerCase()));
            }
            if (cards.length === 0) cards = db.flashcards;
            const card = cards[state.currentFlashcardIdx];
            const content = document.getElementById('flashcard-content');
            if (!content) return;

            isCardFlipped = !isCardFlipped;
            if (isCardFlipped) {
                content.innerHTML = `<p class="text-sm sm:text-base font-semibold text-emerald-300 leading-relaxed bg-emerald-950/40 p-4 rounded-2xl border border-emerald-500/30 shadow-inner">💡 ${card.jawaban}</p>`;
            } else {
                content.innerHTML = `<p class="text-base sm:text-lg font-bold text-white leading-relaxed">${card.pertanyaan}</p>`;
            }
        }

        function setFlashcardFilter(filter) {
            state.flashcardFilter = filter;
            state.currentFlashcardIdx = 0;
            isCardFlipped = false;
            switchView('flashcards');
        }

        function nextFlashcard() {
            let cards = db.flashcards;
            if (state.flashcardFilter && state.flashcardFilter !== 'semua') {
                cards = db.flashcards.filter(c => c.mapel.toLowerCase().includes(state.flashcardFilter.toLowerCase()));
            }
            if (cards.length === 0) cards = db.flashcards;

            isCardFlipped = false;
            state.currentFlashcardIdx = (state.currentFlashcardIdx + 1) % cards.length;
            switchView('flashcards');
        }

        function prevFlashcard() {
            let cards = db.flashcards;
            if (state.flashcardFilter && state.flashcardFilter !== 'semua') {
                cards = db.flashcards.filter(c => c.mapel.toLowerCase().includes(state.flashcardFilter.toLowerCase()));
            }
            if (cards.length === 0) cards = db.flashcards;

            isCardFlipped = false;
            state.currentFlashcardIdx = (state.currentFlashcardIdx - 1 + cards.length) % cards.length;
            switchView('flashcards');
        }

        // Render History View
        function renderRiwayatScreen() {
            if (state.attempts.length === 0) {
                return `
                    <div class="mb-8">
                        <h1 class="text-3xl font-black text-white tracking-tight">Riwayat Pengerjaan</h1>
                        <p class="text-slate-400 text-xs sm:text-sm mt-1">Daftar evaluasi simulasi dan pembahasan akar konsep Anda.</p>
                    </div>
                    <div class="glass-card border border-slate-800 rounded-3xl p-12 text-center text-slate-500 shadow-xl">
                        <div class="w-16 h-16 rounded-full bg-slate-900 border border-slate-800 flex items-center justify-center mx-auto mb-4 text-slate-600">
                            <i data-lucide="history" class="w-8 h-8"></i>
                        </div>
                        <p class="text-base font-extrabold text-slate-300">Belum Ada Riwayat Tersimpan</p>
                        <p class="text-xs text-slate-500 mt-1 mb-6">Selesaikan simulasi TKA/UTBK untuk mencatat riwayat jawaban Anda di sini.</p>
                        <button onclick="switchView('utbk')" class="px-6 py-3 bg-purple-600 hover:bg-purple-500 text-white font-extrabold text-xs rounded-xl transition shadow-lg shadow-purple-600/25">
                            Mulai Simulasi Sekarang
                        </button>
                    </div>
                `;
            }

            return `
                <div class="mb-8 flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                    <div>
                        <h1 class="text-3xl font-black text-white tracking-tight">Riwayat & Pembahasan Akar Konsep</h1>
                        <p class="text-slate-400 text-xs sm:text-sm mt-1">Pilih pengerjaan di bawah untuk memeriksa kunci jawaban & cara pengerjaan terperinci.</p>
                    </div>
                    <button onclick="clearHistory()" class="px-4 py-2 border border-rose-500/30 text-rose-400 hover:bg-rose-500/10 text-xs font-bold rounded-xl transition self-start sm:self-auto flex items-center gap-1.5">
                        <i data-lucide="trash-2" class="w-4 h-4"></i> Hapus Semua Riwayat
                    </button>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                    <div class="lg:col-span-4 space-y-3">
                        <h3 class="text-xs uppercase tracking-wider font-extrabold text-purple-400 px-1">Daftar Pengerjaan</h3>
                        ${state.attempts.map((att, idx) => `
                            <button onclick="openDetailRiwayat(${idx})" id="att-btn-${idx}" class="w-full text-left p-4 rounded-2xl bg-slate-900/60 border border-slate-800 hover:bg-slate-800 transition flex items-center justify-between group">
                                <div>
                                    <span class="text-[10px] text-slate-500 font-mono block">${att.tanggal}</span>
                                    <h4 class="font-extrabold text-xs sm:text-sm text-white group-hover:text-purple-300 transition mt-0.5">${att.judulSimulasi}</h4>
                                </div>
                                <span class="text-sm font-black text-purple-300 font-mono bg-purple-500/10 border border-purple-500/20 px-2.5 py-1 rounded-lg">${att.skor}%</span>
                            </button>
                        `).join('')}
                    </div>

                    <div id="riwayat-detail-container" class="lg:col-span-8 glass-card border border-slate-800 rounded-3xl p-6 sm:p-8 shadow-2xl">
                        <!-- History details injected here -->
                    </div>
                </div>
            `;
        }

        function openDetailRiwayat(index) {
            state.attempts.forEach((_, i) => {
                const btn = document.getElementById(`att-btn-${i}`);
                if (btn) {
                    btn.className = i === index
                        ? "w-full text-left p-4 rounded-2xl bg-slate-800 border border-purple-500/80 flex items-center justify-between shadow-lg"
                        : "w-full text-left p-4 rounded-2xl bg-slate-900/60 border border-slate-800 hover:bg-slate-800 transition flex items-center justify-between group";
                }
            });

            const att = state.attempts[index];
            const container = document.getElementById('riwayat-detail-container');
            if (!container || !att) return;

            container.innerHTML = `
                <div class="flex items-center justify-between pb-6 border-b border-slate-800 mb-6">
                    <div>
                        <span class="text-xs text-purple-400 font-mono font-semibold block">${att.tanggal}</span>
                        <h2 class="text-xl font-black text-white mt-0.5">${att.judulSimulasi}</h2>
                    </div>
                    <div class="text-right">
                        <span class="text-3xl font-black text-purple-300 font-mono">${att.skor}%</span>
                        <p class="text-[10px] text-slate-400 font-bold mt-0.5">${att.benar} dari ${att.totalSoal} Soal Benar</p>
                    </div>
                </div>

                <div class="space-y-6">
                    ${att.detail.map((d, i) => `
                        <div class="bg-slate-900/90 border ${d.isCorrect ? 'border-emerald-500/40' : 'border-rose-500/40'} p-5 rounded-2xl shadow-md">
                            <div class="flex items-center justify-between mb-3">
                                <span class="text-xs font-bold text-slate-400 font-mono">Soal #${i + 1}</span>
                                <span class="text-[10px] font-extrabold px-2.5 py-1 rounded-full ${d.isCorrect ? 'bg-emerald-500/20 text-emerald-300 border border-emerald-500/30' : 'bg-rose-500/20 text-rose-300 border border-rose-500/30'}">
                                    ${d.isCorrect ? '✓ Jawaban Benar' : '✗ Kurang Tepat'}
                                </span>
                            </div>
                            <p class="text-xs sm:text-sm text-slate-200 font-medium mb-4 leading-relaxed">${d.pertanyaan}</p>
                            
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 mb-4 text-xs font-semibold">
                                <div class="bg-slate-950 p-3 rounded-xl border border-slate-800">
                                    <span class="text-slate-500 block text-[10px] font-mono">Jawaban Anda:</span>
                                    <span class="${d.isCorrect ? 'text-emerald-300' : 'text-rose-300'} font-bold">${d.jawabanUser}</span>
                                </div>
                                <div class="bg-slate-950 p-3 rounded-xl border border-slate-800">
                                    <span class="text-slate-500 block text-[10px] font-mono">Kunci Akurat:</span>
                                    <span class="text-emerald-300 font-bold">${d.kunci}</span>
                                </div>
                            </div>

                            <div class="bg-purple-950/30 border border-purple-800/40 p-4 rounded-xl text-xs text-slate-300 leading-relaxed mb-3">
                                <span class="text-purple-300 font-extrabold block mb-1">📘 Pembahasan Akar Konsep & Langkah:</span>
                                ${d.solusi}
                            </div>
                        </div>
                    `).join('')}
                </div>
            `;
            lucide.createIcons();
        }

        function clearHistory() {
            if (confirm('Hapus seluruh riwayat pengerjaan simulasi?')) {
                state.attempts = [];
                localStorage.removeItem('nihiluxxy_v8_attempts');
                switchView('riwayat');
            }
        }

        // AI Tutor Drawer Modal Logic
        function toggleAiModal() {
            const modal = document.getElementById('ai-tutor-modal');
            if (modal) {
                modal.classList.toggle('hidden');
                if (!modal.classList.contains('hidden')) {
                    document.getElementById('ai-user-input')?.focus();
                }
            }
        }

        function handleAiKeyDown(e) {
            if (e.key === 'Enter' && !e.shiftKey) {
                e.preventDefault();
                sendAiQuery();
            }
        }

        function injectAiPrompt(text) {
            const input = document.getElementById('ai-user-input');
            if (input) {
                input.value = text;
                sendAiQuery();
            }
        }

        function askAiAboutTopic(topicTitle) {
            toggleAiModal();
            injectAiPrompt(`Tolong berikan penjelasan super mendalam, akar konsep, derivasi rumus, dan trik bimbel cepat untuk topik: ${topicTitle}`);
        }

        function askAiAboutSubject(subjectName) {
            toggleAiModal();
            injectAiPrompt(`Beri saya peta konsep akar terpenting yang sering keluar di UTBK SNBT 2026 untuk mata pelajaran: ${subjectName}`);
        }

        function sendAiQuery() {
            const input = document.getElementById('ai-user-input');
            const chatBody = document.getElementById('ai-chat-body');
            if (!input || !chatBody) return;

            const text = input.value.trim();
            if (!text) return;

            const userBubble = document.createElement('div');
            userBubble.className = "flex gap-3 items-start justify-end";
            userBubble.innerHTML = `
                <div class="bg-purple-600 text-white p-3.5 rounded-2xl text-xs sm:text-sm max-w-xl leading-relaxed shadow-lg font-medium">
                    ${text}
                </div>
                <div class="w-8 h-8 rounded-xl bg-slate-800 flex-shrink-0 flex items-center justify-center text-purple-300 text-xs font-bold font-mono">You</div>
            `;
            chatBody.appendChild(userBubble);

            input.value = '';
            chatBody.scrollTop = chatBody.scrollHeight;

            const aiBubble = document.createElement('div');
            aiBubble.className = "flex gap-3 items-start";
            const loadingId = 'ai-loading-' + Date.now();
            aiBubble.innerHTML = `
                <div class="w-8 h-8 rounded-xl gradient-accent flex-shrink-0 flex items-center justify-center text-white text-xs font-bold">AI</div>
                <div id="${loadingId}" class="bg-slate-900/90 border border-purple-500/30 p-4 rounded-2xl text-xs sm:text-sm text-slate-300 max-w-xl leading-relaxed shadow-lg flex items-center gap-2">
                    <i data-lucide="loader-2" class="w-4 h-4 text-purple-400 animate-spin"></i>
                    <span>Nihiluxxy AI v8.0 sedang membedah konsep & derivasi rumus...</span>
                </div>
            `;
            chatBody.appendChild(aiBubble);
            lucide.createIcons();
            chatBody.scrollTop = chatBody.scrollHeight;

            setTimeout(() => {
                const target = document.getElementById(loadingId);
                if (target) {
                    target.innerHTML = generateSmartAiResponse(text);
                    chatBody.scrollTop = chatBody.scrollHeight;
                }
            }, 900);
        }

        function generateSmartAiResponse(query) {
            const q = query.toLowerCase();

            if (q.includes('vieta') || q.includes('kuadrat')) {
                return `
                    <div class="space-y-3">
                        <span class="text-blue-400 font-extrabold block text-xs">➡️ Bedah Akar Konsep - Rumus Vieta Persamaan Kuadrat:</span>
                        <p>Persamaan $ax^2 + bx + c = 0$ dapat difaktorkan menjadi $a(x - x_1)(x - x_2) = 0$.</p>
                        <p>Jika dikalikan: $a[x^2 - (x_1 + x_2)x + x_1 x_2] = ax^2 - a(x_1 + x_2)x + a x_1 x_2 = 0$.</p>
                        <p>Dengan menyamakan koefisien $ax^2 + bx + c$, diperoleh dua teorema Vieta utama:</p>
                        <div class="bg-slate-950 p-3 rounded-xl border border-slate-800 text-xs font-mono text-purple-300 text-center">
                            x₁ + x₂ = -b/a   |   x₁ · x₂ = c/a   |   x₁ - x₂ = √D / a
                        </div>
                    </div>
                `;
            } else if (q.includes('respirasi') || q.includes('aerob') || q.includes('krebs')) {
                return `
                    <div class="space-y-3">
                        <span class="text-emerald-400 font-extrabold block text-xs">🧬 Bedah Biokimia - 4 Tahap Respirasi Aerob:</span>
                        <ul class="list-disc list-inside space-y-1.5 text-xs text-slate-300">
                            <li><strong>1. Glikolisis (Sitosol):</strong> 1 Glukosa → 2 Asam Pyruvat + 2 NADH + 2 ATP.</li>
                            <li><strong>2. Dekarboksilasi Oksidatif (Matriks Mitokondria):</strong> 2 Asam Pyruvat → 2 Asetil-KoA + 2 CO₂ + 2 NADH.</li>
                            <li><strong>3. Siklus Krebs (Matriks Mitokondria):</strong> 2 Asetil-KoA → 4 CO₂ + 6 NADH + 2 FADH₂ + 2 ATP.</li>
                            <li><strong>4. Transpor Elektron (Krista Mitokondria):</strong> Pembentukan total 34 ATP via fosforilasi oksidatif. (Akseptor elektron terakhir = O₂).</li>
                        </ul>
                    </div>
                `;
            } else {
                return `
                    <div class="space-y-2">
                        <span class="text-purple-300 font-extrabold block text-xs">🤖 Nihiluxxy AI v8.0 Analysis:</span>
                        <p>Terima kasih atas pertanyaanmu mengenai: <em>"${query}"</em>.</p>
                        <p>Untuk menyelesaikannya secara presisi, urutkan dulu data yang diketahui, tentukan konsep dasar hukum fisika/matematika yang menaunginya, dan gunakan fitur **Graph Visualizer AI** atau **Kalkulator Multi-Solver** jika memerlukan pembuktian visual!</p>
                    </div>
                `;
            }
        }

        // Initialize App
        document.addEventListener('DOMContentLoaded', () => {
            switchView('home');
        });
    </script>
</body>
</html>
