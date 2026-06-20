# .::CSCSD::. gg-Bio-clup
موقع السيرفر فى دسكورد  وسيرفر كنتر ويوتيوب 
<!DOCTYPE html>
<html dir="rtl" lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>.::CSCSD::. - سيرفر Counter-Strike</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            overflow-x: hidden;
            color: white;
        }

        /* زر Discord في الأعلى */
        .top-bar {
            width: 100%;
            padding: 15px;
            text-align: center;
            background: rgba(88, 101, 242, 0.15);
            border-bottom: 1px solid rgba(88, 101, 242, 0.3);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .discord-btn-small {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: linear-gradient(45deg, #5865F2, #7289DA);
            color: white;
            padding: 10px 25px;
            text-decoration: none;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(88, 101, 242, 0.3);
        }

        .discord-btn-small:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(88, 101, 242, 0.5);
        }

        /* المحتوى الرئيسي */
        .main-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            width: 100%;
            padding: 40px 20px;
        }

        .container {
            text-align: center;
            padding: 60px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            animation: fadeIn 1.5s ease-out;
            max-width: 800px;
            width: 90%;
            margin-bottom: 30px;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .logo {
            font-size: 80px;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        h1 {
            color: #00d4ff;
            font-size: 3.5rem;
            margin-bottom: 15px;
            text-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
            letter-spacing: 2px;
        }

        .subtitle {
            color: #a0a0a0;
            font-size: 1.5rem;
            margin-bottom: 40px;
        }

        .welcome-text {
            color: #ffffff;
            font-size: 2rem;
            margin-bottom: 30px;
            padding: 20px 40px;
            background: linear-gradient(45deg, rgba(0, 212, 255, 0.1), rgba(0, 153, 204, 0.1));
            border-radius: 15px;
            border: 1px solid rgba(0, 212, 255, 0.3);
        }

        /* قسم شرح السيرفر */
        .server-info {
            text-align: right;
            margin-top: 40px;
            padding: 30px;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .server-info h2 {
            color: #00d4ff;
            font-size: 2rem;
            margin-bottom: 20px;
            text-align: center;
            border-bottom: 2px solid rgba(0, 212, 255, 0.3);
            padding-bottom: 10px;
        }

        .server-info h3 {
            color: #7289DA;
            font-size: 1.3rem;
            margin: 25px 0 15px 0;
        }

        .server-info p, .server-info li {
            color: #ccc;
            font-size: 1rem;
            line-height: 1.8;
            margin-bottom: 10px;
        }

        .server-info ul {
            padding-right: 20px;
            margin-bottom: 15px;
        }

        .server-info li {
            margin-bottom: 8px;
        }

        .code-block {
            background: #1a1a2e;
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 10px;
            padding: 15px;
            margin: 15px 0;
            font-family: 'Courier New', monospace;
            font-size: 0.85rem;
            color: #00ff88;
            direction: ltr;
            text-align: left;
            overflow-x: auto;
        }

        .highlight {
            color: #ffd700;
            font-weight: bold;
        }

        .note {
            background: rgba(255, 215, 0, 0.1);
            border-right: 4px solid #ffd700;
            padding: 15px;
            margin: 15px 0;
            border-radius: 0 10px 10px 0;
        }

        /* زر Discord في الوسط */
        .discord-btn-large {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: linear-gradient(45deg, #5865F2, #7289DA);
            color: white;
            padding: 18px 40px;
            text-decoration: none;
            border-radius: 50px;
            font-size: 1.3rem;
            font-weight: bold;
            margin: 20px 0;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(88, 101, 242, 0.4);
            border: 2px solid rgba(255, 255, 255, 0.1);
        }

        .discord-btn-large:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 40px rgba(88, 101, 242, 0.6);
        }

        .tagline {
            color: #888;
            font-size: 1rem;
            margin-top: 30px;
        }

        /* Footer في الأسفل */
        .footer {
            width: 100%;
            padding: 30px;
            text-align: center;
            background: rgba(0, 0, 0, 0.3);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
        }

        .footer-text {
            color: #888;
            font-size: 0.9rem;
            margin-bottom: 15px;
        }

        .discord-btn-footer {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: linear-gradient(45deg, #5865F2, #7289DA);
            color: white;
            padding: 12px 30px;
            text-decoration: none;
            border-radius: 25px;
            font-size: 1.1rem;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(88, 101, 242, 0.3);
        }

        .discord-btn-footer:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(88, 101, 242, 0.5);
        }

        /* تأثير الجزيئات */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(0, 212, 255, 0.5);
            border-radius: 50%;
            animation: float 15s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
        }

        /* Responsive */
        @media (max-width: 600px) {
            h1 { font-size: 2.5rem; }
            .welcome-text { font-size: 1.5rem; }
            .container { padding: 40px 20px; }
            .server-info h2 { font-size: 1.5rem; }
        }
    </style>
</head>
<body>
    <!-- رابط Discord في الأعلى -->
    <div class="top-bar">
        <a href="https://discord.gg/vwfpRHkQ5" target="_blank" class="discord-btn-small">
            💬 انضم لـ Discord
        </a>
    </div>

    <div class="particles" id="particles"></div>

    <!-- المحتوى الرئيسي -->
    <div class="main-content">
        <div class="container">
            <div class="logo">🎮</div>
            <h1>.::CSCSD::.</h1>
            <p class="subtitle">Counter-Strike Community Server</p>
            
            <div class="welcome-text">
                مرحبا فى موقع .::CSCSD::.
            </div>
            
            <!-- زر Discord في الوسط -->
            <a href="https://discord.gg/vwfpRHkQ5" target="_blank" class="discord-btn-large">
                <span>💬</span>
                انضم لسيرفر Discord
            </a>
            
            <p class="tagline">
                🔥 أفضل تجربة لعب Counter-Strike 2 🔥
            </p>

            <!-- ═══════════════════════════════════════ -->
            <!-- ═══  شرح مفصل عن سيرفر Counter-Strike  ═══ -->
            <!-- ═══════════════════════════════════════ -->
            
            <div class="server-info">
                <h2>📚 دليل إنشاء سيرفر Counter-Strike</h2>

                <h3>🎮 ما هو سيرفر Counter-Strike؟</h3>
                <p>
                    سيرفر <span class="highlight">Counter-Strike</span> هو جهاز كمبيوتر يعمل كـ "مضيف" للعبة، 
                    يسمح للاعبين من جميع أنحاء العالم بالانضمام واللعب معاً. 
                    السيرفر يتحكم في قواعد اللعبة، الخرائط، عدد اللاعبين، والمزيد.
                </p>

                <h3>🔄 الفرق بين CS:GO و CS2</h3>
                <ul>
                    <li><span class="highlight">CS:GO</span> - اللعبة القديمة (2012-2023)، لا تدعمها Valve بعد الآن</li>
                    <li><span class="highlight">CS2</span> - الإصدار الجديد (2023-الآن)، محرك Source 2، رسومات محسنة</li>
                </ul>
                <div class="note">
                    ⚠️ <strong>ملاحظة:</strong> CS:GO أصبحت غير متوفرة رسمياً. نوصي بـ CS2 للسيرفرات الجديدة.
                </div>

                <h3>🛠️ متطلبات تشغيل السيرفر</h3>
                <ul>
                    <li><strong>نظام التشغيل:</strong> Linux Ubuntu 20.04/22.04 (مستحسن) أو Windows Server</li>
                    <li><strong>المعالج:</strong> 2+ Cores (4+ مستحسن)</li>
                    <li><strong>الرام:</strong> 4GB كحد أدنى (8GB+ مستحسن)</li>
                    <li><strong>التخزين:</strong> 40GB SSD كحد أدنى</li>
                    <li><strong>الشبكة:</strong> سرعة رفع 10 Mbps+</li>
                </ul>

                <h3>☁️ خيارات الاستضافة</h3>
                
                <h3 style="color: #ffd700; font-size: 1.1rem;">1. VPS (الأفضل للاستقرار)</h3>
                <p>سيرفر افتراضي خاص بك، يعمل 24/7:</p>
                <ul>
                    <li><strong>Hetzner:</strong> ~5€/شهر - أفضل قيمة</li>
                    <li><strong>OVHcloud:</strong> ~6€/شهر - داتاسنترات قريبة</li>
                    <li><strong>Contabo:</strong> ~6€/شهر - رام كبير</li>
                </ul>

                <h3 style="color: #ffd700; font-size: 1.1rem;">2. استضافة مجانية (Oracle Cloud)</h3>
                <p>سيرفر مجاني 100%:</p>
                <ul>
                    <li>4 CPU / 24GB RAM (ARM)</li>
                    <li>200GB تخزين</li>
                    <li>مجاني للأبد!</li>
                </ul>
                <div class="note">
                    🔗 <strong>الرابط:</strong> cloud.oracle.com/free
                </div>

                <h3>📥 خطوات تثبيت CS2 Server على Linux</h3>

                <h3 style="color: #ffd700; font-size: 1.1rem;">الخطوة 1: تحديث النظام</h3>
                <div class="code-block">
sudo apt update && sudo apt upgrade -y
                </div>

                <h3 style="color: #ffd700; font-size: 1.1rem;">الخطوة 2: تثبيت المتطلبات</h3>
                <div class="code-block">
sudo apt install -y screen wget tar lib32gcc-s1 libcurl4
                </div>

                <h3 style="color: #ffd700; font-size: 1.1rem;">الخطوة 3: تثبيت SteamCMD</h3>
                <div class="code-block">
mkdir -p /opt/steam && cd /opt/steam
wget https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz
tar -xvzf steamcmd_linux.tar.gz
                </div>

                <h3 style="color: #ffd700; font-size: 1.1rem;">الخطوة 4: تحميل سيرفر CS2</h3>
                <div class="code-block">
./steamcmd.sh +force_install_dir /opt/cs2-server +login anonymous +app_update 730 validate +quit
                </div>
                <div class="note">
                    ⚠️ <strong>تنبيه:</strong> CS2 يتطلب <span class="highlight">Steam Game Server Login Token</span>. 
                    احصل عليه من: steamcommunity.com/dev/managegameservers
                </div>

                <h3 style="color: #ffd700; font-size: 1.1rem;">الخطوة 5: تشغيل السيرفر</h3>
                <div class="code-block">
cd /opt/cs2-server/game/bin/linuxsteamrt64
./cs2 -dedicated -console -usercon +game_type 0 +game_mode 1 +map de_dust2 -maxplayers 10 +sv_setsteamaccount YOUR_TOKEN_HERE
                </div>

                <h3>🔧 تشغيل السيرفر 24/7 (Systemd)</h3>
                <p>أنشئ ملف الخدمة:</p>
                <div class="code-block">
sudo nano /etc/systemd/system/cs2-server.service
                </div>

                <p>أضف المحتوى:</p>
                <div class="code-block">
[Unit]
Description=CS2 Dedicated Server
After=network.target

[Service]
Type=simple
User=root
WorkingDirectory=/opt/cs2-server/game/bin/linuxsteamrt64
ExecStart=/opt/cs2-server/game/bin/linuxsteamrt64/cs2 -dedicated -console -usercon +game_type 0 +game_mode 1 +map de_dust2 -maxplayers 10 +sv_setsteamaccount YOUR_TOKEN_HERE
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target
                </div>

                <p>تفعيل الخدمة:</p>
                <div class="code-block">
sudo systemctl daemon-reload
sudo systemctl enable cs2-server
sudo systemctl start cs2-server
                </div>

                <h3>🌐 فتح المنافذ (Port Forwarding)</h3>
                <p>المنافذ المطلوبة:</p>
                <ul>
                    <li><span class="highlight">UDP:</span> 27015-27050</li>
                    <li><span class="highlight">TCP:</span> 27015</li>
                </ul>
                <div class="note">
                    💡 <strong>نصيحة:</strong> افتح هذه المنافذ في جدار الحماية (UFW):
                    <div class="code-block" style="margin-top: 10px;">
sudo ufw allow 27015:27050/udp
sudo ufw allow 27015/tcp
sudo ufw reload
                    </div>
                </div>

                <h3>🎮 أنواع السيرفرات</h3>
                <ul>
                    <li><strong>Casual:</strong> +game_type 0 +game_mode 0</li>
                    <li><strong>Competitive:</strong> +game_type 0 +game_mode 1</li>
                    <li><strong>Wingman:</strong> +game_type 0 +game_mode 2</li>
                    <li><strong>Deathmatch:</strong> +game_type 1 +game_mode 2</li>
                    <li><strong>Custom:</strong> +game_type 3 +game_mode 0</li>
                </ul>

                <h3>🗺️ خرائط شائعة</h3>
                <ul>
                    <li>de_dust2 - الكلاسيكية</li>
                    <li>de_mirage - الأكثر شعبية</li>
                    <li>de_inferno - تكتيكية</li>
                    <li>de_nuke - عمودية</li>
                    <li>de_overpass - حديثة</li>
                    <li>de_ancient - جديدة</li>
                </ul>

                <h3>🔒 نصائح الأمان</h3>
                <ul>
                    <li>استخدم كلمة مرور قوية للـ VPS</li>
                    <li>فعّل جدار الحماية (UFW)</li>
                    <li>حدّث السيرفر باستمرار</li>
                    <li>استخدم RCON password قوي</li>
                    <li>راقب سجلات الدخول (logs)</li>
                </ul>

                <h3>📞 الدعم والمساعدة</h3>
                <p>
                    لو عندك أي مشكلة، انضم لسيرفر Discord بتاعنا:
                </p>
                <a href="https://discord.gg/vwfpRHkQ5" target="_blank" class="discord-btn-large" style="margin-top: 20px;">
                    <span>💬</span>
                    انضم لسيرفر Discord للمساعدة
                </a>
            </div>
        </div>
    </div>

    <!-- Footer في الأسفل -->
    <div class="footer">
        <p class="footer-text">© 2026 .::CSCSD::. - جميع الحقوق محفوظة</p>
        <a href="https://discord.gg/vwfpRHkQ5" target="_blank" class="discord-btn-footer">
            💬 تواصل معنا على Discord
        </a>
    </div>

    <script>
        // إنشاء جزيئات متحركة
        const particlesContainer = document.getElementById('particles');
        
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (10 + Math.random() * 10) + 's';
            particlesContainer.appendChild(particle);
        }
    </script>
</body>
</html>
