<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>عيد ميلاد - Apple Liquid Glass</title>
    <link href="https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@300;400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <style>
        /* ===== CSS Variables ===== */
        :root {
            --primary-gradient: linear-gradient(135deg, rgba(255, 255, 255, 0.95) 0%, rgba(255, 255, 255, 0.85) 100%);
            --glass-blur: 30px;
            --glass-opacity: 0.7;
            --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
            --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.12);
            --shadow-lg: 0 20px 60px rgba(0, 0, 0, 0.15);
            --shadow-xl: 0 30px 80px rgba(0, 0, 0, 0.2);
            --transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
            --radius-sm: 12px;
            --radius-md: 20px;
            --radius-lg: 28px;
            --radius-xl: 40px;
        }

        /* ===== Reset & Base Styles ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #0f0f1e 0%, #1a1a3e 50%, #0f1a2e 100%);
            min-height: 100vh;
            color: #1d1d1f;
            overflow-x: hidden;
            position: relative;
        }

        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
        }

        ::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.2);
            border-radius: 5px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        /* ===== Background Animation ===== */
        .background-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        .gradient-orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.15;
            animation: float 25s infinite ease-in-out;
        }

        .orb-1 {
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, #00d9ff, #0099ff);
            top: -100px;
            right: -100px;
            animation-delay: 0s;
        }

        .orb-2 {
            width: 350px;
            height: 350px;
            background: radial-gradient(circle, #ff006e, #8338ec);
            bottom: -50px;
            left: -50px;
            animation-delay: 8s;
        }

        .orb-3 {
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, #ffd700, #ffed4e);
            top: 50%;
            left: 50%;
            animation-delay: 16s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(40px, -40px) scale(1.05); }
            66% { transform: translate(-40px, 40px) scale(0.95); }
        }

        /* ===== Glass Morphism Base ===== */
        .glass {
            background: rgba(255, 255, 255, var(--glass-opacity));
            backdrop-filter: blur(var(--glass-blur));
            -webkit-backdrop-filter: blur(var(--glass-blur));
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: var(--shadow-lg);
            position: relative;
            overflow: hidden;
        }

        .glass::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.5), transparent);
        }

        .glass::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 30%, rgba(255, 255, 255, 0.3), transparent 50%);
            pointer-events: none;
        }

        /* ===== Container ===== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* ===== Header Section ===== */
        .header {
            position: relative;
            z-index: 10;
            text-align: center;
            padding: 80px 20px 40px;
            animation: fadeInDown 0.8s ease-out;
        }

        .header-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .title {
            font-family: 'Playfair Display', serif;
            font-size: clamp(2.5rem, 8vw, 4.5rem);
            font-weight: 700;
            letter-spacing: -0.02em;
            margin-bottom: 16px;
            background: linear-gradient(135deg, #ffffff 0%, #e0e0e0 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.1);
        }

        .subtitle {
            font-size: clamp(1rem, 3vw, 1.3rem);
            color: rgba(255, 255, 255, 0.7);
            font-weight: 300;
            letter-spacing: 0.5px;
            margin-bottom: 30px;
        }

        /* ===== Countdown Section ===== */
        .countdown-section {
            margin: 60px 0;
            animation: fadeInUp 0.8s ease-out 0.2s both;
        }

        .countdown-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .countdown-title {
            font-size: clamp(1.5rem, 4vw, 2.2rem);
            color: rgba(255, 255, 255, 0.95);
            font-weight: 600;
            letter-spacing: -0.01em;
        }

        .countdown-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 16px;
            padding: 0 10px;
        }

        .countdown-card {
            glass;
            border-radius: var(--radius-lg);
            padding: 32px 20px;
            text-align: center;
            transition: var(--transition);
            position: relative;
            cursor: pointer;
            group: 'countdown-card';
        }

        .countdown-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 40px 80px rgba(0, 0, 0, 0.25);
            background: rgba(255, 255, 255, 0.85);
        }

        .countdown-card:active {
            transform: translateY(-4px);
        }

        .countdown-number {
            font-family: 'SF Pro Display', -apple-system, sans-serif;
            font-size: clamp(2rem, 5vw, 3.5rem);
            font-weight: 700;
            color: #00d9ff;
            letter-spacing: -0.02em;
            margin-bottom: 8px;
            text-shadow: 0 0 20px rgba(0, 217, 255, 0.3);
        }

        .countdown-label {
            font-size: 0.85rem;
            color: rgba(255, 255, 255, 0.6);
            font-weight: 500;
            letter-spacing: 0.3px;
            text-transform: uppercase;
        }

        /* ===== Buttons Section ===== */
        .buttons-section {
            display: flex;
            gap: 16px;
            justify-content: center;
            flex-wrap: wrap;
            margin: 60px 0;
            animation: fadeInUp 0.8s ease-out 0.4s both;
            padding: 0 10px;
        }

        .glass-button {
            glass;
            border-radius: var(--radius-md);
            padding: 14px 32px;
            font-size: 0.95rem;
            font-weight: 600;
            letter-spacing: 0.3px;
            cursor: pointer;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            border: none;
            color: #1d1d1f;
            text-transform: uppercase;
            font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', sans-serif;
            display: flex;
            align-items: center;
            gap: 8px;
            white-space: nowrap;
        }

        .glass-button::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(0, 0, 0, 0.1);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .glass-button:active::before {
            width: 300px;
            height: 300px;
        }

        .glass-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.2);
            background: rgba(255, 255, 255, 0.85);
        }

        .glass-button:active {
            transform: translateY(0);
        }

        .btn-primary {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.95), rgba(255, 255, 255, 0.85));
            color: #1d1d1f;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.7);
            color: #1d1d1f;
        }

        .btn-music {
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.3), rgba(131, 56, 236, 0.3));
            color: #ffffff;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .music-pulse {
            display: inline-block;
            width: 8px;
            height: 8px;
            background: #00d9ff;
            border-radius: 50%;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(0.8); }
        }

        /* ===== Comments Section ===== */
        .comments-section {
            glass;
            border-radius: var(--radius-lg);
            padding: 40px;
            margin: 60px 0;
            animation: fadeInUp 0.8s ease-out 0.6s both;
        }

        .section-title {
            font-size: clamp(1.5rem, 4vw, 2rem);
            color: rgba(255, 255, 255, 0.95);
            font-weight: 600;
            margin-bottom: 30px;
            letter-spacing: -0.01em;
        }

        .comment-input-group {
            display: grid;
            grid-template-columns: 1fr 1fr auto;
            gap: 12px;
            margin-bottom: 24px;
        }

        .comment-input {
            glass;
            border-radius: var(--radius-md);
            padding: 12px 16px;
            font-size: 0.95rem;
            border: none;
            color: #1d1d1f;
            font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', sans-serif;
            transition: var(--transition);
            background: rgba(255, 255, 255, 0.8);
        }

        .comment-input::placeholder {
            color: rgba(29, 29, 31, 0.5);
        }

        .comment-input:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 0 0 2px rgba(0, 217, 255, 0.3);
        }

        .comment-submit {
            glass;
            border-radius: var(--radius-md);
            padding: 12px 24px;
            background: linear-gradient(135deg, rgba(0, 217, 255, 0.3), rgba(131, 56, 236, 0.3));
            color: #ffffff;
            border: none;
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
            font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', sans-serif;
        }

        .comment-submit:hover {
            transform: translateY(-2px);
            box-shadow: 0 20px 40px rgba(0, 217, 255, 0.2);
        }

        .comment-submit:active {
            transform: translateY(0);
        }

        .comments-list {
            display: flex;
            flex-direction: column;
            gap: 16px;
            max-height: 600px;
            overflow-y: auto;
            padding-right: 8px;
        }

        .comment-card {
            glass;
            border-radius: var(--radius-md);
            padding: 20px;
            transition: var(--transition);
            border-left: 3px solid rgba(0, 217, 255, 0.5);
        }

        .comment-card:hover {
            transform: translateX(-4px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .comment-author {
            font-weight: 600;
            color: #1d1d1f;
            margin-bottom: 8px;
            font-size: 0.95rem;
        }

        .comment-text {
            color: rgba(29, 29, 31, 0.8);
            line-height: 1.6;
            font-size: 0.9rem;
            margin-bottom: 8px;
        }

        .comment-time {
            font-size: 0.75rem;
            color: rgba(29, 29, 31, 0.5);
        }

        /* ===== Animations ===== */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            pointer-events: none;
            z-index: 5;
            animation: confettiFall 3s linear forwards;
        }

        @keyframes confettiFall {
            to {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }

        /* ===== Responsive Design ===== */
        @media (max-width: 768px) {
            .header {
                padding: 60px 20px 30px;
            }

            .title {
                font-size: 2rem;
            }

            .subtitle {
                font-size: 1rem;
            }

            .countdown-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 12px;
            }

            .countdown-card {
                padding: 24px 16px;
            }

            .countdown-number {
                font-size: 2rem;
            }

            .buttons-section {
                flex-direction: column;
                gap: 12px;
            }

            .glass-button {
                width: 100%;
                justify-content: center;
            }

            .comment-input-group {
                grid-template-columns: 1fr;
            }

            .comments-section {
                padding: 24px;
            }

            .comment-submit {
                width: 100%;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 10px;
            }

            .countdown-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 10px;
            }

            .countdown-card {
                padding: 20px 12px;
            }

            .countdown-number {
                font-size: 1.5rem;
            }

            .countdown-label {
                font-size: 0.75rem;
            }

            .comments-section {
                padding: 16px;
            }

            .comment-input {
                font-size: 0.9rem;
                padding: 10px 12px;
            }
        }

        /* ===== Accessibility ===== */
        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }

        @media (prefers-color-scheme: dark) {
            .comment-input {
                background: rgba(255, 255, 255, 0.7);
                color: #1d1d1f;
            }

            .comment-author {
                color: #ffffff;
            }

            .comment-text {
                color: rgba(255, 255, 255, 0.8);
            }
        }
    </style>
</head>
<body>
    <!-- Background Animation -->
    <div class="background-container">
        <div class="gradient-orb orb-1"></div>
        <div class="gradient-orb orb-2"></div>
        <div class="gradient-orb orb-3"></div>
    </div>

    <!-- Main Content -->
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="header-content">
                <h1 class="title">🎂 عيد ميلاد سعيد 🎂</h1>
                <p class="subtitle">يوم خاص لشخص استثنائي</p>
            </div>
        </header>

        <!-- Countdown Section -->
        <section class="countdown-section">
            <div class="countdown-header">
                <h2 class="countdown-title">العد التنازلي</h2>
            </div>
            <div class="countdown-grid">
                <div class="countdown-card">
                    <div class="countdown-number" id="days">0</div>
                    <div class="countdown-label">أيام</div>
                </div>
                <div class="countdown-card">
                    <div class="countdown-number" id="hours">0</div>
                    <div class="countdown-label">ساعات</div>
                </div>
                <div class="countdown-card">
                    <div class="countdown-number" id="minutes">0</div>
                    <div class="countdown-label">دقائق</div>
                </div>
                <div class="countdown-card">
                    <div class="countdown-number" id="seconds">0</div>
                    <div class="countdown-label">ثوان</div>
                </div>
            </div>
        </section>

        <!-- Buttons Section -->
        <section class="buttons-section">
            <button class="glass-button btn-primary" onclick="celebrateWithConfetti()">
                ✨ احتفل معي
            </button>
            <button class="glass-button btn-music" onclick="toggleMusic()" id="musicBtn">
                🎵 اضغط هنا للتشغيل
                <span class="music-pulse" id="musicPulse" style="display: none;"></span>
            </button>
            <button class="glass-button btn-secondary" onclick="scrollToComments()">
                💬 التعليقات
            </button>
        </section>

        <!-- Comments Section -->
        <section class="comments-section" id="commentsSection">
            <h2 class="section-title">💌 رسائل التهاني</h2>
            
            <div class="comment-input-group">
                <input 
                    type="text" 
                    class="comment-input" 
                    id="commentInput" 
                    placeholder="أكتب اسمك..."
                >
                <textarea 
                    class="comment-input" 
                    id="messageInput" 
                    placeholder="أكتب رسالتك الخاصة..." 
                    style="resize: vertical; min-height: 44px;"
                ></textarea>
                <button class="comment-submit" onclick="addComment()">إرسال</button>
            </div>
            
            <div class="comments-list" id="commentsList"></div>
        </section>
    </div>

    <!-- Audio Element -->
    <audio id="birthdayAudio" style="display: none;">
        <source src="https://files.manuscdn.com/user_upload_by_module/session_file/310519663611380693/wnOAursbsVWumqUQ.mp3" type="audio/mpeg">
    </audio>

    <script>
        // ===== State Management =====
        let isAudioPlaying = false;
        let comments = JSON.parse(localStorage.getItem('birthdayComments')) || [];

        // ===== Countdown Timer =====
        function updateCountdown() {
            const targetDate = new Date('2026-06-23T00:00:00').getTime();
            const now = new Date().getTime();
            const difference = targetDate - now;

            if (difference > 0) {
                const days = Math.floor(difference / (1000 * 60 * 60 * 24));
                const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((difference % (1000 * 60)) / 1000);

                document.getElementById('days').textContent = String(days).padStart(2, '0');
                document.getElementById('hours').textContent = String(hours).padStart(2, '0');
                document.getElementById('minutes').textContent = String(minutes).padStart(2, '0');
                document.getElementById('seconds').textContent = String(seconds).padStart(2, '0');
            }
        }

        // ===== Music Control =====
        function toggleMusic() {
            const audio = document.getElementById('birthdayAudio');
            const btn = document.getElementById('musicBtn');
            const pulse = document.getElementById('musicPulse');

            if (isAudioPlaying) {
                audio.pause();
                btn.innerHTML = '🎵 اضغط هنا للتشغيل';
                pulse.style.display = 'none';
                isAudioPlaying = false;
            } else {
                audio.play().catch(err => {
                    console.error('Audio playback error:', err);
                    alert('عذراً، حدث خطأ في تشغيل الموسيقى');
                });
                btn.innerHTML = '⏸️ إيقاف الموسيقى';
                pulse.style.display = 'inline-block';
                isAudioPlaying = true;
                celebrateWithConfetti();
            }
        }

        // ===== Comments Management =====
        function addComment() {
            const nameInput = document.getElementById('commentInput');
            const messageInput = document.getElementById('messageInput');
            const name = nameInput.value.trim();
            const message = messageInput.value.trim();

            if (name && message) {
                const comment = {
                    id: Date.now(),
                    name: name,
                    message: message,
                    time: new Date().toLocaleString('ar-EG')
                };

                comments.unshift(comment);
                localStorage.setItem('birthdayComments', JSON.stringify(comments));
                
                nameInput.value = '';
                messageInput.value = '';
                
                renderComments();
                celebrateWithConfetti();
            }
        }

        function renderComments() {
            const commentsList = document.getElementById('commentsList');
            commentsList.innerHTML = '';

            comments.forEach((comment, index) => {
                const commentCard = document.createElement('div');
                commentCard.className = 'comment-card';
                commentCard.style.animation = `slideIn 0.5s ease-out ${index * 0.1}s both`;
                commentCard.innerHTML = `
                    <div class="comment-author">${escapeHtml(comment.name)}</div>
                    <div class="comment-text">${escapeHtml(comment.message)}</div>
                    <div class="comment-time">${comment.time}</div>
                `;
                commentsList.appendChild(commentCard);
            });
        }

        function escapeHtml(text) {
            const div = document.createElement('div');
            div.textContent = text;
            return div.innerHTML;
        }

        function scrollToComments() {
            document.getElementById('commentsSection').scrollIntoView({ behavior: 'smooth' });
        }

        // ===== Celebration Effects =====
        function celebrateWithConfetti() {
            const colors = ['#00d9ff', '#8338ec', '#ff006e', '#ffd700', '#ffed4e', '#00ff88'];
            const confettiCount = window.innerWidth > 768 ? 100 : 60;

            for (let i = 0; i < confettiCount; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * 100 + '%';
                confetti.style.top = '-10px';
                confetti.style.background = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.width = (Math.random() * 8 + 4) + 'px';
                confetti.style.height = confetti.style.width;
                confetti.style.borderRadius = '50%';
                confetti.style.boxShadow = `0 0 ${Math.random() * 10 + 5}px ${confetti.style.background}`;
                document.body.appendChild(confetti);

                setTimeout(() => confetti.remove(), 3000);
            }
        }

        // ===== Event Listeners =====
        document.getElementById('commentInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                document.getElementById('messageInput').focus();
            }
        });

        document.getElementById('messageInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter' && e.ctrlKey) {
                addComment();
            }
        });

        // ===== Initialization =====
        window.addEventListener('load', () => {
            updateCountdown();
            renderComments();
            
            setTimeout(() => {
                celebrateWithConfetti();
            }, 500);
        });

        // ===== Update Countdown Every Second =====
        setInterval(updateCountdown, 1000);

        // ===== Cleanup =====
        window.addEventListener('beforeunload', () => {
            const audio = document.getElementById('birthdayAudio');
            audio.pause();
        });
    </script>
</body>
</html>
