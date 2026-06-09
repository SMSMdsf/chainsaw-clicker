<!DOCTYPE html>
<html>
<head>
    <title>Zombie.io | Survival Squad: Local Edition</title>
    <style>
        body { background: #050505; color: #00ff00; font-family: 'Courier New', monospace; text-align: center; margin: 0; padding: 0; overflow: hidden; user-select: none; }
        #game-wrapper { perspective: 1000px; perspective-origin: 50% 20%; width: 100vw; height: 85vh; display: none; position: relative; }
        canvas { background: #111411; border: 4px solid #ff3300; cursor: crosshair; margin: 30px auto; display: block; box-shadow: 0 20px 40px rgba(255, 51, 0, 0.5); transform: rotateX(45deg); transform-style: preserve-3d; }
        .screen { padding: 40px; max-width: 700px; margin: auto; height: 80vh; display: flex; flex-direction: column; justify-content: center; align-items: center; }
        .char-btn { padding: 12px; margin: 6px; background: #1a1a1a; color: #00ff00; border: 2px solid #00ff00; cursor: pointer; font-size: 15px; width: 250px; text-transform: uppercase; font-weight: bold; }
        .char-btn:hover { background: #00ff00; color: black; box-shadow: 0 0 15px #00ff00; }
        #ui-box { background: rgba(0,0,0,0.9); padding: 12px; border-bottom: 3px solid #ff3300; display: none; justify-content: space-around; font-size: 16px; font-weight: bold; align-items: center; }
        .btn-upgrade { background: #ff3300; color: white; border: none; padding: 8px 16px; cursor: pointer; font-weight: bold; border-radius: 4px; }
        .btn-upgrade:disabled { background: #444; color: #777; cursor: not-allowed; }
        .btn-menu { background: #00ff00; color: black; border: none; padding: 8px 16px; cursor: pointer; font-weight: bold; border-radius: 4px; margin: 0 5px; }
        .btn-menu:hover { background: #00cc00; }
        #cutscene-text { font-size: 22px; line-height: 1.6; color: #ffffff; text-shadow: 0 0 8px #ff0000; min-height: 150px; }
        .next-btn { background: #fff; color: #000; border: none; padding: 10px 25px; font-size: 18px; cursor: pointer; font-weight: bold; margin-top: 20px; }
        .hp-bar-container { width: 100px; background: #330000; border: 2px solid #ff0000; height: 14px; border-radius: 4px; display: inline-block; vertical-align: middle; }
        #ui-hp-fill { width: 100%; background: #00ff00; height: 100%; transition: width 0.1s; }
        .name-input { padding: 12px; font-size: 18px; background: #111; color: #0f0; border: 2px solid #0f0; text-align: center; margin-bottom: 20px; font-family: monospace; width: 280px; }
        
        /* Overlay Pause Panel Layout */
        #pause-overlay { display: none; position: absolute; top: 0; left: 0; width: 100vw; height: 85vh; background: rgba(0,0,0,0.8); z-index: 100; flex-direction: column; justify-content: center; align-items: center; }
        .menu-title { font-size: 36px; color: #ff3300; margin-bottom: 30px; text-shadow: 0 0 10px #ff3300; }
    </style>
</head>
<body>

    <!-- CAPTIONS TIMELINE COMPONENT -->
    <div id="cutscene-screen" class="screen">
        <h2 style="color: #ff3300; font-size: 32px;">⚠️ EMERGENCY BROADCAST ⚠️</h2>
        <div id="cutscene-text">Loading transmission...</div>
        <button id="cutscene-btn" class="next-btn" onclick="nextCutscene()">NEXT</button>
    </div>

    <!-- CHARACTER AND PROFILE SELECTION MATRIX -->
    <div id="menu-screen" class="screen" style="display:none;">
        <h1>THE OUTBREAK HAS BEGUN</h1>
        <h3>CHOOSE YOUR NAME & SURVIVOR:</h3>
        <input type="text" id="player-custom-name" class="name-input" value="Survivor" maxlength="12" placeholder="ENTER PLAYER NAME">
        <div style="display: flex; flex-wrap: wrap; justify-content: center; max-width: 600px;">
            <button class="char-btn" onclick="startGame('Shuceeb', '#00ffff', 'speed')">Shuceeb (Super Speed)</button>
            <button class="char-btn" onclick="startGame('Aadam', '#ff0055', 'tank')">Aadam (Heavy Armor)</button>
            <button class="char-btn" onclick="startGame('Yakoub', '#ffcc00', 'looter')">Yakoub (Double Cash)</button>
            <button class="char-btn" onclick="startGame('Daiyon', '#9900ff', 'tactical')">Daiyon (Gun Lvl 5 Start)</button>
            <button class="char-btn" onclick="startGame('Arafat', '#00ff66', 'medic')">Arafat (Auto Heal)</button>
            <button class="char-btn" onclick="startGame('Naythan', '#ff6600', 'lucky')">Naythan (Insta-Kill Chance)</button>
        </div>
    </div>

    <!-- GAME DASHBOARD HEADS UP DISPLAY -->
    <div id="ui-box">
        <div>Name: <span id="ui-display-name" style="color:#0f0;">---</span> (<span id="ui-class">---</span>)</div>
        <div>HP: <div class="hp-bar-container"><div id="ui-hp-fill"></div></div></div>
        <div>Round: <span id="ui-round" style="color:red;">1</span> <span id="ui-mode-tag" style="color:#777;">(Story)</span></div>
        <div>Weapon: <span id="ui-weapon" style="color: #ffcc00;">M1911 Pistol</span></div>
        <div>Ammo: <span id="ui-ammo" style="color: #ff00ff;">7/7</span> <span id="ui-reloading" style="color: red; display: none;">[RELOAD]</span></div>
        <div>Gun Level: <span id="ui-lvl">1</span>/100</div>
        <div>Cash: $<span id="ui-cash">0</span></div>
        <button id="up-btn" class="btn-upgrade" onclick="buyUpgrade()">UPGRADE GUN ($50)</button>
        <button class="btn-menu" style="background:#ffcc00;" onclick="togglePause()">PAUSE</button>
    </div>

    <!-- MAIN INTERACTIVE WRAPPER AND INTERFACE CANVAS -->
    <div id="game-wrapper">
        <!-- THE PAUSE DIALOG MENU OVERLAY PANEL -->
        <div id="pause-overlay">
            <div class="menu-title">GAME PAUSED</div>
            <button class="char-btn" style="border-color:#0f0; color:#0f0;" onclick="togglePause()">RESUME RUN</button>
            <button class="char-btn" style="border-color:#ff3300; color:#ff3300;" onclick="returnToMenu()">LEAVE TO MENU</button>
        </div>
        <canvas id="gameCanvas" width="800" height="550"></canvas>
    </div>

    <script>
        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        function playSound(type) {
            if (audioCtx.state === 'suspended') audioCtx.resume();
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.connect(gain); gain.connect(audioCtx.destination);
            if (type === 'shoot') {
                osc.type = 'sawtooth'; osc.frequency.setValueAtTime(lvl >= 10 ? 110 : 180, audioCtx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(30, audioCtx.currentTime + 0.12);
                gain.gain.setValueAtTime(0.08, audioCtx.currentTime);
                gain.gain.linearRampToValueAtTime(0, audioCtx.currentTime + 0.12);
                osc.start(); osc.stop(audioCtx.currentTime + 0.12);
            } else if (type === 'hit') {
                osc.type = 'square'; osc.frequency.setValueAtTime(60, audioCtx.currentTime);
                gain.gain.setValueAtTime(0.12, audioCtx.currentTime);
                gain.gain.linearRampToValueAtTime(0, audioCtx.currentTime + 0.08);
                osc.start(); osc.stop(audioCtx.currentTime + 0.08);
            } else if (type === 'reload') {
                osc.type = 'triangle'; osc.frequency.setValueAtTime(150, audioCtx.currentTime);
                osc.frequency.linearRampToValueAtTime(300, audioCtx.currentTime + 0.3);
                gain.gain.setValueAtTime(0.1, audioCtx.currentTime);
                gain.gain.linearRampToValueAtTime(0, audioCtx.currentTime + 0.3);
                osc.start(); osc.stop(audioCtx.currentTime + 0.3);
            }
        }

        const cutsceneLines = [
            "[SCENE 1: THE HOMEFRONT]\n\nShuceeb, Aadam, Yakoub, Daiyon, Arafat, and Naythan were chilled out at their house playing video games together...",
            "[SCENE 2: INTERRUPTION]\n\nSuddenly, the power cuts out! The TV flashes white static, forcing an emergency news transmission onto the screen.",
            "[SCENE 3: TRUMP BROADCAST]\n\nMr. Trump appears on camera: 'My fellow Americans... a rogue scientist inside our classified labs accidentally cracked open a secret Alien Egg asset...'",
            "[SCENE 4: MOBILIZATION]\n\nThe viral spore is turning citizens into mutants! Complete Rounds 1-100 to win, or push into Endless mode!'"
        ];
        let cutsceneIdx = 0;

        function showCaption() {
            document.getElementById("cutscene-text").innerText = cutsceneLines[cutsceneIdx];
            document.getElementById("cutscene-btn").innerText = cutsceneIdx === cutsceneLines.length - 1 ? "START SURVIVAL SQUAD" : "NEXT CAPTION";
        }

        function nextCutscene() {
            if (audioCtx.state === 'suspended') audioCtx.resume();
            cutsceneIdx++;
            if (cutsceneIdx < cutsceneLines.length) { showCaption(); } 
            else {
                document.getElementById("cutscene-screen").style.display = "none";
                document.getElementById("menu-screen").style.display = "flex";
            }
        }
        window.onload = function() { showCaption(); };

        const canvas = document.getElementById("gameCanvas");
        const ctx = canvas.getContext("2d");
        let cash = 0, lvl = 1, cost = 50, hp = 100, currentWeapon = "M1911 Pistol";
        let player = { x: 400, y: 275, size: 20, color: '#00ffff', speed: 4, angle: 0, perk: '' };
        let bullets = [], enemyBullets = [], zombies = [], bosses = [];
        let keys = {}, mouseX = 0, mouseY = 0;
        
        let isGameRunning = false, isPaused = false, zombieInterval, medicInterval;
        let currentAmmo = 7, maxAmmo = 7, isReloading = false, reloadTimer = 0, weaponCooldown = 0;
        let tier1Defeated = false, tier2Defeated = false, tier3Defeated = false, tier4Defeated = false;
        
        // Progression tracking variables
        let gameRound = 1, zombiesKilledInRound = 0, zombiesRequiredForRound = 10, bossActive = false;

        function startGame(className, color, perk) {
            cash = 0; lvl = 1; cost = 50; hp = 100; currentWeapon = "M1911 Pistol";
            gameRound = 1; zombiesKilledInRound = 0; zombiesRequiredForRound = 10;
            bullets = []; enemyBullets = []; zombies = []; bosses = []; keys = {}; 
            bossActive = false; isPaused = false;
            tier1Defeated = false; tier2Defeated = false; tier3Defeated = false; tier4Defeated = false;
            isReloading = false; reloadTimer = 0; weaponCooldown = 0;
            player.x = 400; player.y = 275;
            player.color = color; player.perk = perk;
            player.speed = perk === 'speed' ? 5.5 : 4;
            if (perk === 'tactical') { lvl = 5; cost = 120; }
            
            checkWeaponTier();
            currentAmmo = maxAmmo;
            
            let customName = document.getElementById("player-custom-name").value.trim();
            if(!customName) customName = "Survivor";
            document.getElementById("ui-display-name").innerText = customName;
            document.getElementById("ui-class").innerText = className;
            
            document.getElementById("menu-screen").style.display = "none";
            document.getElementById("ui-box").style.display = "flex";
            document.getElementById("game-wrapper").style.display = "block";
            document.getElementById("pause-overlay").style.display = "none";
            
            isGameRunning = true;
            zombieInterval = setTimeout(spawnZombie, 1000);
            if (perk === 'medic') medicInterval = setInterval(() => { if(hp < 100 && !isPaused) { hp = Math.min(100, hp + 5); updateUI(); } }, 3000);
            
            requestAnimationFrame(gameLoop);
        }

        function togglePause() {
            if (!isGameRunning) return;
            isPaused = !isPaused;
            document.getElementById("pause-overlay").style.display = isPaused ? "flex" : "none";
        }

        function returnToMenu() {
            isGameRunning = false; isPaused = false;
            clearTimeout(zombieInterval);
            clearInterval(medicInterval);
            document.getElementById("ui-box").style.display = "none";
            document.getElementById("game-wrapper").style.display = "none";
            document.getElementById("menu-screen").style.display = "flex";
        }

        function buyUpgrade() {
            if (cash >= cost && lvl < 100 && !isPaused) {
                cash -= cost; lvl++; cost = Math.floor(cost * 1.25);
                if (player.perk === 'speed') player.speed += 0.3;
                else player.speed += 0.2;
                checkWeaponTier();
                updateUI();
            }
        }

        function triggerMilestoneBoss() {
            bossActive = true;
            zombies = [];
            let tierNum = Math.floor(gameRound / 10);
            bosses.push({ 
                x: 400, y: -50, 
                hp: 50 + (tierNum * 60), maxHp: 50 + (tierNum * 60), 
                size: 35 + (tierNum * 4), speed: 0.6 + (tierNum * 0.08),
                tier: tierNum
            });
        }

        function checkWeaponTier() {
            if (lvl >= 50) { currentWeapon = "Tactical Mini-Gun"; maxAmmo = 100; }
            else if (lvl >= 35) { currentWeapon = "Laser Railgun"; maxAmmo = 3; }
            else if (lvl >= 20) { currentWeapon = "Plasma Rifle"; maxAmmo = 30; }
            else if (lvl >= 10) { currentWeapon = "Remington Shotgun"; maxAmmo = 5; }
            else { currentWeapon = "M1911 Pistol"; maxAmmo = 7; }
            document.getElementById("ui-weapon").innerText = currentWeapon;
        }

        window.addEventListener("keydown", e => { 
            if(!isGameRunning || isPaused) return;
            keys[e.key.toLowerCase()] = true; 
            if(e.key.toLowerCase() === 'r' && !isReloading && currentAmmo < maxAmmo) startManualReload();
        });
        window.addEventListener("keyup", e => { if(isGameRunning) keys[e.key.toLowerCase()] = false; });
        window.addEventListener("mousemove", e => {
            const rect = canvas.getBoundingClientRect();
            let relativeX = e.clientX - rect.left;
            let relativeY = e.clientY - rect.top;
            mouseX = (relativeX / rect.width) * canvas.width;
            mouseY = ((relativeY / rect.height) * canvas.height) * 1.5 - 120; 
        });
        canvas.addEventListener("mousedown", () => { if(isGameRunning && !isPaused) fireWeapon(); });

        function startManualReload() {
            isReloading = true;
            if(currentWeapon === "Tactical Mini-Gun") reloadTimer = 150;
            else if(currentWeapon === "Laser Railgun") reloadTimer = 120;
            else if(currentWeapon === "Remington Shotgun") reloadTimer = 90;
            else reloadTimer = 50;
            playSound('reload');
            document.getElementById("ui-reloading").style.display = "inline";
        }

        function fireWeapon() {
            if (isReloading || weaponCooldown > 0) return;
            if (currentAmmo <= 0) { startManualReload(); return; }

            currentAmmo--;
            playSound('shoot');
            const baseAngle = Math.atan2(mouseY - player.y, mouseX - player.x);
            let bDamage = 1 + Math.floor(lvl / 8);

            if (currentWeapon === "M1911 Pistol") {
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle)*8, vy: Math.sin(baseAngle)*8, dmg: bDamage, color: "#ffff00", life: 1, size: 7 });
                weaponCooldown = 15;
            } 
            else if (currentWeapon === "Remington Shotgun") {
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle-0.2)*8, vy: Math.sin(baseAngle-0.2)*8, dmg: bDamage, color: "#ff3300", life: 1, size: 6 });
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle)*8, vy: Math.sin(baseAngle)*8, dmg: bDamage, color: "#ff3300", life: 1, size: 6 });
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle+0.2)*8, vy: Math.sin(baseAngle+0.2)*8, dmg: bDamage, color: "#ff3300", life: 1, size: 6 });
                weaponCooldown = 35;
            } 
            else if (currentWeapon === "Plasma Rifle") {
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle)*10, vy: Math.sin(baseAngle)*10, dmg: bDamage * 1.5, color: "#00ffff", life: 1, size: 10 });
                weaponCooldown = 8;
            } 
            else if (currentWeapon === "Laser Railgun") {
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle)*12, vy: Math.sin(baseAngle)*12, dmg: bDamage * 2, color: "#00ff00", life: 4, size: 5 });
                weaponCooldown = 50;
            } 
            else if (currentWeapon === "Tactical Mini-Gun") {
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle-0.05)*11, vy: Math.sin(baseAngle-0.05)*11, dmg: bDamage, color: "magenta", life: 1, size: 6 });
                bullets.push({ x: player.x, y: player.y, vx: Math.cos(baseAngle+0.05)*11, vy: Math.sin(baseAngle+0.05)*11, dmg: bDamage, color: "orange", life: 1, size: 6 });
                weaponCooldown = 4;
            }
            updateUI();
        }

        function spawnZombie() {
            if(!isGameRunning) return;
            if(!bossActive && !isPaused && zombiesKilledInRound < zombiesRequiredForRound) {
                let side = Math.floor(Math.random() * 4);
                let rand = Math.random();
                let z = { x: 0, y: 0, hp: 1 + Math.floor(gameRound/5), maxHp: 1 + Math.floor(gameRound/5), speed: 1.5, color: "#39e639", type: "normal", shootCooldown: 0 };
                
                if(side === 0) { z.x = Math.random()*800; z.y = -30; }
                else if(side === 1) { z.x = 830; z.y = Math.random()*550; }
                else if(side === 2) { z.x = Math.random()*800; z.y = 580; }
                else { z.x = -30; z.y = Math.random()*550; }

                if (tier4Defeated && rand < 0.12) {
                    z.color = "#9900ff"; z.type = "purple_gunner"; z.speed = 1.3;
                } else if (tier3Defeated && rand < 0.36) {
                    z.color = "#ff6600"; z.type = "orange_brute"; z.hp *= 2.4; z.maxHp *= 2.4; z.speed = 1.0;
                } else if (tier2Defeated && rand < 0.45) {
                    z.color = "#0055ff"; z.type = "blue_sprinter"; z.speed *= 1.45;
                } else if (tier1Defeated && rand < 0.80) {
                    z.color = "#ff0000"; z.type = "red_stalker"; z.hp *= 1.25; z.maxHp *= 1.25;
                }
                zombies.push(z);
            }
            zombieInterval = setTimeout(spawnZombie, Math.max(120, 1500 - (gameRound * 20)));
        }

        function checkRoundProgression() {
            if(zombiesKilledInRound >= zombiesRequiredForRound && zombies.length === 0 && bosses.length === 0) {
                if(gameRound === 100) {
                    let choice = confirm("ROUND 100 CLEARED! You have survived the narrative simulation. Enter Endless Mode?");
                    if(!choice) { returnToMenu(); return; }
                    document.getElementById("ui-mode-tag").innerText = "(Endless)";
                    document.getElementById("ui-mode-tag").style.color = "cyan";
                }
                gameRound++;
                zombiesKilledInRound = 0;
                zombiesRequiredForRound = 10 + (gameRound * 2);
                if(gameRound % 10 === 0) { triggerMilestoneBoss(); }
                updateUI();
            }
        }

        function gameLoop() {
            if(!isGameRunning) return;
            if(isPaused) { requestAnimationFrame(gameLoop); return; }

            ctx.clearRect(0, 0, 800, 550);
            if(weaponCooldown > 0) weaponCooldown--;

            if (isReloading) {
                reloadTimer--;
                if (reloadTimer <= 0) {
                    currentAmmo = maxAmmo; isReloading = false;
                    document.getElementById("ui-reloading").style.display = "none";
                    updateUI();
                }
            }

            if (keys['w'] && player.y > player.size) player.y -= player.speed;
            if (keys['s'] && player.y < 550 - player.size) player.y += player.speed;
            if (keys['a'] && player.x > player.size) player.x -= player.speed;
            if (keys['d'] && player.x < 800 - player.size) player.x += player.speed;

            player.angle = Math.atan2(mouseY - player.y, mouseX - player.x);

            // Ground Grid
            ctx.strokeStyle = "#223322"; ctx.lineWidth = 1;
            for(let i=0; i<800; i+=40) { ctx.beginPath(); ctx.moveTo(i,0); ctx.lineTo(i,550); ctx.stroke(); }
            for(let j=0; j<550; j+=40) { ctx.beginPath(); ctx.moveTo(0,j); ctx.lineTo(800,j); ctx.stroke(); }

            // PLAYER
            ctx.save();
            ctx.fillStyle = "red"; ctx.fillRect(player.x - 20, player.y - 32, 40, 5);
            ctx.fillStyle = "#00ff00"; ctx.fillRect(player.x - 20, player.y - 32, (hp / 100) * 40, 5);
            ctx.translate(player.x, player.y); ctx.rotate(player.angle);
            ctx.fillStyle = "#555"; ctx.fillRect(5, -5, 25, 6);
            ctx.fillStyle = player.color;
            ctx.beginPath(); ctx.arc(0, 0, player.size, 0, Math.PI * 2); ctx.fill();
            ctx.fillStyle = "#e0a96d"; ctx.beginPath(); ctx.arc(0, 0, player.size*0.6, 0, Math.PI*2); ctx.fill();
            ctx.restore();

            // BULLETS
            bullets.forEach((b, bIdx) => {
                b.x += b.vx; b.y += b.vy;
                ctx.fillStyle = b.color;
                ctx.fillRect(b.x - Math.floor(b.size/2), b.y - Math.floor(b.size/2), b.size, b.size);
                if (b.x < 0 || b.x > 800 || b.y < 0 || b.y > 550) bullets.splice(bIdx, 1);

                zombies.forEach((z, zIdx) => {
                    if (Math.hypot(b.x - z.x, b.y - z.y) < 22) {
                        let dealt = b.dmg;
                        if (player.perk === 'lucky' && Math.random() < 0.12) dealt = 999;
                        z.hp -= dealt; b.life--; playSound('hit');
                        if (z.hp <= 0) {
                            zombies.splice(zIdx, 1);
                            zombiesKilledInRound++;
                            cash += player.perk === 'looter' ? 30 : 15;
                            checkRoundProgression();
                            updateUI();
                        }
                        if (b.life <= 0) bullets.splice(bIdx, 1);
                    }
                });

                bosses.forEach((boss, bossIdx) => {
                    if (Math.hypot(b.x - boss.x, b.y - boss.y) < boss.size) {
                        boss.hp -= b.dmg; b.life--; playSound('hit');
                        if (boss.hp <= 0) {
                            if(boss.tier === 1) tier1Defeated = true;
                            if(boss.tier === 2) tier2Defeated = true;
                            if(boss.tier === 3) tier3Defeated = true;
                            if(boss.tier === 4) tier4Defeated = true;
                            bosses.splice(bossIdx, 1);
                            bossActive = false;
                            cash += player.perk === 'looter' ? 300 : 150;
                            checkRoundProgression();
                            updateUI();
                        }
                        if (b.life <= 0) bullets.splice(bIdx, 1);
                    }
                });
            });

            // ENEMY PROJECTILES
            ctx.fillStyle = "#ff00ff";
            enemyBullets.forEach((eb, ebIdx) => {
                eb.x += eb.vx; eb.y += eb.vy;
                ctx.fillRect(eb.x - 3, eb.y - 3, 6, 6);
                if (eb.x < 0 || eb.x > 800 || eb.y < 0 || eb.y > 550) enemyBullets.splice(ebIdx, 1);

                if (Math.hypot(eb.x - player.x, eb.y - player.y) < player.size) {
                    hp -= player.perk === 'tank' ? 2 : 4;
                    enemyBullets.splice(ebIdx, 1);
                    updateUI();
                    if(hp <= 0) { isGameRunning = false; alert("SQUAD OUT-GUNNED! Game Over."); returnToMenu(); }
                }
            });

            // ZOMBIES TRACKING
            zombies.forEach((z, zIdx) => {
                let zAngle = Math.atan2(player.y - z.y, player.x - z.x);
                z.x += Math.cos(zAngle) * z.speed; z.y += Math.sin(zAngle) * z.speed;
                
                ctx.fillStyle = z.color;
                ctx.beginPath(); ctx.arc(z.x, z.y, 14, 0, Math.PI*2); ctx.fill();

                if (z.type === "purple_gunner") {
                    ctx.save(); ctx.translate(z.x, z.y); ctx.rotate(zAngle);
                    ctx.fillStyle = "#333"; ctx.fillRect(4, 2, 8, 3); ctx.restore();
                    z.shootCooldown++;
                    if (z.shootCooldown > 120) {
                        enemyBullets.push({ x: z.x, y: z.y, vx: Math.cos(zAngle) * 5, vy: Math.sin(zAngle) * 5 });
                        z.shootCooldown = 0;
                    }
                }
                
                ctx.fillStyle = "red"; ctx.fillRect(z.x - 12, z.y - 22, 24, 4);
                ctx.fillStyle = "green"; ctx.fillRect(z.x - 12, z.y - 22, (z.hp / z.maxHp) * 24, 4);

                if (Math.hypot(player.x - z.x, player.y - z.y) < player.size + 10) {
                    hp -= player.perk === 'tank' ? 0.2 : 0.4;
                    updateUI();
                    if(hp <= 0) { isGameRunning = false; alert("SQUAD ELIMINATED! Game Over."); returnToMenu(); }
                }
            });

            // MILESTONE OVERLORD BOSS
            bosses.forEach(boss
