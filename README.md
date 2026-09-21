<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FlyStudy - Aplikasi Belajar SMA K13, Kurikulum Merdeka & UTBK</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Plus Jakarta Sans -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        body { font-family: 'Plus Jakarta Sans', sans-serif; }
        .gradient-bg { background: linear-gradient(135deg, #4F46E5 0%, #7C3AED 100%); }
        .glass-card { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(10px); }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col">

    <!-- Header / Navbar -->
    <header class="sticky top-0 z-50 glass-card border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <div class="flex items-center gap-3 cursor-pointer" onclick="switchView('home')">
                <div class="w-10 h-10 rounded-xl gradient-bg flex items-center justify-center text-white font-bold text-xl shadow-lg shadow-indigo-500/30">
                    <i data-lucide="rocket" class="w-6 h-6"></i>
                </div>
                <span class="text-2xl font-extrabold bg-clip-text text-transparent gradient-bg">FlyStudy</span>
            </div>
            <nav class="hidden md:flex items-center gap-6 font-semibold text-slate-600 text-sm">
                <button onclick="switchView('materi')" class="hover:text-indigo-600 transition">Materi Sekolah</button>
                <button onclick="switchView('utbk')" class="hover:text-indigo-600 transition flex items-center gap-1">
                    <span>UTBK & TKA</span>
                    <span class="bg-red-500 text-white text-[10px] px-1.5 py-0.5 rounded-full uppercase tracking-wider">New</span>
                </button>
                <button onclick="switchView('tryout')" class="hover:text-indigo-600 transition">Simulasi UTBK</button>
            </nav>
            <div class="flex items-center gap-3">
                <div class="hidden sm:flex flex-col text-right">
                    <span class="text-xs text-slate-400 font-semibold">Selamat Datang,</span>
                    <span class="text-sm font-bold text-slate-700">Siswa SMA</span>
                </div>
                <div class="w-9 h-9 rounded-full bg-indigo-100 text-indigo-700 font-bold flex items-center justify-center border border-indigo-200">
                    S
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content Dynamic Container -->
    <main id="app-content" class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <!-- Content will be rendered by JS -->
    </main>

    <!-- Navigation Bar for Mobile -->
    <div class="md:hidden fixed bottom-0 left-0 right-0 glass-card border-t border-slate-200 flex justify-around py-3 text-xs font-semibold text-slate-600 z-50">
        <button onclick="switchView('home')" class="flex flex-col items-center gap-1">
            <i data-lucide="home" class="w-5 h-5 text-indigo-600"></i> Home
        </button>
        <button onclick="switchView('materi')" class="flex flex-col items-center gap-1">
            <i data-lucide="book-open" class="w-5 h-5"></i> Materi
        </button>
        <button onclick="switchView('utbk')" class="flex flex-col items-center gap-1">
            <i data-lucide="award" class="w-5 h-5"></i> UTBK/TKA
        </button>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        // Database Materi & Latihan Soal
        const dataApp = {
            kurikulum: ['Kurikulum Merdeka (Fase E/F)', 'Kurikulum 2013 (K13 Revisi)'],
            kelas: ['Kelas 10', 'Kelas 11', 'Kelas 12'],
            mapel: [
                { id: 'matematika', nama: 'Matematika Umum & Lanjut', icon: 'calculator', color: 'bg-blue-500' },
                { id: 'fisika', nama: 'Fisika', icon: 'zap', color: 'bg-indigo-500' },
                { id: 'kimia', nama: 'Kimia', icon: 'flask-conical', color: 'bg-purple-500' },
                { id: 'biologi', nama: 'Biologi', icon: 'dna', color: 'bg-emerald-500' },
                { id: 'ekonomi', nama: 'Ekonomi & Akuntansi', icon: 'trending-up', color: 'bg-amber-500' },
                { id: 'sosiologi', nama: 'Sosiologi', icon: 'users', color: 'bg-rose-500' },
                { id: 'geografi', nama: 'Geografi', icon: 'globe', color: 'bg-teal-500' },
                { id: 'sejarah', nama: 'Sejarah Indonesia & Tingkat Lanjut', icon: 'landmark', color: 'bg-orange-500' },
                { id: 'bing', nama: 'Bahasa Inggris', icon: 'languages', color: 'bg-cyan-500' },
                { id: 'bindo', nama: 'Bahasa Indonesia', icon: 'book-text', color: 'bg-red-500' }
            ],
            utbkSubtes: [
                { id: 'pu', nama: 'Penalaran Umum (PU)', desc: 'Penalaran Induktif, Deduktif, & Kuantitatif' },
                { id: 'pbm', nama: 'Pemahaman Bacaan & Menulis (PBM)', desc: 'Ejaan, Kalimat Efektif, Kepaduan Wacana' },
                { id: 'ppu', nama: 'Pengetahuan & Pemahaman Umum (PPU)', desc: 'Makna Kata, Ide Pokok, & Hubungan Paragraf' },
                { id: 'pk', nama: 'Pengetahuan Kuantitatif (PK)', desc: 'Aljabar, Geometri, Peluang, & Statistika' },
                { id: 'literasi-indo', nama: 'Literasi Bahasa Indonesia', desc: 'Pemahaman Teks Sastra & Saintek/Soshum' },
                { id: 'literasi-ing', nama: 'Literasi Bahasa Inggris', desc: 'Main Idea, Inference, Tone & Purpose' },
                { id: 'pm', nama: 'Penalaran Matematika (PM)', desc: 'Pemodelan Soal Kontekstual Standar AKM' },
                { id: 'tka-saintek', nama: 'TKA Saintek (Mat, Fis, Kim, Bio)', desc: 'Soal Penguasaan Konsep Level Tinggi (HOTS)' },
                { id: 'tka-soshum', nama: 'TKA Soshum (Eko, Geo, Sos, Sej)', desc: 'Analisis Fenomena Sosial & Aplikasi Konsep' }
            ]
        };

        // Render Home Screen
        function renderHome() {
            return `
                <!-- Banner Hero -->
                <div class="gradient-bg rounded-3xl p-8 sm:p-12 text-white shadow-xl mb-10 relative overflow-hidden">
                    <div class="relative z-10 max-w-2xl">
                        <span class="inline-block px-3 py-1 bg-white/20 rounded-full text-xs font-semibold mb-4 backdrop-blur-md">
                            ✨ Update Terlengkap K13, Kurikulum Merdeka & UTBK SNBT
                        </span>
                        <h1 class="text-3xl sm:text-5xl font-extrabold tracking-tight mb-4 leading-tight">
                            Terbang Lebih Tinggi Bersama FlyStudy! 🚀
                        </h1>
                        <p class="text-indigo-100 text-sm sm:text-base mb-6 leading-relaxed">
                            Akses ringkasan materi SMA Kelas 10-12 super jelas, video pembahasan, serta ribuan latihan soal TKA & UTBK SNBT terbaru dengan format HOTS lengkap.
                        </p>
                        <div class="flex flex-wrap gap-4">
                            <button onclick="switchView('materi')" class="bg-white text-indigo-600 font-bold px-6 py-3 rounded-xl shadow-lg hover:bg-slate-100 transition text-sm">
                                Mulai Belajar Materi
                            </button>
                            <button onclick="switchView('utbk')" class="bg-indigo-900/40 border border-white/30 text-white font-bold px-6 py-3 rounded-xl hover:bg-indigo-900/60 transition text-sm backdrop-blur-md">
                                Latihan UTBK / TKA
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Kurikulum & Pilihan Kelas -->
                <div class="mb-10">
                    <h2 class="text-xl font-bold text-slate-800 mb-4 flex items-center gap-2">
                        <i data-lucide="layers" class="text-indigo-600"></i> Pilih Jenjang & Kurikulum
                    </h2>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        ${['10', '11', '12'].map(kelas => `
                            <div class="bg-white rounded-2xl p-6 border border-slate-200 shadow-sm hover:shadow-md transition">
                                <span class="text-xs font-extrabold uppercase text-indigo-600 tracking-wider">SMA Kelas ${kelas}</span>
                                <h3 class="text-lg font-bold mt-1 text-slate-800">Paket Belajar Lengkap</h3>
                                <p class="text-slate-500 text-xs mt-2 mb-4">Tersedia Kurikulum 2013 & Kurikulum Merdeka (Fase E/F)</p>
                                <button onclick="switchView('materi')" class="w-full py-2.5 bg-slate-100 hover:bg-indigo-50 text-indigo-600 font-semibold rounded-xl text-sm transition">
                                    Lihat Mata Pelajaran
                                </button>
                            </div>
                        `).join('')}
                    </div>
                </div>

                <!-- Modul UTBK SNBT & TKA -->
                <div>
                    <div class="flex justify-between items-center mb-4">
                        <h2 class="text-xl font-bold text-slate-800 flex items-center gap-2">
                            <i data-lucide="target" class="text-indigo-600"></i> Persiapan UTBK SNBT & TKA Terupdate
                        </h2>
                    </div>
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
                        ${dataApp.utbkSubtes.map(subtes => `
                            <div class="bg-white p-5 rounded-2xl border border-slate-200 shadow-sm hover:border-indigo-500 transition cursor-pointer" onclick="openSimulasi('${subtes.nama}')">
                                <div class="flex items-start justify-between mb-3">
                                    <div class="p-3 rounded-xl bg-indigo-50 text-indigo-600">
                                        <i data-lucide="file-text" class="w-6 h-6"></i>
                                    </div>
                                    <span class="text-[11px] bg-emerald-100 text-emerald-700 font-semibold px-2.5 py-0.5 rounded-full">HOTS 2026</span>
                                </div>
                                <h4 class="font-bold text-slate-800 mb-1">${subtes.nama}</h4>
                                <p class="text-xs text-slate-500 mb-4">${subtes.desc}</p>
                                <div class="flex justify-between items-center text-xs font-semibold text-indigo-600">
                                    <span>Latihan Soal & Pembahasan</span>
                                    <i data-lucide="chevron-right" class="w-4 h-4"></i>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                </div>
            `;
        }

        // Render Screen Materi
        function renderMateri() {
            return `
                <div class="mb-6">
                    <h1 class="text-2xl font-bold text-slate-800">Materi Pembelajaran SMA</h1>
                    <p class="text-slate-500 text-sm">Pilih mata pelajaran untuk melihat materi Kurikulum Merdeka atau K13</p>
                </div>

                <!-- Filter Kurikulum -->
                <div class="flex gap-3 mb-6 overflow-x-auto pb-2">
                    <button class="px-4 py-2 bg-indigo-600 text-white rounded-xl text-xs font-semibold shadow-sm">Semua Kurikulum</button>
                    <button class="px-4 py-2 bg-white text-slate-600 border border-slate-200 rounded-xl text-xs font-semibold hover:bg-slate-50">Kurikulum Merdeka</button>
                    <button class="px-4 py-2 bg-white text-slate-600 border border-slate-200 rounded-xl text-xs font-semibold hover:bg-slate-50">Kurikulum 2013 (K13)</button>
                </div>

                <!-- Grid Mapel -->
                <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-4">
                    ${dataApp.mapel.map(m => `
                        <div class="bg-white p-5 rounded-2xl border border-slate-200 text-center hover:shadow-md transition cursor-pointer" onclick="openDetailMateri('${m.nama}')">
                            <div class="w-12 h-12 mx-auto rounded-xl ${m.color} text-white flex items-center justify-center mb-3 shadow-md">
                                <i data-lucide="${m.icon}"></i>
                            </div>
                            <h3 class="font-bold text-sm text-slate-800 mb-1">${m.nama}</h3>
                            <span class="text-[11px] text-slate-400">Kelas 10 - 12</span>
                        </div>
                    `).join('')}
                </div>
            `;
        }

        // Render Screen UTBK / TKA
        function renderUTBK() {
            return `
                <div class="mb-6">
                    <h1 class="text-2xl font-bold text-slate-800">Bank Soal & Drill UTBK SNBT / TKA</h1>
                    <p class="text-slate-500 text-sm">Sistem tes adaptsif dengan tipe soal Isian, Pilihan Ganda Kompleks, & TPS</p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    ${dataApp.utbkSubtes.map(item => `
                        <div class="bg-white rounded-2xl p-6 border border-slate-200 shadow-sm flex justify-between items-center">
                            <div>
                                <span class="text-[10px] font-bold uppercase tracking-wider text-indigo-600 bg-indigo-50 px-2 py-0.5 rounded">Terupdate</span>
                                <h3 class="font-bold text-slate-800 text-lg mt-1">${item.nama}</h3>
                                <p class="text-xs text-slate-500 mt-1">${item.desc}</p>
                            </div>
                            <button onclick="openSimulasi('${item.nama}')" class="px-4 py-2 bg-indigo-600 hover:bg-indigo-700 text-white font-semibold rounded-xl text-xs transition">
                                Kerjakan
                            </button>
                        </div>
                    `).join('')}
                </div>
            `;
        }

        // Modal / Detail View Handlers
        function openDetailMateri(mapel) {
            const app = document.getElementById('app-content');
            app.innerHTML = `
                <div class="mb-6 flex items-center gap-4">
                    <button onclick="switchView('materi')" class="p-2 bg-white rounded-xl border border-slate-200 hover:bg-slate-50">
                        <i data-lucide="arrow-left" class="w-5 h-5"></i>
                    </button>
                    <div>
                        <h1 class="text-2xl font-bold text-slate-800">${mapel}</h1>
                        <p class="text-xs text-slate-500">Rangkuman Materi & Modul Interaktif</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <!-- Sidebar Bab -->
                    <div class="bg-white p-4 rounded-2xl border border-slate-200 h-fit">
                        <h3 class="font-bold text-sm text-slate-700 mb-3">Daftar Bab & Topik</h3>
                        <div class="space-y-2 text-sm">
                            <div class="p-3 bg-indigo-50 text-indigo-700 font-semibold rounded-xl cursor-pointer">Bab 1: Konsep Dasar & Pemodelan</div>
                            <div class="p-3 hover:bg-slate-50 rounded-xl cursor-pointer text-slate-600">Bab 2: Analisis & Penerapan HOTS</div>
                            <div class="p-3 hover:bg-slate-50 rounded-xl cursor-pointer text-slate-600">Bab 3: Evaluasi Solusi Masalah</div>
                        </div>
                    </div>

                    <!-- Content Reader -->
                    <div class="md:col-span-2 bg-white p-6 sm:p-8 rounded-2xl border border-slate-200">
                        <div class="flex items-center justify-between mb-4 pb-4 border-b">
                            <span class="text-xs bg-purple-100 text-purple-700 px-2.5 py-1 rounded-full font-semibold">Kurikulum Merdeka (Fase F)</span>
                            <span class="text-xs text-slate-400">Waktu Baca: ~8 Menit</span>
                        </div>
                        <h2 class="text-xl font-bold text-slate-800 mb-4">Bab 1: Konsep Dasar & Pemodelan</h2>
                        <div class="prose text-slate-600 text-sm space-y-4 leading-relaxed">
                            <p>Pembahasan materi ini dirancang secara sistematis dengan pendekatan visual agar mempermudah pemahaman konsep mendasar siswa SMA.</p>
                            <div class="bg-amber-50 border-l-4 border-amber-400 p-4 rounded-r-xl my-4">
                                <p class="font-semibold text-amber-800 text-xs">💡 Key Concept / Catatan Penting:</p>
                                <p class="text-xs text-amber-700 mt-1">Pastikan Anda memahami perbedaan mendasar antara penalaran konseptual dan aplikasi rumus praktis sebelum mengerjakan latihan soal.</p>
                            </div>
                            <p>Penjelasan dilanjutkan dengan simulasi studi kasus nyata yang sering diujikan dalam tes TKA maupun UTBK SNBT.</p>
                        </div>
                    </div>
                </div>
            `;
            lucide.createIcons();
        }

        function openSimulasi(subtes) {
            const app = document.getElementById('app-content');
            app.innerHTML = `
                <div class="max-w-3xl mx-auto bg-white p-6 sm:p-8 rounded-2xl border border-slate-200 shadow-sm">
                    <div class="flex justify-between items-center mb-6 border-b pb-4">
                        <div>
                            <span class="text-xs text-indigo-600 font-bold uppercase tracking-wider">Simulasi Latihan UTBK</span>
                            <h2 class="text-lg font-bold text-slate-800">${subtes}</h2>
                        </div>
                        <div class="bg-red-50 text-red-600 px-3 py-1.5 rounded-xl font-mono text-xs font-bold flex items-center gap-1">
                            <i data-lucide="clock" class="w-4 h-4"></i> 14:59
                        </div>
                    </div>

                    <!-- Question Container -->
                    <div class="mb-6">
                        <span class="text-xs text-slate-400 font-semibold">Soal 1 dari 15</span>
                        <p class="text-slate-800 text-sm font-medium mt-2 leading-relaxed">
                            Berdasarkan wacana di atas, manakah simpulan yang PALING LOGIS mengenai dampak perubahan iklim terhadap produktivitas pertanian di Indonesia?
                        </p>
                    </div>

                    <!-- Options -->
                    <div class="space-y-3 mb-8">
                        ${['A. Produksi pangan meningkat pesat akibat kenaikan suhu.', 'B. Penurunan hasil panen terjadi apabila pola curah hujan tidak menentu.', 'C. Semua sektor pertanian tidak terdampak oleh perubahan iklim.', 'D. Petani beralih total ke sektor industri manufaktur.'].map((opt, i) => `
                            <label class="flex items-center p-3.5 border border-slate-200 rounded-xl cursor-pointer hover:border-indigo-500 hover:bg-indigo-50/50 transition">
                                <input type="radio" name="answer" class="text-indigo-600 focus:ring-indigo-500">
                                <span class="ml-3 text-xs sm:text-sm text-slate-700 font-medium">${opt}</span>
                            </label>
                        `).join('')}
                    </div>

                    <!-- Action Buttons -->
                    <div class="flex justify-between items-center">
                        <button onclick="switchView('utbk')" class="px-4 py-2 border border-slate-200 text-slate-600 text-xs font-semibold rounded-xl hover:bg-slate-50">Keluar</button>
                        <button onclick="alert('Jawaban disimpan!')" class="px-6 py-2.5 bg-indigo-600 text-white text-xs font-semibold rounded-xl hover:bg-indigo-700">Soal Selanjutnya</button>
                    </div>
                </div>
            `;
            lucide.createIcons();
        }

        // Navigation Controller
        function switchView(view) {
            const app = document.getElementById('app-content');
            if (view === 'home') app.innerHTML = renderHome();
            else if (view === 'materi') app.innerHTML = renderMateri();
            else if (view === 'utbk' || view === 'tryout') app.innerHTML = renderUTBK();
            
            // Re-initialize Icons
            lucide.createIcons();
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Initialize App View
        document.addEventListener('DOMContentLoaded', () => {
            switchView('home');
        });
    </script>
</body>
</html>
