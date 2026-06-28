<html lang="id"><head>    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NEXUS • Generate Key TKC</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;700;900&family=Inter:wght@300;400;500;600&display=swap');
        
        :root {
            --primary: #00eaff;
            --accent: #c026d3;
            --dark: #0a0a1f;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: #05050f;
            color: #ffffff;
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }
        
        /* Deep Space Background */
        .space-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            background: 
                radial-gradient(circle at 30% 20%, rgba(120, 50, 255, 0.25) 0%, transparent 50%),
                radial-gradient(circle at 70% 80%, rgba(0, 234, 255, 0.2) 0%, transparent 60%);
        }
        
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: transparent;
        }
        
        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            box-shadow: 0 0 8px #fff;
            animation: twinkle 6s infinite alternate ease-in-out;
        }
        
        @keyframes twinkle {
            0% { opacity: 0.4; transform: scale(0.8); }
            100% { opacity: 1; transform: scale(1.1); }
        }
        
        /* Slow Moving Nebula */
        .nebula {
            position: fixed;
            inset: 0;
            background: radial-gradient(ellipse at center, rgba(139, 92, 246, 0.12) 0%, transparent 70%);
            animation: nebula-drift 180s linear infinite;
            z-index: -2;
            opacity: 0.6;
        }
        
        @keyframes nebula-drift {
            0% { transform: translate(0, 0) rotate(0deg); }
            100% { transform: translate(30px, -40px) rotate(8deg); }
        }
        
        header {
            position: relative;
            z-index: 10;
            text-align: center;
            padding: 4rem 1rem 3rem;
        }
        
        .logo-container {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 0 auto 1.5rem;
        }
        
        .logo {
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #00eaff, #c026d3, #00eaff);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5.5rem;
            box-shadow: 
                0 0 80px rgba(0, 234, 255, 0.8),
                0 0 160px rgba(192, 38, 211, 0.5);
            animation: logo-glow 4s ease-in-out infinite alternate;
            border: 4px solid rgba(255,255,255,0.2);
        }
        
        @keyframes logo-glow {
            from { box-shadow: 0 0 60px rgba(0, 234, 255, 0.7); }
            to { box-shadow: 0 0 120px rgba(192, 38, 211, 0.9); }
        }
        
        h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: 3.8rem;
            font-weight: 900;
            letter-spacing: 8px;
            background: linear-gradient(90deg, #00eaff, #e0f2fe, #c026d3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 50px rgba(0, 234, 255, 0.6);
        }
        
        .tagline {
            font-size: 1.35rem;
            margin-top: 0.8rem;
            opacity: 0.85;
            letter-spacing: 3px;
            font-weight: 300;
        }
        
        .container {
            position: relative;
            z-index: 10;
            max-width: 820px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }
        
        .card {
            background: rgba(15, 23, 42, 0.75);
            border-radius: 28px;
            padding: 3.5rem 3rem;
            text-align: center;
            border: 1px solid rgba(0, 234, 255, 0.25);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.6),
                        inset 0 0 60px rgba(0, 234, 255, 0.08);
            backdrop-filter: blur(16px);
        }
        
        .app-header {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }
        
        .app-icon {
            width: 130px;
            height: 130px;
            background: linear-gradient(135deg, #1e40af, #3b82f6, #60a5fa);
            border-radius: 28px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4.2rem;
            box-shadow: 0 0 50px rgba(59, 130, 246, 0.7);
            transition: transform 0.4s ease;
        }
        
        .card:hover .app-icon {
            transform: rotate(12deg) scale(1.08);
        }
        
        .info {
            text-align: left;
        }
        
        .info h2 {
            font-size: 2.1rem;
            margin-bottom: 0.4rem;
            font-weight: 600;
        }
        
        .version {
            color: var(--primary);
            font-family: 'Orbitron', sans-serif;
            font-size: 1.1rem;
            letter-spacing: 2px;
        }
        
        .download-section {
            margin: 2.5rem 0;
        }
        
        .download-btn {
            display: inline-flex;
            align-items: center;
            gap: 18px;
            background: linear-gradient(90deg, #00eaff, #67e8f9);
            color: #0a0a1f;
            font-size: 1.45rem;
            font-weight: 700;
            padding: 22px 68px;
            border-radius: 9999px;
            text-decoration: none;
            transition: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
            box-shadow: 0 20px 40px rgba(103, 232, 249, 0.4);
            position: relative;
            overflow: hidden;
            letter-spacing: 1px;
        }
        
        .download-btn:hover {
            transform: translateY(-6px) scale(1.04);
            box-shadow: 0 30px 60px rgba(103, 232, 249, 0.55);
        }
        
        .download-btn i {
            font-size: 1.8rem;
            transition: transform 0.4s ease;
        }
        
        .download-btn:hover i {
            transform: translateY(-4px);
        }
        
        .download-btn::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -100%;
            width: 50%;
            height: 200%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.9), transparent);
            animation: shimmer 5s linear infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-150%); }
            100% { transform: translateX(400%); }
        }
        
        .features {
            display: flex;
            justify-content: center;
            gap: 2.5rem;
            margin: 3rem 0;
            flex-wrap: wrap;
        }
        
        .feature {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.05rem;
            opacity: 0.9;
        }
        
        footer {
            text-align: center;
            padding: 4rem 1rem 2rem;
            opacity: 0.75;
            font-size: 0.95rem;
            z-index: 10;
            position: relative;
        }
        
        .status {
            margin-top: 2rem;
            font-size: 0.9rem;
            color: #67e8f9;
        }
    </style>
</head>
<body>
    <div class="space-bg"></div>
    <div class="nebula"></div>
    <div class="stars" id="stars"></div>
    
    <header>
        <div class="logo-container">
            <div class="logo">
                <i class="fas fa-satellite"></i>
            </div>
        </div>
        <h1>NEXUS</h1>
        <p class="tagline">COSMIC • KEY GENERATOR</p>
    </header>
    
    <div class="container">
        <div class="card">
            <div class="app-header">
                <div class="app-icon">
                    <i class="fas fa-key"></i>
                </div>
                <div class="info">
                    <h2>Generate_Key_Tkc</h2>
                    <p class="version">v1.0 • 31.94 MB • APK</p>
                    <p style="margin-top: 12px; opacity: 0.85;">
                        Aplikasi Generate Key TKC Terbaru
                    </p>
                </div>
            </div>
            
            <div class="download-section">
                <a href="https://download1351.mediafire.com/8mr0wg3rjshgIokNAtV1E7ZcNrm1LGdnKDDodJfeX9is11rBdpuZjfXEKwjwxOe0LuKj4BxZufZpx8ZOJneE2Q6xrxgmgkDU6onAAR8TAYHLaQDGeyESblVIMIHsBk5pfFuZ283GOm62DA0vXjeuDBIySxiKK65tfn2QTDzCXbVawUQ/953liuc0u88njnk/Generate_Key_Tkc.apk" 
                   class="download-btn" 
                   download="Generate_Key_Tkc.apk">
                    <i class="fas fa-rocket"></i>
                    DOWNLOAD NOW
                </a>
            </div>
            
            <div class="features">
                <div class="feature">
                    <i class="fas fa-bolt" style="color:#67e8f9"></i>
                    <span>Instant Download</span>
                </div>
                <div class="feature">
                    <i class="fas fa-shield-alt" style="color:#67e8f9"></i>
                    <span>Secure &amp; Verified</span>
                </div>
                <div class="feature">
                    <i class="fas fa-satellite-dish" style="color:#67e8f9"></i>
                    <span>Space Optimized</span>
                </div>
            </div>
            
            <div style="margin-top: 2rem; padding: 1rem; background: rgba(255,255,255,0.05); border-radius: 16px; font-size: 0.95rem;">
                <strong>🚀 Langsung terdownload tanpa iklan atau redirect</strong>
            </div>
        </div>
    </div>
    
    <footer>
        <p>NEXUS • 2026 • Powered by Deep Space</p>
        <div class="status">
            <i class="fas fa-circle" style="color:#22c55e"></i> Server Connected • Ready to Launch
        </div>
    </footer>

    <script>
        // Generate elegant stars
        function createStars() {
            const container = document.getElementById('stars');
            for (let i = 0; i < 450; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                
                const size = Math.random() * 2.8 + 0.8;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                
                star.style.left = `${Math.random() * 100}%`;
                star.style.top = `${Math.random() * 100}%`;
                
                const duration = Math.random() * 5 + 4;
                star.style.animationDuration = `${duration}s`;
                
                container.appendChild(star);
            }
        }
        
        window.onload = () => {
            createStars();
        };
    </script>
</body>
</html>
