<!DOCTYPE html>
<html lang="id" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nihiluxxy AI Pro v6.5 - Super Module Elite & Presentation Learning Engine</title>
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
                        'fadeIn': 'fadeIn 0.3s ease-out forwards',
                    },
                    keyframes: {
                        pulseGlow: {
                            '0%': { boxShadow: '0 0 15px rgba(139, 92, 246, 0.25), 0 0 30px rgba(99, 102, 241, 0.15)' },
                            '100%': { boxShadow: '0 0 35px rgba(168, 85, 247, 0.55), 0 0 60px rgba(236, 72, 153, 0.3)' }
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0px)' },
                            '50%': { transform: 'translateY(-8px)' }
                        },
                        fadeIn: {
                            '0%': { opacity: '0', transform: 'translateY(6px)' },
                            '100%': { opacity: '1', transform: 'translateY(0)' }
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
            background-color: #050811;
            background-image: 
                radial-gradient(at 0% 0%, rgba(124, 58, 237, 0.22) 0px, transparent 50%),
                radial-gradient(at 100% 0%, rgba(99, 102, 241, 0.2) 0px, transparent 50%),
                radial-gradient(at 50% 100%, rgba(236, 72, 153, 0.15) 0px, transparent 50%);
            background-attachment: fixed;
        }
        .gradient-brand { background: linear-gradient(135deg, #090e1a 0%, #161b33 45%, #2a224a 100%); }
        .gradient-accent { background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 50%, #ec4899 100%); }
        .glass-header { background: rgba(5, 8, 17, 0.88); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); }
        .glass-card { background: rgba(18, 25, 43, 0.55); backdrop-filter: blur(16px); -webkit-backdrop-filter: blur(16px); border: 1px solid rgba(255, 255, 255, 0.09); }
        .glass-modal { background: rgba(8, 12, 24, 0.96); backdrop-filter: blur(24px); -webkit-backdrop-filter: blur(24px); border: 1px solid rgba(139, 92, 246, 0.4); }
        
        .custom-scrollbar::-webkit-scrollbar { width: 6px; height: 6px; }
        .custom-scrollbar::-webkit-scrollbar-track { background: rgba(9, 14, 26, 0.8); }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: rgba(139, 92, 246, 0.45); border-radius: 9999px; }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover { background: rgba(139, 92, 246, 0.8); }
    </style>
</head>
<body class="bg-[#050811] text-slate-100 min-h-screen flex flex-col selection:bg-purple-500 selection:text-white custom-scrollbar relative">

    <!-- Top Announcement & AI Status Bar -->
    <div class="bg-gradient-to-r from-purple-950 via-slate-950 to-indigo-950 text-xs py-2 px-4 font-medium border-b border-purple-500/20 text-purple-200 flex justify-between items-center z-50">
        <div class="flex items-center gap-2">
            <span class="inline-flex items-center px-2.5 py-0.5 rounded-full text-[10px] font-black bg-purple-500/20 text-purple-300 border border-purple-500/40 shadow-sm">
                ⚡ Nihiluxxy AI Pro v6.5 Slide Edition
            </span>
            <span class="hidden sm:inline text-slate-300">Sistem Modul Slide Interactive 15 Bab SMA & Bank Soal UTBK SNBT 2026</span>
        </div>
        <div class="flex items-center gap-4 text-[11px] font-semibold text-purple-300">
            <span class="hidden md:flex items-center gap-1.5 font-mono text-emerald-400">
                <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span> Presenter Engine Active
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
                    <i data-lucide="presentation" class="w-6 h-6"></i>
                </div>
                <div class="flex flex-col">
                    <div class="flex items-center gap-1.5">
                        <span class="text-2xl font-black tracking-tight text-white group-hover:text-purple-300 transition">Nihiluxxy</span>
                        <span class="text-[9px] font-black px-1.5 py-0.5 rounded-md bg-gradient-to-r from-purple-500 to-pink-500 text-white uppercase tracking-wider">AI PRO</span>
                    </div>
                    <span class="text-[9px] uppercase tracking-widest text-purple-400 font-extrabold -mt-1">Super Learning Engine</span>
                </div>
            </div>

            <!-- Global Search Desktop -->
            <div class="hidden lg:flex items-center flex-1 max-w-md mx-6">
                <div class="relative w-full">
                    <i data-lucide="search" class="w-4 h-4 absolute left-3.5 top-1/2 -translate-y-1/2 text-slate-400"></i>
                    <input type="text" id="global-search" oninput="handleGlobalSearch(this.value)" placeholder="Cari materi & soal (misal: Turunan, Termokimia, Hukum Newton, Indrajaja)..." class="w-full bg-slate-900/90 border border-slate-700/80 rounded-2xl pl-10 pr-12 py-2 text-xs text-slate-200 focus:outline-none focus:border-purple-500 focus:ring-1 focus:ring-purple-500 transition shadow-inner">
                    <kbd class="hidden sm:inline-block absolute right-3 top-1/2 -translate-y-1/2 text-[9px] bg-slate-800 border border-slate-700 px-1.5 py-0.5 rounded text-slate-400 font-mono font-bold">⌘K</kbd>
                    <div id="search-results-popover" class="hidden absolute left-0 right-0 top-12 bg-slate-900/95 border border-purple-500/30 rounded-2xl shadow-2xl p-2 z-50 max-h-80 overflow-y-auto custom-scrollbar backdrop-blur-xl"></div>
                </div>
            </div>

            <!-- Navigation Desktop -->
            <nav class="hidden md:flex items-center gap-1 bg-slate-900/90 p-1.5 rounded-2xl border border-slate-800 text-xs font-semibold">
                <button onclick="switchView('home')" id="nav-home" class="px-4 py-2.5 rounded-xl text-white bg-purple-600 transition flex items-center gap-1.5 font-bold shadow-md shadow-purple-600/30">
                    <i data-lucide="home" class="w-4 h-4"></i> Beranda
                </button>
                <button onclick="switchView('materi')" id="nav-materi" class="px-4 py-2.5 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="book-open" class="w-4 h-4"></i> Modul Slide
                </button>
                <button onclick="switchView('kalkulator')" id="nav-kalkulator" class="px-4 py-2.5 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="calculator" class="w-4 h-4 text-cyan-400"></i> Kalkulator AI
                </button>
                <button onclick="switchView('utbk')" id="nav-utbk" class="px-4 py-2.5 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="award" class="w-4 h-4 text-amber-400"></i> Simulasi UTBK
                </button>
                <button onclick="switchView('flashcards')" id="nav-flashcards" class="px-4 py-2.5 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
                    <i data-lucide="brain" class="w-4 h-4 text-emerald-400"></i> Flashcards
                </button>
                <button onclick="switchView('riwayat')" id="nav-riwayat" class="px-4 py-2.5 rounded-xl text-slate-300 hover:text-white transition flex items-center gap-1.5">
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
                            <h3 class="font-black text-white text-base">Nihiluxxy AI Super Tutor</h3>
                            <span class="text-[9px] px-2 py-0.5 rounded-full bg-emerald-500/20 text-emerald-300 border border-emerald-500/40 font-mono font-bold">Smart Multi-Solver v6.5</span>
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
                <button onclick="injectAiPrompt('Bagaimana cara cepat menghitung Perkalian Titik dan Proyeksi Vektor Ortogonal?')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="move-right" class="w-3.5 h-3.5 text-blue-400"></i> Proyeksi Vektor
                </button>
                <button onclick="injectAiPrompt('Tolong jelaskan konsep Hukum Orde Reaksi Kimia dan cara menentukan persamaan laju reaksi!')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="flask-conical" class="w-3.5 h-3.5 text-pink-400"></i> Laju Reaksi Kimia
                </button>
                <button onclick="injectAiPrompt('Jelaskan prinsip Gerak Harmonis Sederhana dan periode ayunan bandul fisika!')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="zap" class="w-3.5 h-3.5 text-amber-400"></i> Gerak Harmonis
                </button>
                <button onclick="injectAiPrompt('Bagaimana cara menghitung skala peta dan interpretasi citra penginderaan jauh geografi?')" class="px-3.5 py-1.5 rounded-xl bg-slate-800 hover:bg-purple-900/50 border border-slate-700 text-purple-200 whitespace-nowrap transition flex items-center gap-1.5">
                    <i data-lucide="globe" class="w-3.5 h-3.5 text-emerald-400"></i> Indrajaja Geografi
                </button>
            </div>

            <!-- AI Chat Body Container -->
            <div id="ai-chat-body" class="flex-1 p-4 sm:p-6 overflow-y-auto custom-scrollbar space-y-4 bg-slate-950/60">
                <div class="flex gap-3 items-start">
                    <div class="w-9 h-9 rounded-xl gradient-accent flex-shrink-0 flex items-center justify-center text-white text-xs font-bold shadow-md">AI</div>
                    <div class="bg-slate-900/90 border border-purple-500/30 p-4 sm:p-5 rounded-2xl text-xs sm:text-sm text-slate-200 max-w-xl leading-relaxed shadow-xl">
                        <p class="font-bold text-purple-300 text-sm mb-1">Selamat datang di Nihiluxxy AI Super Tutor v6.5 Presentation Edition! 🚀</p>
                        <p>Ketik soal dari 15 bab mata pelajaran Matematika, Fisika, Kimia, Biologi, Geografi, Ekonomi, Sosiologi, Sejarah, atau UTBK. Engine AI akan mengurai rumus, menyajikan analogi, dan memberikan solusi presisi langkah-demi-langkah!</p>
                    </div>
                </div>
            </div>

            <!-- AI Input Box Area -->
            <div class="p-3 sm:p-4 bg-slate-900 border-t border-slate-800 flex items-center gap-2">
                <textarea id="ai-user-input" rows="1" onkeydown="handleAiKeyDown(event)" placeholder="Ketik pertanyaan atau salin soal di sini (misal: 'Berapa laju reaksi jika konsentrasi A dinaikkan 2 kali membuat laju naik 4 kali?')..." class="flex-1 bg-slate-950 border border-slate-700/80 rounded-2xl px-4 py-3 text-xs sm:text-sm text-slate-100 focus:outline-none focus:border-purple-500 custom-scrollbar resize-none"></textarea>
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
                <span class="font-extrabold text-slate-200">Nihiluxxy AI Platform Edition 2026</span>
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

        // Core State Engine
        const state = {
            activeView: 'home',
            selectedKurikulum: 'Merdeka',
            selectedSubject: 'mat',
            currentBabIdx: 0,
            currentTabSlide: 'konsep', // 'konsep' | 'formula' | 'tips' | 'soal'
            attempts: JSON.parse(localStorage.getItem('nihiluxxy_attempts') || '[]'),
            currentSimAnswers: {},
            activeSimKey: null,
            simTimerInterval: null,
            simTimeLeft: 0,
            currentFlashcardIdx: 0,
            flashcardFilter: 'semua'
        };

        // Fully Expanded Database Engine - 15 Complete Chapters Per Subject (Elite Presentation Standard)
        const db = {
            mapel: [
                { id: 'mat', nama: 'Matematika Wajib & Lanjut', icon: 'calculator', color: 'from-blue-600 to-cyan-500', k13: 'Kelas 10-12 IPA/IPS', merdeka: 'Fase E & F (15 Bab Slide System)' },
                { id: 'fis', nama: 'Fisika Lanjut', icon: 'zap', color: 'from-indigo-600 to-blue-500', k13: 'Kelas 10-12 IPA', merdeka: 'Fase F (15 Bab Slide System)' },
                { id: 'kim', nama: 'Kimia Lanjut', icon: 'flask-conical', color: 'from-purple-600 to-pink-500', k13: 'Kelas 10-12 IPA', merdeka: 'Fase F (15 Bab Slide System)' },
                { id: 'bio', nama: 'Biologi Lanjut', icon: 'dna', color: 'from-emerald-600 to-teal-500', k13: 'Kelas 10-12 IPA', merdeka: 'Fase F (15 Bab Slide System)' },
                { id: 'geo', nama: 'Geografi Lanjut', icon: 'globe', color: 'from-teal-600 to-emerald-500', k13: 'Kelas 10-12 IPS', merdeka: 'Fase F (15 Bab Slide System)' },
                { id: 'eko', nama: 'Ekonomi & Akuntansi', icon: 'trending-up', color: 'from-amber-600 to-yellow-500', k13: 'Kelas 10-12 IPS', merdeka: 'Fase F (15 Bab Slide System)' },
                { id: 'sos', nama: 'Sosiologi Lanjut', icon: 'users', color: 'from-rose-600 to-red-500', k13: 'Kelas 10-12 IPS', merdeka: 'Fase F (15 Bab Slide System)' },
                { id: 'sej', nama: 'Sejarah Indonesia & Dunia', icon: 'landmark', color: 'from-red-600 to-orange-500', k13: 'Kelas 10-12 Wajib/Peminatan', merdeka: 'Fase E & F (15 Bab Slide System)' },
                { id: 'lit', nama: 'Literasi Bahasa & Penalaran', icon: 'book-marked', color: 'from-orange-600 to-amber-500', k13: 'Wajib Semua Jurusan', merdeka: 'Fase E & F (15 Bab Slide System)' }
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
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Eksponen menggambarkan bentuk perkalian berulang dari suatu bilangan basis. Logaritma merupakan fungsi kebalikan (invers) dari eksponensial yang digunakan untuk menentukan besar pangkat bilangan pokok. Pemahaman bentuk akar digunakan untuk merasionalkan penyebut irasional.',
                        visual: 'ᵃlog(b·c) = ᵃlog b + ᵃlog c  |  ᵃlog(b/c) = ᵃlog b - ᵃlog c  |  ᵃlog bⁿ = n · ᵃlog b',
                        tips: '<strong>Trik Cepat Bimbingan Belajar:</strong> Apabila menemui persamaan eksponen berbentuk a^(f(x)) = a^(g(x)), segera samakan pangkatnya menjadi f(x) = g(x) dengan syarat basis a > 0 dan a ≠ 1.',
                        contohSoal: 'Jika diketahui ᵃlog b + ᵃlog b² = 12, hitunglah nilai dari ᵃlog(a·b).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Gunakan sifat logaritma: ᵃlog b² = 2 · ᵃlog b.<br>2. Persamaan menjadi: ᵃlog b + 2 · ᵃlog b = 12 ⇒ 3 · ᵃlog b = 12 ⇒ ᵃlog b = 4.<br>3. Hitung ᵃlog(a·b) = ᵃlog a + ᵃlog b = 1 + 4 = <strong>5</strong>.'
                    },
                    {
                        title: 'Bab 2: Persamaan & Fungsi Kuadrat serta Rumus Vieta',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Persamaan kuadrat ax² + bx + c = 0 memiliki nilai diskriminan D = b² - 4ac yang menentukan jenis akar. Rumus Vieta memberikan hubungan langsung antara koefisien persamaan dan jumlah serta hasil kali akar-akarnya tanpa harus mencari akar secara eksplisit.',
                        visual: 'Vieta: x₁ + x₂ = -b/a  |  x₁ · x₂ = c/a  |  Puncak Parabola: (-b / 2a , -D / 4a)',
                        tips: 'Gunakan identitas aljabar Vieta untuk menentukan jumlah kuadrat akar-akar: x₁² + x₂² = (x₁ + x₂)² - 2(x₁·x₂).',
                        contohSoal: 'Jika x² - (k + 2)x + 16 = 0 memiliki dua akar kembar positif, tentukan nilai k.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Syarat akar kembar D = 0 ⇒ (-(k+2))² - 4(1)(16) = 0 ⇒ (k+2)² = 64.<br>2. Maka k + 2 = 8 atau k + 2 = -8 ⇒ k = 6 atau k = -10.<br>3. Syarat akar positif: x₁+x₂ = k+2 > 0 ⇒ 6+2 = 8 > 0. Jadi k = <strong>6</strong>.'
                    },
                    {
                        title: 'Bab 3: Trigonometri Analitik & Identitas Jumlah Sudut',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Trigonometri analitik memperluas perbandingan siku-siku ke seluruh kuadran serta memperkenalkan rumus jumlah dan selisih dua sudut, sudut ganda, serta perkalian fungsi sinus dan kosinus.',
                        visual: 'sin(A ± B) = sin A cos B ± cos A sin B  |  cos(A ± B) = cos A cos B ∓ sin A sin B',
                        tips: 'Gunakan Aturan Sinus (a/sin A = b/sin B) jika diketahui pasang sudut-sisi berhadapan, dan Aturan Kosinus (c² = a² + b² - 2ab cos C) jika diketahui dua sisi dan sudut apit.',
                        contohSoal: 'Segitiga ABC memiliki a = 4 cm, b = 6 cm, dan sudut C = 60°. Hitunglah panjang sisi c.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. c² = a² + b² - 2ab cos C = 4² + 6² - 2(4)(6) cos 60°.<br>2. c² = 16 + 36 - 48(0.5) = 52 - 24 = 28.<br>3. c = √28 = <strong>2√7 cm</strong>.'
                    },
                    {
                        title: 'Bab 4: Vektor pada R² & R³ serta Proyeksi Ortogonal',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Vektor merepresentasikan besaran berarah. Perkalian skalar dua vektor (dot product) digunakan untuk mengukur sudut antar vektor serta menentukan proyeksi ortogonal skalar maupun vektor.',
                        visual: 'Dua Vektor Tegak Lurus: u · v = 0  |  Proyeksi Skalar: |p| = (u · v) / |v|',
                        tips: 'Dua vektor u dan v saling tegak lurus (ortogonal) jika dan hanya jika hasil perkalian titiknya sama dengan nol (u · v = 0).',
                        contohSoal: 'Diketahui u = (2, -1) dan v = (x, 4). Jika u dan v saling tegak lurus, berapa x?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Syarat tegak lurus u · v = 0.<br>2. (2)(x) + (-1)(4) = 0 ⇒ 2x - 4 = 0 ⇒ <strong>x = 2</strong>.'
                    },
                    {
                        title: 'Bab 5: Matriks, Determinan & Invers Operasi Baris',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Matriks digunakan untuk menyusun sistem persamaan linear secara efisien. Determinan memberikan nilai skalar unik yang menentukan keberadaan invers matriks.',
                        visual: 'det(A · B) = det(A) · det(B)  |  det(A⁻¹) = 1 / det(A)  |  det(k·A_2x2) = k²·det(A)',
                        tips: 'Jika determinan det(A) = 0, matriks bersifat singular dan tidak memiliki invers.',
                        contohSoal: 'Jika det(A) = 5 dan det(B) = 2, berapakah determinan dari 3A⁻¹ · B untuk matriks 2x2?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. det(3A⁻¹ · B) = 3² · det(A⁻¹) · det(B).<br>2. det(A⁻¹) = 1/5.<br>3. Hasil = 9 × (1/5) × 2 = <strong>18/5 = 3,6</strong>.'
                    },
                    {
                        title: 'Bab 6: Barisan & Deret Aritmatika, Geometri & Tak Hingga',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Barisan aritmatika memiliki beda tetap b, sedangkan geometri memiliki rasio r. Deret geometri tak hingga konvergen menuju nilai terbatas jika rasio memenuhi -1 < r < 1.',
                        visual: 'Aritmatika: U_n = a + (n-1)b  |  Geometri: U_n = a·rⁿ⁻¹  |  Tak Hingga: S_∞ = a / (1 - r)',
                        tips: 'Jumlah n suku pertama deret aritmatika dapat dicari instan dengan S_n = (n / 2) · (a + U_n).',
                        contohSoal: 'Deret geometri tak hingga memiliki a = 12 dan S_∞ = 18. Hitunglah rasionya.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. S_∞ = a / (1 - r) ⇒ 18 = 12 / (1 - r).<br>2. 1 - r = 12/18 = 2/3 ⇒ r = 1 - 2/3 = <strong>1/3</strong>.'
                    },
                    {
                        title: 'Bab 7: Limit Fungsi Aljabar, Trigonometri & Aturan L\'Hopital',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Limit fungsi menentukan kecenderungan nilai f(x) saat x mendekati batas c. Bentuk tak tentu 0/0 diselesaikan dengan pemfaktoran, perkalian sekawan, atau diferensiasi L\'Hopital.',
                        visual: 'lim (x→c) [f(x)/g(x)] = lim (x→c) [f\'(x)/g\'(x)]  |  lim (x→0) (sin ax / bx) = a/b',
                        tips: 'Limit trigonometri dasar: lim (x→0) (sin ax / bx) = a/b dan lim (x→0) (tan ax / bx) = a/b.',
                        contohSoal: 'Hitung lim (x→0) (1 - cos 2x) / (x sin x).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Ubah 1 - cos 2x menjadi 2 sin² x.<br>2. lim (x→0) (2 sin² x) / (x sin x) = lim (x→0) (2 sin x / x) = 2(1) = <strong>2</strong>.'
                    },
                    {
                        title: 'Bab 8: Turunan Fungsi, Garis Singgung & Titik Stasioner',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Turunan f\'(x) merepresentasikan gradien garis singgung kurva di titik tertentu. Titik stasioner dicapai saat turunan pertama bernilai nol (f\'(x) = 0).',
                        visual: 'Aturan Rantai: d/dx [f(g(x))] = f\'(g(x)) · g\'(x)  |  m = f\'(x₁)',
                        tips: 'Fungsi selalu naik pada interval di mana f\'(x) > 0, dan fungsi turun jika f\'(x) < 0.',
                        contohSoal: 'Tentukan titik stasioner minimum f(x) = x² - 6x + 8.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. f\'(x) = 2x - 6 = 0 ⇒ x = 3.<br>2. y = f(3) = 3² - 6(3) + 8 = -1.<br>3. Titik minimum = <strong>(3, -1)</strong>.'
                    },
                    {
                        title: 'Bab 9: Integral Tentu, Luas Daerah & Benda Putar',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Integral merupakan kebalikan dari turunan. Integral tentu digunakan untuk mengukur luas wilayah yang dibatasi kurva serta volume benda putar hasil rotasi.',
                        visual: 'Trik Luas Parabola-Garis: L = (D √D) / (6 a²)',
                        tips: 'Gunakan rumus cepat L = (D √D) / (6a²) untuk menghitung luas antara parabola ax²+bx+c dan sumbu-X secara instan.',
                        contohSoal: 'Hitung luas daerah dibatasi y = x² - 4x dan sumbu-X.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. a = 1, D = (-4)² - 4(1)(0) = 16.<br>2. Luas = (16 × √16) / (6 × 1²) = 64 / 6 = <strong>32/3 satuan luas</strong>.'
                    },
                    {
                        title: 'Bab 10: Polinomial, Metode Horner & Teorema Sisa',
                        kurikulum: 'K13 & Merdeka (Fase F Lanjut)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Polinomial P(x) adalah fungsi suku banyak. Teorema Sisa menyatakan bahwa sisa pembagian P(x) oleh (x - k) sama dengan nilai P(k).',
                        visual: 'Teorema Faktor: (x - k) adalah faktor dari P(x) jika dan hanya jika P(k) = 0',
                        tips: 'Gunakan Bagan Horner untuk mempercepat pembagian polinomial dibandingkan cara bersusun.',
                        contohSoal: 'Jika P(x) = 2x³ - x² + ax - 4 dibagi (x - 2) bersisa 10, tentukan nilai a.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. P(2) = 10 ⇒ 2(2)³ - (2)² + a(2) - 4 = 10.<br>2. 16 - 4 + 2a - 4 = 10 ⇒ 8 + 2a = 10 ⇒ <strong>a = 1</strong>.'
                    },
                    {
                        title: 'Bab 11: Kombinatorika, Permutasi, Kombinasi & Peluang',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Permutasi memperhatikan urutan susunan, sedangkan Kombinasi tidak memperhatikan urutan. Peluang mengukur tingkat kepastian terjadinya suatu kejadian.',
                        visual: 'Peluang P(A) = n(A) / n(S)  |  P(A ∩ B) = P(A) × P(B)',
                        tips: 'Keyword: "Jabatan/Ranking" = Permutasi. "Tim/Pengambilan Acak" = Kombinasi.',
                        contohSoal: 'Dari 6 calon, dipilih 3 orang anggota tim. Berapa banyak cara pemilihan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Kombinasi C(6,3) = 6! / (3! 3!) = (6 × 5 × 4) / (3 × 2 × 1) = <strong>20 cara</strong>.'
                    },
                    {
                        title: 'Bab 12: Geometri Analitik Lingkaran & Garis Singgung',
                        kurikulum: 'K13 & Merdeka (Fase F Lanjut)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Lingkaran adalah tempat kedudukan titik-titik berjarak sama terhadap titik pusat. Persamaan umum x² + y² + Ax + By + C = 0 memiliki Pusat (-A/2, -B/2) dan Jari-jari r = √(A²/4 + B²/4 - C).',
                        visual: 'Garis Singgung Bergradien m: y - b = m(x - a) ± r √(1 + m²)',
                        tips: 'Jarak titik (x₁, y₁) ke garis Ax + By + C = 0 adalah d = |Ax₁ + By₁ + C| / √(A² + B²).',
                        contohSoal: 'Tentukan pusat dan jari-jari lingkaran x² + y² - 4x + 6y - 12 = 0.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Pusat = (-(-4)/2, -6/2) = (2, -3).<br>2. r = √(4 + 9 - (-12)) = √25 = <strong>5</strong>.'
                    },
                    {
                        title: 'Bab 13: Fungsi Komposisi & Fungsi Invers',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Fungsi komposisi (f ∘ g)(x) memetakan g(x) ke dalam f(x). Invers f⁻¹(x) merepresentasikan pemetaan kebalikan dari daerah hasil ke daerah asal.',
                        visual: 'Invers Rasional: f(x) = (ax + b)/(cx + d) ⇒ f⁻¹(x) = (-dx + b)/(cx - a)',
                        tips: 'Tukar posisi a dan d pada fungsi rasional lalu balikkan tandanya untuk menentukan invers instan.',
                        contohSoal: 'Jika f(x) = (3x + 2) / (x - 4), tentukan f⁻¹(x).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. a = 3, d = -4.<br>2. Tukar posisi dan ubah tanda: f⁻¹(x) = <strong>(4x + 2) / (x - 3)</strong>.'
                    },
                    {
                        title: 'Bab 14: Program Linear & Uji Titik Pojok Optimum',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Program linear menentukan nilai optimum (maksimum/minimum) fungsi tujuan di bawah kendala sistem pertidaksamaan linear.',
                        visual: 'Garis Selidik: ax + by = k  |  Uji Titik Pojok Daerah Penyelesaian (DP)',
                        tips: 'Nilai optimum selalu terletak pada salah satu titik sudut (pojok) daerah penyelesaian.',
                        contohSoal: 'Maksimumkan z = 3x + 4y pada titik pojok (0,5), (3,3), dan (4,0).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. z(0,5) = 20, z(3,3) = 21, z(4,0) = 12.<br>2. Nilai maksimum = <strong>21</strong>.'
                    },
                    {
                        title: 'Bab 15: Dimensi Tiga (Jarak & Sudut dalam Ruang)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Geometri ruang menganalisis hubungan titik, garis, dan bidang pada bangun tiga dimensi dengan bantuan Teorema Pythagoras dan proyeksi tegak lurus.',
                        visual: 'Diagonal Sisi Kubus = s√2  |  Diagonal Ruang Kubus = s√3',
                        tips: 'Untuk mencari jarak titik ke garis, buat segitiga penolong lalu gunakan aturan luas segitiga.',
                        contohSoal: 'Kubus ABCD.EFGH memiliki rusuk 6 cm. Hitung jarak titik A ke C.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. AC merupakan diagonal sisi kubus.<br>2. Jarak AC = s√2 = <strong>6√2 cm</strong>.'
                    }
                ],
                'fis': [
                    {
                        title: 'Bab 1: Kinematika Gerak Lurus & Parabola',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kinematika mempelajari gerak tanpa meninjau penyebabnya. Gerak parabola merupakan gabungan GLB pada sumbu X dan GLBB pada sumbu Y di bawah gravitasi.',
                        visual: 'H_max = (v₀² sin² θ) / 2g  |  X_max = (v₀² sin 2θ) / g',
                        tips: 'Di titik puncak lintasan parabola, kecepatan vertikal v_y bernilai 0 m/s.',
                        contohSoal: 'Ditembakkan v₀ = 20 m/s sudut 30° (g = 10 m/s²). Ketinggian maksimum?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. H_max = (20² × sin² 30°) / (2 × 10) = (400 × 0.25) / 20 = <strong>5 meter</strong>.'
                    },
                    {
                        title: 'Bab 2: Hukum-Hukum Newton & Dinamika Gerak',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Dinamika menganalisis penyebab gerak. Hukum I Newton (kelembaman), Hukum II Newton (ΣF = m·a), dan Hukum III Newton (aksi-reaksi).',
                        visual: 'Gaya Gesek: f_g = μ · N  |  Komponen Bidang Miring: F = m·g sin θ',
                        tips: 'Uraikan seluruh komponen gaya searah dan tegak lurus bidang gerak terlebih dahulu.',
                        contohSoal: 'Balok 4 kg berada pada bidang miring licin 30° (g = 10 m/s²). Hitung percepatannya.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. a = g sin 30° = 10 × 0,5 = <strong>5 m/s²</strong>.'
                    },
                    {
                        title: 'Bab 3: Usaha, Energi & Hukum Kekekalan Energi Mekanik',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Usaha W = F · s cos θ adalah perubahan energi. Energi Mekanik EM = EP + EK bersifat kekal pada sistem tertentu tanpa gesekan.',
                        visual: 'Usaha: W = ΔEK = ΔEP  |  Hukum Kekekalan: EP₁ + EK₁ = EP₂ + EK₂',
                        tips: 'Pada gerak jatuh bebas, berkurangnya EP sama persis dengan bertambahnya EK.',
                        contohSoal: 'Benda 1 kg jatuh dari ketinggian 20 m (g = 10 m/s²). Hitung EK saat h = 5 m.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. ΔEP = m·g·Δh = 1 × 10 × (20 - 5) = 150 J.<br>2. EK saat h=5 m = ΔEP = <strong>150 Joule</strong>.'
                    },
                    {
                        title: 'Bab 4: Impuls, Momentum & Tumbukan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Momentum p = m·v merepresentasikan kesukaran menghentikan benda. Impuls I = F·Δt adalah perubahan momentum (I = Δp).',
                        visual: 'Kekekalan Momentum: m₁v₁ + m₂v₂ = m₁v₁\' + m₂v₂\'  |  Koefisien Restitusi e',
                        tips: 'Pada tumbukan tidak lenting sama sekali, kedua benda bergabung dan bergerak bersama (v₁\' = v₂\').',
                        contohSoal: 'Benda A (2 kg, 4 m/s) menumbuk B (3 kg, diam) dan menyatu. Berapa kecepatan akhirnya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. (2×4) + (3×0) = (2+3)v\' ⇒ 8 = 5v\' ⇒ v\' = <strong>1,6 m/s</strong>.'
                    },
                    {
                        title: 'Bab 5: Gerak Harmonis Sederhana & Ayunan Bandul',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> GHS adalah gerak bolak-balik periodik di sekitar titik setimbang dengan gaya pemulih berbanding lurus dengan simpangan.',
                        visual: 'Periode Pegas: T = 2π √(m/k)  |  Periode Bandul: T = 2π √(L/g)',
                        tips: 'Periode ayunan bandul sederhana hanya bergantung pada panjang tali L dan gravitasi g, bukan massa bandul.',
                        contohSoal: 'Panjang tali bandul 0,98 m (g = 9,8 m/s²). Hitung periodenya.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. T = 2π √(0,98 / 9,8) = 2π √0,1 ≈ <strong>2π × 0,316 detik</strong>.'
                    },
                    {
                        title: 'Bab 6: Dinamika Rotasi & Kesetimbangan Benda Tegar',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Rotasi dipengaruhi momen gaya (torsi τ = F·r sin θ) dan momen inersia I. Kesetimbangan tegar membutuhkan ΣF = 0 dan Στ = 0.',
                        visual: 'Hukum II Rotasi: Στ = I · α  |  Momentum Sudut: L = I · ω',
                        tips: 'Batang homogen yang diputar di ujung memiliki momen inersia I = (1/3) m L².',
                        contohSoal: 'Momen gaya 20 Nm bekerja pada roda dengan I = 4 kg m². Hitung percepatan sudutnya.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. α = τ / I = 20 / 4 = <strong>5 rad/s²</strong>.'
                    },
                    {
                        title: 'Bab 7: Fluida Statis: Hukum Pascal & Archimedes',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Fluida statis mengkaji zat alir diam. Tekanan hidrostatis P = ρ·g·h. Gaya apung Archimedes F_a = ρ_fluida · V_celup · g.',
                        visual: 'Hukum Pascal: F₁ / A₁ = F₂ / A₂  |  F_a = ρ · V · g',
                        tips: 'Benda terapung memiliki gaya apung F_a sama dengan berat total benda W.',
                        contohSoal: 'Dongkrak hidrolik memiliki A₁ = 10 cm² dan A₂ = 200 cm². Jika F₁ = 50 N, hitung F₂.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. F₂ = (A₂ / A₁) × F₁ = (200 / 10) × 50 = 20 × 50 = <strong>1000 N</strong>.'
                    },
                    {
                        title: 'Bab 8: Fluida Dinamis & Persamaan Kontinuitas - Bernoulli',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Fluida ideal dianggap tidak kompresibel dan tidak memiliki viskositas. Debit air konstan Q = A·v. Hukum Bernoulli merupakan kekekalan energi fluida.',
                        visual: 'Kontinuitas: A₁ v₁ = A₂ v₂  |  Bernoulli: P + ½ ρ v² + ρ g h = Konstan',
                        tips: 'Makin kecil penampang pipa, makin besar kelajuan alir fluidanya.',
                        contohSoal: 'Pipa penampang A₁ = 8 cm² (v₁ = 2 m/s) menyempit ke A₂ = 2 cm². Hitung v₂.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. v₂ = (A₁ / A₂) × v₁ = (8 / 2) × 2 = 4 × 2 = <strong>8 m/s</strong>.'
                    },
                    {
                        title: 'Bab 9: Termodinamika & Mesin Carnot',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Termodinamika mengkaji hubungan kalor dan usaha. Hukum I Termodinamika Q = ΔU + W. Mesin Carnot adalah mesin kalor ideal efisiensi maksimum.',
                        visual: 'Efisiensi Carnot: η = (1 - T₂ / T₁) × 100%  (Suhu dalam Kelvin)',
                        tips: 'Suhu pada perhitungan termodinamika selalu wajib diubah ke Kelvin (T_K = T_C + 273).',
                        contohSoal: 'Mesin Carnot bekerja antara reservoir T₁ = 600 K dan T₂ = 300 K. Berapa efisiensinya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. η = (1 - 300 / 600) × 100% = (1 - 0.5) × 100% = <strong>50%</strong>.'
                    },
                    {
                        title: 'Bab 10: Gelombang Bunyi & Efek Doppler Lanjut',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Bunyi merupakan gelombang longitudinal mekanik. Efek Doppler menjelaskan pergeseran frekuensi akibat gerak relatif sumber dan pendengar.',
                        visual: 'f_p = [(v ± v_p) / (v ± v_s)] · f_s  |  Intensitas TI = 10 log(I / I₀)',
                        tips: 'Pendengar mendekat (+), Sumber mendekat (-).',
                        contohSoal: 'Ambulans (f_s = 640 Hz) mendekati pendengar diam (v = 340 m/s, v_s = 20 m/s). Hitung f_p.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. f_p = [340 / (340 - 20)] × 640 = (340 / 320) × 640 = <strong>680 Hz</strong>.'
                    },
                    {
                        title: 'Bab 11: Listrik Searah (DC) & Hukum Kirchhoff',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Arus listrik adalah aliran muatan. Hukum Kirchhoff I (arus cabang) dan II (loop tegangan ΣE + Σ(IR) = 0).',
                        visual: 'Seri: R_total = R₁ + R₂  |  Paralel: 1/R_total = 1/R₁ + 1/R₂',
                        tips: 'Hambatan paralel selalu menghasilkan R total lebih kecil dari hambatan terkecilnya.',
                        contohSoal: 'R₁ = 3 Ω dan R₂ = 6 Ω dirangkai paralel pada baterai 12 V. Arus total?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. R_p = (3×6)/(3+6) = 2 Ω. Arus I = 12 / 2 = <strong>6 Ampere</strong>.'
                    },
                    {
                        title: 'Bab 12: Listrik Statis, Medan Listrik & Kapasitor',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Gaya Coulomb F = k q₁ q₂ / r². Kapasitor menyimpan energi listrik W = ½ C V².',
                        visual: 'Hukum Coulomb: F = k (q₁ q₂) / r²  |  Kapasitansi: C = ε₀ A / d',
                        tips: 'Jika jarak r diperbesar 2 kali, gaya Coulomb berkurang menjadi 1/4 kali semula.',
                        contohSoal: 'Dua muatan q₁=2μC dan q₂=3μC berjarak 0,3 m (k=9×10⁹). Hitung gaya F.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. F = (9×10⁹ × 2×10⁻⁶ × 3×10⁻⁶) / (0.3)² = 0.054 / 0.09 = <strong>0,6 Newton</strong>.'
                    },
                    {
                        title: 'Bab 13: Medan Magnet & Induksi Elektromagnetik Faraday',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Arus listrik menimbulkan medan magnet (Hukum Ampere/Lorentz). Perubahan fluks magnetik menimbulkan GGL induksi (Hukum Faraday).',
                        visual: 'Gaya Lorentz: F = B · I · L sin θ  |  GGL Induksi: E = -N (ΔΦ / Δt)',
                        tips: 'Gunakan Aturan Tangan Kanan untuk menentukan arah Gaya Lorentz.',
                        contohSoal: 'Kawat L = 2 m berarus I = 5 A dalam medan B = 0,4 T tegak lurus. Hitung F.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. F = B · I · L = 0,4 × 5 × 2 = <strong>4 Newton</strong>.'
                    },
                    {
                        title: 'Bab 14: Rangkaian Listrik Bolak-Balik (AC) & Resonansi RLC',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Arus AC bervariasi secara sinusoidal. Impedansi Z = √(R² + (X_L - X_C)²). Resonansi terjadi saat X_L = X_C.',
                        visual: 'Impedansi: Z = √(R² + (X_L - X_C)²)  |  Frekuensi Resonansi: f = 1 / (2π √(LC))',
                        tips: 'Saat resonansi, hambatan total bernilai minimum (Z = R) dan arus bernilai maksimum.',
                        contohSoal: 'Rangkaian RLC memiliki R=30 Ω, X_L=80 Ω, X_C=40 Ω. Hitung Z.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Z = √(30² + (80 - 40)²) = √(900 + 1600) = √2500 = <strong>50 Ohm</strong>.'
                    },
                    {
                        title: 'Bab 15: Fisika Modern, Efek Fotolistrik & Relativitas',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Cahaya bersifat dualisme (gelombang-partikel). Efek fotolistrik membuktikan cahaya sebagai paket energi foton E = h·f. Relativitas Einstein membatasi kecepatan maksimal c.',
                        visual: 'Energi Foton: E = h · f = h (c / λ)  |  Relativitas Massa: m = m₀ / √(1 - v²/c²)',
                        tips: 'Efek fotolistrik terjadi hanya jika frekuensi foton melebihi frekuensi ambang logam.',
                        contohSoal: 'Hitung energi foton cahaya dengan frekuensi 5 × 10¹⁴ Hz (h = 6,63 × 10⁻³⁴ J s).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. E = h · f = 6,63 × 10⁻³⁴ × 5 × 10¹⁴ = <strong>3,315 × 10⁻¹⁹ Joule</strong>.'
                    }
                ],
                'kim': [
                    {
                        title: 'Bab 1: Struktur Atom, Konfigurasi spdf & Sistem Periodik',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Atom terdiri dari proton, neutron, dan elektron. Konfigurasi elektron subkulit (s, p, d, f) ditentukan berdasarkan Aturan Aufbau, Larangan Pauli, dan Kaidah Hund.',
                        visual: 'Jumlah Maksimal Elektron Subkulit: s=2, p=6, d=10, f=14',
                        tips: 'Kulit valensi menentukan Golongan, sedangkan jumlah kulit menentukan Periode unsur.',
                        contohSoal: 'Tentukan golongan dan periode dari unsur ₂₆Fe (konfigurasi: [Ar] 4s² 3d⁶).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Jumlah elektron valensi 4s² + 3d⁶ = 8 (Golongan VIII B). Kulit terbesar = 4 (Periode 4).'
                    },
                    {
                        title: 'Bab 2: Ikatan Kimia, Bentuk Molekul VSEPR & Kepolaran',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Unsur berikatan untuk mencapai konfigurasi oktet (8 elektron valensi). Ikatan ion (serah terima elektron), ikatan kovalen (pemakaian bersama). Geometri molekul ditentukan teori VSEPR.',
                        visual: 'AX₂ = Linear  |  AX₃ = Trigonal Planar  |  AX₄ = Tetrahedral  |  AX₂E₂ = Bengkok',
                        tips: 'Molekul simetris tanpa Pasangan Elektron Bebas (PEB) pada atom pusat bersifat Nonpolar.',
                        contohSoal: 'Tentukan bentuk molekul CH₄ (Atom pusat C punya 4 elektron valensi berikatan dengan 4 H).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Domain ikatan X = 4, PEB E = (4-4)/2 = 0. Tipe AX₄ = <strong>Tetrahedral</strong>.'
                    },
                    {
                        title: 'Bab 3: Stoikiometri, Konsep Mol & Pereaksi Pembatas',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Mol adalah jembatan kuantitatif kimia (n = m / Mr). Hukum stoikiometri menghubungkan mol dengan jumlah partikel, volume gas STP, dan molaritas larutan.',
                        visual: 'n = m / Mr  |  V_STP = n × 22,4 L  |  Molaritas M = n / V(L)',
                        tips: 'Bagi mol reaktan dengan koefisiennya. Nilai terkecil menjadi Pereaksi Pembatas.',
                        contohSoal: 'Berapakah volume dari 0,25 mol gas O₂ pada keadaan STP?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. V = 0.25 × 22,4 = <strong>5,6 Liter</strong>.'
                    },
                    {
                        title: 'Bab 4: Termokimia, Entalpi & Hukum Hess',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Termokimia mempelajari efek kalor reaksi. Reaksi eksoterm melepaskan kalor (ΔH < 0), endoterm menyerap kalor (ΔH > 0). Hukum Hess menyatakan ΔH tidak bergantung pada tahapan lintasan.',
                        visual: 'ΔH_reaksi = Σ ΔH°f(produk) - Σ ΔH°f(pereaksi)',
                        tips: 'Jika persamaan reaksi dibalik, nilai ΔH berganti tanda (+/-).',
                        contohSoal: 'ΔH°f CO₂ = -393.5 kJ/mol. Pembakaran 12 gram C (Ar=12) melepas kalor sebesar?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. mol C = 12/12 = 1 mol. Kalor yang dilepas = <strong>393,5 kJ</strong>.'
                    },
                    {
                        title: 'Bab 5: Laju Reaksi, Teori Tumbukan & Orde Reaksi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Laju reaksi V = k [A]ᵐ [B]ⁿ diukur dari berkurangnya reaktan per satuan waktu. Faktor yang mempercepat laju: konsentrasi, suhu, luas permukaan, dan katalis.',
                        visual: 'Persamaan Laju: V = k [A]ᵐ [B]ⁿ  |  Orde Total = m + n',
                        tips: 'Katalis mempercepat reaksi dengan cara menurunkan Energi Aktivasi (Ea).',
                        contohSoal: 'Jika konsentrasi A dinaikkan 2 kali membuat laju V naik 4 kali, berapa orde reaksi terhadap A?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. 2ᵐ = 4 ⇒ <strong>m = 2 (Orde 2)</strong>.'
                    },
                    {
                        title: 'Bab 6: Kesetimbangan Kimia & Asas Le Chatelier',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kesetimbangan dinamis terjadi saat laju reaksi maju sama dengan laju reaksi balik. Pergeseran kesetimbangan dipengaruhi perubahan konsentrasi, suhu, dan tekanan.',
                        visual: 'K_c = [Produk]ⁿ / [Reaktan]ᵐ  |  Hanya wujud Gas (g) dan Larutan (aq)',
                        tips: 'Jika suhu dinaikkan, kesetimbangan bergeser ke arah reaksi Endoterm (ΔH positif).',
                        contohSoal: 'Reaksi N₂ + 3H₂ ⇌ 2NH₃ (ΔH = -92 kJ). Agar NH₃ bertambah, suhu harus?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Karena reaksi pembentukan NH₃ eksoterm, suhu harus <strong>Diturunkan</strong>.'
                    },
                    {
                        title: 'Bab 7: Larutan Asam-Basa, Derajat pH & Indikator',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Menurut Arrhenius, asam menghasilkan H⁺ dan basa menghasilkan OH⁻. Nilai pH = -log[H⁺]. Asam kuat terionisasi sempurna, asam lemah terionisasi sebagian (Ka).',
                        visual: 'Asam Kuat: [H⁺] = M × valensi  |  Asam Lemah: [H⁺] = √(K_a × M)',
                        tips: 'pH + pOH = 14 pada suhu kamar 25°C.',
                        contohSoal: 'Hitung pH larutan CH₃COOH 0,1 M jika Ka = 10⁻⁵.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. [H⁺] = √(10⁻⁵ × 0.1) = √10⁻⁶ = 10⁻³ M. pH = -log(10⁻³) = <strong>3</strong>.'
                    },
                    {
                        title: 'Bab 8: Larutan Penyangga (Buffer) & Kapasitas Penyangga',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Larutan buffer mampu mempertahankan pH dari penambahan sedikit asam, basa, atau pengenceran. Terdiri dari campuran asam lemah + basa konjugasi.',
                        visual: 'Buffer Asam: [H⁺] = K_a × (mol Asam Lemah / mol Basa Konjugasi)',
                        tips: 'Jika reaksi asam lemah dan basa kuat menyisakan asam lemah, maka terbentuk buffer.',
                        contohSoal: '0.1 mol CH₃COOH (Ka=10⁻⁵) dicampur dengan 0.01 mol CH₃COONa. Hitung pH.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. [H⁺] = 10⁻⁵ × (0.1 / 0.01) = 10⁻⁴ M. pH = -log(10⁻⁴) = <strong>4</strong>.'
                    },
                    {
                        title: 'Bab 9: Hidrolisis Garam & Sifat Asam-Basa Garam',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Hidrolisis adalah reaksi kation/anion garam dengan air. Garam dari asam lemah + basa kuat mengalami hidrolisis sebagian bersifat basa (pH > 7).',
                        visual: 'Garam Basa: [OH⁻] = √( (K_w / K_a) × M_garam )',
                        tips: 'Garam dari asam kuat dan basa kuat tidak mengalami hidrolisis (pH netral = 7).',
                        contohSoal: 'Hitung [OH⁻] larutan CH₃COONa 0.1 M (Kw=10⁻¹⁴, Ka=10⁻⁵).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. [OH⁻] = √( (10⁻¹⁴ / 10⁻⁵) × 0.1 ) = √10⁻¹⁰ = <strong>10⁻⁵ M</strong>.'
                    },
                    {
                        title: 'Bab 10: Kelarutan & Hasil Kali Kelarutan (Ksp)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Ksp adalah konstanta kesetimbangan larutan jenuh garam sukar larut. Jika Qsp > Ksp, terjadi pengendapan.',
                        visual: 'Garam AX₂ ⇌ A²⁺ + 2X⁻  ⇒  Ksp = 4s³',
                        tips: 'Penambahan ion sejenis akan menurunkan kelarutan zat dalam larutan.',
                        contohSoal: 'Jika kelarutan AgCl (s) = 10⁻⁵ M, hitung Ksp AgCl.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. AgCl ⇌ Ag⁺ + Cl⁻. Ksp = s × s = (10⁻⁵)² = <strong>10⁻¹⁰</strong>.'
                    },
                    {
                        title: 'Bab 11: Sifat Koligatif Larutan & Hukum Raoult',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sifat koligatif hanya bergantung pada jumlah partikel zat terlarut, meliputi: penurunan tekanan uap, kenaikan titik didih, penurunan titik beku, dan tekanan osmotik.',
                        visual: 'ΔTb = m · Kb · i  |  ΔTf = m · Kf · i  |  π = M · R · T · i',
                        tips: 'Untuk zat elektrolit, sertakan faktor van\'t Hoff i = 1 + (n - 1)α.',
                        contohSoal: 'Hitung ΔTb larutan 1 mol glukosa non-elektrolit dalam 1 kg air (Kb = 0,52 °C/m).<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. ΔTb = m × Kb × 1 = 1 × 0,52 = <strong>0,52 °C</strong>.'
                    },
                    {
                        title: 'Bab 12: Reaksi Redoks & Penyetaraan Bilangan Oksidasi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Oksidasi adalah kenaikan biloks (pelepasan elektron), reduksi adalah penurunan biloks (penerimaan elektron). Di setarakan dengan metode setengah reaksi atau biloks.',
                        visual: 'Oksidator = Mengalami Reduksi  |  Reduktor = Mengalami Oksidasi',
                        tips: 'Unsur bebas selalu memiliki bilangan oksidasi bernilai 0.',
                        contohSoal: 'Tentukan biloks Mangan (Mn) dalam senyawa KMnO₄.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. (+1) + Mn + 4(-2) = 0 ⇒ 1 + Mn - 8 = 0 ⇒ <strong>Mn = +7</strong>.'
                    },
                    {
                        title: 'Bab 13: Sel Volta, Deret Volta & Korosi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sel Volta mengubah reaksi kimia spontan menjadi energi listrik. Katode (reduksi, +) dan Anode (oksidasi, -).',
                        visual: 'E°sel = E°katode - E°anode  |  KRAO (Katode Reduksi, Anode Oksidasi)',
                        tips: 'Logam dengan E° lebih positif berada di katode.',
                        contohSoal: 'E° Zn²⁺/Zn = -0,76 V, E° Cu²⁺/Cu = +0,34 V. Hitung E°sel.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. E°sel = +0,34 - (-0,76) = <strong>+1,10 Volt</strong>.'
                    },
                    {
                        title: 'Bab 14: Sel Elektrolisis & Hukum Faraday I - II',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Elektrolisis menggunakan energi listrik untuk menjalankan reaksi redoks tidak spontan. Hukum Faraday I: massa zat terendap W = (e · I · t) / 96500.',
                        visual: 'W = (e · I · t) / 96500  |  massa ekuivalen e = Ar / valensi',
                        tips: 'Di katode, kation Logam Aktif (Gol I A, II A, Al, Mn) larutan tidak tereduksi, melainkan air (H₂O).',
                        contohSoal: 'Hitung massa Cu (Ar=63.5, valensi=2) terendap jika arus 10 A mengalir 965 detik.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. W = [(63.5/2) × 10 × 965] / 96500 = 31.75 × 10 × 0.01 = <strong>3,175 gram</strong>.'
                    },
                    {
                        title: 'Bab 15: Kimia Organik, Tata Nama Alkana & Gugus Fungsi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kimia karbon mengkaji senyawa hidrokarbon dan turunannya berdasarkan gugus fungsi (Alkohol -OH, Eter -O-, Aldehid -CHO, Keton -CO-, Asam Karboksilat -COOH, Ester -COO-).',
                        visual: 'Alkohol & Eter (Isomer Fungsi C_n H_2n+2 O)',
                        tips: 'Uji Seliwanoff dan Biuret digunakan untuk mengidentifikasi karbohidrat dan protein.',
                        contohSoal: 'Apakah rumus gugus fungsi dari senyawa Asam Asetat (Asam Cuka)?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Asam asetat tergolong Asam Karboksilat dengan gugus fungsi <strong>-COOH</strong>.'
                    }
                ],
                'bio': [
                    {
                        title: 'Bab 1: Organel Sel, Struktur Membran & Transpor',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sel adalah unit struktural terkecil kehidupan. Membran sel bersifat semipermeabel mengatur transpor pasif (difusi, osmosis) dan aktif (pompa ATP).',
                        visual: 'Osmosis: Pelarut air bergerak dari hipotonis (encer) ke hipertonis (pekat)',
                        tips: 'Sel darah merah di larutan hipertonis mengalami pengerutan (Krenasi).',
                        contohSoal: 'Mengapa sel tumbuhan tidak pecah di lingkungan hipotonis?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Karena memiliki <strong>Dinding Sel</strong> kaku dari selulosa.'
                    },
                    {
                        title: 'Bab 2: Biokimia Enzim & Bioenergetika Sel',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Enzim adalah biokatalisator protein yang menurunkan energi aktivasi. Bekerja spesifik berdasarkan teori Lock and Key dan Induced Fit.',
                        visual: 'Faktor Pengaruh Enzim: Suhu Optima, pH, Konsentrasi Substrat, Inhibitor',
                        tips: 'Inhibitor kompetitif bersaing merebut sisi aktif enzim dengan substrat.',
                        contohSoal: 'Apakah dampak pemanasan enzim di atas suhu 60 °C?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Enzim mengalami <strong>Denaturasi</strong> (kerusakan struktur tersier protein).'
                    },
                    {
                        title: 'Bab 3: Katabolisme Karbohidrat: Respirasi Aerob & Anaerob',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Respirasi aerob memecah glukosa menjadi CO₂, H₂O, dan 36-38 ATP melalui 4 tahap: Glikolisis, Dekarboksilasi Oksidatif, Siklus Krebs, dan Transpor Elektron.',
                        visual: 'Glikolisis (Sitosol) → DO & Krebs (Mitokondria) → Transpor Elektron (Krista)',
                        tips: 'Akseptor elektron terakhir pada respirasi aerob adalah Oksigen (O₂).',
                        contohSoal: 'Di manakah tempat terjadinya Siklus Krebs dalam sel?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Berlangsung di dalam <strong>Matriks Mitokondria</strong>.'
                    },
                    {
                        title: 'Bab 4: Anabolisme: Fotosintesis Reaksi Terang & Gelap',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Fotosintesis mengubah energi foton menjadi kimia. Reaksi terang (Tilakoid) menghasilkan ATP, NADPH, O₂. Reaksi gelap/Siklus Calvin (Stroma) menghasilkan glukosa.',
                        visual: 'Reaksi Terang (Tilakoid) + Reaksi Gelap / Siklus Calvin (Stroma)',
                        tips: 'Fotolisis air H₂O → 2H⁺ + 2e⁻ + ½O₂ terjadi pada Reaksi Terang.',
                        contohSoal: 'Di manakah tempat terjadinya Reaksi Gelap fotosintesis?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Berlangsung di dalam <strong>Stroma Kloroplas</strong>.'
                    },
                    {
                        title: 'Bab 5: Genetik, Struktur DNA, RNA & Sintesis Protein',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> DNA rantai ganda heliks ganda menyimpan kode genetik. Sintesis protein terdiri dari Transkripsi (DNA → mRNA di inti) dan Translasi (mRNA → Protein di ribosom).',
                        visual: 'Pasangan Basa: Adenin - Timin (2 H)  |  Guanin - Sitosin (3 H)',
                        tips: 'Pada RNA, basa Timin (T) digantikan oleh Urasil (U).',
                        contohSoal: 'Tentukan rantai mRNA dari cetakan DNA antisense 3\'-TAC GGC-5\'.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. mRNA dibentuk komplementer: 5\'-<strong>AUG CCG</strong>-3\'.'
                    },
                    {
                        title: 'Bab 6: Pembelahan Sel: Mitosis, Meiosis & Gametogenesis',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Mitosis menghasilkan 2 sel anakan identik diploid (2n) untuk pertumbuhan. Meiosis menghasilkan 4 sel anakan haploid (n) untuk pembentukan gamet.',
                        visual: 'Tahapan: Profase → Metafase → Anafase → Telofase',
                        tips: 'Crossing over (pindah silang) terjadi pada Profase I Meiosis I.',
                        contohSoal: 'Pada fase manakah kromosom berjajar di bidang ekuator sel?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Berjajar di tengah terjadi pada fase <strong>Metafase</strong>.'
                    },
                    {
                        title: 'Bab 7: Hukum Mendel & Persilangan Monohibrid - Dihibrid',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Hukum I Mendel (Segregasi Bebas) dan Hukum II Mendel (Asortasi Bebas). Rasio F2 monohibrid = 3:1, dihibrid heterozigot = 9:3:3:1.',
                        visual: 'Dihibrid Heterozigot (AaBb × AaBb) ⇒ Rasio 9 : 3 : 3 : 1',
                        tips: 'Peluang genotip homozigot resesif aabb dari AaBb × AaBb adalah 1/16.',
                        contohSoal: 'Dihibrid AaBb disilangkan sesamanya. Peluang anak aabb?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. (1/4) × (1/4) = <strong>1/16</strong>.'
                    },
                    {
                        title: 'Bab 8: Penyimpangan Semu Hukum Mendel & Hereditas',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Interaksi gen mengubah rasio klasik Mendel 9:3:3:1. Meliputi: Atavisme (9:3:3:1), Kriptomeri (9:3:4), Epistasis-Hipostasis (12:3:1), dan Polimeri (15:1).',
                        visual: 'Epistasis Dominan = 12 : 3 : 1  |  Kriptomeri = 9 : 3 : 4',
                        tips: 'Pada epistasis dominan, gen epistasis menutupi ekspresi gen hipostatis.',
                        contohSoal: 'Persilangan kriptomeri menghasilkan rasio fenotip F2 sebesar?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Rasionya adalah <strong>9 : 3 : 4</strong>.'
                    },
                    {
                        title: 'Bab 9: Pola Hereditas Manusia & Golongan Darah ABO',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pewarisan sifat terlink-kromosom seks (Buta Warna, Hemofilia) dan autosom (Albinisme, Golongan Darah ABO/Rhesus).',
                        visual: 'Golongan Darah ABO: Iᴬ, Iᴮ (Kodominan), Iᴼ (Resesif)',
                        tips: 'Ibu pembawa (carrier) hemofilia XᴴXʰ menikah dengan ayah normal XᴴY memiliki 25% anak laki-laki hemofilia.',
                        contohSoal: 'Pasangan bergolongan darah A heterozigot (IᴬIᴼ) dan B heterozigot (IᴮIᴼ) dapat memiliki anak bergolongan darah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Kemungkinan anak: A, B, AB, dan O (<strong>Semua golongan darah mungkin</strong>).'
                    },
                    {
                        title: 'Bab 10: Mutasi Gen & Mutasi Kromosom (Aneuploidi)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Mutasi adalah perubahan materi genetik. Mutasi gen (substitusi, adisi, delesi). Mutasi kromosom (delesi, duplikasi, inversi, translokasi, aneuploidi seperti Sindrom Down 47,XX/XY +21).',
                        visual: 'Sindrom Down = Trisomi Kromosom Nomor 21 (2n + 1 = 47)',
                        tips: 'Sindrom Turner memiliki karyotipe 45,XO (Monosomi kromosom seks).',
                        contohSoal: 'Apakah penyebab mutasi pada penderita Sindrom Klinefelter (47,XXY)?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Akibat Nondisjunction (gagal berpisah) kromosom seks saat gametogenesis.'
                    },
                    {
                        title: 'Bab 11: Teori Evolusi, Seleksi Alam & Hukum Hardy-Weinberg',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Evolusi adalah perubahan frekuensi alel populasi dari waktu ke waktu. Darwin menekankan Seleksi Alam. Hukum Hardy-Weinberg: p² + 2pq + q² = 1.',
                        visual: 'Hardy-Weinberg: p + q = 1  |  p² + 2pq + q² = 1',
                        tips: 'Syarat Hardy-Weinberg: populasi besar, perkawinan acak, tidak ada mutasi, migrasi, atau seleksi.',
                        contohSoal: 'Dalam populasi, 16% albino (q²=0,16). Berapa frekuensi alel resesif q?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. q = √0,16 = <strong>0,4</strong>.'
                    },
                    {
                        title: 'Bab 12: Bioteknologi Konvensional & Modern',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Bioteknologi memanfaatkan organisme. Konvensional (fermentasi: Rhizopus, Saccharomyces). Modern (rekayasa genetika: DNA rekombinan, antibodi monoklonal, kultur jaringan).',
                        visual: 'Kloning = Transfer Inti Sel Somatis (Somatic Cell Nuclear Transfer)',
                        tips: 'Pembuatan Insulin menggunakan bakteri E. coli dengan teknik Plasmid Rekombinan.',
                        contohSoal: 'Mikroorganisme yang berperan dalam pembuatan Tempeh adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Jamur <strong>Rhizopus oryzae</strong>.'
                    },
                    {
                        title: 'Bab 13: Sistem Koordinasi: Saraf, Hormon & Indra',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sistem saraf mengatur respon cepat melalui impuls listrik neuron. Sistem endokrin mengatur respon lambat via hormon darah (insulin, tiroksin, adrenalin).',
                        visual: 'Gerak Refleks: Reseptor → Neuron Sensorik → Sumsum Tulang Belakang → Neuron Motorik → Efektor',
                        tips: 'Hormon Insulin menurunkan kadar gula darah dengan mengubah glukosa menjadi glikogen.',
                        contohSoal: 'Di manakah pusat pengendali keseimbangan tubuh pada otak manusia?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dikendalikan oleh Otak Kecil (<strong>Cerebellum</strong>).'
                    },
                    {
                        title: 'Bab 14: Ekosistem, Daur Biogeokimia & Suksesi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Ekosistem adalah interaksi biotik dan abiotik. Daur biogeokimia (Karbon, Nitrogen, Fosfor, Air). Nitrifikasi: Amonium → Nitrit → Nitrat.',
                        visual: 'Nitrifikasi: Nitrosomonas (Amonium → Nitrit) + Nitrobacter (Nitrit → Nitrat)',
                        tips: 'Tumbuhan menyerap nitrogen tanah utamanya dalam bentuk molekul Nitrat (NO₃⁻).',
                        contohSoal: 'Bakteri yang berperan mengikat nitrogen bebas di udara pada bintil akar legum?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Bakteri <strong>Rhizobium leguminosarum</strong>.'
                    },
                    {
                        title: 'Bab 15: Imunologi & Sistem Pertahanan Tubuh',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pertahanan non-spesifik (kulit, mukosa, fagositosis) dan spesifik (Limfosit B membentuk antibodi, Limfosit T menyerang sel terinfeksi).',
                        visual: 'Limfosit B (Imunitas Humoral / Antibodi)  |  Limfosit T (Imunitas Seluler)',
                        tips: 'Vaksinasi memberikan imunitas buatan aktif dengan memasukkan antigen yang dilemahkan.',
                        contohSoal: 'Sel manakah yang memproduksi antibodi spesifik dalam tubuh?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Diproduksi oleh <strong>Sel Plasma (Turunan Limfosit B)</strong>.'
                    }
                ],
                'geo': [
                    {
                        title: 'Bab 1: Konsep Dasar & 4 Prinsip Utama Geografi',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Geografi mengkaji fenomena geosfer. 4 Prinsip Geografi: Persebaran (distribusi), Interelasi (sebab-akibat), Deskripsi (penjelasan data/peta), dan Korologi (komprehensif).',
                        visual: 'Prinsip Interelasi = Keterkaitan hubungan sebab-akibat fenomena geosfer',
                        tips: 'Banjir di hilir akibat penggundulan hutan di hulu dianalisis dengan Prinsip Interelasi.',
                        contohSoal: 'Longsor terjadi akibat penebangan liar di lereng bukit. Prinsip yang digunakan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Menggunakan <strong>Prinsip Interelasi</strong>.'
                    },
                    {
                        title: 'Bab 2: Pemetaan, Skala & Sistem Informasi Geografis (SIG)',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Peta adalah gambaran permukaan bumi pada bidang datar. SIG mengolah data spasial melalui tahap Input, Analisis (Overlay/Buffering), dan Output.',
                        visual: 'Skala Peta = Jarak Peta / Jarak Sebenarnya  |  Kontur Interval CI = (1/2000) × Skala Utama',
                        tips: 'Makin besar angka penyebut skala, makin kecil cakupan detail peta yang ditampilkan.',
                        contohSoal: 'Jarak A-B di peta 4 cm, jarak sebenarnya 2 km. Berapa skala petanya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Skala = 4 cm / 200.000 cm = 1 / 50.000 (Skala <strong>1 : 50.000</strong>).'
                    },
                    {
                        title: 'Bab 3: Penginderaan Jauh & Interpretasi Citra Satelit',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Indrajaja merekam objek dari jarak jauh menggunakan sensor satelit/pesawat. Unsur interpretasi: Bentuk, Ukuran, Rona/Warna, Tekstur, Pola, Bayangan, Situs, Asosiasi.',
                        visual: 'Unsur Utama: Rona (Tingkat Kecerahan) & Asosiasi (Keterkaitan Ciri Objek)',
                        tips: 'Lapangan bola sepak dikenali dari bentuk persegi panjang dan asosiasi gawang di kedua ujungnya.',
                        contohSoal: 'Objek pemukiman kumuh pada citra tampak bertekstur kasar dan pola tidak teratur. Unsur interpretasinya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Mengenali objek berdasarkan <strong>Tekstur dan Pola</strong>.'
                    },
                    {
                        title: 'Bab 4: Litosfer: Batuan, Tektonisme & Vulkanisme',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Litosfer adalah lapisan batuan bumi. Batuan beku, sedimen, metamorf. Gerak tektonik epirogenetik dan orogenetik. Erupsi gunung api menghasilkan intrusi dan ekstrusi magmatik.',
                        visual: 'Divergen (Saling Menjauh)  |  Konvergen (Saling Tumbukan)  |  Transform (Sesar Geser)',
                        tips: 'Zona Subduksi terbentuk akibat tumbukan Konvergen antara lempeng samudera dan benua.',
                        contohSoal: 'Pegunungan Himalaya terbentuk akibat jenis pergerakan lempeng tektonik apakah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Akibat pergerakan <strong>Konvergen (Tumbukan Benua-Benua)</strong>.'
                    },
                    {
                        title: 'Bab 5: Seismisitas & Bencana Gempa Bumi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Gempa disebabkan pelepasan energi tektonik. Hiposentrum (pusat gempa di dalam bumi), Episentrum (pusat gempa di permukaan bumi). Rumus Laska menghitung jarak episentrum.',
                        visual: 'Rumus Laska: Δ = [ (S - P) - 1\' ] × 1.000 km',
                        tips: 'S = waktu gelombang sekunder, P = waktu gelombang primer.',
                        contohSoal: 'Gelombang P tercatat 02.14\'00", S tercatat 02.17\'30". Hitung jarak episentrum Δ.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Δ = [ (3\'30") - 1\' ] × 1000 = 2.5 × 1000 = <strong>2.500 km</strong>.'
                    },
                    {
                        title: 'Bab 6: Pedosfer: Pembentukan & Konservasi Tanah',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pedosfer adalah lapisan tanah hasil pelapukan batuan. Profil tanah (Horizon O, A, B, C, R). Konservasi tanah mekanik (terasering), vegetatif (reboisasi), kimiawi.',
                        visual: 'Horizon O (Humus Organik) → A (Topsoil) → B (Subsoil) → C (Pelapukan) → R (Batuan Induk)',
                        tips: 'Terasering pada lereng curam efektif menahan laju erosi tanah.',
                        contohSoal: 'Metode konservasi tanah dengan menanam tanaman mengikut garis kontur disebut?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Disebut teknik <strong>Contour Plowing</strong>.'
                    },
                    {
                        title: 'Bab 7: Atmosfer: Cuaca, Iklim & Unsur Klimatologi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Atmosfer adalah lapisan udara. Troposfer (tempat fenomena cuaca). Unsur cuaca: suhu, tekanan, kelembaban, angin, curah hujan. Klasifikasi iklim Junghuhn & Koppen.',
                        visual: 'Troposfer (Cuaca) → Stratosfer (Ozon) → Mesosfer (Meteor) → Termosfer (Ionosfer)',
                        tips: 'Hukum Moksche: setiap naik 100 meter, suhu udara turun rata-rata 0.6 °C.',
                        contohSoal: 'Suhu pantai (0 m) 27°C. Berapa suhu kota A di ketinggian 1.000 meter?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Penurunan = (1000/100) × 0.6 = 6°C. Suhu = 27 - 6 = <strong>21 °C</strong>.'
                    },
                    {
                        title: 'Bab 8: Hidrosfer: Siklus Air & Perairan Darat - Laut',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Siklus hidrologi (Evaporasi, Transpirasi, Kondensasi, Presipitasi, Infiltrasi). Perairan darat (sungai, danau, air tanah). Morfologi laut (pola arus, zona neritik).',
                        visual: 'Zona Neritik (Kedalaman < 200 m, Paling Banyak Ikan & Terumbu Karang)',
                        tips: 'Zona Neritik kaya organisme laut karena masih tertembus sinar matahari secara optimal.',
                        contohSoal: 'Di manakah zona laut yang paling kaya akan biota laut dan ikan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Terletak pada <strong>Zona Neritik</strong>.'
                    },
                    {
                        title: 'Bab 9: Biosfer: Bioma Dunia & Persebaran Flora-Fauna',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Bioma dunia (Hutan Hujan Tropis, Taiga, Tundra, Savana, Gurun). Garis Wallace dan Weber membagi fauna Indonesia (Asiatis, Peralihan, Australis).',
                        visual: 'Asiatis (Gajah, Harimau) | Garis Wallace | Peralihan (Komodo, Anoa) | Garis Weber | Australis (Cenderawasih, Kanguru)',
                        tips: 'Komodo dan Anoa merupakan fauna endemik kawasan Peralihan (Wallacea).',
                        contohSoal: 'Fauna cenderawasih dan kakatua raja tergolong ke dalam tipe fauna?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Tergolong fauna tipe <strong>Australis</strong>.'
                    },
                    {
                        title: 'Bab 10: Antroposfer: Dinamika Penduduk & Proyeksi Demografi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Demografi menganalisis pertumbuhan penduduk (Natalitas, Mortalitas, Migrasi). Piramida penduduk (Muda/Ekspansif, Stasioner, Tua/Konstruktif).',
                        visual: 'Dependency Ratio = (Penduduk Non-Produktif / Penduduk Produktif 15-64 thn) × 100',
                        tips: 'Bonus Demografi terjadi ketika proporsi penduduk usia produktif (15-64 thn) melimpah tinggi.',
                        contohSoal: 'Piramida penduduk dengan alas melebar menunjukkan karakteristik penduduk?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Menunjukkan pertumbuhan penduduk usia muda yang tinggi (<strong>Piramida Ekspansif</strong>).'
                    },
                    {
                        title: 'Bab 11: Geografi Desa & Kota serta Interaksi Spasial',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Desa penyedia bahan mentah, kota pusat pelayanan. Teori Titik Henti (Break-off Point) menentukan lokasi ideal fasilitas umum di antara dua kota.',
                        visual: 'Teori Titik Henti: D_TH = d_AB / (1 + √(P_B / P_A))',
                        tips: 'P_A adalah jumlah penduduk kota yang lebih kecil.',
                        contohSoal: 'Jarak A-B = 30 km. Penduduk A = 10.000, B = 40.000. Lokasi titik henti dari A?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. D_TH = 30 / (1 + √(40.000/10.000)) = 30 / (1 + √4) = 30 / 3 = <strong>10 km dari Kota A</strong>.'
                    },
                    {
                        title: 'Bab 12: Wilayah, Perwilayahan & Pusat Pertumbuhan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Wilayah formal (homogen) dan fungsional (heterogen dinamis). Teori Tempat Sentral Christaller (K=3, K=4, K=7). Spread effect dan backwash effect.',
                        visual: 'K=3 (Pasar Optimum)  |  K=4 (Lalu Lintas Optimum)  |  K=7 (Administrasi Optimum)',
                        tips: 'Hierarki K=3 melayani kebutuhan tempat belanja pasar secara optimum.',
                        contohSoal: 'Hierarki K=4 menurut Christaller berfokus pada optimum sektor apakah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Berfokus pada situasi <strong>Lalu Lintas / Transportasi Optimum</strong>.'
                    },
                    {
                        title: 'Bab 13: Indonesia Sebagai Poros Maritim Dunia',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Letak strategis Indonesia di antara dua samudera dan benua. Alur Laut Kepulauan Indonesia (ALKI I, II, III) serta potensi ekonomi kelautan.',
                        visual: 'ALKI I (Sunda) | ALKI II (Lombok) | ALKI III (Ombai-Wetar)',
                        tips: 'ALKI II melintasi Selat Lombok, Selat Makassar, hingga Laut Sulawesi.',
                        contohSoal: 'Selat Sunda tergolong dalam jalur pelayaran internasional ALKI nomor?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Tergolong dalam jalur <strong>ALKI I</strong>.'
                    },
                    {
                        title: 'Bab 14: Mitigasi & Adaptasi Bencana Alam',
                        kurikulum: 'K13 & Merdeka (Fase E/F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Siklus bencana: Pra-bencana (mitigasi/kesiapsiagaan), Saat bencana (tanggap darurat), Pasca-bencana (rehabilitasi/rekonsiliasi).',
                        visual: 'Mitigasi Struktural (Fisik / Candi) vs Mitigasi Non-Struktural (Edukasi / Simulasi)',
                        tips: 'Membuat bangunan tahan gempa tergolong Mitigasi Struktural.',
                        contohSoal: 'Penanaman hutan mangrove di pesisir pantai merupakan mitigasi bencana?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Mitigasi struktural vegetatif penahan gelombang <strong>Tsunami dan Abrasi</strong>.'
                    },
                    {
                        title: 'Bab 15: Pembangunan Berkelanjutan & Kerjasama Internasional',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pembangunan berkelanjutan (SDGs) memenuhi kebutuhan masa kini tanpa mengorbankan generasi mendatang. Analisis AMDAL.',
                        visual: 'AMDAL (Analisis Mengenai Dampak Lingkungan) Wajib Bagi Proyek Berdampak Luas',
                        tips: 'Prinsip eco-efficiency memanfaatkan sumber daya secara hemat dan ramah lingkungan.',
                        contohSoal: 'Dokumen kajian lingkungan hidup wajib bagi proyek industri besar disebut?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dokumen <strong>AMDAL</strong>.'
                    }
                ],
                'eko': [
                    {
                        title: 'Bab 1: Kelangkaan & Biaya Peluang (Opportunity Cost)',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kelangkaan memicu masalah ekonomi. Biaya peluang adalah nilai opsi terbaik yang dikorbankan.',
                        visual: 'Biaya Peluang = Nilai Kesempatan Terbaik yang Tidak Dipilih',
                        tips: 'Biaya peluang tidak dijumlahkan, diambil nilai opsi tertinggi yang dilepas.',
                        contohSoal: 'Budi melepas tawaran gaji 4 jt dan 5 jt demi kuliah. Biaya peluangnya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Opsi tertinggi yang dilepas adalah <strong>Rp 5.000.000</strong>.'
                    },
                    {
                        title: 'Bab 2: Keseimbangan Pasar, Permintaan & Penawaran',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pasar seimbang saat Qd = Qs. Hukum permintaan (P naik, Q turun), hukum penawaran (P naik, Q naik).',
                        visual: 'Keseimbangan Pasar: Q_d = Q_s',
                        tips: 'Perubahan harga barang itu sendiri menyebabkan pergerakan DI SEPANJANG kurva.',
                        contohSoal: 'Qd = 20 - 2P dan Qs = -4 + 2P. Hitung P keseimbangan.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. 20 - 2P = -4 + 2P ⇒ 4P = 24 ⇒ P = <strong>6</strong>.'
                    },
                    {
                        title: 'Bab 3: Elastisitas Harga Permintaan & Penawaran',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Elastisitas mengukur derajat kepekaan Q terhadap P. E = (%ΔQ) / (%ΔP). E>1 Elastis, E<1 Inelastis.',
                        visual: 'E = (ΔQ / ΔP) × (P / Q)',
                        tips: 'Barang kebutuhan pokok (beras, garam) bersifat Inelastis (E < 1).',
                        contohSoal: 'Harga naik 10% menyebabkan jumlah barang yang diminta turun 20%. Koefisien E?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. E = 20% / 10% = <strong>2 (Elastis)</strong>.'
                    },
                    {
                        title: 'Bab 4: Biaya Produksi, Penerimaan & Laba Maksimum',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> TC = TFC + TVC. Laba maksimum dicapai saat Penerimaan Marjinal sama dengan Biaya Marjinal (MR = MC).',
                        visual: 'Laba Maksimum Syarat: MR = MC',
                        tips: 'Jika MR > MC, perusahaan masih bisa meningkatkan laba dengan menambah output.',
                        contohSoal: 'Kondisi optimum produsen untuk mencapai keuntungan maksimal adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Terjadi saat <strong>MR = MC</strong>.'
                    },
                    {
                        title: 'Bab 5: Struktur Pasar: Persaingan Sempurna & Monopoli',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pasar Persaingan Sempurna (banyak penjual, barang homogen, price taker). Pasar Monopoli (satu penjual, barrier to entry tinggi).',
                        visual: 'Monopoli = Single Seller | Oligopoli = Beberap Produsen Dominan',
                        tips: 'Pada Pasar Persaingan Sempurna, P = MR = AR.',
                        contohSoal: 'Pasar dengan produsen semen dan rokok tergolong ke dalam bentuk pasar?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Tergolong pasar <strong>Oligopoli</strong>.'
                    },
                    {
                        title: 'Bab 6: Pendapatan Nasional (PDB, PNB & Pendapatan Per Kapita)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> PDB mengukur total output wilayah. PNB = PDB + Pendapatan Neto Luar Negeri. Pendapatan Per Kapita = PNB / Jumlah Penduduk.',
                        visual: 'Pendapatan Per Kapita = PNB Total / Jumlah Penduduk',
                        tips: 'PDB mengikat batas wilayah geografi, PNB mengikat kewarganegaraan.',
                        contohSoal: 'Gaji TKI di Malaysia dihitung dalam komputasi PNB Indonesia atau PDB Indonesia?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Masuk dalam perhitungan <strong>PNB Indonesia</strong>.'
                    },
                    {
                        title: 'Bab 7: Kebijakan Moneter, Bank Sentral & Kebijakan Fiskal',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kebijakan moneter (Bank Indonesia) mengontrol jumlah uang beredar (Suku bunga, Operasi pasar terbuka, Giro wajib minimum). Kebijakan fiskal (Pemerintah) mengontrol pajak dan APBN.',
                        visual: 'Atasi Inflasi: Naikkan Suku Bunga (BI Rate) & Jual Surat Berharga (SBI)',
                        tips: 'Kebijakan uang ketat (tight money policy) digunakan untuk mengatasi inflasi tinggi.',
                        contohSoal: 'Instrumen kebijakan moneter dengan menaikkan cadangan kas minimum bank disebut?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Disebut kebijakan <strong>Discount Rate / Reserve Requirement</strong>.'
                    },
                    {
                        title: 'Bab 8: Inflasi, Indeks Harga Consumer (IHK) & Pengangguran',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Inflasi adalah kenaikan harga secara umum dan terus menerus. Pengangguran friksional, struktural, konjungtur/siklis.',
                        visual: 'Laju Inflasi = [ (IHK_t - IHK_t-1) / IHK_t-1 ] × 100%',
                        tips: 'Pengangguran akibat alih teknologi otomatisasi mesin tergolong Pengangguran Struktural.',
                        contohSoal: 'IHK bulan lalu 110, bulan ini 121. Hitung laju inflasinya.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Inflasi = [(121 - 110) / 110] × 100% = (11 / 110) × 100% = <strong>10%</strong>.'
                    },
                    {
                        title: 'Bab 9: Perdagangan Internasional, Kurs & Neraca Pembayaran',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Teori Keunggulan Mutlak (Adam Smith) & Komparatif (David Ricardo). Neraca Pembayaran mencatat seluruh transaksi ekonomi luar negeri.',
                        visual: 'Neraca Perdagangan = Total Ekspor Barang - Total Impor Barang',
                        tips: 'Jika Ekspor > Impor, neraca perdagangan mengalami Surplus.',
                        contohSoal: 'Keunggulan produksi barang dengan biaya alternatif terendah disebut?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Keunggulan <strong>Komparatif</strong>.'
                    },
                    {
                        title: 'Bab 10: Persamaan Dasar Akuntansi & Analisis Transaksi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Akuntansi adalah sistem informasi keuangan. Persamaan dasar akuntansi: Aset = Liabilitas + Ekuitas.',
                        visual: 'ASET (Harta) = LIABILITAS (Utang) + EKUITAS (Modal)',
                        tips: 'Pembelian perlengkapan secara kredit menambah Aset (Perlengkapan) dan Utang.',
                        contohSoal: 'Diterima pendapatan jasa Rp 2.000.000 Tunai. Pengaruhnya pada persamaan dasar?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Kas (Aset) bertambah Rp 2 jt, Modal (Ekuitas) bertambah Rp 2 jt.'
                    },
                    {
                        title: 'Bab 11: Jurnal Umum & Mekanisme Debet-Kredit',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Jurnal umum mencatat transaksi secara kronologis. Aturan Debet Kredit: Harta & Beban bertambah di Debet; Utang, Modal, Pendapatan bertambah di Kredit.',
                        visual: 'Harta & Beban (+) Debet | Utang, Modal, Pendapatan (+) Kredit',
                        tips: 'Selalu pastikan total jumlah kolom Debet dan Kredit sejajar seimbang (balanced).',
                        contohSoal: 'Membeli peralatan Rp 5 jt tunai. Jurnal umumnya adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Debet: Peralatan Rp 5 jt, Kredit: Kas Rp 5 jt.'
                    },
                    {
                        title: 'Bab 12: Buku Besar & Neraca Saldo Saldo Sebelum Penyesuaian',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Posting adalah memindahkan catatan jurnal umum ke buku besar masing-masing akun. Neraca saldo menguji kesamaan total debet kredit.',
                        visual: 'Buku Besar Akun T: Saldo Akhir = Total Debet - Total Kredit',
                        tips: 'Kesamaan angka di neraca saldo belum menjamin bebas dari kesalahan pencatatan transaksi.',
                        contohSoal: 'Proses memindahkan ayat jurnal ke buku besar dinamakan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dinamakan proses <strong>Posting</strong>.'
                    },
                    {
                        title: 'Bab 13: Jurnal Penyesuaian (AJP) Perusahaan Jasa & Dagang',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> AJP mengupdate saldo akun di akhir periode agar mencerminkan kondisi riil (beban dibayar dimuka, penyusutan aset, beban terutang).',
                        visual: 'AJP Penyusutan: Debet Beban Penyusutan | Kredit Akumulasi Penyusutan',
                        tips: 'Perlengkapan di AJP dihitung dari nilai perlengkapan yang TERPAKAI.',
                        contohSoal: 'Saldo Perlengkapan 1 jt. Di akhir periode sisa perlengkapan 300rb. AJP beban perlengkapan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Terpakai = 1jt - 300rb = 700rb. AJP: Debet Beban Perlengkapan 700rb, Kredit Perlengkapan 700rb.'
                    },
                    {
                        title: 'Bab 14: Kertas Kerja (Neraca Lajur) & Laporan Keuangan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kertas kerja mempermudah penyusunan Laporan Keuangan (Laporan Laba Rugi, Perubahan Ekuitas, Neraca Posisi Keuangan, Laporan Arus Kas).',
                        visual: 'Laba Bersih = Total Pendapatan - Total Beban',
                        tips: 'Akun Nominal (Pendapatan & Beban) masuk ke Laporan Laba Rugi.',
                        contohSoal: 'Pendapatan 10 jt, Beban 6 jt, Prive 1 jt. Hitung laba bersih perusahaan.<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Laba Bersih = 10 jt - 6 jt = <strong>Rp 4.000.000</strong>.'
                    },
                    {
                        title: 'Bab 15: Jurnal Penutup & Saldo Setelah Penutupan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Jurnal penutup menolkan akun sementara (nominal) di akhir periode ke akun Ikhtisar Laba Rugi agar siap dipakai periode berikutnya.',
                        visual: 'Menutup Pendapatan: Debet Pendapatan | Kredit Ikhtisar Laba Rugi',
                        tips: 'Akun riil (Harta, Utang, Modal) tidak ditutup dan dibawa ke periode berikutnya.',
                        contohSoal: 'Akun manakah yang wajib ditutup pada akhir periode akuntansi?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Ditutup pada akun nominal yaitu <strong>Pendapatan dan Beban</strong>.'
                    }
                ],
                'sos': [
                    {
                        title: 'Bab 1: Hakikat Sosiologi & 4 Ciri Ilmiah Sosiologi',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sosiologi mengkaji masyarakat. Ciri: Empiris, Teoritis, Kumulatif, dan Non-Etis (objektif).',
                        visual: 'Non-Etis = Menganalisis fakta tanpa menghakimi secara moral',
                        tips: 'Jika peneliti tidak menyalahkan pelaku kejahatan melainkan mengkaji motifnya, cirinya Non-Etis.',
                        contohSoal: 'Peneliti mengkaji prostitusi tanpa menilai moral pelaku. Ciri sosiologi?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Ciri <strong>Non-Etis</strong>.'
                    },
                    {
                        title: 'Bab 2: Interaksi Sosial, Syarat & Faktor pendorong',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Syarat interaksi: Kontak Sosial & Komunikasi. Faktor pendorong: Imitasi, Sugesti, Identifikasi, Simpati, Empati.',
                        visual: 'Imitasi (Meniru luar) vs Identifikasi (Meniru identik/menjiwai penuh)',
                        tips: 'Empati melibat aksi nyata pertolongan, simpati sebatas perasaan.',
                        contohSoal: 'Seorang fans merubah penampilan dan perilakunya persis idola. Faktornya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Mengalami proses <strong>Identifikasi</strong>.'
                    },
                    {
                        title: 'Bab 3: Nilai & Norma Sosial dalam Masyarakat',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Nilai adalah sesuatu yang dianggap ideal. Tingkatan norma: Cara (Usage), Kebiasaan (Folkways), Tata Kelakuan (Mores), Adat Istiadat (Customs).',
                        visual: 'Sanksi Terberat = Adat Istiadat (Hukum Adat / Pengucilan)',
                        tips: 'Melanggar kebiasaan hanya mendapat teguran/sindiran halus.',
                        contohSoal: 'Mengunyah makanan dengan bersuara keras melanggar tingkatan norma sosial apakah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Melanggar norma <strong>Cara (Usage)</strong>.'
                    },
                    {
                        title: 'Bab 4: Sosialisasi & Agen Pembentuk Kepribadian',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sosialisasi adalah proses mempelajari nilai budaya. Tahap Mead: Preparatory, Play, Game, Generalized Other. Agen: Keluarga, Sekolah, Teman Sebaya, Media.',
                        visual: 'Tahap Generalized Other = Mampu menjalankan peran di masyarakat luas',
                        tips: 'Sosialisasi primer pertama terjadi di lingkungan internal keluarga.',
                        contohSoal: 'Anak mulai menirukan peran dewasa tanpa memahami maksudnya pada tahap?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Berada pada tahap <strong>Play Stage</strong>.'
                    },
                    {
                        title: 'Bab 5: Perilaku Menyimpang & Teori Anomie Merton',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Penyimpangan sosial akibat sosialisasi tidak sempurna atau subkebudayaan menyimpang. Teori Anomie Merton (Kesesuaian, Inovasi, Ritualisme, Retretisme, Pemberontakan).',
                        visual: 'Inovasi = Menerima Tujuan Budaya tetapi Menolak Cara Legal',
                        tips: 'Korupsi demi gaya hidup tergolong bentuk adaptasi Inovasi Merton.',
                        contohSoal: 'Karyawan bekerja hanya formalitas routine tanpa peduli target sukses tergolong adaptasi?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Bentuk adaptasi <strong>Ritualisme</strong>.'
                    },
                    {
                        title: 'Bab 6: Struktur Sosial & Stratifikasi Sosial (Pelapisan)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Stratifikasi (vertikal/hierarki) dan Diferensiasi (horizontal/setara). Sifat stratifikasi: Terbuka, Tertutup, Campuran.',
                        visual: 'Stratifikasi Tertutup (Kasta Bali/India) vs Terbuka (Prestasi/Ekonomi)',
                        tips: 'Sistem kasta Bali tergolong stratifikasi sosial tertutup.',
                        contohSoal: 'Pelapisan sosial berdasarkan kepemilikan kasta di India tergolong bersifat?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Stratifikasi sosial <strong>Tertutup</strong>.'
                    },
                    {
                        title: 'Bab 7: Diferensiasi Sosial & Multikulturalisme',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pengelompokan horizontal tanpa hierarki (Ras, Etnis, Agama, Gender). Konsolidasi sosial dan Interseksi sosial.',
                        visual: 'Interseksi = Persilangan keanggotaan kelompok sosial yang berbeda',
                        tips: 'Sikap toleransi merupakan kunci utama masyarakat multikultural.',
                        contohSoal: 'Persilangan keanggotaan berdasarkan agama dan suku bangsa dinamakan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dinamakan proses <strong>Interseksi Sosial</strong>.'
                    },
                    {
                        title: 'Bab 8: Konflik Sosial & Resolusi Akomodasi Konflik',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Konflik timbul karena perbedaan kepentingan. Bentuk akomodasi: Konsiliasi, Mediasi (Pihak ketiga netral penasihat), Arbitrase (Pihak ketiga pengambil keputusan mengikat), Ajudikasi (Pengadilan).',
                        visual: 'Mediasi (Ketiga = Penasihat) vs Arbitrase (Ketiga = Pemutus Mengikat)',
                        tips: 'Penyelesaian konflik melalui meja hijau pengadilan dinamakan Ajudikasi.',
                        contohSoal: 'Penyelesaian sengketa lahan di pengadilan dinamakan bentuk akomodasi?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Bentuk akomodasi <strong>Ajudikasi</strong>.'
                    },
                    {
                        title: 'Bab 9: Mobilitas Sosial & Saluran-Salurannya',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Perubahan status sosial individu/kelompok. Mobilitas Vertikal (Naik/Climbing, Turun/Sinking) & Horizontal. Saluran: Pendidikan, Organisasi Politik, Ekonomi, Militer.',
                        visual: 'Pendidikan = Saluran Utama Mobilitas Sosial Vertikal Naik (Social Elevator)',
                        tips: 'Seorang guru naik jabatan menjadi kepala sekolah tergolong mobilitas vertikal naik.',
                        contohSoal: 'Saluran mobilitas sosial paling efektif yang sering disebut social elevator adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Saluran lembaga <strong>Pendidikan</strong>.'
                    },
                    {
                        title: 'Bab 10: Perubahan Sosial & Teori-Teori Perubahan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Perubahan struktur dan fungsi masyarakat. Teori Evolusi, Teori Siklus (Oswald Spengler), Teori Konflik (Karl Marx), dan Teori Linier.',
                        visual: 'Teori Siklus = Perubahan berulang seperti roda berputar (Lahir-Tumbuh-Runtuh)',
                        tips: 'Penyebab internal perubahan sosial: jumlah penduduk, penemuan baru, konflik internal.',
                        contohSoal: 'Peradaban manusia berkembang dari primitif menuju modern secara berurutan dijelaskan teori?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dijelaskan oleh <strong>Teori Linier / Evolusi</strong>.'
                    },
                    {
                        title: 'Bab 11: Modernisasi, Globalisasi & Sekularisasi',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Globalisasi menghubungkan batas dunia. Dampak: Westernisasi, Konsumerisme, Hedonisme, Anomie Budaya, Sekularisasi.',
                        visual: 'Cultural Lag = Ketimpangan pertumbuhan antara budaya material & non-material',
                        tips: 'Teknologi cepat berkembang tetapi mental hukum lambat beradaptasi disebut Cultural Lag.',
                        contohSoal: 'Masyarakat menerima HP canggih tetapi menyebarkan hoax menunjukkan fenomena?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Fenomena <strong>Cultural Lag (Ketimpangan Budaya)</strong>.'
                    },
                    {
                        title: 'Bab 12: Lembaga Sosial & Fungsi Manfaatnya',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sistem norma terorganisir untuk memenuhi kebutuhan dasar. Lembaga Keluarga, Agama, Ekonomi, Politik, Pendidikan.',
                        visual: 'Ciri Lembaga: Punya Simbol, Alat Kelengkapan, Norma Tertulis/Lisan, Kekekalan',
                        tips: 'Fungsi laten adalah fungsi tersembunyi yang tidak disadari dari suatu lembaga.',
                        contohSoal: 'Fungsi keluarga dalam memberikan kasih sayang dan rasa aman dinamakan fungsi?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dinamakan fungsi <strong>Afeksi</strong>.'
                    },
                    {
                        title: 'Bab 13: Penelitian Sosial: Metode Kualitatif & Kuantitatif',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Penelitian ilmiah mencari kebenaran fakta sosial. Metode Kuantitatif (Survei, Angket, Statistik) vs Kualitatif (Wawancara mendalam, Observasi).',
                        visual: 'Kuantitatif (Data Angka) vs Kualitatif (Deskripsi Kata & Motif)',
                        tips: 'Sampel acak (Random Sampling) digunakan pada metode Kuantitatif.',
                        contohSoal: 'Penelitian yang berfokus menguraikan riwayat hidup dan motif mendalam subjek adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Penelitian dengan pendekatan <strong>Kualitatif</strong>.'
                    },
                    {
                        title: 'Bab 14: Masalah Sosial, Kemiskinan & Ketimpangan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kondisi tidak sesuai ekspektasi masyarakat. Kemiskinan Absolut vs Relatif. Ketimpangan sosial akibat redistribusi ekonomi tidak merata.',
                        visual: 'Kemiskinan Absolut = Tidak mampu memenuhi kebutuhan dasar minimum (makan/papan)',
                        tips: 'Indeks Gini mengukur tingkat ketimpangan distribusi pendapatan masyarakat.',
                        contohSoal: 'Koefisien Indeks Gini mendekati angka 1 menunjukkan tingkat ketimpangan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Menunjukkan ketimpangan pendapatan yang <strong>Sangat Tinggi</strong>.'
                    },
                    {
                        title: 'Bab 15: Pemberdayaan Masyarakat & Kearifan Lokal',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Pemberdayaan tingkatkan kemandirian warga berbasis kearifan lokal. Menjaga identitas kebudayaan nasional di tengah arus globalisasi.',
                        visual: 'Kearifan Lokal = Pengetahuan tradisional adaptif mengelola lingkungan',
                        tips: 'Sistem Subak di Bali merupakan contoh kearifan lokal dalam pengelolaan irigasi pertanian.',
                        contohSoal: 'Sistem irigasi pertanian tradisional Subak di Bali tergolong bentuk?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Bentuk <strong>Kearifan Lokal (Local Wisdom)</strong>.'
                    }
                ],
                'sej': [
                    {
                        title: 'Bab 1: Hakikat Ilmu Sejarah, Diakronik & Sinkronik',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sejarah merekonstruksi peristiwa masa lalu. Berpikir Diakronik (memanjang waktu, kronologis) vs Sinkronik (meluas dalam ruang, mendalam).',
                        visual: 'Diakronik (Kronologi Waktu) vs Sinkronik (Kajian Ruang Mendalam)',
                        tips: 'Kritik sumber sejarah terdiri dari Kritik Intern (kredibilitas isi) dan Ekstern (keaslian fisik).',
                        contohSoal: 'Mengkaji kondisi ekonomi Indonesia saat krisis 1998 secara mendalam menggunakan pendekatan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Menggunakan pendekatan <strong>Sinkronik</strong>.'
                    },
                    {
                        title: 'Bab 2: Manusia Purba & Kehidupan Praaksara Nusantara',
                        kurikulum: 'K13 & Merdeka (Fase E)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Manusia purba Nusantara (Meganthropus, Pithecanthropus, Homo). Kebudayaan Paleolitikum, Mesolitikum (Kjokkenmoddinger), Neolitikum (Beliung persegi), Megalitikum.',
                        visual: 'Neolitikum = Revolusi dari Food Gathering menjadi Food Producing',
                        tips: 'Kjokkenmoddinger adalah fosil tumpukan bukit sampah dapur kerang pada masa Mesolitikum.',
                        contohSoal: 'Revolusi kebudayaan perubahan pola hidup berpindah menjadi menetap terjadi pada masa?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Terjadi pada masa <strong>Neolitikum</strong>.'
                    },
                    {
                        title: 'Bab 3: Kerajaan-Kerajaan Hindu-Buddha di Indonesia',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Masuknya Hindu-Buddha (Teori Brahmana, Ksatria, Waisya, Arus Balik). Kerajaan Kutai, Tarumanegara, Sriwijaya (Maritim), Mataram Kuno, Majapahit.',
                        visual: 'Sriwijaya = Kerajaan Maritim & Pusat Agama Buddha terbesar di Asia Tenggara',
                        tips: 'Sumpah Palapa diucapkan Patih Gajah Mada untuk menyatukan Nusantara di bawah Majapahit.',
                        contohSoal: 'Prasasti Yupa dari Kerajaan Kutai ditulis menggunakan huruf dan bahasa apakah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Huruf <strong>Pallawa</strong> dan bahasa <strong>Sanskerta</strong>.'
                    },
                    {
                        title: 'Bab 4: Kerajaan-Kerajaan Islam & Akulturasi Budaya',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Islamisasi via perdagangan, pernikahan, tasawuf, pendidikan. Samudera Pasai, Demak, Mataram Islam, Gowa-Tallo, Ternate-Tidore. Akulturasi arsitektur masjid beratap tumpang.',
                        visual: 'Akulturasi Masjid Kudus = Menara masjid berbentuk Candi Hindu',
                        tips: 'Atap masjid berbentuk tumpang susun merupakan akulturasi budaya Islam dan Hindu-Buddha.',
                        contohSoal: 'Kerajaan Islam pertama di pulau Jawa adalah Kerajaan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Kerajaan <strong>Demak</strong>.'
                    },
                    {
                        title: 'Bab 5: Kolonialisme Barat & Perlawanan Daerah',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Penjelajahan Samudera (Gold, Glory, Gospel). Kekuasaan VOC (Monopoli, Hak Ekstirpasi), Tanam Paksa Cultuurstelsel (Van den Bosch). Perlawanan Diponegoro, Pattimura, Aceh.',
                        visual: 'VOC Hancur 1799 akibat Korupsi & Utang Besar',
                        tips: 'Sistem Tanam Paksa mewajibkan rakyat menanam komoditas ekspor pasar Eropa.',
                        contohSoal: 'Tokoh Belanda penggagas Kebijakan Politik Etis (Trias Van Deventer) adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Digagas oleh <strong>Conrad Theodor van Deventer</strong>.'
                    },
                    {
                        title: 'Bab 6: Pergerakan Nasional & Sumpah Pemuda 1928',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kebangkitan nasional dipicu Politik Etis (edukasi). Budi Utomo (1908), Sarekat Islam, Indische Partij. Kongres Pemuda II (28 Oktober 1928) lahirkan Sumpah Pemuda.',
                        visual: 'Sumpah Pemuda: Satu Nusa, Satu Bangsa, Satu Bahasa Indonesia',
                        tips: 'Indische Partij adalah organisasi pergerakan radikal pertama yang menyuarakan kemerdekaan.',
                        contohSoal: 'Organisasi pergerakan nasional pertama di Indonesia yang berdiri 20 Mei 1908 adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Organisasi <strong>Budi Utomo</strong>.'
                    },
                    {
                        title: 'Bab 7: Pendudukan Jepang di Indonesia (1942-1945)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Propaganda Jepang (3A). Organisasi militer/semimiliter (PETA, Heiho, Seinendan). Kerja paksa Romusha. PETA melatih militer pemuda Indonesia.',
                        visual: 'PETA (Pembela Tanah Air) = Cikal bakal pembentukan TNI',
                        tips: 'Perlawanan PETA Blitar dipimpin oleh Supriyadi pada Februari 1945.',
                        contohSoal: 'Siapakah pemimpin pemberontakan PETA di Blitar melawan tentara Jepang?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dipimpin oleh <strong>Supriyadi</strong>.'
                    },
                    {
                        title: 'Bab 8: Proklamasi Kemerdekaan & Peristiwa Rengasdengklok',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Rengasdengklok (16 Ags 1945) penculikan Soekarno-Hatta oleh pemuda. Penyusunan teks proklamasi di rumah Laksamana Maeda. Pembacaan teks 17 Agustus 1945.',
                        visual: 'Rengasdengklok → Rumah Laksamana Maeda → Pegangsaan Timur 56',
                        tips: 'Teks Proklamasi diketik oleh Sayuti Melik dengan perubahan tiga kata.',
                        contohSoal: 'Siapakah tokoh yang mengetik naskah asli Proklamasi Kemerdekaan Indonesia?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Diketik oleh <strong>Sayuti Melik</strong>.'
                    },
                    {
                        title: 'Bab 9: Perjuangan Mempertahankan Kemerdekaan (Diplomasi & Fisik)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Perjuangan fisik (Surabaya, Medan Area, Bandung Lautan Api). Perjuangan diplomasi (Perjanjian Linggajati, Renville, Roem-Royen, KMB 1949).',
                        visual: 'KMB (Konferensi Meja Bundar 1949) = Pengakuan kedaulatan RIS oleh Belanda',
                        tips: 'Peristiwa Bandung Lautan Api bertujuan mencegah pangkalan militer Sekutu.',
                        contohSoal: 'Konferensi internasional yang menghasilkan pengakuan kedaulatan Indonesia oleh Belanda?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Hasil dari <strong>Konferensi Meja Bundar (KMB)</strong>.'
                    },
                    {
                        title: 'Bab 10: Demokrasi Liberal & Pemilu Pertama 1955',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Sistem parlementer banyak partai. Pergantian kabinet cepat (Natsir, Sukiman, Wilopo, Ali Sastroamidjojo, Burhanuddin Harahap). Pemilu 1955 memilih DPR dan Konstituante.',
                        visual: 'Pemilu 1955 = Pemilu paling demokratis memilih DPR & Konstituante',
                        tips: '4 Partai Pemenang Pemilu 1955: PNI, Masyumi, NU, PKI.',
                        contohSoal: 'Kabinet yang berhasil menyelenggarakan Pemilu pertama tahun 1955 adalah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Kabinet <strong>Burhanuddin Harahap</strong>.'
                    },
                    {
                        title: 'Bab 11: Demokrasi Terpimpin & Dekrit Presiden 5 Juli 1959',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Dekrit Presiden 1959 kembali ke UUD 1945 dan membubarkan Konstituante. Konsep Nasakom. Politik Mercusuar dan pembebasan Irian Barat.',
                        visual: 'Dekrit Presiden 5 Juli 1959: Kembali ke UUD 1945 & Bubarkan Konstituante',
                        tips: 'Politik Mercusuar menghasilkan bangunan fisik seperti GBK, Monas, Hotel Indonesia.',
                        contohSoal: 'Apakah isi utama dari Dekrit Presiden 5 Juli 1959?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Pembubaran Konstituante dan <strong>kembali berlakunya UUD 1945</strong>.'
                    },
                    {
                        title: 'Bab 12: Orde Baru: Dualisme Kepemimpinan & Pembangunan',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Peralihan pasca G30S/PKI via Supersemar. Dwifungsi ABRI. Pembangunan Ekonomi Repelita dan stabilitas politik.',
                        visual: 'Supersemar 11 Maret 1966 = Penyerahan mandat pengamanan kepada Soeharto',
                        tips: 'Dwifungsi ABRI menempatkan militer dalam ranah pertahanan dan politik pemerintahan.',
                        contohSoal: 'Surat perintah tanggal 11 Maret 1966 yang menjadi pilar awal Orde Baru dinamakan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Dinamakan surat <strong>Supersemar</strong>.'
                    },
                    {
                        title: 'Bab 13: Reformasi 1998 & Jatuhnya Pemerintahan Orde Baru',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Krisis moneter 1997 memicu gerakan mahasiswa 1998 menduduki gedung DPR. Pengunduran diri Presiden Soeharto 21 Mei 1998 gantikan BJ Habibie.',
                        visual: '21 Mei 1998 = Soeharto Mundur, B.J. Habibie dilantik jadi Presiden ke-3',
                        tips: '6 Agenda Reformasi: Adili Soeharto, Amandemen UUD, Otonomi Daerah, Hapus Dwifungsi ABRI.',
                        contohSoal: 'Siapakah Presiden yang menggantikan Soeharto saat menyatakan mundur 21 Mei 1998?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Digantikan oleh <strong>B.J. Habibie</strong>.'
                    },
                    {
                        title: 'Bab 14: Perang Dingin & Organisasi Internasional (KAA, ASEAN)',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Persaingan Blok Barat (USA) dan Blok Timur (Uni Soviet). Indonesia aktif Bebas Aktif. Konferensi Asia Afrika (KAA 1955), Gerakan Non-Blok (GNB), pendirian ASEAN 1967.',
                        visual: 'Deklarasi Bangkok (12 Ags 1967) = Berdirinya organisasi ASEAN',
                        tips: 'Peran Indonesia dalam KAA Bandung melahirkan Dasa Sila Bandung.',
                        contohSoal: 'Deklarasi pendirian ASEAN tahun 1967 ditandatangani di kota?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Ditandatangani di <strong>Bangkok, Thailand</strong>.'
                    },
                    {
                        title: 'Bab 15: Perang Dunia I - II & Organisasi Perdamaian LBB - PBB',
                        kurikulum: 'K13 & Merdeka (Fase F)',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> PD I (Sebab khusus: Terbunuhnya Franz Ferdinand). PD II (Sebab khusus: Serangan Jerman ke Polandia 1939). Pembentukan Liga Bangsa-Bangsa (LBB) lalu PBB (24 Okt 1945).',
                        visual: 'PBB (Perserikatan Bangsa-Bangsa) didirikan 24 Oktober 1945 San Francisco',
                        tips: '5 Anggota Tetap Dewan Keamanan PBB punya Hak Veto: USA, Inggris, Prancis, Rusia, China.',
                        contohSoal: 'Sebutkan peristiwa sebab khusus meletusnya Perang Dunia II di kawasan Eropa!<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Serangan invasi militer <strong>Jerman ke Polandia pada 1 September 1939</strong>.'
                    }
                ],
                'lit': [
                    {
                        title: 'Bab 1: Penalaran Logis: Modus Ponens, Tollens & Silogisme',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Logika deduktif menarik kesimpulan yang pasti dari premis. Aturan: Modus Ponens (P→Q, P ⇒ Q), Modus Tollens (P→Q, ~Q ⇒ ~P), Silogisme (P→Q, Q→R ⇒ P→R).',
                        visual: 'Ponens: P→Q, P ⇒ Q  |  Tollens: P→Q, ~Q ⇒ ~P  |  Silogisme: P→Q, Q→R ⇒ P→R',
                        tips: 'Jebakan UTBK: P → Q TIDAK BISA disimpulkan ~P → ~Q atau Q → P.',
                        contohSoal: 'Premis 1: Jika rajin, maka sukses. Premis 2: Budi tidak sukses. Kesimpulan?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Menurut Modus Tollens: Budi tidak rajin.'
                    },
                    {
                        title: 'Bab 2: Penalaran Analitis & Urutan Posisi Kompleks',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Penalaran analitis menguji kemampuan menyusun urutan, jadwal, atau posisi berdasarkan sekumpulan syarat dan batasan.',
                        visual: 'Metode Diagram Matriks / Garis Urutan Posisi',
                        tips: 'Pilih syarat yang memberikan kepastian posisi absolut terlebih dahulu.',
                        contohSoal: 'A lebih tinggi dari B, C lebih tinggi dari A. Siapa paling tinggi?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Urutan tinggi: C > A > B. Paling tinggi adalah <strong>C</strong>.'
                    },
                    {
                        title: 'Bab 3: Penalaran Kuantitatif: Pola Barisan & Deret Angka',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Mengidentifikasi pola deret bilangan: tingkat satu, tingkat dua, larik berselang, atau operasi bertingkat.',
                        visual: 'Pola Beda Bertingkat atau Pola Larik Selang-Seling',
                        tips: 'Jika pola angka naik turun berulang, kemungkinan besar merupakan deret berselang 2 atau 3 langkah.',
                        contohSoal: '3, 6, 12, 21, 33, ... Berapa angka selanjutnya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Selisih: +3, +6, +9, +12. Selisih berikut +15. 33 + 15 = <strong>48</strong>.'
                    },
                    {
                        title: 'Bab 4: Pemahaman Bacaan: Ide Pokok & Kalimat Utama',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Gagasan utama adalah inti pembahasan paragraf. Paragraf Deduktif (awal), Induktif (akhir), Campuran.',
                        visual: 'Gagasan Utama = Topik Bahasan + Pandangan Penulis',
                        tips: 'Kalimat utama bersifat umum dan dijelaskan oleh kalimat-kalimat pengembang.',
                        contohSoal: 'Di manakah letak ide pokok paragraf deduktif?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Terletak pada <strong>Awal Paragraf</strong>.'
                    },
                    {
                        title: 'Bab 5: Penggunaan EBI: Ejaan, Tanda Baca & Kata Baku',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Menguji kaidah Bahasa Indonesia baku: penulisan huruf kapital, kata serapan, pemakaian tanda koma, dan titik koma.',
                        visual: 'Kata Baku: Apotek (bukan Apotik), Praktik (bukan Praktek), Efektif',
                        tips: 'Gelar akademis diapit tanda koma: Budi, S.Pd.',
                        contohSoal: 'Manakah bentuk penulisan kata baku yang benar: Apotik atau Apotek?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Bentuk baku adalah <strong>Apotek</strong>.'
                    },
                    {
                        title: 'Bab 6: Analisis Makna Kata: Konotatif, Denotatif & Kontekstual',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Denotatif adalah makna sebenarnya/Kamus. Konotatif adalah makna kiasan/tambahan. Makna kontekstual bergantung pada kalimat.',
                        visual: 'Denotatif (Makna Sebenarnya) vs Konotatif (Kiasan)',
                        tips: 'Perhatikan hubungan asosiasi kata dalam kalimat untuk menemukan makna konotasi.',
                        contohSoal: 'Frasa "panjang tangan" dalam arti suka mencuri tergolong makna?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Tergolong makna <strong>Konotatif</strong>.'
                    },
                    {
                        title: 'Bab 7: Penalaran Gambar & Spasial (Figural)',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Menganalisis rotasi, cermin, analogi gambar, atau kelanjutan pola perubahan bentuk 2D/3D.',
                        visual: 'Rotasi Searah Jarum Jam 90° / 180° / Pencerminan',
                        tips: 'Fokus pada satu elemen kecil dalam gambar lalu ikuti pergerakannya.',
                        contohSoal: 'Bentuk yang diputar 90 derajat searah jarum jam akan menghadap ke?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Sisi atas berpindah menghadap ke <strong>Sisi Kanan</strong>.'
                    },
                    {
                        title: 'Bab 8: Kalimat Efektif & Kehematan Kata',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Kalimat efektif memenuhi syarat: kesepadanan struktur, keparalelan bentuk, kehematan kata, dan kelogisan penalaran.',
                        visual: 'Hindari Pleonasme: "sangat indah sekali" (Salah) → "sangat indah" (Benar)',
                        tips: 'Subjek kalimat tidak boleh didahului oleh kata depan (seperti "Dalam...", "Bagi...").',
                        contohSoal: 'Perbaiki kalimat pleonasme: "Hadirin para bapak-bapak sekalian".<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Kalimat efektif: "<strong>Hadirin sekalian</strong>" atau "<strong>Para bapak</strong>".'
                    },
                    {
                        title: 'Bab 9: Pemahaman Paragraf: Hubungan Antarkalimat',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Menganalisis keterkaitan logis antarkalimat: hubungan penjelas, pertentangan, sebab-akibat, penegasan, atau contoh.',
                        visual: 'Konjungsi Antarkalimat: Namun, Oleh karena itu, Dengan demikian',
                        tips: 'Kata konjungsi "Namun" digunakan di awal kalimat untuk menyatakan pertentangan.',
                        contohSoal: 'Kata sambung untuk menunjukkan hubungan akibat di awal kalimat?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Menggunakan konjungsi <strong>"Oleh karena itu,"</strong>.'
                    },
                    {
                        title: 'Bab 10: Teks Argumentasi: Inferensi & Simpulan Implisit',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Menarik inferensi yang tidak tertulis secara eksplisit dalam teks berdasarkan bukti faktual paragraf.',
                        visual: 'Inferensi Sah = Harus Didukung Bukti Langsung dalam Teks',
                        tips: 'Jangan memilih jawaban simpulan yang mengandung kata ekstrem tanpa bukti kuat.',
                        contohSoal: 'Apakah syarat utama kesimpulan implisit paragraf dapat dinyatakan sah?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Harus sepenuhnya <strong>didukung oleh fakta dalam teks</strong>.'
                    },
                    {
                        title: 'Bab 11: Literasi Bahasa Inggris: Main Idea & Author\'s Attitude',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Memahami teks Bahasa Inggris akademik: Main Idea, Author\'s Tone (Critical, Neutral, Optimistic), Synonyms in Context.',
                        visual: 'Tone: Critical, Informative, Objective, Persuasive',
                        tips: 'Skimming paragraf pertama dan terakhir untuk menemukan topic sentence.',
                        contohSoal: 'What is the main purpose of an informative text in English literacy?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. To <strong>provide factual information to the readers</strong>.'
                    },
                    {
                        title: 'Bab 12: Literasi Bahasa Inggris: Inference & Vocabulary',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Menarik kesimpulan tersirat dalam bacaan Bahasa Inggris serta menentukan padanan kata teknis.',
                        visual: 'Inference Questions: "It can be inferred from paragraph 2 that..."',
                        tips: 'Gunakan kalimat sebelum dan sesudah kata asing untuk menebak konteks arti.',
                        contohSoal: 'Synonym of the word "substantial" in academic context?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Synonym: <strong>Significant / Considerable</strong>.'
                    },
                    {
                        title: 'Bab 13: Penalaran Matematika Sederhana & Diagram Venn',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Soal cerita aplikasi himpunan dan diagram Venn pada permasalahan sehari-hari.',
                        visual: 'n(A ∪ B) = n(A) + n(B) - n(A ∩ B)',
                        tips: 'Isi bagian irisan n(A ∩ B) terlebih dahulu di tengah diagram Venn.',
                        contohSoal: 'Dari 30 siswa, 20 suka Mat, 15 suka Fis, 10 suka keduanya. Berapa tidak suka keduanya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Total suka setidaknya satu = 20 + 15 - 10 = 25. Tidak suka = 30 - 25 = <strong>5 siswa</strong>.'
                    },
                    {
                        title: 'Bab 14: Analisis Tabel, Grafik & Data Statistik UTBK',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Membaca dan menyimpulkan tren data kuantitatif dalam bentuk tabel, diagram batang, atau grafik garis.',
                        visual: 'Persentase Kenaikan = [ (Data Baru - Data Lama) / Data Lama ] × 100%',
                        tips: 'Perhatikan sumbu X dan Y beserta satuan skala sebelum menghitung.',
                        contohSoal: 'Penjualan naik dari 100 ke 150 unit. Berapa persen kenaikannya?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Kenaikan = [(150 - 100) / 100] × 100% = <strong>50%</strong>.'
                    },
                    {
                        title: 'Bab 15: Pemecahan Masalah Studi Kasus Kebijakan Publik',
                        kurikulum: 'UTBK SNBT 2026',
                        summary: '<strong>Penjelasan Konsep Terperinci:</strong> Menguji penalaran logis kritis dalam menilai solusi paling efektif dari permasalahan sosial atau ekonomi.',
                        visual: 'Pilih Solusi yang Paling Rasional, Berdampak Luas & Minim Risiko',
                        tips: 'Gunakan prinsip kepatuhan hukum dan efisiensi biaya saat memilih solusi.',
                        contohSoal: 'Kriteria utama memilih solusi terbaik dari kasus dilema publik?<br><strong>Langkah Penyelesaian Terperinci:</strong><br>1. Memilih solusi yang <strong>paling rasional, minim dampak negatif, dan sesuai hukum</strong>.'
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
                        },
                        {
                            id: 'pk_q3',
                            pertanyaan: 'Jika ᵃlog 2 = x dan ᵃlog 3 = y, maka nilai dari ᵃlog 18 adalah...',
                            pilihan: ['A. x + y', 'B. x + 2y', 'C. 2x + y', 'D. x² + y', 'E. x · y²'],
                            kunci: 'B. x + 2y',
                            solusiLengkap: 'ᵃlog 18 = ᵃlog(2 × 3²) = ᵃlog 2 + 2 · ᵃlog 3 = x + 2y.'
                        },
                        {
                            id: 'pk_q4',
                            pertanyaan: 'Nilai dari lim (x→2) (x² - 4) / (x - 2) adalah...',
                            pilihan: ['A. 0', 'B. 2', 'C. 4', 'D. 8', 'E. Tidak terdefinisi'],
                            kunci: 'C. 4',
                            solusiLengkap: 'Bentuk 0/0. Aturan L\'Hopital: turunkan pembilang (2x) dan penyebut (1). lim (x→2) (2x / 1) = 2(2) = 4.'
                        },
                        {
                            id: 'pk_q5',
                            pertanyaan: 'Luas daerah yang dibatasi oleh parabola y = x² dan garis y = 4 adalah...',
                            pilihan: ['A. 16/3 satuan', 'B. 32/3 satuan', 'C. 64/3 satuan', 'D. 8 satuan', 'E. 12 satuan'],
                            kunci: 'B. 32/3 satuan',
                            solusiLengkap: 'Titik potong x² = 4 ⇒ x = -2 sampai x = 2. Luas = ∫[-2,2] (4 - x²) dx = [4x - x³/3] limit -2 sampai 2 = (8 - 8/3) - (-8 + 8/3) = 16 - 16/3 = 32/3.'
                        }
                    ]
                },
                'utbk-pu': {
                    title: 'UTBK SNBT - Penalaran Umum & Logika (PU)',
                    durasiMinutes: 10,
                    soal: [
                        {
                            id: 'pu_q1',
                            pertanyaan: 'Semua peserta tryout membawa kartu ujian. Sebagian peserta tryout menggunakan kemeja putih. Kesimpulan yang tepat adalah...',
                            pilihan: [
                                'A. Semua peserta tryout berkemeja putih membawa kartu ujian',
                                'B. Sebagian peserta tryout yang membawa kartu ujian berkemeja putih',
                                'C. Semua peserta tryout tidak berkemeja putih',
                                'D. Peserta yang membawa kartu ujian pasti tidak berkemeja putih',
                                'E. Tidak ada kesimpulan yang dapat ditarik'
                            ],
                            kunci: 'B. Sebagian peserta tryout yang membawa kartu ujian berkemeja putih',
                            solusiLengkap: 'Karena SEMUA peserta membawa kartu ujian, maka SEBAGIAN peserta berkemeja putih pasti membawa kartu ujian.'
                        },
                        {
                            id: 'pu_q2',
                            pertanyaan: 'Jika hari hujan, maka jalanan licin. Hari ini jalanan tidak licin. Kesimpulan yang sah adalah...',
                            pilihan: ['A. Hari ini hujan', 'B. Hari ini tidak hujan', 'C. Hari ini mendung', 'D. Jalanan kering karena hujan', 'E. Tidak dapat disimpulkan'],
                            kunci: 'B. Hari ini tidak hujan',
                            solusiLengkap: 'Modus Tollens: P → Q, ~Q ⇒ ~P. P = Hujan, Q = Licin. Karena ~Q (tidak licin), maka ~P (tidak hujan).'
                        },
                        {
                            id: 'pu_q3',
                            pertanyaan: 'Diketahui barisan angka: 3, 6, 12, 21, 33, ... Angka berikutnya adalah...',
                            pilihan: ['A. 42', 'B. 45', 'C. 48', 'D. 51', 'E. 54'],
                            kunci: 'C. 48',
                            solusiLengkap: 'Pola selisih: +3, +6, +9, +12, ... Selisih berikutnya adalah +15. Maka 33 + 15 = 48.'
                        }
                    ]
                },
                'tka-saintek': {
                    title: 'TKA Saintek - Fisika, Kimia & Biologi HOTS',
                    durasiMinutes: 10,
                    soal: [
                        {
                            id: 'saintek_q1',
                            pertanyaan: 'Benda bermassa 2 kg ditarik gaya F = 20 N sudut 60° terhadap horizontal pada lantai licin. Berapakah percepatan benda?',
                            pilihan: ['A. 5 m/s²', 'B. 10 m/s²', 'C. 5√3 m/s²', 'D. 20 m/s²', 'E. 10√3 m/s²'],
                            kunci: 'A. 5 m/s²',
                            solusiLengkap: 'F_x = F cos 60° = 20 (0,5) = 10 N. a = F_x / m = 10 / 2 = 5 m/s².'
                        },
                        {
                            id: 'saintek_q2',
                            pertanyaan: 'Larutan HCl 0,01 M memiliki volume 100 mL. Nilai pH larutan tersebut adalah...',
                            pilihan: ['A. 1', 'B. 2', 'C. 3', 'D. 12', 'E. 13'],
                            kunci: 'B. 2',
                            solusiLengkap: 'HCl asam kuat valensi 1. [H⁺] = 10⁻² M. pH = -log(10⁻²) = 2.'
                        },
                        {
                            id: 'saintek_q3',
                            pertanyaan: 'Pada katode sel elektrolisis larutan CuSO₄ dengan elektrode karbon (C), zat yang dihasilkan adalah...',
                            pilihan: ['A. Gas Oksigen', 'B. Gas Hidrogen', 'C. Endapan Logam Tembaga (Cu)', 'D. Gas Klorin', 'E. Larutan Asam Sulfat'],
                            kunci: 'C. Endapan Logam Tembaga (Cu)',
                            solusiLengkap: 'Di katode terjadi reduksi kation. Kation Cu²⁺ memiliki E° lebih positif daripada air, sehingga Cu²⁺ tereduksi menjadi logam Cu (Cu²⁺ + 2e⁻ → Cu).'
                        }
                    ]
                },
                'tka-soshum': {
                    title: 'TKA Soshum - Ekonomi, Sosiologi & Geografi',
                    durasiMinutes: 10,
                    soal: [
                        {
                            id: 'soshum_q1',
                            pertanyaan: 'Apabila pemerintah menetapkan harga maksimum (Ceiling Price) di bawah harga keseimbangan pasar, dampak langsung yang terjadi adalah...',
                            pilihan: ['A. Kelebihan penawaran (Excess Supply)', 'B. Kelebihan permintaan / Kelangkaan barang (Excess Demand)', 'C. Harga pasar melonjak', 'D. Produsen mengalami surplus besar', 'E. Kurva penawaran bergeser ke kanan'],
                            kunci: 'B. Kelebihan permintaan / Kelangkaan barang (Excess Demand)',
                            solusiLengkap: 'Harga maksimum di bawah pasar membuat Qd naik (pembeli ingin beli banyak) tetapi Qs turun (penjual enggan menjual), memicu Excess Demand.'
                        },
                        {
                            id: 'soshum_q2',
                            pertanyaan: 'Peneliti sosiologi menganalisis fenomena kemiskinan perkotaan tanpa menghakimi secara moral baik atau buruknya objek. Ciri sosiologi ini adalah...',
                            pilihan: ['A. Empiris', 'B. Kumulatif', 'C. Non-Etis', 'D. Teoritis', 'E. Spekulatif'],
                            kunci: 'C. Non-Etis',
                            solusiLengkap: 'Ciri Non-Etis berarti sosiologi menjelaskan fakta sosial secara objektif tanpa memberikan penilaian etis/moral.'
                        }
                    ]
                }
            }
        };

        // UI View Switcher Engine
        function switchView(viewName) {
            state.activeView = viewName;

            ['home', 'materi', 'kalkulator', 'utbk', 'flashcards', 'riwayat'].forEach(v => {
                const el = document.getElementById(`nav-${v}`);
                if (el) {
                    el.className = v === viewName 
                        ? "px-4 py-2.5 rounded-xl text-white bg-purple-600 font-bold shadow-md shadow-purple-600/30 transition flex items-center gap-1.5"
                        : "px-4 py-2.5 rounded-xl text-slate-300 hover:text-white font-medium transition flex items-center gap-1.5";
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

        // Global Search Logic
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
                list.forEach((mat, idx) => {
                    if (mat.title.toLowerCase().includes(q) || mat.summary.toLowerCase().includes(q)) {
                        matches.push({ mapelId: m.id, mapelNama: m.nama, title: mat.title, babIdx: idx });
                    }
                });
            });

            if (matches.length === 0) {
                popover.innerHTML = `<div class="p-3 text-xs text-slate-400 text-center">Tidak ditemukan materi dengan kata kunci "${query}"</div>`;
            } else {
                popover.innerHTML = matches.map(res => `
                    <div onclick="selectSearchResult('${res.mapelId}', ${res.babIdx})" class="p-3 hover:bg-slate-800/80 rounded-xl cursor-pointer transition border-b border-slate-800/60 last:border-0">
                        <span class="text-[10px] font-bold text-purple-400 uppercase tracking-wider block">${res.mapelNama}</span>
                        <span class="text-xs text-white font-semibold block mt-0.5">${res.title}</span>
                    </div>
                `).join('');
            }
            popover.classList.remove('hidden');
        }

        function selectSearchResult(mapelId, babIdx = 0) {
            document.getElementById('search-results-popover').classList.add('hidden');
            document.getElementById('global-search').value = '';
            state.selectedSubject = mapelId;
            state.currentBabIdx = babIdx;
            switchView('materi');
            openDetailMapel(mapelId);
        }

        // Render Home View
        function renderHome() {
            return `
                <!-- Hero Banner -->
                <div class="relative rounded-3xl gradient-brand p-8 sm:p-12 overflow-hidden border border-purple-500/30 shadow-2xl mb-12">
                    <div class="absolute -right-20 -bottom-20 w-96 h-96 bg-purple-600/20 rounded-full blur-3xl pointer-events-none"></div>
                    <div class="relative z-10 max-w-3xl">
                        <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-purple-500/10 border border-purple-500/30 text-purple-300 text-xs font-semibold mb-6">
                            <i data-lucide="sparkles" class="w-4 h-4 text-purple-400"></i>
                            <span>Nihiluxxy AI Pro 2026 • Dedicated Slide Presentation System</span>
                        </div>
                        <h1 class="text-3xl sm:text-5xl font-black text-white tracking-tight mb-4 leading-tight">
                            Mode Presentasi Slide Interaktif & <span class="bg-clip-text text-transparent gradient-accent">UTBK SNBT 2026</span>.
                        </h1>
                        <p class="text-slate-300 text-xs sm:text-sm mb-8 leading-relaxed">
                            Nikmati cara belajar baru seperti dalam ruang les bimbel elite! 15 Bab Terperinci per mapel kini tersaji dalam **Sistem Slide Mandiri** lengkap dengan indikator progress, tab konsep visual, tips cepat, dan contoh soal HOTS.
                        </p>
                        <div class="flex flex-wrap gap-4">
                            <button onclick="switchView('materi')" class="gradient-accent text-white font-extrabold px-6 py-3.5 rounded-2xl shadow-lg shadow-purple-500/25 hover:opacity-95 transition flex items-center gap-2 text-xs sm:text-sm">
                                <i data-lucide="presentation" class="w-4 h-4"></i> Buka Mode Slide Presentasi
                            </button>
                            <button onclick="switchView('kalkulator')" class="bg-slate-900/90 border border-cyan-500/40 text-cyan-200 font-extrabold px-6 py-3.5 rounded-2xl hover:bg-slate-800 transition flex items-center gap-2 text-xs sm:text-sm">
                                <i data-lucide="calculator" class="w-4 h-4 text-cyan-400"></i> Kalkulator AI Math & Sains
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Stats Cards -->
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-12">
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-purple-400 font-mono">135+</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">Bab Slide Mandiri</span>
                    </div>
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-emerald-400 font-mono">100%</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">K13 & Merdeka Active</span>
                    </div>
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-amber-400 font-mono">HOTS</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">Pembahasan Akurat</span>
                    </div>
                    <div class="glass-card p-5 rounded-2xl text-center border-purple-500/20">
                        <span class="text-2xl font-black text-cyan-400 font-mono">v6.5</span>
                        <span class="text-xs text-slate-400 block mt-1 font-semibold">Slide Presenter Engine</span>
                    </div>
                </div>

                <!-- Subject Grid Section -->
                <div class="mb-12">
                    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 mb-6">
                        <div>
                            <h2 class="text-2xl font-black text-white tracking-tight">Mata Pelajaran SMA (Format Slide Interaktif)</h2>
                            <p class="text-slate-400 text-xs sm:text-sm">Pilih mata pelajaran untuk langsung memulai mode slide presentasi</p>
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
                                    <span class="font-bold text-[11px]">Putar Slide Belajar</span>
                                    <i data-lucide="play-circle" class="w-4 h-4 text-purple-400 group-hover:scale-110 transition"></i>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                </div>

                <!-- Last Attempt Card -->
                <div class="glass-card border border-slate-800 rounded-3xl p-6 sm:p-8 shadow-xl">
                    <div class="flex items-center justify-between mb-4">
                        <div class="flex items-center gap-3">
                            <div class="p-2.5 rounded-2xl bg-purple-500/10 text-purple-400 border border-purple-500/20">
                                <i data-lucide="history" class="w-5 h-5"></i>
                            </div>
                            <div>
                                <h3 class="font-extrabold text-white text-base">Riwayat Simulasi Terakhir</h3>
                                <p class="text-xs text-slate-400">Evaluasi & pelajari pembahasan akurat dari pengerjaan Anda</p>
                            </div>
                        </div>
                        <button onclick="switchView('riwayat')" class="text-xs text-purple-400 hover:text-purple-300 font-bold flex items-center gap-1">
                            <span>Lihat Semua</span>
                            <i data-lucide="chevron-right" class="w-4 h-4"></i>
                        </button>
                    </div>
                    ${renderLastAttemptCard()}
                </div>
            `;
        }

        function renderLastAttemptCard() {
            if (state.attempts.length === 0) {
                return `
                    <div class="text-center py-8 text-slate-500 text-xs border border-dashed border-slate-800 rounded-2xl bg-slate-900/40">
                        <i data-lucide="info" class="w-6 h-6 mx-auto mb-2 text-slate-600"></i>
                        Belum ada simulasi yang diselesaikan. Selesaikan simulasi TKA/UTBK untuk mencatat riwayat akurat Anda di sini.
                    </div>
                `;
            }
            const last = state.attempts[state.attempts.length - 1];
            return `
                <div class="bg-slate-900/80 border border-slate-800 p-5 rounded-2xl flex flex-col sm:flex-row justify-between sm:items-center gap-4">
                    <div>
                        <div class="flex items-center gap-2 mb-1.5">
                            <span class="text-[10px] font-extrabold px-2 py-0.5 rounded-full bg-emerald-500/20 text-emerald-300 border border-emerald-500/30">Pengerjaan Terakhir</span>
                            <span class="text-xs text-slate-500 font-mono">${last.tanggal}</span>
                        </div>
                        <h4 class="font-black text-white text-base">${last.judulSimulasi}</h4>
                        <p class="text-xs text-slate-400 mt-1">Akurasi Skor: <span class="text-purple-300 font-bold font-mono">${last.skor}%</span> (${last.benar} dari ${last.totalSoal} Soal Benar)</p>
                    </div>
                    <button onclick="openDetailRiwayat(${state.attempts.length - 1})" class="px-5 py-3 bg-purple-600 hover:bg-purple-500 text-white font-extrabold text-xs rounded-xl transition shadow-lg shadow-purple-600/20 flex items-center justify-center gap-2">
                        <i data-lucide="file-search" class="w-4 h-4"></i> Lihat Pembahasan Akurat
                    </button>
                </div>
            `;
        }

        function setKurikulum(k) {
            state.selectedKurikulum = k;
            switchView('home');
        }

        // ==========================================
        // DEDICATED SLIDE PRESENTATION ENGINE (v6.5)
        // ==========================================
        function renderMateriScreen() {
            return `
                <div class="mb-6 flex flex-col md:flex-row md:items-center justify-between gap-4">
                    <div>
                        <h1 class="text-2xl sm:text-3xl font-black text-white tracking-tight">Modul Pembelajaran SMA (Mode Presentasi Slide)</h1>
                        <p class="text-slate-400 text-xs sm:text-sm mt-1">Pelajari 15 Bab terperinci per mata pelajaran dalam format slide interaktif mandiri.</p>
                    </div>
                    <!-- Pemilih Mapel Cepat -->
                    <div class="flex items-center gap-2 bg-slate-900 p-1.5 rounded-2xl border border-slate-800">
                        <i data-lucide="book-open" class="w-4 h-4 text-purple-400 ml-2"></i>
                        <select id="mapel-slide-select" onchange="openDetailMapel(this.value)" class="bg-transparent text-xs font-bold text-slate-200 p-2 focus:outline-none cursor-pointer">
                            ${db.mapel.map(m => `<option value="${m.id}" ${m.id === state.selectedSubject ? 'selected' : ''} class="bg-slate-900 text-white">${m.nama}</option>`).join('')}
                        </select>
                    </div>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                    <!-- Sidebar Daftar Bab Slide -->
                    <div class="lg:col-span-4 space-y-2 max-h-[75vh] overflow-y-auto custom-scrollbar pr-1">
                        <h3 class="text-xs uppercase tracking-wider font-extrabold text-purple-400 px-1 mb-2">Daftar 15 Bab Presentasi</h3>
                        <div id="bab-slide-list" class="space-y-2">
                            <!-- Injected by JS -->
                        </div>
                    </div>

                    <!-- Slide Reader Area Utama -->
                    <div id="materi-reader" class="lg:col-span-8 glass-card border border-purple-500/40 rounded-3xl p-6 sm:p-8 shadow-2xl relative flex flex-col justify-between min-h-[620px]">
                        <!-- Injected by JS -->
                    </div>
                </div>
            `;
        }

        function openDetailMapel(mapelId) {
            state.selectedSubject = mapelId;
            state.currentBabIdx = 0;
            state.currentTabSlide = 'konsep';
            
            if (state.activeView !== 'materi') {
                switchView('materi');
                return;
            }

            const selectEl = document.getElementById('mapel-slide-select');
            if (selectEl) selectEl.value = mapelId;

            renderBabListSidebar();
            renderSlideBab();
        }

        function renderBabListSidebar() {
            const listContainer = document.getElementById('bab-slide-list');
            if (!listContainer) return;

            const materiList = db.materiDetails[state.selectedSubject] || [];

            listContainer.innerHTML = materiList.map((mat, idx) => `
                <button onclick="jumpToBabSlide(${idx})" class="w-full text-left p-3.5 rounded-2xl border transition flex items-center justify-between group ${idx === state.currentBabIdx ? 'bg-purple-900/40 border-purple-500/80 text-white shadow-lg' : 'bg-slate-900/60 border-slate-800 text-slate-400 hover:bg-slate-800 hover:text-slate-200'}">
                    <div class="flex items-center gap-3">
                        <span class="w-7 h-7 rounded-xl ${idx === state.currentBabIdx ? 'bg-purple-600 text-white' : 'bg-slate-800 text-slate-400'} flex items-center justify-center text-xs font-mono font-bold">${idx + 1}</span>
                        <span class="text-xs font-bold leading-tight line-clamp-1 group-hover:text-purple-300 transition">${mat.title.replace(/^Bab \d+: /, '')}</span>
                    </div>
                    <i data-lucide="chevron-right" class="w-4 h-4 ${idx === state.currentBabIdx ? 'text-purple-400' : 'opacity-0 group-hover:opacity-100'} transition"></i>
                </button>
            `).join('');
            
            lucide.createIcons();
        }

        function renderSlideBab() {
            const reader = document.getElementById('materi-reader');
            if (!reader) return;

            const mapel = db.mapel.find(m => m.id === state.selectedSubject);
            const materiList = db.materiDetails[state.selectedSubject] || [];
            const bab = materiList[state.currentBabIdx];

            if (!bab) {
                reader.innerHTML = `<div class="text-center py-12 text-slate-400">Data modul bab belum tersedia.</div>`;
                return;
            }

            const totalBab = materiList.length;

            reader.innerHTML = `
                <!-- Top Bar Slide Info & Progress Bar -->
                <div>
                    <div class="flex flex-wrap items-center justify-between gap-2 pb-4 border-b border-slate-800 mb-4">
                        <div class="flex items-center gap-2">
                            <span class="text-[10px] font-black uppercase px-2.5 py-1 rounded-full bg-purple-500/20 text-purple-300 border border-purple-500/30">
                                ${mapel.nama}
                            </span>
                            <span class="text-[10px] font-extrabold uppercase px-2.5 py-1 rounded-full bg-emerald-500/20 text-emerald-300 border border-emerald-500/30">
                                ${bab.kurikulum}
                            </span>
                        </div>
                        <div class="flex items-center gap-2">
                            <span class="text-xs font-mono font-extrabold text-purple-400">Slide ${state.currentBabIdx + 1} / ${totalBab}</span>
                            <button onclick="askAiAboutTopic('${bab.title}')" class="px-3 py-1.5 bg-purple-600/20 border border-purple-500/40 text-purple-300 hover:bg-purple-600 hover:text-white rounded-xl text-xs font-bold transition flex items-center gap-1">
                                <i data-lucide="bot" class="w-3.5 h-3.5"></i> Tanya AI
                            </button>
                        </div>
                    </div>

                    <!-- Progress Indicator Bar -->
                    <div class="w-full bg-slate-900 rounded-full h-1.5 mb-6 overflow-hidden border border-slate-800">
                        <div class="bg-gradient-to-r from-purple-500 to-pink-500 h-1.5 rounded-full transition-all duration-500" style="width: ${((state.currentBabIdx + 1) / totalBab) * 100}%"></div>
                    </div>

                    <!-- Title Slide -->
                    <h2 class="text-xl sm:text-2xl font-black text-white tracking-tight mb-6 leading-snug">
                        ${bab.title}
                    </h2>

                    <!-- Sub-Slide Tab Navigation Bar -->
                    <div class="flex gap-2 border-b border-slate-800/80 pb-3 mb-6 overflow-x-auto custom-scrollbar text-xs font-bold">
                        <button onclick="changeSlideTab('konsep')" class="px-4 py-2 rounded-xl transition flex items-center gap-1.5 whitespace-nowrap ${state.currentTabSlide === 'konsep' ? 'bg-purple-600 text-white shadow-md' : 'bg-slate-900 text-slate-400 hover:text-white'}">
                            <i data-lucide="book-open-text" class="w-3.5 h-3.5"></i> 1. Penjelasan Konsep
                        </button>
                        <button onclick="changeSlideTab('formula')" class="px-4 py-2 rounded-xl transition flex items-center gap-1.5 whitespace-nowrap ${state.currentTabSlide === 'formula' ? 'bg-purple-600 text-white shadow-md' : 'bg-slate-900 text-slate-400 hover:text-white'}">
                            <i data-lucide="binary" class="w-3.5 h-3.5"></i> 2. Formula & Visual
                        </button>
                        <button onclick="changeSlideTab('tips')" class="px-4 py-2 rounded-xl transition flex items-center gap-1.5 whitespace-nowrap ${state.currentTabSlide === 'tips' ? 'bg-purple-600 text-white shadow-md' : 'bg-slate-900 text-slate-400 hover:text-white'}">
                            <i data-lucide="zap" class="w-3.5 h-3.5 text-amber-400"></i> 3. Tips Cepat Bimbel
                        </button>
                        <button onclick="changeSlideTab('soal')" class="px-4 py-2 rounded-xl transition flex items-center gap-1.5 whitespace-nowrap ${state.currentTabSlide === 'soal' ? 'bg-purple-600 text-white shadow-md' : 'bg-slate-900 text-slate-400 hover:text-white'}">
                            <i data-lucide="file-check-2" class="w-3.5 h-3.5 text-emerald-400"></i> 4. Bedah Soal HOTS
                        </button>
                    </div>

                    <!-- Dynamic Content Body Slide -->
                    <div class="bg-slate-950/70 border border-slate-800/90 rounded-2xl p-5 sm:p-6 min-h-[220px] leading-relaxed text-xs sm:text-sm text-slate-200">
                        ${renderSlideTabContent(bab)}
                    </div>
                </div>

                <!-- Bottom Controls Slide Navigation -->
                <div class="flex items-center justify-between pt-6 border-t border-slate-800/80 mt-6">
                    <button onclick="prevBabSlide()" ${state.currentBabIdx === 0 ? 'disabled class="opacity-40 cursor-not-allowed px-5 py-2.5 bg-slate-900 text-slate-500 rounded-xl text-xs font-bold"' : 'class="px-5 py-2.5 bg-slate-900 border border-slate-700 hover:bg-slate-800 text-slate-200 rounded-xl text-xs font-bold transition flex items-center gap-2"'}>
                        <i data-lucide="arrow-left" class="w-4 h-4"></i> Bab Sebelumnya
                    </button>

                    <span class="hidden sm:inline text-[11px] font-mono text-slate-500 font-bold">Gunakan tombol atau klik daftar bab</span>

                    <button onclick="nextBabSlide()" ${state.currentBabIdx === totalBab - 1 ? 'disabled class="opacity-40 cursor-not-allowed px-5 py-2.5 bg-slate-900 text-slate-500 rounded-xl text-xs font-bold"' : 'class="px-6 py-2.5 bg-purple-600 hover:bg-purple-500 text-white rounded-xl text-xs font-extrabold transition shadow-lg shadow-purple-600/30 flex items-center gap-2"'}>
                        Bab Selanjutnya <i data-lucide="arrow-right" class="w-4 h-4"></i>
                    </button>
                </div>
            `;

            lucide.createIcons();
            renderBabListSidebar();
        }

        function renderSlideTabContent(bab) {
            if (state.currentTabSlide === 'konsep') {
                return `
                    <div class="space-y-3 animate-fadeIn">
                        <span class="text-xs font-extrabold text-purple-400 uppercase tracking-wider block">📖 Penjelasan Konsep Inti:</span>
                        <div class="text-slate-200 leading-relaxed">${bab.summary}</div>
                    </div>
                `;
            } else if (state.currentTabSlide === 'formula') {
                return `
                    <div class="space-y-3 animate-fadeIn">
                        <span class="text-xs font-extrabold text-cyan-400 uppercase tracking-wider block">📐 Formulasi & Ringkasan Rumus Visual:</span>
                        <div class="bg-slate-900 p-4 sm:p-6 rounded-2xl border border-purple-500/30 font-mono text-xs sm:text-sm text-purple-300 text-center overflow-x-auto shadow-inner my-2">
                            ${bab.visual}
                        </div>
                    </div>
                `;
            } else if (state.currentTabSlide === 'tips') {
                return `
                    <div class="space-y-3 animate-fadeIn">
                        <span class="text-xs font-extrabold text-amber-400 uppercase tracking-wider block">⚡ Tips & Trik Cepat Soal Bimbel:</span>
                        <div class="bg-amber-500/10 border-l-4 border-amber-500 p-4 rounded-r-2xl text-amber-200 text-xs sm:text-sm leading-relaxed">
                            ${bab.tips}
                        </div>
                    </div>
                `;
            } else if (state.currentTabSlide === 'soal') {
                return `
                    <div class="space-y-3 animate-fadeIn">
                        <span class="text-xs font-extrabold text-emerald-400 uppercase tracking-wider block">📝 Bedah Contoh Soal HOTS & Solusi Terperinci:</span>
                        <div class="bg-slate-900 border border-slate-800 p-4 sm:p-5 rounded-2xl text-slate-200 leading-relaxed">
                            ${bab.contohSoal}
                        </div>
                    </div>
                `;
            }
        }

        function changeSlideTab(tabKey) {
            state.currentTabSlide = tabKey;
            renderSlideBab();
        }

        function jumpToBabSlide(index) {
            state.currentBabIdx = index;
            state.currentTabSlide = 'konsep';
            renderSlideBab();
        }

        function nextBabSlide() {
            const materiList = db.materiDetails[state.selectedSubject] || [];
            if (state.currentBabIdx < materiList.length - 1) {
                state.currentBabIdx++;
                state.currentTabSlide = 'konsep';
                renderSlideBab();
            }
        }

        function prevBabSlide() {
            if (state.currentBabIdx > 0) {
                state.currentBabIdx--;
                state.currentTabSlide = 'konsep';
                renderSlideBab();
            }
        }

        // Render Kalkulator Sains & Matematika Screen
        function renderKalkulatorScreen() {
            return `
                <div class="mb-8">
                    <h1 class="text-3xl font-black text-white tracking-tight">Kalkulator AI Matematika & Sains</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Hitung otomatis persamaan kuadrat, invers/determinan matriks, kombinatorika, deret tak hingga, pH kimia, dan kinematics.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    
                    <!-- 1. Kalkulator Persamaan Kuadrat -->
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

                    <!-- 2. Kalkulator Determinan & Invers Matriks 2x2 -->
                    <div class="glass-card border border-cyan-500/30 p-6 rounded-3xl shadow-xl">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="p-2.5 rounded-xl bg-cyan-500/20 text-cyan-300">
                                <i data-lucide="grid" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-extrabold text-white text-sm">Determinan & Invers Matriks</h3>
                        </div>
                        <div class="grid grid-cols-2 gap-2 mb-4 max-w-xs mx-auto">
                            <input type="number" id="mat-a" placeholder="a" value="3" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="mat-b" placeholder="b" value="2" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="mat-c" placeholder="c" value="1" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="mat-d" placeholder="d" value="4" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                        </div>
                        <button onclick="calculateMatrix()" class="w-full py-2 bg-cyan-600 hover:bg-cyan-500 text-white font-extrabold text-xs rounded-xl transition mb-4 shadow-md">
                            Hitung Invers & Det
                        </button>
                        <div id="calc-mat-res" class="bg-slate-950/80 border border-slate-800 p-3 rounded-xl text-xs font-mono text-cyan-300">
                            Hasil matriks muncul di sini...
                        </div>
                    </div>

                    <!-- 3. Kalkulator Permutasi & Kombinasi -->
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
                            Hasil kombinasi muncul di sini...
                        </div>
                    </div>

                    <!-- 4. Deret Geometri Tak Hingga -->
                    <div class="glass-card border border-amber-500/30 p-6 rounded-3xl shadow-xl">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="p-2.5 rounded-xl bg-amber-500/20 text-amber-300">
                                <i data-lucide="infinity" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-extrabold text-white text-sm">Deret Geometri Tak Hingga (S_∞)</h3>
                        </div>
                        <div class="grid grid-cols-2 gap-2 mb-4">
                            <input type="number" id="geo-a" placeholder="a (suku awal)" value="12" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="text" id="geo-r" placeholder="r (rasio < 1)" value="0.333" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                        </div>
                        <button onclick="calculateGeoInfin()" class="w-full py-2 bg-amber-600 hover:bg-amber-500 text-white font-extrabold text-xs rounded-xl transition mb-4 shadow-md">
                            Hitung Jumlah Tak Hingga
                        </button>
                        <div id="calc-geo-res" class="bg-slate-950/80 border border-slate-800 p-3 rounded-xl text-xs font-mono text-amber-300">
                            Hasil deret muncul di sini...
                        </div>
                    </div>

                    <!-- 5. Kalkulator Kimia: pH Larutan Asam / Basa -->
                    <div class="glass-card border border-pink-500/30 p-6 rounded-3xl shadow-xl">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="p-2.5 rounded-xl bg-pink-500/20 text-pink-300">
                                <i data-lucide="flask-conical" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-extrabold text-white text-sm">Hitung pH Asam Kuat (pH = -log[H⁺])</h3>
                        </div>
                        <div class="grid grid-cols-2 gap-2 mb-4">
                            <input type="number" step="0.001" id="chem-m" placeholder="Molaritas (M)" value="0.01" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="chem-val" placeholder="Valensi Asam" value="1" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                        </div>
                        <button onclick="calculatePH()" class="w-full py-2 bg-pink-600 hover:bg-pink-500 text-white font-extrabold text-xs rounded-xl transition mb-4 shadow-md">
                            Hitung Konsentrasi & pH
                        </button>
                        <div id="calc-ph-res" class="bg-slate-950/80 border border-slate-800 p-3 rounded-xl text-xs font-mono text-pink-300">
                            Hasil pH muncul di sini...
                        </div>
                    </div>

                    <!-- 6. Kalkulator Fisika: Tinggi Maksimum Gerak Parabola -->
                    <div class="glass-card border border-blue-500/30 p-6 rounded-3xl shadow-xl">
                        <div class="flex items-center gap-3 mb-4">
                            <div class="p-2.5 rounded-xl bg-blue-500/20 text-blue-300">
                                <i data-lucide="zap" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-extrabold text-white text-sm">Tinggi Maksimum Gerak Parabola</h3>
                        </div>
                        <div class="grid grid-cols-2 gap-2 mb-4">
                            <input type="number" id="phys-v0" placeholder="v₀ (m/s)" value="20" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                            <input type="number" id="phys-angle" placeholder="Sudut θ (°)" value="30" class="bg-slate-950 border border-slate-700 rounded-xl p-2 text-center text-xs font-mono text-white">
                        </div>
                        <button onclick="calculateParabola()" class="w-full py-2 bg-blue-600 hover:bg-blue-500 text-white font-extrabold text-xs rounded-xl transition mb-4 shadow-md">
                            Hitung H_max & X_max
                        </button>
                        <div id="calc-phys-res" class="bg-slate-950/80 border border-slate-800 p-3 rounded-xl text-xs font-mono text-blue-300">
                            Hasil ketinggian muncul di sini...
                        </div>
                    </div>

                </div>
            `;
        }

        // Calculation Logic
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
                text += `Akar Real Beda: x₁ = ${x1.toFixed(2)}, x₂ = ${x2.toFixed(2)}`;
            } else if (D === 0) {
                const x = -b / (2 * a);
                text += `Akar Kembar: x₁ = x₂ = ${x.toFixed(2)}`;
            } else {
                text += `Akar Imajiner (D < 0)`;
            }
            res.innerHTML = text;
        }

        function calculateMatrix() {
            const a = parseFloat(document.getElementById('mat-a').value);
            const b = parseFloat(document.getElementById('mat-b').value);
            const c = parseFloat(document.getElementById('mat-c').value);
            const d = parseFloat(document.getElementById('mat-d').value);
            const res = document.getElementById('calc-mat-res');

            const det = a * d - b * c;
            let text = `det(A) = ${det}<br>`;

            if (det === 0) {
                text += `Matriks Singular (Tidak berpangkat/invers).`;
            } else {
                text += `A⁻¹ = [[ ${(d/det).toFixed(2)}, ${(-b/det).toFixed(2)} ], [ ${(-c/det).toFixed(2)}, ${(a/det).toFixed(2)} ]]`;
            }
            res.innerHTML = text;
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

        function calculateGeoInfin() {
            const a = parseFloat(document.getElementById('geo-a').value);
            let r_str = document.getElementById('geo-r').value;
            let r = parseFloat(r_str);

            if (r_str.includes('/')) {
                const parts = r_str.split('/');
                r = parseFloat(parts[0]) / parseFloat(parts[1]);
            }

            const res = document.getElementById('calc-geo-res');

            if (Math.abs(r) >= 1) {
                res.innerHTML = "Deret Divergen (|r| ≥ 1).";
                return;
            }

            const S_inf = a / (1 - r);
            res.innerHTML = `r = ${r.toFixed(3)}<br>Jumlah S_∞ = ${S_inf.toFixed(2)}`;
        }

        function calculatePH() {
            const m = parseFloat(document.getElementById('chem-m').value);
            const val = parseFloat(document.getElementById('chem-val').value);
            const res = document.getElementById('calc-ph-res');

            if (isNaN(m) || isNaN(val) || m <= 0) {
                res.innerHTML = "Masukkan molaritas positif!";
                return;
            }

            const h_plus = m * val;
            const ph = -Math.log10(h_plus);
            res.innerHTML = `[H⁺] = ${h_plus.toExponential(2)} M<br><strong>pH Larutan = ${ph.toFixed(2)}</strong>`;
        }

        function calculateParabola() {
            const v0 = parseFloat(document.getElementById('phys-v0').value);
            const angleDeg = parseFloat(document.getElementById('phys-angle').value);
            const res = document.getElementById('calc-phys-res');

            if (isNaN(v0) || isNaN(angleDeg)) {
                res.innerHTML = "Masukkan nilai valid!";
                return;
            }

            const g = 10;
            const rad = (angleDeg * Math.PI) / 180;
            const sinVal = Math.sin(rad);
            const sin2Val = Math.sin(2 * rad);

            const H_max = (v0 * v0 * sinVal * sinVal) / (2 * g);
            const X_max = (v0 * v0 * sin2Val) / g;

            res.innerHTML = `H_max = ${H_max.toFixed(2)} meter<br>Jarak Terjauh X_max = ${X_max.toFixed(2)} meter`;
        }

        // Render UTBK Simulation Screen
        function renderUTBKScreen() {
            return `
                <div class="mb-8">
                    <h1 class="text-3xl font-black text-white tracking-tight">Simulasi TKA & UTBK SNBT 2026</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Uji pemahaman dengan timer real-time interaktif, penilaian otomatis, & pembahasan terperinci.</p>
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

                    <div class="glass-card border border-slate-800 p-6 rounded-3xl flex flex-col justify-between shadow-xl">
                        <div>
                            <div class="w-12 h-12 rounded-2xl bg-cyan-500/20 border border-cyan-500/30 text-cyan-400 flex items-center justify-center mb-4 font-black">
                                <i data-lucide="brain" class="w-6 h-6"></i>
                            </div>
                            <span class="text-[10px] uppercase font-extrabold text-cyan-400 bg-cyan-500/10 px-2.5 py-1 rounded-md border border-cyan-500/20">SNBT Standard</span>
                            <h3 class="text-xl font-extrabold text-white mt-3 mb-1">UTBK - Penalaran Umum (PU)</h3>
                            <p class="text-slate-400 text-xs mb-6 leading-relaxed">Uji logika deduktif, silogisme, pola barisan, & kesimpulan paragraf.</p>
                        </div>
                        <button onclick="startSimulasi('utbk-pu')" class="w-full py-3.5 bg-cyan-500 hover:bg-cyan-400 text-slate-950 font-black text-xs rounded-xl transition shadow-lg shadow-cyan-500/20 flex items-center justify-center gap-2">
                            <i data-lucide="play" class="w-4 h-4 fill-current"></i> Mulai Tes (10 Menit)
                        </button>
                    </div>

                    <div class="glass-card border border-slate-800 p-6 rounded-3xl flex flex-col justify-between shadow-xl">
                        <div>
                            <div class="w-12 h-12 rounded-2xl bg-indigo-500/20 border border-indigo-500/30 text-indigo-400 flex items-center justify-center mb-4 font-black">
                                <i data-lucide="zap" class="w-6 h-6"></i>
                            </div>
                            <span class="text-[10px] uppercase font-extrabold text-indigo-400 bg-indigo-500/10 px-2.5 py-1 rounded-md border border-indigo-500/20">TKA High Level</span>
                            <h3 class="text-xl font-extrabold text-white mt-3 mb-1">TKA Saintek - Fisika, Kimia & Bio</h3>
                            <p class="text-slate-400 text-xs mb-6 leading-relaxed">Uji penalaran sains lanjutan: mekanika, sel elektrolisis, & genetika.</p>
                        </div>
                        <button onclick="startSimulasi('tka-saintek')" class="w-full py-3.5 bg-indigo-600 hover:bg-indigo-500 text-white font-black text-xs rounded-xl transition shadow-lg shadow-indigo-600/20 flex items-center justify-center gap-2">
                            <i data-lucide="play" class="w-4 h-4 fill-current"></i> Mulai Tes (10 Menit)
                        </button>
                    </div>

                    <div class="glass-card border border-slate-800 p-6 rounded-3xl flex flex-col justify-between shadow-xl">
                        <div>
                            <div class="w-12 h-12 rounded-2xl bg-rose-500/20 border border-rose-500/30 text-rose-400 flex items-center justify-center mb-4 font-black">
                                <i data-lucide="users" class="w-6 h-6"></i>
                            </div>
                            <span class="text-[10px] uppercase font-extrabold text-rose-400 bg-rose-500/10 px-2.5 py-1 rounded-md border border-rose-500/20">TKA High Level</span>
                            <h3 class="text-xl font-extrabold text-white mt-3 mb-1">TKA Soshum - Eko, Sos & Geo</h3>
                            <p class="text-slate-400 text-xs mb-6 leading-relaxed">Uji pemahaman ekonomi ceiling price, sosiologi empiris, & prinsip geografi.</p>
                        </div>
                        <button onclick="startSimulasi('tka-soshum')" class="w-full py-3.5 bg-rose-600 hover:bg-rose-500 text-white font-black text-xs rounded-xl transition shadow-lg shadow-rose-600/20 flex items-center justify-center gap-2">
                            <i data-lucide="play" class="w-4 h-4 fill-current"></i> Mulai Tes (10 Menit)
                        </button>
                    </div>
                </div>
            `;
        }

        // Active Simulation Engine with Timer
        function startSimulasi(simKey) {
            state.activeSimKey = simKey;
            state.currentSimAnswers = {};
            const currentSim = db.simulasiBank[simKey];
            
            state.simTimeLeft = (currentSim.durasiMinutes || 10) * 60;

            const app = document.getElementById('app-content');
            app.innerHTML = `
                <div class="max-w-3xl mx-auto glass-card border border-purple-500/30 p-6 sm:p-8 rounded-3xl shadow-2xl relative">
                    
                    <!-- Timer Header -->
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
                    alert('Waktu pengerjaan telah habis! Jawaban Anda akan tersimpan secara otomatis.');
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
            localStorage.setItem('nihiluxxy_attempts', JSON.stringify(state.attempts));

            switchView('riwayat');
            openDetailRiwayat(state.attempts.length - 1);
        }

        // Render Interactive Flashcard View
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
                    <span class="text-xs font-extrabold uppercase tracking-widest text-emerald-400 bg-emerald-500/10 px-3 py-1 rounded-full border border-emerald-500/20 mb-2 inline-block">Flashcards Pintar</span>
                    <h1 class="text-3xl font-black text-white tracking-tight">Latihan Cepat Hafalan & Konsep</h1>
                    <p class="text-slate-400 text-xs sm:text-sm mt-1">Uji ingatan intuitif Anda sebelum menghadapi ujian asli.</p>

                    <!-- Filter Chips -->
                    <div class="flex flex-wrap justify-center gap-2 mt-4 text-xs font-semibold">
                        <button onclick="setFlashcardFilter('semua')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'semua' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Semua</button>
                        <button onclick="setFlashcardFilter('matematika')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'matematika' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Matematika</button>
                        <button onclick="setFlashcardFilter('fisika')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'fisika' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Fisika</button>
                        <button onclick="setFlashcardFilter('kimia')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'kimia' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Kimia</button>
                        <button onclick="setFlashcardFilter('biologi')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'biologi' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Biologi</button>
                        <button onclick="setFlashcardFilter('geografi')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'geografi' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Geografi</button>
                        <button onclick="setFlashcardFilter('ekonomi')" class="px-3.5 py-1.5 rounded-xl transition ${state.flashcardFilter === 'ekonomi' ? 'bg-purple-600 text-white' : 'bg-slate-900 text-slate-400 border border-slate-800 hover:text-white'}">Ekonomi</button>
                    </div>
                </div>

                <div class="max-w-xl mx-auto">
                    <div id="flashcard-box" onclick="flipFlashcard()" class="glass-card border border-purple-500/40 rounded-3xl p-8 sm:p-12 min-h-[280px] flex flex-col justify-between items-center text-center cursor-pointer shadow-2xl transition-all duration-300 transform hover:scale-[1.02]">
                        <span class="text-[10px] font-black uppercase text-purple-400 font-mono tracking-widest">${card.mapel} • Klik Kartu Untuk Membalik</span>
                        
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
                        <p class="text-slate-400 text-xs sm:text-sm mt-1">Daftar evaluasi simulasi dan pembahasan akurat Anda.</p>
                    </div>
                    <div class="glass-card border border-slate-800 rounded-3xl p-12 text-center text-slate-500 shadow-xl">
                        <div class="w-16 h-16 rounded-full bg-slate-900 border border-slate-800 flex items-center justify-center mx-auto mb-4 text-slate-600">
                            <i data-lucide="history" class="w-8 h-8"></i>
                        </div>
                        <p class="text-base font-extrabold text-slate-300">Belum Ada Riwayat Tersimpan</p>
                        <p class="text-xs text-slate-500 mt-1 mb-6">Selesaikan simulasi TKA/UTBK untuk mencatat riwayat jawaban akurat Anda di sini.</p>
                        <button onclick="switchView('utbk')" class="px-6 py-3 bg-purple-600 hover:bg-purple-500 text-white font-extrabold text-xs rounded-xl transition shadow-lg shadow-purple-600/25">
                            Mulai Simulasi Sekarang
                        </button>
                    </div>
                `;
            }

            return `
                <div class="mb-8 flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                    <div>
                        <h1 class="text-3xl font-black text-white tracking-tight">Riwayat & Pembahasan Akurat</h1>
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
                                <span class="text-purple-300 font-extrabold block mb-1">📘 Pembahasan Akurat & Langkah Penyelesaian:</span>
                                ${d.solusi}
                            </div>

                            <button onclick="askAiAboutQuestion('${d.pertanyaan.replace(/'/g, "\\'")}')" class="w-full py-2 bg-slate-950 hover:bg-purple-950/50 border border-purple-500/30 text-purple-300 text-xs font-bold rounded-xl transition flex items-center justify-center gap-1.5">
                                <i data-lucide="bot" class="w-3.5 h-3.5"></i> Jelaskan Langkah Ini Lebih Detail via AI
                            </button>
                        </div>
                    `).join('')}
                </div>
            `;
            lucide.createIcons();
        }

        function clearHistory() {
            if (confirm('Apakah Anda yakin ingin menghapus seluruh riwayat pengerjaan simulasi?')) {
                state.attempts = [];
                localStorage.removeItem('nihiluxxy_attempts');
                switchView('riwayat');
            }
        }

        // ==========================================
        // ENHANCED NIHILUXXY AI TUTOR ENGINE v6.5
        // ==========================================
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
            injectAiPrompt(`Tolong berikan penjelasan super mendalam, analisis konsep, dan rumus praktis untuk topik: ${topicTitle}`);
        }

        function askAiAboutSubject(subjectName) {
            toggleAiModal();
            injectAiPrompt(`Beri saya ringkasan peta konsep terpenting yang sering keluar di UTBK SNBT untuk mata pelajaran: ${subjectName}`);
        }

        function askAiAboutQuestion(qText) {
            toggleAiModal();
            injectAiPrompt(`Tolong bedah dan jelaskan langkah demi langkah penyelesaian dari soal berikut: "${qText}"`);
        }

        function sendAiQuery() {
            const input = document.getElementById('ai-user-input');
            const chatBody = document.getElementById('ai-chat-body');
            if (!input || !chatBody) return;

            const text = input.value.trim();
            if (!text) return;

            // Render User Bubble
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

            // Render AI Loading State
            const aiBubble = document.createElement('div');
            aiBubble.className = "flex gap-3 items-start";
            const loadingId = 'ai-loading-' + Date.now();
            aiBubble.innerHTML = `
                <div class="w-8 h-8 rounded-xl gradient-accent flex-shrink-0 flex items-center justify-center text-white text-xs font-bold">AI</div>
                <div id="${loadingId}" class="bg-slate-900/90 border border-purple-500/30 p-4 rounded-2xl text-xs sm:text-sm text-slate-300 max-w-xl leading-relaxed shadow-lg flex items-center gap-2">
                    <i data-lucide="loader-2" class="w-4 h-4 text-purple-400 animate-spin"></i>
                    <span>Nihiluxxy AI v6.5 sedang memproses & menganalisis pertanyaan...</span>
                </div>
            `;
            chatBody.appendChild(aiBubble);
            lucide.createIcons();
            chatBody.scrollTop = chatBody.scrollHeight;

            // Multi-Subject Smart Response Engine
            setTimeout(() => {
                const target = document.getElementById(loadingId);
                if (target) {
                    const responseHTML = generateSmartAiResponse(text);
                    target.innerHTML = responseHTML;
                    chatBody.scrollTop = chatBody.scrollHeight;
                }
            }, 1000);
        }

        function generateSmartAiResponse(query) {
            const q = query.toLowerCase();

            // VEKTOR & PROYEKSI
            if (q.includes('vektor') || q.includes('proyeksi') || q.includes('ortogonal')) {
                return `
                    <div class="space-y-3">
                        <span class="text-blue-400 font-extrabold block text-xs">➡️ Nihiluxxy AI Multi-Solver - Vektor:</span>
                        <p><strong>1. Perkalian Titik (Dot Product):</strong> u · v = u₁v₁ + u₂v₂ + u₃v₃ = |u||v| cos θ</p>
                        <p><strong>2. Syarat Saling Tegak Lurus:</strong> u · v = 0</p>
                        <p><strong>3. Proyeksi Vektor Ortogonal u pada v:</strong></p>
                        <div class="bg-slate-950 p-3 rounded-xl border border-slate-800 text-xs font-mono text-purple-300 text-center">
                            p = [ (u · v) / |v|² ] · v
                        </div>
                    </div>
                `;
            }
            // MATRIKS & INVERS
            else if (q.includes('matriks') || q.includes('determinan') || q.includes('invers')) {
                return `
                    <div class="space-y-3">
                        <span class="text-pink-400 font-extrabold block text-xs">📊 Nihiluxxy AI - Matriks & Invers:</span>
                        <p><strong>Invers Matriks 2x2:</strong> Jika A = [[a,b],[c,d]], maka A⁻¹ = (1/det A) · [[d,-b],[-c,a]] dengan det A = ad - bc.</p>
                        <p><strong>Sifat Utama Determinan UTBK:</strong></p>
                        <ul class="list-disc list-inside space-y-1 text-xs text-slate-300 font-mono">
                            <li>det(A · B) = det(A) · det(B)</li>
                            <li>det(A⁻¹) = 1 / det(A)</li>
                            <li>det(k · A_n×n) = kⁿ · det(A)</li>
                        </ul>
                    </div>
                `;
            }
            // GEOGRAFI
            else if (q.includes('geografi') || q.includes('peta') || q.includes('indrajaja') || q.includes('litosfer')) {
                return `
                    <div class="space-y-3">
                        <span class="text-emerald-400 font-extrabold block text-xs">🌍 Nihiluxxy AI - Geografi & SIG:</span>
                        <p><strong>1. Skala Peta:</strong> Skala = Jarak Peta / Jarak Sebenarnya</p>
                        <p><strong>2. Kontur Interval (CI):</strong> CI = (1 / 2.000) × Penyebut Skala Utama</p>
                        <p><strong>3. Teori Titik Henti (Break-Off Point):</strong> D_TH = d_AB / (1 + √(P_B / P_A)) dengan P_A < P_B.</p>
                    </div>
                `;
            }
            // KIMIA & LAJU REAKSI
            else if (q.includes('kimia') || q.includes('laju') || q.includes('buffer') || q.includes('ph')) {
                return `
                    <div class="space-y-3">
                        <span class="text-pink-400 font-extrabold block text-xs">🧪 Nihiluxxy AI - Kimia & Laju Reaksi:</span>
                        <p><strong>1. Persamaan Laju Reaksi:</strong> V = k [A]ᵐ [B]ⁿ</p>
                        <p><strong>2. pH Asam Kuat:</strong> [H⁺] = Molaritas × Valensi Asam ⇒ pH = -log[H⁺]</p>
                        <p><strong>3. Buffer Asam:</strong> [H⁺] = K_a × (mol Asam Lemah / mol Basa Konjugasi)</p>
                    </div>
                `;
            }
            // FALLBACK GENERAL
            else {
                return `
                    <div class="space-y-2">
                        <span class="text-purple-300 font-extrabold block text-xs">🤖 Analisis AI Nihiluxxy v6.5:</span>
                        <p>Terima kasih atas pertanyaanmu mengenai: <em>"${query}"</em>.</p>
                        <p>Untuk membedah tipe soal ini dengan tepat, petakan variabel ke rumus utamanya dan eliminasi pilihan jawaban yang tidak logis. Kamu juga bisa menggunakan fitur <strong>Kalkulator AI Math & Sains</strong> di menu navigasi!</p>
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
