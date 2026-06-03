# Watch_futuristik
Time
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Jam Tangan Futuristik | Holographic Timepiece</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            user-select: none; /* Mencegah teks terpilih untuk tampilan lebih murni */
        }

        body {
            min-height: 100vh;
            background: radial-gradient(circle at 20% 30%, #0a0f1e, #03050b);
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', 'Orbitron', 'Courier New', monospace;
            overflow: hidden;
            position: relative;
        }

        /* Efek grid holografis latar belakang */
        body::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(0, 255, 255, 0.05) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 255, 255, 0.05) 1px, transparent 1px);
            background-size: 40px 40px;
            pointer-events: none;
            z-index: 0;
        }

        /* Container jam dengan efek mengambang */
        .watch-container {
            position: relative;
            z-index: 10;
            perspective: 800px;
            animation: levitate 4s ease-in-out infinite;
        }

        @keyframes levitate {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-12px); }
            100% { transform: translateY(0px); }
        }

        /* Body jam - futuristik dengan lapisan kaca */
        .watch-face {
            width: 320px;
            height: 380px;
            background: rgba(10, 20, 30, 0.45);
            backdrop-filter: blur(15px);
            border-radius: 55px;
            box-shadow: 
                0 25px 45px rgba(0, 0, 0, 0.5),
                0 0 0 2px rgba(0, 255, 255, 0.25),
                inset 0 0 20px rgba(0, 255, 255, 0.2),
                0 0 40px rgba(0, 200, 255, 0.3);
            border: 1px solid rgba(0, 255, 255, 0.6);
            position: relative;
            transition: all 0.3s ease;
        }

        /* Efek pinggiran bercahaya saat hover */
        .watch-face:hover {
            box-shadow: 
                0 30px 55px rgba(0, 0, 0, 0.6),
                0 0 0 3px rgba(0, 255, 255, 0.5),
                inset 0 0 30px rgba(0, 255, 255, 0.3),
                0 0 60px rgba(0, 200, 255, 0.5);
            border-color: rgba(0, 255, 255, 0.9);
        }

        /* Lingkaran luar seperti bezel */
        .watch-face::before {
            content: "";
            position: absolute;
            top: 12px;
            left: 12px;
            right: 12px;
            bottom: 12px;
            border-radius: 46px;
            border: 1px solid rgba(0, 255, 255, 0.4);
            pointer-events: none;
            box-shadow: inset 0 0 8px rgba(0, 255, 255, 0.3);
        }

        /* Layar utama */
        .screen {
            width: 100%;
            height: 100%;
            padding: 25px 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            z-index: 2;
        }

        /* Header futuristik (logo / status) */
        .status-bar {
            display: flex;
            justify-content: space-between;
            font-size: 14px;
            letter-spacing: 1px;
            color: #0ff;
            text-shadow: 0 0 5px #0ff, 0 0 2px #0af;
            font-weight: 500;
            border-bottom: 1px solid rgba(0, 255, 255, 0.4);
            padding-bottom: 8px;
            margin-bottom: 15px;
        }

        .brand {
            font-family: 'Orbitron', monospace;
            font-weight: bold;
            background: linear-gradient(135deg, #0ff, #f0f);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: 1px;
        }

        .battery {
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .battery-icon {
            width: 20px;
            height: 10px;
            border: 1px solid #0ff;
            border-radius: 2px;
            position: relative;
            background: rgba(0, 255, 255, 0.2);
        }

        .battery-icon::after {
            content: "";
            position: absolute;
            right: -3px;
            top: 2px;
            width: 3px;
            height: 4px;
            background: #0ff;
            border-radius: 1px;
        }

        /* Waktu utama futuristik */
        .time-container {
            text-align: center;
            margin: 10px 0;
        }

        .digital-time {
            font-family: 'Orbitron', 'Courier New', monospace;
            font-size: 72px;
            font-weight: 700;
            letter-spacing: 8px;
            background: linear-gradient(135deg, #eef, #0ff, #6ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 15px rgba(0, 255, 255, 0.7);
            filter: drop-shadow(0 0 8px cyan);
        }

        .date-container {
            font-size: 18px;
            margin-top: 10px;
            font-family: 'Segoe UI', monospace;
            color: #bbffff;
            text-shadow: 0 0 6px #0ff;
            background: rgba(0, 20, 30, 0.5);
            display: inline-block;
            padding: 4px 18px;
            border-radius: 40px;
            backdrop-filter: blur(4px);
            letter-spacing: 1px;
        }

        /* Detak jantung animasi + info tambahan */
        .vital-stats {
            display: flex;
            justify-content: space-between;
            background: rgba(0, 20, 30, 0.6);
            backdrop-filter: blur(8px);
            border-radius: 35px;
            padding: 12px 20px;
            margin: 15px 0;
            border: 1px solid rgba(0, 255, 255, 0.3);
            gap: 15px;
        }

        .stat {
            flex: 1;
            text-align: center;
        }

        .stat-label {
            font-size: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: #8affff;
            font-weight: 300;
        }

        .stat-value {
            font-size: 20px;
            font-weight: bold;
            font-family: 'Orbitron', monospace;
            color: #0ff;
            text-shadow: 0 0 5px cyan;
            display: flex;
            align-items: baseline;
            justify-content: center;
            gap: 4px;
        }
        
        .heart-icon {
            color: #ff3366;
            text-shadow: 0 0 5px #ff3366;
            animation: pulse 1.2s ease infinite;
        }
        
        @keyframes pulse {
            0% { opacity: 0.6; transform: scale(1);}
            100% { opacity: 1; transform: scale(1.1);}
        }

        /* Lingkaran analog kecil futuristik */
        .analog-ring {
            display: flex;
            justify-content: center;
            margin-top: 10px;
        }
        
        .mini-dial {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: radial-gradient(circle at 30% 30%, rgba(0, 30, 40, 0.7), rgba(0, 0, 0, 0.4));
            border: 1px solid cyan;
            position: relative;
            box-shadow: 0 0 12px cyan;
        }
        
        .mini-hand {
            position: absolute;
            bottom: 50%;
            left: 50%;
            width: 2px;
            height: 28px;
            background: linear-gradient(to top, cyan, #0af);
            transform-origin: 50% 100%;
            border-radius: 2px;
        }
        
        .center-dot {
            position: absolute;
            width: 6px;
            height: 6px;
            background: #0ff;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            box-shadow: 0 0 6px #0ff;
        }

        /* Footer dengan loading bar cyber */
        .cyber-footer {
            margin-top: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 10px;
            color: #4affff;
        }
        
        .scan-line {
            width: 60%;
            height: 2px;
            background: linear-gradient(90deg, transparent, cyan, transparent);
            animation: scan 2s linear infinite;
        }
        
        @keyframes scan {
            0% { width: 0%; opacity: 0.3; }
            50% { width: 100%; opacity: 1; }
            100% { width: 0%; opacity: 0.3; }
        }

        /* Efek reflek kaca */
        .glass-reflection {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 55px;
            background: radial-gradient(circle at 30% 20%, rgba(255,255,255,0.15) 2%, transparent 70%);
            pointer-events: none;
            z-index: 3;
        }

        /* Responsif */
        @media (max-width: 400px) {
            .watch-face {
                width: 280px;
                height: 340px;
            }
            .digital-time {
                font-size: 56px;
                letter-spacing: 4px;
            }
        }
    </style>
</head>
<body>
<div class="watch-container">
    <div class="watch-face">
        <div class="glass-reflection"></div>
        <div class="screen">
            <div class="status-bar">
                <span class="brand">⚡ NEOCHRON ⚡</span>
                <div class="battery">
                    <span>98%</span>
                    <div class="battery-icon"></div>
                </div>
            </div>

            <div class="time-container">
                <div class="digital-time" id="clockDisplay">--:--:--</div>
                <div class="date-container" id="dateDisplay">--/--/----</div>
            </div>

            <div class="vital-stats">
                <div class="stat">
                    <div class="stat-label">❤️ HEART RATE</div>
                    <div class="stat-value"><span id="heartRate">72</span><span class="heart-icon"> bpm</span></div>
                </div>
                <div class="stat">
                    <div class="stat-label">🌡️ TEMP</div>
                    <div class="stat-value"><span id="tempValue">36.5</span>°C</div>
                </div>
                <div class="stat">
                    <div class="stat-label">🔋 ENERGY</div>
                    <div class="stat-value"><span id="energyLevel">97</span>%</div>
                </div>
            </div>

            <div class="analog-ring">
                <div class="mini-dial" id="miniDial">
                    <div class="mini-hand" id="secHand"></div>
                    <div class="center-dot"></div>
                </div>
            </div>

            <div class="cyber-footer">
                <span>◢ HOLO MODE ◣</span>
                <div class="scan-line"></div>
                <span>UTC+7</span>
            </div>
        </div>
    </div>
</div>

<script>
    (function() {
        // Elemen DOM
        const clockDisplay = document.getElementById('clockDisplay');
        const dateDisplay = document.getElementById('dateDisplay');
        const heartSpan = document.getElementById('heartRate');
        const tempSpan = document.getElementById('tempValue');
        const energySpan = document.getElementById('energyLevel');
        const secHand = document.getElementById('secHand');

        // Data vital dengan sedikit variasi realistis
        let heartRate = 72;
        let temperature = 36.5;
        let energy = 97;

        // Update detak jantung setiap 5 detik (simulasi sensor)
        function updateVitalSigns() {
            // Perubahan kecil dan realistis
            let heartVariation = Math.floor(Math.random() * 7) - 3; // -3 .. +3
            let newHeart = heartRate + heartVariation;
            if (newHeart >= 58 && newHeart <= 98) heartRate = newHeart;
            else if (newHeart < 58) heartRate = 58 + Math.floor(Math.random() * 3);
            else heartRate = 95 - Math.floor(Math.random() * 5);
            
            // Suhu berfluktuasi halus
            let tempVariation = (Math.random() * 0.3) - 0.15;
            let newTemp = temperature + tempVariation;
            if (newTemp >= 35.8 && newTemp <= 37.2) temperature = newTemp;
            else if (newTemp < 35.8) temperature = 35.9;
            else temperature = 37.0;
            
            // Energy sedikit berkurang tiap menit (simulasi pemakaian)
            if (energy > 5) {
                energy -= 0.05;
                if (energy < 0) energy = 100; // reset siklus
            } else {
                energy = 100;
            }
            
            // Update tampilan dengan 1 desimal untuk suhu
            heartSpan.innerText = Math.floor(heartRate);
            tempSpan.innerText = temperature.toFixed(1);
            energySpan.innerText = Math.floor(energy);
        }

        // Update jarum detik analog (mini dial)
        function updateAnalogSeconds(seconds) {
            if (secHand) {
                // 360 derajat / 60 detik = 6 derajat per detik
                const deg = seconds * 6;
                secHand.style.transform = `rotate(${deg}deg)`;
            }
        }

        // Format waktu dengan leading zero
        function formatTwoDigits(num) {
            return num < 10 ? '0' + num : num;
        }

        // Nama hari (dalam bahasa Indonesia / futuristik tetap pakai English biar keren)
        const weekdays = ['SUN', 'MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT'];
        const months = ['JAN', 'FEB', 'MAR', 'APR', 'MAY', 'JUN', 'JUL', 'AUG', 'SEP', 'OCT', 'NOV', 'DEC'];

        function updateClock() {
            const now = new Date();
            
            // Jam, menit, detik
            let hours = now.getHours();
            const minutes = now.getMinutes();
            const seconds = now.getSeconds();
            
            // Format 24 jam -> Tampilan futuristik dengan detik
            const timeStr = `${formatTwoDigits(hours)}:${formatTwoDigits(minutes)}:${formatTwoDigits(seconds)}`;
            clockDisplay.innerText = timeStr;
            
            // Update analog seconds hand
            updateAnalogSeconds(seconds);
            
            // Date: 25 JAN 2026 (contoh)
            const day = weekdays[now.getDay()];
            const date = now.getDate();
            const month = months[now.getMonth()];
            const year = now.getFullYear();
            const dateStr = `${day} ${date} ${month} ${year}`;
            dateDisplay.innerText = dateStr;
            
            // Efek tambahan: glitch kecil setiap menit berganti? Hanya gaya.
            // Setiap detik ke 0 atau 30 kita beri efek kecil pada time display (optional)
            if (seconds === 0) {
                clockDisplay.style.textShadow = "0 0 20px #f0f, 0 0 5px cyan";
                setTimeout(() => {
                    clockDisplay.style.textShadow = "0 0 15px rgba(0, 255, 255, 0.7)";
                }, 200);
            }
        }
        
        // Simulasi data 'sensor' lebih menarik dan update interval
        setInterval(() => {
            updateVitalSigns();
        }, 3800);   // tiap 3.8 detik update detak, suhu, energy
        
        // Jadwalkan update waktu setiap 100ms untuk keakuratan detik yg smooth pada jarum
        setInterval(() => {
            updateClock();
        }, 100);
        
        // inisialisasi pertama dan update vital
        updateClock();
        updateVitalSigns();
        
        // Efek ekstra: jam tangan menyesuaikan 'energy' berdasarkan jam (hanya untuk efek)
        // buat glitch dinamis
        setInterval(() => {
            const now = new Date();
            const hour = now.getHours();
            // if malam, kurangi energy lebih cepat (simulasi)
            if (hour >= 22 || hour <= 5) {
                // efek redup pada display? tidak mengganggu
                document.querySelector('.watch-face').style.boxShadow = "0 0 20px rgba(0, 150, 200, 0.4)";
            } else {
                document.querySelector('.watch-face').style.boxShadow = "0 25px 45px rgba(0, 0, 0, 0.5), 0 0 0 2px rgba(0, 255, 255, 0.25), inset 0 0 20px rgba(0, 255, 255, 0.2), 0 0 40px rgba(0, 200, 255, 0.3)";
            }
        }, 2000);
        
        // animasi untuk membuat detak jantung icon kedip lebih dinamis
        const heartIconElem = document.querySelector('.heart-icon');
        if(heartIconElem) {
            setInterval(() => {
                heartIconElem.style.transform = "scale(1.2)";
                setTimeout(() => { heartIconElem.style.transform = "scale(1)"; }, 300);
            }, 900);
        }
        
        // Optional: Menampilkan pesan di console biar makin ciamik
        console.log("⌚ Jam Tangan Futuristik siap! Hologram aktif.");
    })();
</script>
</body>
</html>
