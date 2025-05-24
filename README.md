<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anii B'day</title>
    <link href="https://fonts.googleapis.com/css2?family=Sacramento&display=swap" rel="stylesheet">
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffcccb;
            font-family: Arial, sans-serif;
            text-align: center;
            overflow: hidden;
            position: relative;
        }

        h1 {
            font-family: 'Sacramento', cursive;
            font-size: 48px;
            color: #d63031;
        }

        .box {
            width: 200px;
            height: 200px;
            background: url('https://i.pinimg.com/originals/24/69/f5/2469f54eed6a0ac51f2ea276882c79ac.gif') no-repeat center;
            background-size: cover;
        }

        #btnOpen, #btnPress, #btnMusic {
            margin-top: 20px;
            padding: 15px 25px;
            font-size: 18px;
            background: red;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 8px;
            transition: 0.3s;
            position: relative;
        }

        #btnOpen:hover, #btnPress:hover, #btnMusic:hover {
            background: darkred;
        }

        #message {
            display: none;
            font-size: 22px;
            margin-top: 20px;
            color: #000000;
            background: rgba(255, 255, 255, 0.7); /* Background putih transparan */
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Efek bayangan lembut */
            max-width: 80%;
            font-family: 'Patrick Hand', cursive; /* Menggunakan font Patrick Hand */
        }

        #photo {
            display: none;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            margin-top: 20px;
            border: 5px solid white;
            box-shadow: 0 0 10px rgba(0,0,0,0.3);
        }

        /* Efek hujan love */
        .heart {
            position: absolute;
            top: -50px;
            animation: fall 5s linear infinite;
            font-size: 24px;
            color: red;
        }

        @keyframes fall {
            0% {
                transform: translateY(0);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <h1 id="title">✨ Hadiah Special Untuk Kamu❤️</h1>
    <div class="box"></div>

    <!-- Tombol awal -->
    <button id="btnPress">Klik di Sini</button>
    <button id="btnOpen" style="display: none;">Buka Kado</button>
    <button id="btnMusic" style="display: none;">🔊 Matikan Musik</button>

    <p id="message">Selamat Ulang Tahun Sayangkuu Semoga bahagia selalu, maaf yaa cuman bisa ngasih surprise dari jauh 💖🎂🎉</p>
    <img id="photo" src="https://i.ibb.co.com/JFFDPVWz/1742725750161.png" alt="Foto Ulang Tahun">

    <!-- Musik -->
    <audio id="bgMusic" loop>
        <source src="https://cdn.pixabay.com/download/audio/2023/09/13/audio_838c40b03c.mp3?filename=happy-birthday-2-version-166416.mp3" type="audio/mp3">
    </audio>

    <script>
        const btnPress = document.getElementById("btnPress");
        const btnOpen = document.getElementById("btnOpen");
        const btnMusic = document.getElementById("btnMusic");
        const message = document.getElementById("message");
        const photo = document.getElementById("photo");
        const bgMusic = document.getElementById("bgMusic");
        const title = document.getElementById("title");

        btnPress.addEventListener("click", function() {
            message.style.display = "block";
            photo.style.display = "block";
            btnPress.style.display = "none";
            btnOpen.style.display = "block";
            btnMusic.style.display = "block";
            bgMusic.play();
            document.body.style.background = "url('https://i.ibb.co.com/FLkw9r4t/IMG-20250323-175649-378.webp') no-repeat center center fixed";
            document.body.style.backgroundSize = "cover";
            title.style.display = "none"; // Menghilangkan judul setelah tombol ditekan

            // Menambahkan efek hujan love yang looping
            startLoveRain();
        });

        btnOpen.addEventListener("click", function() {
            window.location.href = "https://wa.me/+6282359165456?text=Terima%20kasih%20sayang%20kadonya%20❤️";
        });

        btnMusic.addEventListener("click", function() {
            if (bgMusic.paused) {
                bgMusic.play();
                btnMusic.textContent = "🔊 Matikan Musik";
            } else {
                bgMusic.pause();
                btnMusic.textContent = "🔈 Nyalakan Musik";
            }
        });

        // Fungsi untuk memulai efek hujan love
        function startLoveRain() {
            setInterval(function() {
                createLoveHeart();
            }, 200); // Menghasilkan hati baru setiap 200ms
        }

        // Fungsi untuk membuat hati jatuh
        function createLoveHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.textContent = "❤️";
            heart.style.left = Math.random() * 100 + "vw"; // Posisi acak
            document.body.appendChild(heart);
            setTimeout(() => {
                heart.remove();
            }, 5000); // Menghapus hati setelah animasi selesai
        }
    </script>

</body>
</html>
