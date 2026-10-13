<html lang="ar" dir="rtl">
<head>
   <title>منصة مضيف أهل العباء</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&family=Amiri:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        gold: {
                            light: '#f2d06b',
                            DEFAULT: '#d4af37',
                            dark: '#aa820a',
                        },
                        maroon: {
                            light: '#800000',
                            DEFAULT: '#5c0000',
                            dark: '#3b0000',
                        }
                    },
                    fontFamily: {
                        tajawal: ['Tajawal', 'sans-serif'],
                        amiri: ['Amiri', 'serif'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #0b0507;
            min-height: 100vh;
            color: #f3f4f6;
            touch-action: manipulation;
        }

        .bg-pattern {
            background-image: radial-gradient(#d4af37 0.75px, transparent 0.75px), radial-gradient(#d4af37 0.75px, #0b0507 0.75px);
            background-size: 30px 30px;
            background-position: 0 0, 15px 15px;
            opacity: 0.12;
        }

        /* Watermark logo matching uploaded image design */
        .bg-logo-watermark {
            background-image: url('image_be668db9-removebg-preview_2.png');
            background-repeat: no-repeat;
            background-position: center center;
            background-size: min(85vw, 650px);
            opacity: 0.08;
            filter: drop-shadow(0 0 20px rgba(212, 175, 55, 0.2));
        }

        .glass-card {
            background: rgba(22, 10, 14, 0.88);
            backdrop-filter: blur(14px);
            border: 1px solid rgba(212, 175, 55, 0.25);
            box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.8);
            transition: all 0.3s ease-in-out;
        }

        .glass-card:hover, .glass-card:focus-within {
            border-color: rgba(212, 175, 55, 0.75);
            transform: translateY(-3px);
            box-shadow: 0 15px 35px -5px rgba(212, 175, 55, 0.2);
        }

        .gold-glow {
            filter: drop-shadow(0 0 14px rgba(212, 175, 55, 0.35));
        }

        /* Controller / D-Pad focus support for Playstation and Keyboards */
        a:focus, button:focus, input:focus {
            outline: 2px solid #d4af37;
            outline-offset: 3px;
        }
    </style>
</head>
<body class="relative min-h-screen flex flex-col justify-between overflow-x-hidden selection:bg-gold selection:text-black">

    <!-- Background Pattern & Watermark Logo -->
    <div class="fixed inset-0 bg-pattern pointer-events-none z-0"></div>
    <div class="fixed inset-0 bg-logo-watermark pointer-events-none z-0"></div>

    <header class="relative z-10 w-full px-4 sm:px-8 py-5 flex flex-col md:flex-row justify-between items-center border-b border-gold/30 bg-black/80 backdrop-blur-md gap-4">
        <div class="flex items-center space-x-4 space-x-reverse">
            <!-- Medium Sized Corner Logo -->
            <div class="p-2 sm:p-2.5 rounded-2xl bg-gradient-to-b from-maroon/80 to-black border border-gold/40 shadow-xl gold-glow flex-shrink-0">
                <img src="image_be668db9-removebg-preview_2.png" alt="شعار مضيف أهل العباء" class="h-16 sm:h-20 md:h-24 w-auto object-contain">
            </div>
            <div>
                <h1 class="text-2xl sm:text-3xl md:text-4xl font-extrabold text-transparent bg-clip-text bg-gradient-to-l from-gold-light via-gold to-yellow-200 font-amiri tracking-wide">
                    منصة مضيف أهل العباء
                </h1>
                <p class="text-xs sm:text-sm text-gold/80 mt-1 font-medium">عَلَيْهِمُ السَّلَامُ — البوابة الإلكترونية الرسمية</p>
            </div>
        </div>

        <div class="hidden md:flex items-center gap-2 px-4 py-2 rounded-full bg-gold/10 border border-gold/30 text-gold text-xs font-bold">
            <i class="fa-solid fa-kaaba text-sm"></i>
            <span>أهلاً وسهلاً بكم في المضيف</span>
        </div>
    </header>

    <main class="relative z-10 container mx-auto px-4 py-8 sm:py-12 flex-grow flex flex-col justify-center max-w-5xl">
        <div class="text-center mb-8 sm:mb-10">
            <h2 class="text-2xl sm:text-4xl font-bold text-white mb-3 font-amiri">الخدمات والمواقع الإلكترونية</h2>
            <p class="text-xs sm:text-sm text-gray-400 max-w-lg mx-auto">اضغط على أي موقع للانتقال إليه. المواقع المحمية تتطلب إدخال كلمة السر المخصصة للدخول.</p>
        </div>

        <!-- 4 Main Sites Grid -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            
            <!-- Site 1: Open -->
            <div class="glass-card rounded-2xl p-6 flex flex-col justify-between group">
                <div>
                    <div class="flex items-center justify-between mb-4">
                        <div class="w-12 h-12 rounded-xl bg-gold/10 border border-gold/30 text-gold flex items-center justify-center text-2xl gold-glow">
                            <i class="fa-solid fa-globe"></i>
                        </div>
                        <span class="px-3 py-1 rounded-full bg-emerald-950/80 border border-emerald-500/40 text-emerald-400 text-xs font-bold flex items-center gap-1.5">
                            <i class="fa-solid fa-circle-check text-[10px]"></i>
                            مفتوح للجميع
                        </span>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 group-hover:text-gold transition-colors font-tajawal">موقع الكتروني الأصلي</h3>
                    <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-4">الوصول المباشر للواجهة الأساسية الرسمية لمنصة مضيف أهل العباء والبلاد القديم.</p>
                </div>
                <a href="https://ahlaalaba.github.io/albelad.alqadeem/" target="_blank" tabindex="0" class="w-full py-3 rounded-xl bg-gradient-to-r from-gold-dark via-gold to-gold-light text-black font-bold text-sm flex items-center justify-center gap-2 hover:brightness-110 transition-all shadow-lg">
                    <span>الانتقال للموقع</span>
                    <i class="fa-solid fa-arrow-left"></i>
                </a>
            </div>

            <!-- Site 2: Protected -->
            <div class="glass-card rounded-2xl p-6 flex flex-col justify-between group">
                <div>
                    <div class="flex items-center justify-between mb-4">
                        <div class="w-12 h-12 rounded-xl bg-maroon/40 border border-gold/30 text-gold flex items-center justify-center text-2xl">
                            <i class="fa-solid fa-key"></i>
                        </div>
                        <span class="px-3 py-1 rounded-full bg-amber-950/80 border border-gold/40 text-gold text-xs font-bold flex items-center gap-1.5">
                            <i class="fa-solid fa-lock text-[10px]"></i>
                            يتطلب كلمة سر
                        </span>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 group-hover:text-gold transition-colors font-tajawal">موقع الكتروني فقدان كلمة السر</h3>
                    <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-4">صفحة استعادة وإعادة تعيين كلمة السر للخدمات الخاصة بـ المنصة.</p>
                </div>
                <button onclick="requestAccess('https://ahlaalaba.github.io/forgetpasscode/', 'موقع الكتروني فقدان كلمة السر')" tabindex="0" class="w-full py-3 rounded-xl bg-zinc-900 border border-gold/40 text-gold font-bold text-sm flex items-center justify-center gap-2 hover:bg-gold hover:text-black transition-all">
                    <i class="fa-solid fa-lock"></i>
                    <span>فتح الموقع المحمي</span>
                </button>
            </div>

            <!-- Site 3: Protected -->
            <div class="glass-card rounded-2xl p-6 flex flex-col justify-between group">
                <div>
                    <div class="flex items-center justify-between mb-4">
                        <div class="w-12 h-12 rounded-xl bg-maroon/40 border border-gold/30 text-gold flex items-center justify-center text-2xl">
                            <i class="fa-solid fa-tower-cell"></i>
                        </div>
                        <span class="px-3 py-1 rounded-full bg-amber-950/80 border border-gold/40 text-gold text-xs font-bold flex items-center gap-1.5">
                            <i class="fa-solid fa-lock text-[10px]"></i>
                            يتطلب كلمة سر
                        </span>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 group-hover:text-gold transition-colors font-tajawal">موقع الكتروني الحالات المتصل</h3>
                    <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-4">متابعة الاتصالات والمستخدمين المتصلين وخدمات المتابعة الحية.</p>
                </div>
                <button onclick="requestAccess('https://ahlaalaba.github.io/Caller-status/', 'موقع الكتروني الحالات المتصل')" tabindex="0" class="w-full py-3 rounded-xl bg-zinc-900 border border-gold/40 text-gold font-bold text-sm flex items-center justify-center gap-2 hover:bg-gold hover:text-black transition-all">
                    <i class="fa-solid fa-lock"></i>
                    <span>فتح الموقع المحمي</span>
                </button>
            </div>

            <!-- Site 4: Protected -->
            <div class="glass-card rounded-2xl p-6 flex flex-col justify-between group">
                <div>
                    <div class="flex items-center justify-between mb-4">
                        <div class="w-12 h-12 rounded-xl bg-maroon/40 border border-gold/30 text-gold flex items-center justify-center text-2xl">
                            <i class="fa-solid fa-envelope-open-text"></i>
                        </div>
                        <span class="px-3 py-1 rounded-full bg-amber-950/80 border border-gold/40 text-gold text-xs font-bold flex items-center gap-1.5">
                            <i class="fa-solid fa-lock text-[10px]"></i>
                            يتطلب كلمة سر
                        </span>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-2 group-hover:text-gold transition-colors font-tajawal">موقع الكتروني المراسلات</h3>
                    <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-4">منظومة المراسلات والرسائل الواردة والصادرة الخاصة بـ المضيف.</p>
                </div>
                <button onclick="requestAccess('https://ahlaalaba.github.io/message/', 'موقع الكتروني المراسلات')" tabindex="0" class="w-full py-3 rounded-xl bg-zinc-900 border border-gold/40 text-gold font-bold text-sm flex items-center justify-center gap-2 hover:bg-gold hover:text-black transition-all">
                    <i class="fa-solid fa-lock"></i>
                    <span>فتح الموقع المحمي</span>
                </button>
            </div>

        </div>
    </main>

    <div id="passwordModal" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden opacity-0 transition-opacity duration-300">
        <div class="bg-gradient-to-b from-zinc-900 via-zinc-950 to-black border border-gold/50 rounded-3xl p-6 sm:p-8 max-w-md w-full shadow-2xl relative text-center">
            
            <div class="w-16 h-16 bg-gold/10 border border-gold/40 rounded-2xl flex items-center justify-center text-gold mx-auto mb-4 text-3xl gold-glow">
                <i class="fa-solid fa-shield-halved"></i>
            </div>

            <h3 id="modalSiteTitle" class="text-xl font-bold text-white mb-2 font-amiri">موقع محمي</h3>
            <p class="text-xs text-gray-400 mb-6">الرجاء إدخال كلمة السر للدخول إلى الرابط المطلوب</p>

            <form onsubmit="verifyPassword(event)" class="space-y-4">
                <div class="relative">
                    <input type="password" id="passInput" required placeholder="أدخل كلمة السر هنا..." class="w-full bg-black/80 border border-gold/40 rounded-xl px-4 py-3 text-center text-white text-lg tracking-widest focus:border-gold focus:outline-none placeholder:text-gray-600 placeholder:tracking-normal placeholder:text-sm">
                </div>

                <div id="errorMessage" class="text-xs text-red-400 font-bold hidden flex items-center justify-center gap-1">
                    <i class="fa-solid fa-triangle-exclamation"></i>
                    <span>كلمة السر غير صحيحة! حاول مرة أخرى.</span>
                </div>

                <div class="flex gap-3 pt-2">
                    <button type="submit" class="flex-1 py-3 rounded-xl bg-gradient-to-r from-gold-dark via-gold to-gold-light text-black font-bold text-sm hover:brightness-110 transition-all">
                        تأكيد والدخول
                    </button>
                    <button type="button" onclick="closeModal()" class="flex-1 py-3 rounded-xl bg-zinc-800 text-gray-300 font-bold text-sm hover:bg-zinc-700 transition-all">
                        إلغاء
                    </button>
                </div>
            </form>
        </div>
    </div>

    <footer class="relative z-10 w-full py-5 border-t border-gold/20 text-center text-xs text-gray-400 bg-black/80 backdrop-blur-sm">
        <p>جميع الحقوق محفوظة © منصة مضيف أهل العباء (عَلَيْهِمُ السَّلَامُ)</p>
    </footer>

    <script>
        const CORRECT_PASSCODE = "36386184";
        let targetUrl = "";

        const modal = document.getElementById('passwordModal');
        const passInput = document.getElementById('passInput');
        const errorMessage = document.getElementById('errorMessage');
        const modalSiteTitle = document.getElementById('modalSiteTitle');

        function requestAccess(url, siteName) {
            targetUrl = url;
            modalSiteTitle.innerText = siteName;
            passInput.value = "";
            errorMessage.classList.add('hidden');

            modal.classList.remove('hidden');
            setTimeout(() => {
                modal.classList.remove('opacity-0');
                passInput.focus();
            }, 10);
        }

        function closeModal() {
            modal.classList.add('opacity-0');
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300);
        }

        function verifyPassword(e) {
            e.preventDefault();
            const enteredPass = passInput.value.trim();

            if (enteredPass === CORRECT_PASSCODE) {
                errorMessage.classList.add('hidden');
                closeModal();
                window.open(targetUrl, '_blank');
            } else {
                errorMessage.classList.remove('hidden');
                passInput.value = "";
                passInput.focus();
            }
        }
    </script>
</body>
