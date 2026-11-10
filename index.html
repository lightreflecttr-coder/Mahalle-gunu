<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>3D Mahalle ve Görev Simülasyonu</title>
    <style>
        body, html {
            margin: 0; padding: 0; width: 100%; height: 100%;
            background-color: #70c1b3; font-family: 'Segoe UI', Tahoma, sans-serif;
            overflow: hidden; touch-action: none; user-select: none; -webkit-user-select: none;
        }
        #game-canvas { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 1; }
        #zone-left { position: absolute; top: 0; left: 0; width: 50%; height: 100%; z-index: 5; touch-action: none; }
        #zone-right { position: absolute; top: 0; left: 50%; width: 50%; height: 100%; z-index: 5; touch-action: none; }
        #crosshair {
            position: absolute; top: 50%; left: 50%; width: 6px; height: 6px;
            background: rgba(255,255,255,0.7); border-radius: 50%; transform: translate(-50%, -50%);
            z-index: 6; pointer-events: none; box-shadow: 0 0 4px rgba(0,0,0,0.8);
        }
        #joystick-base {
            position: absolute; width: 110px; height: 110px;
            background: rgba(255,255,255,0.15); border: 2px solid rgba(255,255,255,0.4);
            border-radius: 50%; z-index: 6; pointer-events: none; display: none;
            transform: translate(-50%, -50%);
        }
        #joystick-stick {
            position: absolute; top: 50%; left: 50%; width: 45px; height: 45px;
            background: rgba(255,255,255,0.8); border-radius: 50%;
            transform: translate(-50%, -50%); pointer-events: none;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
        }
        #ui-layer { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 10; pointer-events: none; }
        #hud {
            position: absolute; top: 15px; left: 50%; transform: translateX(-50%);
            background: rgba(15, 20, 25, 0.85); color: #fff; padding: 10px 25px;
            border-radius: 25px; font-size: 16px; font-weight: bold;
            display: flex; gap: 25px; border: 1px solid rgba(255,255,255,0.2);
            pointer-events: auto; backdrop-filter: blur(8px);
            box-shadow: 0 5px 20px rgba(0,0,0,0.4);
        }
        .val-money { color: #2ecc71; text-shadow: 0 0 8px rgba(46, 204, 113, 0.6); }
        .val-quest { color: #f39c12; text-shadow: 0 0 8px rgba(243, 156, 18, 0.6); }
        #btn-interact {
            position: absolute; bottom: 35px; right: 35px; width: 85px; height: 85px;
            background: rgba(255, 255, 255, 0.2); color: rgba(255,255,255,0.4);
            border: 2px solid rgba(255,255,255,0.3); border-radius: 50%;
            font-size: 15px; font-weight: bold; display: flex; justify-content: center; align-items: center;
            pointer-events: auto; transition: 0.2s; touch-action: none;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        #btn-interact.ready {
            background: rgba(46, 204, 113, 0.95); color: white; border-color: white;
            box-shadow: 0 0 25px rgba(46, 204, 113, 0.8); transform: scale(1.08);
        }
        #npc-labels { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 4; pointer-events: none; overflow: hidden; }
        .label {
            position: absolute; background: rgba(0,0,0,0.7); color: white;
            padding: 4px 10px; border-radius: 6px; font-size: 12px; font-weight: bold;
            transform: translate(-50%, -100%); transition: opacity 0.1s; pointer-events: none;
            border: 1px solid rgba(255,255,255,0.2);
        }
        #modal {
            display: none; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
            width: 85%; max-width: 420px; background: rgba(20, 25, 32, 0.96); color: white;
            padding: 24px; border-radius: 16px; border: 1px solid rgba(255,255,255,0.2);
            box-shadow: 0 15px 50px rgba(0,0,0,0.8); z-index: 20; pointer-events: auto; text-align: center;
        }
        #m-title { font-size: 22px; color: #f1c40f; margin-top: 0; margin-bottom: 12px; border-bottom: 1px solid rgba(255,255,255,0.1); padding-bottom: 10px; }
        #m-text { font-size: 16px; margin-bottom: 20px; color: #ecf0f1; line-height: 1.5; min-height: 50px; text-align: left; }
        .btn-opt {
            background: #34495e; color: white; border: none; padding: 14px; margin-bottom: 10px;
            width: 100%; border-radius: 8px; font-size: 16px; font-weight: bold; touch-action: none;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2); transition: 0.1s; cursor: pointer; text-align: left;
        }
        .btn-opt:active { background: #2980b9; transform: scale(0.98); }
        #btn-close { background: #c0392b; margin-top: 5px; text-align: center; }
    </style>
</head>
<body>

    <div id="game-canvas"></div>
    <div id="npc-labels"></div>
    <div id="zone-left"></div>
    <div id="zone-right"></div>
    <div id="joystick-base"><div id="joystick-stick"></div></div>
    <div id="crosshair"></div>

    <div id="ui-layer">
        <div id="hud">
            <div>Bakiye: <span id="v-money" class="val-money">0</span> ₺</div>
            <div>Görev: <span id="v-quest" class="val-quest">Yok</span></div>
        </div>
        <div id="btn-interact">Konuş</div>
    </div>

    <div id="modal">
        <h3 id="m-title">İsim</h3>
        <div id="m-text">Metin</div>
        <button id="opt-1" class="btn-opt">Seçenek 1</button>
        <button id="opt-2" class="btn-opt">Seçenek 2</button>
        <button id="opt-3" class="btn-opt">Seçenek 3</button>
        <button id="btn-close" class="btn-opt">Kapat</button>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

    <script>
        // --- GLOBAL DEĞİŞKENLER ---
        let scene, camera, renderer;
        let money = 0, currentQuest = null;
        let hasBucket = false;
        let npcs = [], cars = [], colliders = [];
        let nearestNPC = null, inDialog = false;

        let camPitch = 0, camYaw = 0;
        let joyMoveX = 0, joyMoveY = 0;
        const SPEED = 0.16;
        const LOOK_SENSITIVITY = 0.0038;

        const uiMoney = document.getElementById('v-money');
        const uiQuest = document.getElementById('v-quest');
        const btnInteract = document.getElementById('btn-interact');
        const labelContainer = document.getElementById('npc-labels');
        const modal = document.getElementById('modal');

        const addMoney = (m) => { money += m; uiMoney.innerText = money; };
        const setQuestDesc = (q) => { currentQuest = q; uiQuest.innerText = q ? q.name : "Yok"; };

        // --- DİYALOG MOTORU (close düzeltmesi ile) ---
        function showDialogue(node, npcData) {
            document.getElementById('m-title').innerText = npcData.name;
            document.getElementById('m-text').innerText = node.text;

            ['opt-1', 'opt-2', 'opt-3'].forEach((id, idx) => {
                const btn = document.getElementById(id);
                if (node.opts && node.opts[idx]) {
                    btn.style.display = 'block';
                    btn.innerText = node.opts[idx].t;
                    btn.onclick = () => {
                        if (node.opts[idx].action) node.opts[idx].action();
                        const nxt = node.opts[idx].next;
                        if (nxt === 'close') {
                            modal.style.display = 'none';
                            inDialog = false;
                        } else if (nxt && npcData.dialogues[nxt]) {
                            showDialogue(npcData.dialogues[nxt], npcData);
                        }
                    };
                } else {
                    btn.style.display = 'none';
                }
            });
            modal.style.display = 'block';
        }

        // --- NPC VERİTABANI ---
        const npcDB = [
            {
                name: "Tamirci Mehmet", color: 0xd35400, pos: [-25, 23],
                fixed: true,
                text: "Ooo çırak! Hoş geldin dükkana. Mahallede işler yoğun, yardım edersen para kazanırsın. Ne yapmak istiyorsun?",
                dialogues: {
                    main: {
                        text: "Mehmet Usta: Mahallede yapılacak çok iş var. Hangisinden başlamak istersin?",
                        opts: [
                            { t: "1. Görev Al: Kovayı Getir (Zorlu)", next: "quest_bucket" },
                            { t: "2. Görev Al: Su Taşıma İşi", next: "quest_water" },
                            { t: "3. Görevi Tamamla", action: () => {
                                if(currentQuest && currentQuest.id === 'bucket') {
                                    if(hasBucket) {
                                        addMoney(100);
                                        hasBucket = false;
                                        setQuestDesc(null);
                                        alert("Helal olsun! Kovayı başarıyla getirdin ve 100₺ kazandın.");
                                    } else {
                                        alert("Mehmet Usta: Usta ortada kova yok! Önce uzak depodan kovayı bulup almalısın.");
                                    }
                                } else if(currentQuest) {
                                    addMoney(currentQuest.reward);
                                    setQuestDesc(null);
                                    alert("Görev başarıyla tamamlandı!");
                                } else {
                                    alert("Mehmet Usta: Şu an aktif bir görevin yok ki!");
                                }
                            }, next: "main" },
                            { t: "4. Hayat ve dükkan hakkında sohbet et", next: "chat_life" }
                        ]
                    },
                    quest_bucket: {
                        text: "Mehmet Usta: Harika! Mahallenin diğer ucundaki eski hurdalıkta mavi bir kova var. O kovayı bulup bana getirmeni istiyorum. Dikkat et yolda arabalar hızlı geçer!",
                        opts: [
                            { t: "Görevi kabul ediyorum!", action: () => {
                                setQuestDesc({id: 'bucket', name: "Kovayı Depodan Getir", reward: 100});
                            }, next: "main" },
                            { t: "Vazgeçtim, başka zaman.", next: "main" }
                        ]
                    },
                    quest_water: {
                        text: "Mehmet Usta: Çeşmeden büyük bidonu doldurup buraya taşıman lazım. Kuvvetli olmak gerek!",
                        opts: [
                            { t: "Su taşıma görevini al", action: () => {
                                setQuestDesc({id: 'water', name: "Su Taşı", reward: 75});
                            }, next: "main" },
                            { t: "Geri dön", next: "main" }
                        ]
                    },
                    chat_life: {
                        text: "Mehmet Usta: Ah be evlat... Eskiden buralar hep dutluktu. Şimdi herkes elektronik ve motor peşinde. Sen ne düşünüyorsun bu işler hakkında?",
                        opts: [
                            { t: "Ben donanım ve elektrik işlerini seviyorum usta!", next: "chat_support" },
                            { t: "Sadece para kazanmak istiyorum.", next: "chat_money" },
                            { t: "Ana menüye dön", next: "main" }
                        ]
                    },
                    chat_support: {
                        text: "Mehmet Usta: Helal olsun! Çekirdekten yetişmek en iyisidir. Okumak da güzel ama pratik ustalık altın bileziktir.",
                        opts: [{ t: "Haklısın usta, sağol.", next: "main" }]
                    },
                    chat_money: {
                        text: "Mehmet Usta: Para kazanmak emek ister çırak! Çalışmadan yemek olmaz.",
                        opts: [{ t: "Haklısın, işe koyulalım.", next: "main" }]
                    }
                }
            },
            {
                name: "Simitçi Hüseyin", color: 0xe74c3c, pos: [-8, -15],
                text: "Taze simitler taze!",
                dialogues: {
                    main: {
                        text: "Hüseyin Abi: Selamün aleyküm! Simitler sıcak, atıştıralım mı?",
                        opts: [
                            { t: "Simit al (-10₺)", action: () => {
                                if(money >= 10) { addMoney(-10); alert("Afiyet olsun, simit çıtır çıtır!"); }
                                else { alert("Yeterli paran yok!"); }
                            }, next: "main" },
                            { t: "Mahallede neler dönüyor anlat bakalım?", next: "chat_gossip" },
                            { t: "İyi günler abi.", next: "close" }
                        ]
                    },
                    chat_gossip: {
                        text: "Hüseyin Abi: Valla ne olsun, Tamirci Mehmet bu aralar çırak arıyor diyorlar. Bir de uzak depoda esrarengiz eşyalar unutulmuş duyduğuma göre.",
                        opts: [{ t: "Sağol abi bilgi için.", next: "main" }]
                    }
                }
            },
            {
                name: "Çaycı Remzi", color: 0x8e44ad, pos: [10, -25],
                text: "Demli bir çay yorgunluğunu alır.",
                dialogues: {
                    main: {
                        text: "Remzi: Ooo kaptan, yoruldun galiba? Demli bir çay ister misin?",
                        opts: [
                            { t: "Çay iç (-5₺)", action: () => {
                                if(money >= 5) { addMoney(-5); alert("Mis gibi çay yorgunluğunu aldı."); }
                                else { alert("Cebinde 5 liran bile yok!"); }
                            }, next: "main" },
                            { t: "İşler nasıl gidiyor Remzi?", next: "chat_tea" },
                            { t: "Kolay gelsin.", next: "close" }
                        ]
                    },
                    chat_tea: {
                        text: "Remzi: Çaylar yetişmiyor valla! Herkes esnaf çayına bayılıyor.",
                        opts: [{ t: "Harika, bol kazançlar.", next: "main" }]
                    }
                }
            },
            {
                name: "Turist Maykıl", color: 0xf1c40f, pos: [5, -35],
                text: "Hello! Can you help me?",
                dialogues: {
                    main: {
                        text: "Michael: Hello my friend! Can you help me navigate this town?",
                        opts: [
                            { t: "Sure! Guide you (+25₺)", action: () => {
                                addMoney(25);
                                alert("Michael: Thank you so much! Here is your tip.");
                            }, next: "main" },
                            { t: "Sorry, I'm busy.", next: "close" }
                        ]
                    }
                }
            },
            {
                name: "Ayşe Teyze", color: 0x9b59b6, pos: [-15, -28],
                text: "Evladım dikkat et.",
                dialogues: {
                    main: {
                        text: "Ayşe Teyze: Yavrum dikkat et kendine, bu arabalar deliler gibi sürüyor.",
                        opts: [
                            { t: "Haklısın teyzeciğim, dikkat ederim.", next: "chat_advice" },
                            { t: "Görüşürüz teyze.", next: "close" }
                        ]
                    },
                    chat_advice: {
                        text: "Ayşe Teyze: Allah zihin açıklığı versin evladım, dualarım seninle.",
                        opts: [{ t: "Sağol var ol.", next: "main" }]
                    }
                }
            }
        ];

        const otherNames = ["Berber Ali", "Kasap Nuri", "Öğrenci Can", "Manav Hasan", "Kurye Efe", "Mimar Su", "Doktor Alp", "Eczacı Buse", "Tamirci Kadir", "Sporcu Ege", "Kasiyer Ceren", "Çöpçü Şaban", "Gazeteci Eda", "Hemşire Ece", "Mühendis Kaan", "Taksici Veli", "Teyze Fatma", "Aşçı Cemal", "Müzisyen Mert", "Bahçıvan Kemal"];
        otherNames.forEach((n) => {
            npcDB.push({
                name: n, color: Math.random() * 0xffffff,
                pos: [(Math.random()-0.5)*90, (Math.random()-0.5)*90 - 20],
                text: "Selam komşu.",
                dialogues: {
                    main: {
                        text: n + ": Selam dostum! Mahallede hayat nasıl gidiyor?",
                        opts: [
                            { t: "Gayet iyi, koşturmaca.", next: "chat_nice" },
                            { t: "İyi günler.", next: "close" }
                        ]
                    },
                    chat_nice: {
                        text: n + ": Harika, kendine iyi bak görüşürüz!",
                        opts: [{ t: "Görüşürüz.", next: "close" }]
                    }
                }
            });
        });

        // --- ÜNİVERSİTE PROFESÖRÜ ---
        npcDB.push({
            name: "Profesör Ahmet", color: 0x2c3e50, pos: [-65, -50],
            fixed: true,
            text: "Üniversiteye hoş geldin evlat!",
            dialogues: {
                main: {
                    text: "Profesör Ahmet: Merhaba evlat, üniversitemize hoş geldin. İlim öğrenmek ister misin?",
                    opts: [
                        { t: "Evet, öğrenmek isterim!", next: "chat_learn" },
                        { t: "Sadece geziyorum.", next: "chat_visit" },
                        { t: "Görüşürüz hocam.", next: "close" }
                    ]
                },
                chat_learn: {
                    text: "Profesör Ahmet: Harika! Burada çok şey öğreneceksin. Dersler her gün sabah 9'da başlıyor.",
                    opts: [{ t: "Teşekkürler hocam!", next: "main" }]
                },
                chat_visit: {
                    text: "Profesör Ahmet: Anlıyorum. Üniversitemizi gezmekten keyif alacağını umuyorum.",
                    opts: [{ t: "Sağolun hocam.", next: "main" }]
                }
            }
        });

        window.onload = () => {
            initThree();
            buildWorld();
            setupControls();
            animate();
        };

        function initThree() {
            scene = new THREE.Scene();
            scene.background = new THREE.Color(0x87CEEB);
            scene.fog = new THREE.Fog(0x87CEEB, 20, 160);

            camera = new THREE.PerspectiveCamera(70, window.innerWidth / window.innerHeight, 0.1, 500);
            camera.position.set(0, 1.8, 0);
            camera.rotation.order = 'YXZ';

            const ambLight = new THREE.AmbientLight(0xffffff, 0.65);
            scene.add(ambLight);

            const dirLight = new THREE.DirectionalLight(0xffffff, 0.8);
            dirLight.position.set(60, 120, 60);
            scene.add(dirLight);

            renderer = new THREE.WebGLRenderer({ antialias: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
            document.getElementById('game-canvas').appendChild(renderer.domElement);

            window.addEventListener('resize', () => {
                camera.aspect = window.innerWidth / window.innerHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, window.innerHeight);
            });
        }

        function addCol(mesh) {
            mesh.updateMatrixWorld(true);
            const box = new THREE.Box3().setFromObject(mesh);
            colliders.push(box);
        }

        let collectibleBucket = null;

        // --- YAZI TEXTURE ÜRETİCİ ---
        function makeTextTexture(text, bgColor, textColor, w, h) {
            const canvas = document.createElement('canvas');
            canvas.width = w || 512;
            canvas.height = h || 128;
            const ctx = canvas.getContext('2d');
            ctx.fillStyle = bgColor || '#000';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = textColor || '#fff';
            ctx.font = 'bold ' + Math.floor(canvas.height * 0.55) + 'px Arial';
            ctx.textAlign = 'center';
            ctx.textBaseline = 'middle';
            ctx.fillText(text, canvas.width/2, canvas.height/2);
            return new THREE.CanvasTexture(canvas);
        }

        // --- TAMİRCİ DÜKKANI ---
        function createShop() {
            const cx = -25, cz = 25;
            const W = 14, H = 5, D = 12;
            const wallMat = new THREE.MeshLambertMaterial({ color: 0xd35400 });
            const roofMat = new THREE.MeshLambertMaterial({ color: 0x2c3e50 });

            const bw = new THREE.Mesh(new THREE.BoxGeometry(W, H, 0.4), wallMat);
            bw.position.set(cx, H/2, cz + D/2);
            scene.add(bw); addCol(bw);

            const lw = new THREE.Mesh(new THREE.BoxGeometry(0.4, H, D), wallMat);
            lw.position.set(cx - W/2, H/2, cz);
            scene.add(lw); addCol(lw);

            const rw = new THREE.Mesh(new THREE.BoxGeometry(0.4, H, D), wallMat);
            rw.position.set(cx + W/2, H/2, cz);
            scene.add(rw); addCol(rw);

            const doorW = 3, doorH = 3.5;
            const sideW = (W - doorW) / 2;
            const frontZ = cz - D/2;

            const fwL = new THREE.Mesh(new THREE.BoxGeometry(sideW, H, 0.4), wallMat);
            fwL.position.set(cx - doorW/2 - sideW/2, H/2, frontZ);
            scene.add(fwL); addCol(fwL);

            const fwR = new THREE.Mesh(new THREE.BoxGeometry(sideW, H, 0.4), wallMat);
            fwR.position.set(cx + doorW/2 + sideW/2, H/2, frontZ);
            scene.add(fwR); addCol(fwR);

            const lintel = new THREE.Mesh(new THREE.BoxGeometry(doorW, H - doorH, 0.4), wallMat);
            lintel.position.set(cx, doorH + (H - doorH)/2, frontZ);
            scene.add(lintel); addCol(lintel);

            const roof = new THREE.Mesh(new THREE.BoxGeometry(W + 1, 0.5, D + 1), roofMat);
            roof.position.set(cx, H + 0.25, cz);
            scene.add(roof);

            const signTex = makeTextTexture('TAMİRCİ MEHMET', '#d35400', '#ffffff', 512, 128);
            const sign = new THREE.Mesh(
                new THREE.PlaneGeometry(8, 1.1),
                new THREE.MeshBasicMaterial({ map: signTex })
            );
            sign.position.set(cx, doorH + 1.0, frontZ - 0.25);
            sign.rotation.y = Math.PI;
            scene.add(sign);

            const shopLight = new THREE.PointLight(0xfff2cc, 0.7, 22);
            shopLight.position.set(cx, H - 0.8, cz);
            scene.add(shopLight);

            const bench = new THREE.Mesh(
                new THREE.BoxGeometry(9, 1.1, 1.6),
                new THREE.MeshLambertMaterial({ color: 0x5d4037 })
            );
            bench.position.set(cx, 0.55, cz + D/2 - 1.6);
            scene.add(bench); addCol(bench);

            const shelf = new THREE.Mesh(
                new THREE.BoxGeometry(8, 0.2, 0.6),
                new THREE.MeshLambertMaterial({ color: 0x3e2723 })
            );
            shelf.position.set(cx, 2.4, cz + D/2 - 0.4);
            scene.add(shelf);

            const floor = new THREE.Mesh(
                new THREE.BoxGeometry(W - 0.8, 0.1, D - 0.8),
                new THREE.MeshLambertMaterial({ color: 0x7f8c8d })
            );
            floor.position.set(cx, 0.05, cz);
            scene.add(floor);
        }

        // --- ÜNİVERSİTE ---
        function createUniversity() {
            const cx = -65, cz = -55;
            const W = 40, H = 18, D = 30;
            const wallMat = new THREE.MeshLambertMaterial({ color: 0xf5f5dc });
            const trimMat = new THREE.MeshLambertMaterial({ color: 0x8b4513 });
            const roofMat = new THREE.MeshLambertMaterial({ color: 0x2c3e50 });

            const floor = new THREE.Mesh(
                new THREE.BoxGeometry(W - 1.2, 0.2, D - 1.2),
                new THREE.MeshLambertMaterial({ color: 0xbdc3c7 })
            );
            floor.position.set(cx, 0.1, cz);
            scene.add(floor);

            const bw = new THREE.Mesh(new THREE.BoxGeometry(W, H, 0.6), wallMat);
            bw.position.set(cx, H/2, cz - D/2);
            scene.add(bw); addCol(bw);

            const lw = new THREE.Mesh(new THREE.BoxGeometry(0.6, H, D), wallMat);
            lw.position.set(cx - W/2, H/2, cz);
            scene.add(lw); addCol(lw);

            const rw = new THREE.Mesh(new THREE.BoxGeometry(0.6, H, D), wallMat);
            rw.position.set(cx + W/2, H/2, cz);
            scene.add(rw); addCol(rw);

            const doorW = 8, doorH = 5;
            const sideW = (W - doorW) / 2;
            const frontZ = cz + D/2;

            const fwL = new THREE.Mesh(new THREE.BoxGeometry(sideW, H, 0.6), wallMat);
            fwL.position.set(cx - doorW/2 - sideW/2, H/2, frontZ);
            scene.add(fwL); addCol(fwL);

            const fwR = new THREE.Mesh(new THREE.BoxGeometry(sideW, H, 0.6), wallMat);
            fwR.position.set(cx + doorW/2 + sideW/2, H/2, frontZ);
            scene.add(fwR); addCol(fwR);

            const lintel = new THREE.Mesh(new THREE.BoxGeometry(doorW, H - doorH, 0.6), wallMat);
            lintel.position.set(cx, doorH + (H - doorH)/2, frontZ);
            scene.add(lintel); addCol(lintel);

            const roof = new THREE.Mesh(new THREE.BoxGeometry(W + 2, 0.8, D + 2), roofMat);
            roof.position.set(cx, H + 0.4, cz);
            scene.add(roof);

            for (let i = -1; i <= 1; i += 2) {
                const col = new THREE.Mesh(
                    new THREE.CylinderGeometry(0.7, 0.7, doorH, 16),
                    trimMat
                );
                col.position.set(cx + i * (doorW/2 + 1.5), doorH/2, frontZ + 0.8);
                scene.add(col); addCol(col);
            }

            const signTex = makeTextTexture('ÜNİVERSİTE', '#1a5276', '#ffffff', 768, 192);
            const sign = new THREE.Mesh(
                new THREE.PlaneGeometry(18, 3),
                new THREE.MeshBasicMaterial({ map: signTex })
            );
            sign.position.set(cx, doorH + 3, frontZ + 0.35);
            scene.add(sign);

            const l1 = new THREE.PointLight(0xffffff, 0.7, 45);
            l1.position.set(cx, H - 2, cz + 5);
            scene.add(l1);
            const l2 = new THREE.PointLight(0xffffff, 0.7, 45);
            l2.position.set(cx, H - 2, cz - 5);
            scene.add(l2);

            const board = new THREE.Mesh(
                new THREE.BoxGeometry(24, 8, 0.3),
                new THREE.MeshLambertMaterial({ color: 0x1e8449 })
            );
            board.position.set(cx, 7, cz - D/2 + 0.5);
            scene.add(board);

            const deskMat = new THREE.MeshLambertMaterial({ color: 0x8e44ad });
            const seatMat = new THREE.MeshLambertMaterial({ color: 0x34495e });
            for (let row = 0; row < 4; row++) {
                for (let side = -1; side <= 1; side += 2) {
                    const dx = cx + side * 12;
                    const dz = cz - 9 + row * 6;
                    const desk = new THREE.Mesh(new THREE.BoxGeometry(5, 1.2, 2), deskMat);
                    desk.position.set(dx, 0.6, dz);
                    scene.add(desk); addCol(desk);

                    const seat = new THREE.Mesh(new THREE.BoxGeometry(2.5, 1.2, 1.8), seatMat);
                    seat.position.set(dx, 0.6, dz + 2.2);
                    scene.add(seat); addCol(seat);
                }
            }
        }

        // --- DÜNYA İNŞASI ---
        function buildWorld() {
            const grassMat = new THREE.MeshLambertMaterial({ color: 0x38b000 });
            const ground = new THREE.Mesh(new THREE.PlaneGeometry(300, 300), grassMat);
            ground.rotation.x = -Math.PI/2;
            scene.add(ground);

            const roadMat = new THREE.MeshLambertMaterial({ color: 0x333333 });
            const roadZ = new THREE.Mesh(new THREE.PlaneGeometry(16, 300), roadMat);
            roadZ.rotation.x = -Math.PI/2; roadZ.position.y = 0.02;
            scene.add(roadZ);

            const roadX = new THREE.Mesh(new THREE.PlaneGeometry(300, 16), roadMat);
            roadX.rotation.x = -Math.PI/2; roadX.position.y = 0.02;
            scene.add(roadX);

            const curbMat = new THREE.MeshLambertMaterial({ color: 0x95a5a6 });
            const c1 = new THREE.Mesh(new THREE.BoxGeometry(2, 0.15, 300), curbMat); c1.position.set(-9, 0.075, 0); scene.add(c1);
            const c2 = new THREE.Mesh(new THREE.BoxGeometry(2, 0.15, 300), curbMat); c2.position.set(9, 0.075, 0); scene.add(c2);
            const c3 = new THREE.Mesh(new THREE.BoxGeometry(300, 0.15, 2), curbMat); c3.position.set(0, 0.075, -9); scene.add(c3);
            const c4 = new THREE.Mesh(new THREE.BoxGeometry(300, 0.15, 2), curbMat); c4.position.set(0, 0.075, 9); scene.add(c4);

            // === OYUNCU EVİ ===
            const wallMat = new THREE.MeshLambertMaterial({ color: 0xecf0f1 });
            const w1 = new THREE.Mesh(new THREE.BoxGeometry(10, 4, 0.4), wallMat); w1.position.set(0, 2, 5); scene.add(w1); addCol(w1);
            const w2 = new THREE.Mesh(new THREE.BoxGeometry(0.4, 4, 10), wallMat); w2.position.set(-5, 2, 0); scene.add(w2); addCol(w2);
            const w3 = new THREE.Mesh(new THREE.BoxGeometry(0.4, 4, 10), wallMat); w3.position.set(5, 2, 0); scene.add(w3); addCol(w3);
            const w4 = new THREE.Mesh(new THREE.BoxGeometry(3.5, 4, 0.4), wallMat); w4.position.set(-3.25, 2, -5); scene.add(w4); addCol(w4);
            const w5 = new THREE.Mesh(new THREE.BoxGeometry(3.5, 4, 0.4), wallMat); w5.position.set(3.25, 2, -5); scene.add(w5); addCol(w5);
            const roof = new THREE.Mesh(new THREE.BoxGeometry(10.5, 0.3, 10.5), new THREE.MeshLambertMaterial({color:0x7f8c8d}));
            roof.position.set(0, 4.15, 0); scene.add(roof);

            const bed = new THREE.Mesh(new THREE.BoxGeometry(2.2, 0.6, 4), new THREE.MeshLambertMaterial({color:0x2980b9}));
            bed.position.set(-3.5, 0.3, 2); scene.add(bed); addCol(bed);
            const desk = new THREE.Mesh(new THREE.BoxGeometry(3, 1, 1.5), new THREE.MeshLambertMaterial({color:0x8e44ad}));
            desk.position.set(3, 0.5, 3.5); scene.add(desk); addCol(desk);

            createShop();
            createUniversity();

            // === KOVA (görev eşyası) ===
            const bucketGeo = new THREE.CylinderGeometry(0.5, 0.4, 0.9, 12);
            const bucketMat = new THREE.MeshLambertMaterial({ color: 0xe74c3c });
            collectibleBucket = new THREE.Mesh(bucketGeo, bucketMat);
            collectibleBucket.position.set(45, 0.45, -45);
            scene.add(collectibleBucket);

            // === MODERN BİNALAR ===
            for(let i = -6; i <= 6; i += 4) {
                if(Math.abs(i) < 4) continue;
                createModernBuilding(20, i * 12, 12, 35, 12);
                createModernBuilding(-20, i * 12, 12, 28, 12);
                createModernBuilding(i * 12, 20, 12, 30, 12);
                createModernBuilding(i * 12, -20, 12, 40, 12);
            }

            // === NPC'LER ===
            const npcBodyGeo = new THREE.CylinderGeometry(0.45, 0.45, 1.8, 12);
            const npcHeadGeo = new THREE.SphereGeometry(0.38, 12, 12);

            npcDB.forEach(data => {
                const group = new THREE.Group();
                group.position.set(data.pos[0], 0, data.pos[1]);

                const body = new THREE.Mesh(npcBodyGeo, new THREE.MeshLambertMaterial({color: data.color}));
                body.position.y = 0.9; group.add(body);

                const head = new THREE.Mesh(npcHeadGeo, new THREE.MeshLambertMaterial({color: 0xffdbac}));
                head.position.y = 2.1; group.add(head);

                scene.add(group);
                group.userData = data;
                group.userData.targetX = data.pos[0] + (Math.random() - 0.5) * 15;
                group.userData.targetZ = data.pos[1] + (Math.random() - 0.5) * 15;

                const lbl = document.createElement('div');
                lbl.className = 'label'; lbl.innerText = data.name;
                labelContainer.appendChild(lbl);
                npcs.push({ group: group, label: lbl });
            });

            // === ARABALAR ===
            const carGeo = new THREE.BoxGeometry(2.2, 1.2, 4.5);
            const carColors = [0xe74c3c, 0x3498db, 0xf1c40f, 0x2ecc71];
            for(let i=0; i<4; i++) {
                const cMat = new THREE.MeshLambertMaterial({color: carColors[i]});
                const car = new THREE.Mesh(carGeo, cMat);
                car.position.set(3, 0.6, i * 40 - 60);
                scene.add(car);
                cars.push({ mesh: car, speed: 0.35, dir: 1, limit: 100, start: -100 });
            }
        }

        // --- MODERN BİNA ÜRETİCİ ---
        function createModernBuilding(x, z, w, h, d) {
            const bMat = new THREE.MeshLambertMaterial({ color: 0xbdc3c7 });
            const building = new THREE.Mesh(new THREE.BoxGeometry(w, h, d), bMat);
            building.position.set(x, h/2, z);
            scene.add(building);
            addCol(building);

            const paneMat = new THREE.MeshLambertMaterial({ color: 0x2c3e50 });
            for(let py = 3; py < h - 2; py += 4) {
                for(let pw = -w/2 + 2; pw < w/2 - 1; pw += 3) {
                    const pane = new THREE.Mesh(new THREE.BoxGeometry(1.2, 2, 0.2), paneMat);
                    pane.position.set(x + pw, py, z + d/2 + 0.1);
                    scene.add(pane);
                }
            }
        }

        // --- KONTROLLER (Dokunmatik + Klavye + Fare) ---
        const keys = {};
        function setupControls() {
            const joyBase = document.getElementById('joystick-base');
            const joyStick = document.getElementById('joystick-stick');

            let lookTouchId = null, lx = 0, ly = 0;
            let moveTouchId = null, jcx = 0, jcy = 0;
            const J_MAX = 45;

            // --- Dokunmatik ---
            window.addEventListener('touchstart', e => {
                for (let i = 0; i < e.changedTouches.length; i++) {
                    let t = e.changedTouches[i];
                    if (t.clientX >= window.innerWidth / 2 && lookTouchId === null) {
                        lookTouchId = t.identifier;
                        lx = t.clientX; ly = t.clientY;
                    } else if (t.clientX < window.innerWidth / 2 && moveTouchId === null && !inDialog) {
                        moveTouchId = t.identifier;
                        jcx = t.clientX; jcy = t.clientY;
                        joyBase.style.display = 'block';
                        joyBase.style.left = jcx + 'px'; joyBase.style.top = jcy + 'px';
                        updateJoy(jcx, jcy);
                    }
                }
            });

            window.addEventListener('touchmove', e => {
                for (let i = 0; i < e.changedTouches.length; i++) {
                    let t = e.changedTouches[i];
                    if (t.identifier === lookTouchId && !inDialog) {
                        let cx = t.clientX, cy = t.clientY;
                        camYaw -= (cx - lx) * LOOK_SENSITIVITY;
                        camPitch -= (cy - ly) * LOOK_SENSITIVITY;
                        camPitch = Math.max(-1.4, Math.min(1.4, camPitch));
                        camera.rotation.set(camPitch, camYaw, 0, 'YXZ');
                        lx = cx; ly = cy;
                    } else if (t.identifier === moveTouchId && !inDialog) {
                        updateJoy(t.clientX, t.clientY);
                    }
                }
            });

            const resetTouch = (e) => {
                for (let i = 0; i < e.changedTouches.length; i++) {
                    let t = e.changedTouches[i];
                    if (t.identifier === lookTouchId) lookTouchId = null;
                    if (t.identifier === moveTouchId) {
                        moveTouchId = null;
                        joyMoveX = 0; joyMoveY = 0;
                        joyBase.style.display = 'none';
                        joyStick.style.transform = `translate(-50%, -50%)`;
                    }
                }
            };
            window.addEventListener('touchend', resetTouch);
            window.addEventListener('touchcancel', resetTouch);

            function updateJoy(tx, ty) {
                let dx = tx - jcx, dy = ty - jcy;
                let dist = Math.sqrt(dx*dx + dy*dy);
                if(dist > J_MAX) { dx = (dx/dist)*J_MAX; dy = (dy/dist)*J_MAX; }
                joyStick.style.transform = `translate(calc(-50% + ${dx}px), calc(-50% + ${dy}px))`;
                joyMoveX = dx / J_MAX; joyMoveY = -dy / J_MAX;
            }

            // --- Klavye ---
            window.addEventListener('keydown', e => { keys[e.key.toLowerCase()] = true; });
            window.addEventListener('keyup',   e => { keys[e.key.toLowerCase()] = false; });

            // --- Fare ile bakış ---
            let mouseDown = false, lastMX = 0, lastMY = 0;
            renderer.domElement.addEventListener('mousedown', e => {
                mouseDown = true; lastMX = e.clientX; lastMY = e.clientY;
            });
            window.addEventListener('mousemove', e => {
                if (!mouseDown || inDialog) return;
                camYaw -= (e.clientX - lastMX) * LOOK_SENSITIVITY;
                camPitch -= (e.clientY - lastMY) * LOOK_SENSITIVITY;
                camPitch = Math.max(-1.4, Math.min(1.4, camPitch));
                camera.rotation.set(camPitch, camYaw, 0, 'YXZ');
                lastMX = e.clientX; lastMY = e.clientY;
            });
            window.addEventListener('mouseup', () => { mouseDown = false; });

            // --- Etkileşim Butonu (dokunmatik + fare) ---
            let lastTouchTime = 0;
            const handleInteract = (e) => {
                if (e.type === 'click' && Date.now() - lastTouchTime < 500) return;
                if (e.type === 'touchstart') lastTouchTime = Date.now();
                if (e.cancelable) e.preventDefault();
                e.stopPropagation();

                if (collectibleBucket && camera.position.distanceTo(collectibleBucket.position) < 3.5) {
                    hasBucket = true;
                    scene.remove(collectibleBucket);
                    collectibleBucket = null;
                    alert("Kovayı başarıyla aldın! Şimdi Tamirci Mehmet'e geri götür.");
                    return;
                }

                if (nearestNPC && !inDialog) {
                    inDialog = true; joyMoveX = 0; joyMoveY = 0;
                    joyBase.style.display = 'none';
                    moveTouchId = null; lookTouchId = null;
                    showDialogue(nearestNPC.userData.dialogues.main, nearestNPC.userData);
                }
            };
            btnInteract.addEventListener('touchstart', handleInteract, {passive: false});
            btnInteract.addEventListener('click', handleInteract);

            const closeHandler = (e) => {
                e.stopPropagation();
                modal.style.display = 'none';
                inDialog = false;
            };
            document.getElementById('btn-close').addEventListener('touchstart', closeHandler, {passive: false});
            document.getElementById('btn-close').addEventListener('click', closeHandler);
        }

        const pBox = new THREE.Box3();
        function canMoveTo(nx, nz) {
            pBox.min.set(nx - 0.4, 0.5, nz - 0.4);
            pBox.max.set(nx + 0.4, 2.5, nz + 0.4);
            for(let i=0; i<colliders.length; i++) {
                if(pBox.intersectsBox(colliders[i])) return false;
            }
            return true;
        }

        // --- OYUN DÖNGÜSÜ ---
        function animate() {
            requestAnimationFrame(animate);

            // Hareket girdisi: joystick + klavye birleşimi
            let mx = joyMoveX, mz = joyMoveY;
            if (keys['w'] || keys['arrowup'])    mz = 1;
            if (keys['s'] || keys['arrowdown'])  mz = -1;
            if (keys['a'] || keys['arrowleft'])  mx = -1;
            if (keys['d'] || keys['arrowright']) mx = 1;

            if (!inDialog && (mx !== 0 || mz !== 0)) {
                const fw = new THREE.Vector3(0,0,-1).applyAxisAngle(new THREE.Vector3(0,1,0), camYaw);
                const rt = new THREE.Vector3(1,0,0).applyAxisAngle(new THREE.Vector3(0,1,0), camYaw);

                let dx = (rt.x * mx * SPEED) + (fw.x * mz * SPEED);
                let dz = (rt.z * mx * SPEED) + (fw.z * mz * SPEED);

                let px = camera.position.x, pz = camera.position.z;
                if(canMoveTo(px + dx, pz)) camera.position.x += dx;
                if(canMoveTo(px, pz + dz)) camera.position.z += dz;
            }

            let minDist = 4, closest = null;
            npcs.forEach(n => {
                let group = n.group;
                let d = camera.position.distanceTo(group.position);
                if(d < minDist) { minDist = d; closest = group; }

                // SABİT NPC'ler yerinden oynamasın
                if (!group.userData.fixed) {
                    let tx = group.userData.targetX, tz = group.userData.targetZ;
                    let dir = new THREE.Vector3(tx - group.position.x, 0, tz - group.position.z);
                    if(dir.length() < 1) {
                        group.userData.targetX = group.position.x + (Math.random() - 0.5) * 20;
                        group.userData.targetZ = group.position.z + (Math.random() - 0.5) * 20;
                    } else {
                        dir.normalize();
                        group.position.addScaledVector(dir, 0.02);
                    }
                }

                let p = group.position.clone(); p.y += 2.8;
                p.project(camera);
                if(p.z > 1) {
                    n.label.style.display = 'none';
                } else {
                    n.label.style.display = 'block';
                    n.label.style.left = (p.x * 0.5 + 0.5) * window.innerWidth + 'px';
                    n.label.style.top = (p.y * -0.5 + 0.5) * window.innerHeight + 'px';
                    n.label.style.opacity = Math.max(0, 1 - (d / 22));
                }
            });

            let nearBucket = collectibleBucket && camera.position.distanceTo(collectibleBucket.position) < 3.5;

            nearestNPC = closest;
            if((nearestNPC || nearBucket) && !inDialog) {
                btnInteract.classList.add('ready');
                btnInteract.innerText = nearBucket ? "Al" : "Konuş";
            } else {
                btnInteract.classList.remove('ready');
                btnInteract.innerText = "Konuş";
            }

            cars.forEach(c => {
                c.mesh.position.z += c.speed * c.dir;
                if(c.mesh.position.z > c.limit) c.mesh.position.z = c.start;
            });

            renderer.render(scene, camera);
        }
    </script>
</body>
</html>
