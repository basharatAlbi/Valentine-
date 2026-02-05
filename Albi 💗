<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Albi ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Quicksand:wght@300;500;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #d6336c; /* Deep Rose */
            --secondary: #ff8787; /* Soft Pink */
            --accent: #ffb703; /* Gold */
            --bg-start: #fff0f3;
            --bg-end: #ffc9c9;
            --text-color: #630420;
            --room-wall: #fcd5ce;
            --room-floor: #e0a874;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            background: radial-gradient(circle at center, var(--bg-start), var(--bg-end));
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Quicksand', sans-serif;
            overflow: hidden;
            color: var(--text-color);
            user-select: none;
        }

        /* --- CONTAINER --- */
        .app-container {
            width: 100%;
            max-width: 420px;
            height: 100%;
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 20px;
            perspective: 1000px;
        }

        /* --- SCENE MANAGEMENT --- */
        .scene {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            display: none;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 1s ease-in-out;
            z-index: 10;
        }
        .scene.active { display: flex; opacity: 1; }

        /* --- BACKGROUND PARTICLES --- */
        .bg-particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 50%;
            animation: floatUp linear infinite;
            z-index: 0;
            pointer-events: none;
        }
        @keyframes floatUp {
            from { transform: translateY(100vh) scale(0.5); opacity: 0; }
            to { transform: translateY(-10vh) scale(1.2); opacity: 0; }
        }

        /* --- TYPOGRAPHY --- */
        h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 3rem;
            color: var(--primary);
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
            margin-bottom: 20px;
            line-height: 1.2;
        }
        p { font-size: 1.1rem; line-height: 1.6; font-weight: 500; }

        /* --- BUTTONS --- */
        .btn {
            background: white;
            color: var(--primary);
            border: 2px solid var(--secondary);
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1rem;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(214, 51, 108, 0.2);
            transition: transform 0.2s, opacity 0.5s;
            margin-top: 30px;
            opacity: 0; pointer-events: none;
        }
        .btn.visible { opacity: 1; pointer-events: all; animation: popIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .btn:active { transform: scale(0.95); }
        @keyframes popIn { from{transform:scale(0);} to{transform:scale(1);} }

        /* --- SCENE 1: MAGIC BOX --- */
        .magic-box {
            width: 140px; height: 120px;
            background: linear-gradient(135deg, #e64980, #a61e4d);
            border-radius: 15px;
            position: relative;
            cursor: pointer;
            box-shadow: 0 0 40px var(--secondary);
            display: flex; justify-content: center; align-items: center;
            font-size: 3rem;
            animation: bounce 2s infinite;
            z-index: 5;
        }
        .lid {
            position: absolute; top: -10px; left: -5px; width: 150px; height: 40px;
            background: #820b2e; border-radius: 10px;
            transform-origin: top; transition: transform 0.6s;
            z-index: 6;
        }
        .magic-box.open .lid { transform: rotateX(180deg) translateY(-20px); }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-15px); } }

        /* Letters */
        .letter {
            width: 60px; height: 40px; background: white;
            border: 1px solid var(--primary); border-radius: 4px;
            position: absolute; display: flex; justify-content: center; align-items: center;
            font-size: 1.2rem; cursor: pointer;
            box-shadow: 0 5px 10px rgba(0,0,0,0.1);
            transition: all 0.8s ease; opacity: 0; pointer-events: none; z-index: 1;
        }
        .magic-box.open .letter { opacity: 1; pointer-events: all; }

        /* Reading View */
        .paper-view {
            background: #fffdfc;
            width: 90%; padding: 25px;
            border-radius: 10px;
            border: 1px dashed var(--accent);
            box-shadow: 0 20px 50px rgba(0,0,0,0.15);
            transform: scale(0); transition: transform 0.5s;
            display: none; position: relative; z-index: 20;
        }
        .paper-view.show { display: block; transform: scale(1); }

        /* --- SCENE 2: MAGICIAN --- */
        .fingerprint {
            width: 90px; height: 120px;
            border: 2px solid var(--primary); border-radius: 30px;
            position: relative; display: flex; justify-content: center; align-items: center;
            font-size: 3rem; color: var(--primary);
            background: rgba(255,255,255,0.4);
            cursor: pointer; overflow: hidden; margin: 20px auto;
        }
        .scan-line {
            position: absolute; top: 0; left: 0; width: 100%; height: 5px;
            background: var(--accent); box-shadow: 0 0 15px var(--accent);
            animation: scan 1.5s linear infinite; display: none;
        }
        .scanning .scan-line { display: block; }
        @keyframes scan { 0% { top: 0; } 100% { top: 100%; } }
        
        .result-list { font-weight: bold; font-size: 1.1rem; min-height: 120px; }

        /* --- SCENE 3: HENRY'S HEART & ROOM --- */
        .heart-door-container {
            position: relative; width: 220px; height: 200px;
            display: flex; justify-content: center; align-items: center;
            transition: transform 1s;
        }
        .big-heart {
            width: 220px; height: 200px;
            background: var(--primary); position: absolute;
            transform: rotate(-45deg); display: flex; justify-content: center; align-items: center;
            box-shadow: 0 0 50px rgba(214, 51, 108, 0.6);
        }
        .big-heart::before, .big-heart::after {
            content: ""; width: 220px; height: 220px; background: var(--primary);
            border-radius: 50%; position: absolute;
        }
        .big-heart::before { top: -100px; left: 0; }
        .big-heart::after { left: 110px; top: 0; }

        /* Door Inside Heart */
        .heart-content {
            position: absolute; z-index: 10;
            transform: rotate(45deg); /* Counter rotate to stand straight */
            display: flex; flex-direction: column; align-items: center;
        }
        .door {
            width: 60px; height: 90px; background: #630420;
            border: 2px solid var(--accent);
            cursor: pointer; transition: 1s cubic-bezier(0.68, -0.55, 0.27, 1.55);
            display: flex; justify-content: center; align-items: center;
            overflow: hidden;
        }
        .knob { width: 8px; height: 8px; background: var(--accent); border-radius: 50%; margin-left: 30px; }

        /* --- COZY ROOM VISUALS (CSS ART) --- */
        .room-visual {
            width: 100%; height: 100%; background: var(--room-wall);
            position: relative; opacity: 0; transition: opacity 1s 0.5s;
            display: flex; flex-direction: column; justify-content: flex-end;
        }
        .floor { position: absolute; bottom: 0; width: 100%; height: 25%; background: var(--room-floor); border-top: 3px solid #b08d6e; }
        
        .window {
            position: absolute; top: 15px; left: 20px; width: 60px; height: 60px;
            background: #2b2d42; border: 3px solid #6d597a; border-radius: 5px;
            box-shadow: 0 0 15px rgba(255,255,255,0.4); overflow: hidden;
        }
        .moon { position: absolute; top: 5px; right: 5px; width: 15px; height: 15px; background: #fff; border-radius: 50%; box-shadow: 0 0 10px #fff; }
        
        .bed {
            position: absolute; bottom: 15px; right: 10px;
            width: 100px; height: 50px; background: #ff99ac;
            border-radius: 5px 5px 0 0; border-bottom: 5px solid #590d22;
        }
        .pillow { position: absolute; top: -5px; right: 5px; width: 30px; height: 15px; background: white; border-radius: 3px; }
        
        .sofa {
            position: absolute; bottom: 15px; left: 10px;
            width: 60px; height: 40px; background: #6a4c93;
            border-radius: 10px 10px 0 0;
        }
        
        .fairy-lights {
            position: absolute; top: 5px; width: 100%; height: 10px;
            display: flex; justify-content: space-around;
        }
        .light-bulb { width: 5px; height: 5px; background: var(--accent); border-radius: 50%; box-shadow: 0 0 10px var(--accent); animation: blink 2s infinite alternate; }

        /* Cleaning Sparkle Effect */
        .clean-shine {
            position: absolute; top: 0; left: -100%; width: 50%; height: 100%;
            background: linear-gradient(to right, transparent, rgba(255,255,255,0.6), transparent);
            transform: skewX(-20deg); pointer-events: none;
        }
        
        /* Door Opens into Room */
        .door.open {
            width: 320px; height: 300px;
            background: white; border-radius: 10px;
            border: 4px solid var(--accent);
            cursor: default;
        }
        .door.open .room-visual { opacity: 1; }
        .cleaning .clean-shine { animation: shineMove 1.5s forwards; }
        @keyframes shineMove { from { left: -100%; } to { left: 200%; } }
        @keyframes blink { from { opacity: 0.5; } to { opacity: 1; } }

        /* The Room Message Overlay */
        .room-msg-overlay {
            position: absolute; top: 15%; width: 90%; left: 5%;
            background: rgba(255,255,255,0.9); padding: 15px;
            border-radius: 10px; box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            opacity: 0; transform: translateY(-10px);
            transition: all 1s ease 1s; z-index: 50;
        }
        .cleaning .room-msg-overlay { opacity: 1; transform: translateY(0); }

        /* --- FINAL SCENE --- */
        .sparkle { position: absolute; width: 5px; height: 5px; background: gold; border-radius: 50%; animation: fade 1s forwards; }
        @keyframes fade { to { opacity: 0; transform: translateY(-20px); } }
        
        /* Music Control */
        .music-btn { position: absolute; top: 20px; right: 20px; background: rgba(255,255,255,0.6); padding: 8px; border-radius: 50%; cursor: pointer; border: none; z-index: 100; font-size: 1.2rem; }

    </style>
</head>
<body>

    <audio id="bgMusic" loop>
        <source src="love.mp3" type="audio/mpeg">
    </audio>
    <button class="music-btn" onclick="toggleMusic()">🎵</button>

    <div class="app-container">
        
        <div id="particles"></div>

        <div id="scene1" class="scene active">
            <h1 id="intro-text" style="opacity:0; transition:opacity 2s;">Henry wants to tell you something...</h1>
            
            <div class="magic-box" id="magicBox" onclick="openBox()" style="display:none;">
                <div class="lid"></div>✨
                <div class="letter" style="top:50%; left:50%;" onclick="openLetter(1)">💌</div>
                <div class="letter" style="top:50%; left:50%;" onclick="openLetter(2)">💌</div>
                <div class="letter" style="top:50%; left:50%;" onclick="openLetter(3)">💌</div>
                <div class="letter" style="top:50%; left:50%;" onclick="openLetter(4)">💌</div>
            </div>

            <div class="paper-view" id="letterPaper">
                <h2 style="font-family:'Great Vibes'; color:var(--primary);">My Dearest Albi,</h2>
                <br>
                <p id="typewriter-text"></p>
            </div>
            
            <button class="btn" id="btn-s1" onclick="nextScene('scene2')">Next Magic Step ✨</button>
        </div>


        <div id="scene2" class="scene">
            <h1>I am a Magician 🎩</h1>
            <p>I can tell who loves you the most.</p>
            <p style="font-size:0.9rem; opacity:0.7;">(Hold your thumb here)</p>
            
            <div class="fingerprint" id="fingerprint" 
                 onmousedown="startScan()" onmouseup="stopScan()" 
                 ontouchstart="startScan()" ontouchend="stopScan()">
                <div class="scan-line"></div>👍
            </div>
            
            <div class="result-list" id="reveal-text"></div>
            
            <button class="btn" id="btn-s2" onclick="nextScene('scene3')">Enter Henry's Heart ❤️</button>
        </div>


        <div id="scene3" class="scene">
            <h1 style="color:white; margin-bottom: 20px; z-index: 20;">Henry's Heart</h1>
            <p style="color:white; margin-bottom: 30px; z-index: 20;" id="enter-text">Enter Henry's Heart</p>
            
            <div class="heart-door-container">
                <div class="big-heart"></div>
                
                <div class="heart-content">
                    <div class="door" id="roomDoor" onclick="enterRoom()">
                        <div class="knob"></div>
                        
                        <div class="room-visual" id="cozyRoom">
                            <div class="clean-shine"></div>
                            
                            <div class="room-msg-overlay">
                                <p style="font-size:1.1rem; color:#d00000; font-weight:bold;">✨ Surprise! ✨</p>
                                <p style="font-size:0.9rem; margin-top:5px; color:#444;">
                                    "You don’t even clean your room properly...<br>
                                    so today <b>Henry</b> cleaned it for you!" 🧹
                                </p>
                            </div>

                            <div class="window"><div class="moon"></div></div>
                            <div class="fairy-lights">
                                <div class="light-bulb"></div><div class="light-bulb"></div><div class="light-bulb"></div>
                            </div>
                            <div class="floor"></div>
                            <div class="sofa"></div>
                            <div class="bed"><div class="pillow"></div></div>
                        </div>

                    </div>
                    <div style="margin-top:10px; color:white; font-weight:bold; cursor:pointer;" id="doorLabel">Tap Door</div>
                </div>
            </div>

            <button class="btn" id="btn-s3" style="margin-top: 150px; z-index:20;" onclick="nextScene('scene4')">Awww, Thanks! ❤️</button>
        </div>


        <div id="scene4" class="scene">
            <div class="paper-view show">
                <div id="emotional-text"></div>
            </div>
            <button class="btn" id="btn-s4" onclick="nextScene('scene5')">Final Message ❤️</button>
        </div>


        <div id="scene5" class="scene">
            <h1 style="font-size: 3.5rem; animation: floatBox 3s infinite;">Happy Valentine's Day Albi ❤️</h1>
            <br>
            <p style="font-size:1.2rem; max-width:300px;">Made with love, feelings, and truth...</p>
            <br>
            <h2 style="font-family:'Great Vibes'; color:var(--primary); font-size:2.5rem;">From Henry</h2>
            <br><br>
            <button class="btn visible" onclick="location.reload()">Replay Story 🔄</button>
        </div>

    </div>

    <script>
        /* --- UTILS --- */
        function typeWriter(text, elementId, speed, callback) {
            let i = 0;
            document.getElementById(elementId).innerHTML = "";
            function type() {
                if (i < text.length) {
                    document.getElementById(elementId).innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                } else if (callback) {
                    callback();
                }
            }
            type();
        }

        /* --- BACKGROUND PARTICLES --- */
        setInterval(() => {
            const p = document.createElement('div');
            p.className = 'bg-particle';
            p.style.left = Math.random() * 100 + '%';
            p.style.width = Math.random() * 10 + 5 + 'px';
            p.style.height = p.style.width;
            p.style.animationDuration = Math.random() * 5 + 5 + 's';
            document.getElementById('particles')?.appendChild(p);
            setTimeout(() => p.remove(), 10000);
        }, 500);

        /* --- NAVIGATION --- */
        function nextScene(id) {
            document.querySelectorAll('.scene').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
            
            if(id === 'scene4') {
                const msg = "Albi, cleaning jokes aside, I want you to know that my heart is your home. You bring warmth, light, and magic into my life. I admire everything about you.";
                typeWriter(msg, 'emotional-text', 40, () => {
                     document.getElementById('btn-s4').classList.add('visible');
                });
            }
            if(id === 'scene5') {
                createSparklesLoop();
            }
        }

        /* --- SCENE 1 LOGIC --- */
        setTimeout(() => {
            document.getElementById('intro-text').style.opacity = 1;
            setTimeout(() => { document.getElementById('magicBox').style.display = 'flex'; }, 2000);
        }, 500);

        function openBox() {
            const box = document.getElementById('magicBox');
            if(box.classList.contains('open')) return;
            box.classList.add('open');
            box.style.animation = 'none';

            const letters = document.querySelectorAll('.letter');
            letters.forEach((l, i) => {
                setTimeout(() => {
                    let x = (Math.random() - 0.5) * 250;
                    let y = (Math.random() - 0.5) * 200 - 50;
                    l.style.transform = `translate(${x}px, ${y}px) rotate(${Math.random()*20}deg)`;
                }, i * 100);
            });
        }

        function openLetter(id) {
            document.getElementById('magicBox').style.opacity = 0;
            const paper = document.getElementById('letterPaper');
            paper.classList.add('show');
            
            const msg = "Albi, you are the most beautiful part of my day. Your kindness and your smile make everything better. I promise to always care for you, tease you, and love you endlessly.";
            typeWriter(msg, 'typewriter-text', 35, () => {
                document.getElementById('btn-s1').classList.add('visible');
            });
        }

        /* --- SCENE 2 LOGIC --- */
        let scanTimer;
        function startScan() {
            document.getElementById('fingerprint').querySelector('.scan-line').style.display = 'block';
            document.getElementById('reveal-text').innerHTML = "Scanning heart... ✨";
            scanTimer = setTimeout(revealResults, 2000);
        }
        function stopScan() {
           
