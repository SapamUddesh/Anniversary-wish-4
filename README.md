<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 1st Anniversary, Sanaa!</title>
    <style>
        :root {
            --primary-pink: #ff4d6d;
            --soft-pink: #ffb3c1;
            --soft-cream: #fff0f3;
            --dark-text: #590d22;
        }

        body {
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--soft-cream);
            color: var(--dark-text);
            text-align: center;
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Floating Hearts Background */
        .heart-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .floating-heart {
            position: absolute;
            color: var(--soft-pink);
            font-size: 20px;
            animation: float 10s linear infinite;
            opacity: 0.6;
        }

        @keyframes float {
            0% { transform: translateY(110vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* Hero Section */
        header {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: linear-gradient(rgba(255, 240, 243, 0.7), rgba(255, 240, 243, 0.7)),
                        url('photo1.jpg'); /* Background Image */
            background-size: cover;
            background-position: center;
        }

        h1 {
            font-size: 3.5rem;
            margin: 10px 0;
            animation: heartbeat 1.5s ease-in-out infinite;
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Scroll Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 1.2s ease-out;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        .section {
            padding: 80px 20px;
            max-width: 900px;
            margin: 0 auto;
        }

        .message-card {
            background: white;
            padding: 40px;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(255, 77, 109, 0.1);
            line-height: 1.8;
            font-size: 1.1rem;
        }

        /* Photo Grid */
        .photo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .photo-grid img {
            width: 100%;
            height: 300px;
            object-fit: cover;
            border-radius: 20px;
            transition: 0.5s;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .photo-grid img:hover {
            transform: scale(1.03) rotate(1deg);
            box-shadow: 0 10px 25px rgba(255, 77, 109, 0.3);
        }

        /* Secret Button Styles */
        #gift-button {
            background-color: var(--primary-pink);
            color: white;
            border: none;
            padding: 18px 35px;
            font-size: 1.3rem;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 8px 20px rgba(255, 77, 109, 0.4);
            transition: all 0.3s ease;
            font-weight: bold;
        }

        #gift-button:hover {
            background-color: #e63958;
            transform: translateY(-3px) scale(1.05);
        }

        #secret-message {
            animation: fadeIn 1.5s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        footer {
            padding: 60px 20px;
            font-style: italic;
            opacity: 0.7;
        }
    </style>
</head>
<body>

    <div class="heart-bg" id="heartContainer"></div>

    <header>
        <p style="font-size: 1.4rem; letter-spacing: 2px;">TO MY DEAREST SANAA</p>
        <h1>Happy 1st Anniversary</h1>
        <p style="font-size: 1.2rem;">Our beautiful journey began 365 days ago.</p>
        <div style="margin-top: 20px; font-size: 2rem;">👇</div>
    </header>

    <div class="section reveal">
        <div class="message-card">
            <h2 style="color: var(--primary-pink);">My Favorite Year</h2>
            <p>Sanaa, this past year has been a dream come true. From our very first date to the small everyday moments, every second spent with you is a memory I cherish.</p>
            <p>Thank you for your kindness, your laughter, and for being the incredible person you are. I'm so lucky to call you mine.</p>
        </div>
    </div>

    <div class="section reveal">
        <h2 style="margin-bottom: 30px;">365 Days of Us</h2>
        <div class="photo-grid">
            <img src="photo1.jpg" alt="Memory 1">
            <img src="photo2.jpg" alt="Memory 2">
            <img src="photo3.jpg" alt="Memory 3">
        </div>
    </div>

    <div class="section reveal">
        <div id="secret-area">
            <button id="gift-button" onclick="revealSecret()">🎁 Click for a Secret Message</button>
            <div id="secret-message" style="display: none; margin-top: 30px;">
                <div class="message-card" style="border: 3px dashed var(--primary-pink); background-color: #fff9fa;">
                    <h3 style="color: var(--primary-pink);">My Promise To You</h3>
                    <p>No matter where life takes us, I promise to always hold your hand, listen to your stories, and love you more each day.</p>
                    <p style="font-size: 1.8rem;">❤️ Forever & Always ❤️</p>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>Made with love for Sanaa</p>
        <p>&copy; 2025 - 2026 Our First Year</p>
    </footer>

    <script>
        // Generate Floating Hearts
        const container = document.getElementById('heartContainer');
        const heartCount = 25;

        for (let i = 0; i < heartCount; i++) {
            const heart = document.createElement('div');
            heart.className = 'floating-heart';
            heart.innerHTML = '❤';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDelay = Math.random() * 10 + 's';
            heart.style.fontSize = (Math.random() * 15 + 15) + 'px';
            container.appendChild(heart);
        }

        // Scroll Reveal Logic
        const handleScroll = () => {
            const reveals = document.querySelectorAll('.reveal');
            reveals.forEach(reveal => {
                const windowHeight = window.innerHeight;
                const revealTop = reveal.getBoundingClientRect().top;
                const revealPoint = 100;

                if (revealTop < windowHeight - revealPoint) {
                    reveal.classList.add('active');
                }
            });
        };

        window.addEventListener('scroll', handleScroll);
        // Run once on load to show elements already in view
        window.addEventListener('load', handleScroll);

        // Secret Button Logic
        function revealSecret() {
            const message = document.getElementById('secret-message');
            const button = document.getElementById('gift-button');
            
            message.style.display = 'block';
            button.style.display = 'none';
            
            // Auto-scroll to the message
            setTimeout(() => {
                message.scrollIntoView({ behavior: 'smooth' });
            }, 100);
        }
    </script>
</body>
</html>
