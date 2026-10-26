<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة مضيف أهل العباء</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Cairo Font -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800;900&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        cairo: ['Cairo', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            gold: '#D4AF37',
                            goldLight: '#F3E5AB',
                            goldDark: '#AA7C11',
                            emeraldDark: '#022C22',
                            emeraldMid: '#064E3B',
                            emeraldLight: '#059669',
                        }
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Cairo', sans-serif;
            background: radial-gradient(circle at top right, #064E3B 0%, #022C22 60%, #011712 100%);
            min-height: 100vh;
        }

        /* Glassmorphism Classes */
        .glass-header {
            background: rgba(2, 44, 34, 0.85);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(212, 175, 55, 0.25);
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.04);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border: 1px solid rgba(212, 175, 55, 0.25);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.35);
        }

        .glass-card-hover {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .glass-card-hover:hover {
            background: rgba(255, 255, 255, 0.09);
            border-color: rgba(212, 175, 55, 0.6);
            transform: translateY(-3px);
            box-shadow: 0 15px 35px -5px rgba(0, 0, 0, 0.6), 0 0 20px rgba(212, 175, 55, 0.2);
        }

        .glass-modal {
            background: rgba(2, 44, 34, 0.95);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(212, 175, 55, 0.4);
        }

        /* Shake animation for incorrect passcode */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-8px); }
            40%, 80% { transform: translateX(8px); }
        }
        .animate-shake {
            animation: shake 0.4s cubic-bezier(.36,.07,.19,.97) both;
        }

        /* Toast Animation */
        @keyframes fadeInDown {
            from { transform: translate(-50%, -25px); opacity: 0; }
            to { transform: translate(-50%, 0); opacity: 1; }
        }
        .animate-toast {
            animation: fadeInDown 0.3s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }
    </style>
</head>
<body class="text-slate-100 flex flex-col justify-between min-h-screen relative overflow-x-hidden selection:bg-brand-gold selection:text-slate-950">

    <!-- Toast Notification Overlay -->
    <div id="toast" class="fixed top-5 left-1/2 -translate-x-1/2 z-50 hidden max-w-md w-11/12 bg-slate-900 border border-brand-gold/50 text-brand-goldLight p-4 rounded-2xl shadow-2xl flex items-center gap-3 animate-toast">
        <i class="fa-solid fa-circle-check text-xl text-brand-gold"></i>
        <div class="text-xs md:text-sm font-bold" id="toastText">تم الإجراء بنجاح!</div>
    </div>

    <!-- Background Decorative Glows -->
    <div class="absolute top-0 right-0 -z-10 w-96 h-96 bg-brand-gold/10 rounded-full blur-3xl pointer-events-none"></div>
    <div class="absolute bottom-0 left-0 -z-10 w-96 h-96 bg-brand-emeraldLight/10 rounded-full blur-3xl pointer-events-none"></div>

    <!-- Header Section (Medium Logo in Top Corner) -->
    <header class="w-full px-4 md:px-8 py-4 glass-header sticky top-0 z-40 shadow-xl">
        <div class="max-w-5xl mx-auto flex justify-between items-center">
            
            <!-- Logo Component (Top Right Corner, Medium Size) -->
            <div class="flex items-center gap-3 md:gap-4">
                <div class="w-14 h-14 md:w-16 md:h-16 rounded-2xl p-0.5 bg-gradient-to-tr from-brand-goldDark via-brand-gold to-brand-goldLight shadow-lg flex items-center justify-center shrink-0">
                    <div class="w-full h-full bg-brand-emeraldDark rounded-[14px] flex items-center justify-center border border-brand-gold/30">
                        <i class="fa-solid fa-mosque text-2xl md:text-3xl text-brand-gold"></i>
                    </div>
                </div>
                <div>
                    <h1 class="text-xl md:text-2xl font-black bg-gradient-to-l from-brand-goldLight via-brand-gold to-white bg-clip-text text-transparent leading-tight">
                        منصة مضيف أهل العباء
                    </h1>
                    <p class="text-[11px] md:text-xs text-brand-gold/90 font-bold flex items-center gap-1.5 mt-0.5">
                        <i class="fa-solid fa-shield-halved text-[10px]"></i> البوابة الإلكترونية الرسمية
                    </p>
                </div>
            </div>

            <!-- Portal Badge Status -->
            <div class="hidden sm:flex items-center gap-2 bg-brand-gold/10 border border-brand-gold/30 px-3.5 py-1.5 rounded-full text-xs text-brand-goldLight font-semibold">
                <span class="w-2.5 h-2.5 rounded-full bg-brand-gold animate-pulse"></span>
                <span>النظام يعمل بنشاط</span>
            </div>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="max-w-4xl mx-auto px-4 py-8 md:py-12 w-full flex-grow flex flex-col justify-center">

        <div class="text-center space-y-3 mb-8 md:mb-12">
            <h2 class="text-2xl md:text-4xl font-black text-white">دليل الخدمات والمواقع الإلكترونية</h2>
            <p class="text-xs md:text-sm text-slate-300 max-w-xl mx-auto">
                يرجى اختيار الخدمة المطلوبة. الخدمات المحمية بـ <i class="fa-solid fa-key text-brand-gold mx-1"></i> تتطلب إدخال رمز المرور الخاص بالمنصة للوصول إليها.
            </p>
        </div>

        <!-- Links Directory Section -->
        <div class="space-y-4">

            <!-- 1. موقع الكتروني الأصلي (Direct Link) -->
            <a href="https://ahlaalaba.github.io/albelad.alqadeem/" target="_blank" rel="noopener noreferrer" 
               class="glass-card glass-card-hover p-4 md:p-5 rounded-2xl flex items-center justify-between group">
                <div class="flex items-center gap-4">
                    <div class="w-12 h-12 rounded-2xl bg-brand-gold/10 text-brand-gold flex items-center justify-center text-xl shrink-0 border border-brand-gold/30 group-hover:bg-brand-gold group-hover:text-slate-950 transition-colors">
                        <i class="fa-solid fa-house-chimney"></i>
                    </div>
                    <div>
                        <h3 class="text-sm md:text-base font-bold text-white group-hover:text-brand-goldLight transition-colors">
                            1- موقع الكتروني الأصلي
                        </h3>
                        <p class="text-xs text-slate-400 mt-0.5">الرابط والصفحة الرئيسية لمنصة مضيف أهل العباء</p>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <span class="text-[11px] bg-emerald-500/20 text-emerald-300 border border-emerald-500/30 px-2.5 py-1 rounded-full font-semibold hidden sm:inline-block">وصول مباشر</span>
                    <i class="fa-solid fa-arrow-left text-sm text-slate-500 group-hover:text-brand-gold group-hover:-translate-x-1 transition-all"></i>
                </div>
            </a>

            <!-- 2. موقع الكتروني فقدان كلمة السر (Protected by passcode 36386184) -->
            <button onclick="openPasscodeModal('https://ahlaalaba.github.io/forgetpasscode/', 'موقع الكتروني فقدان كلمة السر')" 
                    class="glass-card glass-card-hover p-4 md:p-5 rounded-2xl flex items-center justify-between group text-right w-full">
                <div class="flex items-center gap-4">
                    <div class="w-12 h-12 rounded-2xl bg-amber-500/10 text-amber-400 flex items-center justify-center text-xl shrink-0 border border-amber-500/30 group-hover:bg-amber-400 group-hover:text-slate-950 transition-colors">
                        <i class="fa-solid fa-key"></i>
                    </div>
                    <div>
                        <h3 class="text-sm md:text-base font-bold text-white group-hover:text-amber-300 transition-colors">
                            موقع الكتروني فقدان كلمة السر
                        </h3>
                        <p class="text-xs text-slate-400 mt-0.5">خدمة استعادة وتعيين كلمة المرور (محمي برمز المرور)</p>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <span class="w-9 h-9 rounded-xl bg-amber-500/20 border border-amber-500/40 text-amber-400 flex items-center justify-center">
                        <i class="fa-solid fa-lock text-sm"></i>
                    </span>
                </div>
            </button>

            <!-- 3. موقع الكتروني الحالات المتصل (Protected by passcode 36386184) -->
            <button onclick="openPasscodeModal('https://ahlaalaba.github.io/Caller-status/', 'موقع الكتروني الحالات المتصل')" 
                    class="glass-card glass-card-hover p-4 md:p-5 rounded-2xl flex items-center justify-between group text-right w-full">
                <div class="flex items-center gap-4">
                    <div class="w-12 h-12 rounded-2xl bg-sky-500/10 text-sky-400 flex items-center justify-center text-xl shrink-0 border border-sky-500/30 group-hover:bg-sky-400 group-hover:text-slate-950 transition-colors">
                        <i class="fa-solid fa-phone-volume"></i>
                    </div>
                    <div>
                        <h3 class="text-sm md:text-base font-bold text-white group-hover:text-sky-300 transition-colors">
                            موقع الكتروني الحالات المتصل
                        </h3>
                        <p class="text-xs text-slate-400 mt-0.5">متابعة حالة الاتصالات والنشاط المباشر (محمي برمز المرور)</p>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <span class="w-9 h-9 rounded-xl bg-amber-500/20 border border-amber-500/40 text-amber-400 flex items-center justify-center">
                        <i class="fa-solid fa-lock text-sm"></i>
                    </span>
                </div>
            </button>

            <!-- 4. موقع الكتروني المراسلات (Protected by passcode 36386184) -->
            <button onclick="openPasscodeModal('https://ahlaalaba.github.io/message/', 'موقع الكتروني المراسلات')" 
                    class="glass-card glass-card-hover p-4 md:p-5 rounded-2xl flex items-center justify-between group text-right w-full">
                <div class="flex items-center gap-4">
                    <div class="w-12 h-12 rounded-2xl bg-purple-500/10 text-purple-400 flex items-center justify-center text-xl shrink-0 border border-purple-500/30 group-hover:bg-purple-400 group-hover:text-slate-950 transition-colors">
                        <i class="fa-solid fa-comments"></i>
                    </div>
                    <div>
                        <h3 class="text-sm md:text-base font-bold text-white group-hover:text-purple-300 transition-colors">
                            موقع الكتروني المراسلات
                        </h3>
                        <p class="text-xs text-slate-400 mt-0.5">نظام الرسائل والتواصل الداخلي (محمي برمز المرور)</p>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <span class="w-9 h-9 rounded-xl bg-amber-500/20 border border-amber-500/40 text-amber-400 flex items-center justify-center">
                        <i class="fa-solid fa-lock text-sm"></i>
                    </span>
                </div>
            </button>

            <!-- 5. موقع البلاغ مشاكل (Direct Link / No passcode) -->
            <a href="https://ahlaalaba.github.io/report/#%D9%85%D8%B6%D9%8A%D9%81-%D8%A3%D9%87%D9%84-%D8%A7%D9%84%D8%B9%D8%A8%D8%A7%D8%A1" target="_blank" rel="noopener noreferrer" 
               class="glass-card glass-card-hover p-4 md:p-5 rounded-2xl flex items-center justify-between group border-rose-500/30">
                <div class="flex items-center gap-4">
                    <div class="w-12 h-12 rounded-2xl bg-rose-500/10 text-rose-400 flex items-center justify-center text-xl shrink-0 border border-rose-500/30 group-hover:bg-rose-500 group-hover:text-white transition-colors">
                        <i class="fa-solid fa-triangle-exclamation"></i>
                    </div>
                    <div>
                        <h3 class="text-sm md:text-base font-bold text-white group-hover:text-rose-300 transition-colors">
                            موقع البلاغ مشاكل
                        </h3>
                        <p class="text-xs text-slate-400 mt-0.5">تقديم بلاغات عن المشاكل التقنية والإنذارات (لا يوجد كلمة سر)</p>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <span class="text-[11px] bg-emerald-500/20 text-emerald-300 border border-emerald-500/30 px-2.5 py-1 rounded-full font-semibold hidden sm:inline-block">وصول مباشر</span>
                    <i class="fa-solid fa-arrow-left text-sm text-slate-500 group-hover:text-rose-400 group-hover:-translate-x-1 transition-all"></i>
                </div>
            </a>

        </div>

    </main>

    <!-- Footer -->
    <footer class="w-full text-center py-5 border-t border-brand-gold/20 text-xs text-slate-400 glass-header mt-8">
        <p class="font-semibold text-brand-gold/90">جميع الحقوق محفوظة &copy; منصة مضيف أهل العباء</p>
    </footer>

    <!-- Passcode Verification Modal -->
    <div id="passcodeModal" class="fixed inset-0 bg-slate-950/85 backdrop-blur-md hidden justify-center items-center p-4 z-50 transition-all">
        <div id="modalBox" class="glass-modal p-6 md:p-8 rounded-3xl max-w-sm w-full text-center relative shadow-2xl">
            
            <button onclick="closePasscodeModal()" class="absolute top-4 left-4 text-slate-400 hover:text-white w-8 h-8 rounded-full bg-white/5 flex items-center justify-center transition-all">
                <i class="fa-solid fa-xmark text-sm"></i>
            </button>

            <div class="w-16 h-16 bg-brand-gold/15 text-brand-gold rounded-2xl flex items-center justify-center mx-auto mb-4 text-2xl border border-brand-gold/30 shadow-inner">
                <i class="fa-solid fa-shield-halved"></i>
            </div>

            <h3 class="text-base md:text-lg font-extrabold text-white mb-1" id="modalTitle">إدخال كلمة السر</h3>
            <p class="text-xs text-slate-300 mb-5" id="modalSubtitle">هذا الموقع محمي، يرجى إدخال كلمة السر للمتابعة</p>

            <form onsubmit="handlePasscodeVerification(event)" class="space-y-4">
                <div class="text-right">
                    <label class="block text-xs font-semibold text-brand-goldLight mb-1.5">كلمة السر المطلوبة:</label>
                    <div class="relative">
                        <input type="password" id="passcodeInput" required placeholder="أدخل كلمة السر هنا" 
                               class="w-full bg-slate-900/90 border border-slate-700 focus:border-brand-gold rounded-xl px-4 py-3 pl-10 text-white text-center tracking-widest text-base font-mono focus:outline-none focus:ring-1 focus:ring-brand-gold">
                        <button type="button" onclick="togglePasscodeVisibility()" class="absolute left-3 top-1/2 -translate-y-1/2 text-slate-400 hover:text-brand-gold text-sm">
                            <i class="fa-solid fa-eye" id="eyeIcon"></i>
                        </button>
                    </div>
                </div>

                <div id="modalError" class="hidden p-3 rounded-xl bg-rose-500/20 border border-rose-500/40 text-rose-300 text-xs text-center flex items-center justify-center gap-2">
                    <i class="fa-solid fa-circle-exclamation"></i>
                    <span>كلمة السر غير صحيحة! يرجى المحاولة مرة أخرى.</span>
                </div>

                <div class="flex gap-2 pt-2">
                    <button type="button" onclick="closePasscodeModal()" class="w-1/3 bg-slate-800 hover:bg-slate-700 text-slate-300 font-bold py-3 rounded-xl text-xs transition-all">
                        إلغاء
                    </button>
                    <button type="submit" class="w-2/3 bg-gradient-to-r from-brand-goldDark via-brand-gold to-brand-goldLight hover:brightness-110 text-slate-950 font-black py-3 rounded-xl text-xs transition-all shadow-lg flex items-center justify-center gap-2">
                        <i class="fa-solid fa-unlock"></i> دخول الموقع
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- JavaScript Handling Password Security and Dialogs -->
    <script>
        const MASTER_PASSCODE = "36386184";
        let targetUrlToOpen = null;

        const passcodeModal = document.getElementById('passcodeModal');
        const modalBox = document.getElementById('modalBox');
        const modalTitle = document.getElementById('modalTitle');
        const passcodeInput = document.getElementById('passcodeInput');
        const modalError = document.getElementById('modalError');
        const eyeIcon = document.getElementById('eyeIcon');
        const toast = document.getElementById('toast');
        const toastText = document.getElementById('toastText');

        function openPasscodeModal(url, siteTitle) {
            targetUrlToOpen = url;
            modalTitle.innerText = siteTitle;
            passcodeInput.value = '';
            modalError.classList.add('hidden');
            modalBox.classList.remove('animate-shake');
            passcodeModal.classList.remove('hidden');
            passcodeModal.classList.add('flex');
            setTimeout(() => passcodeInput.focus(), 150);
        }

        function closePasscodeModal() {
            passcodeModal.classList.add('hidden');
            passcodeModal.classList.remove('flex');
            targetUrlToOpen = null;
        }

        function togglePasscodeVisibility() {
            if (passcodeInput.type === 'password') {
                passcodeInput.type = 'text';
                eyeIcon.classList.remove('fa-eye');
                eyeIcon.classList.add('fa-eye-slash');
            } else {
                passcodeInput.type = 'password';
                eyeIcon.classList.remove('fa-eye-slash');
                eyeIcon.classList.add('fa-eye');
            }
        }

        function handlePasscodeVerification(e) {
            e.preventDefault();
            const value = passcodeInput.value.trim();

            if (value === MASTER_PASSCODE) {
                modalError.classList.add('hidden');
                showToast("تم التحقق من كلمة السر بنجاح! جاري التوجيه...");
                const destination = targetUrlToOpen;
                closePasscodeModal();
                setTimeout(() => {
                    if (destination) {
                        window.open(destination, '_blank');
                    }
                }, 500);
            } else {
                modalError.classList.remove('hidden');
                modalBox.classList.remove('animate-shake');
                void modalBox.offsetWidth; // Force reflow
                modalBox.classList.add('animate-shake');
                passcodeInput.value = '';
                passcodeInput.focus();
            }
        }

        function showToast(msg) {
            toastText.innerText = msg;
            toast.classList.remove('hidden');
            setTimeout(() => {
                toast.classList.add('hidden');
            }, 3000);
        }

        // Close modal on outer click
        window.onclick = function(event) {
            if (event.target === passcodeModal) {
                closePasscodeModal();
            }
        };
    </script>
</body>
</html>
