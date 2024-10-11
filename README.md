<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Maafin kajoo ya Nalaa!?</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif, sans-serif;
            color: #ffffff;
            text-align: center;
            padding: 50px;
            height: 100vh;
            overflow: hidden;
            position: relative;
        }
        h1 {
            color: #65a8ffbe;
        }
        .container {
            background-color: rgba(0, 0, 0, 0.553);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgb(255, 255, 255);
            display: inline-block;
            position: relative;
            z-index: 1;
        }
        button {
            padding: 10px 20px;
            background-color: #a7aaff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            margin: 5px;
        }
        button:hover {
            background-color: #ffffff;
        }
        video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: 0;
        }
        audio {
            display: none; /* Sembunyikan audio player */
        }
    </style>
</head>
<body>

    <audio id="backgroundMusic" autoplay loop>
        <source src="GAMBARKUU/WhatsApp Audio 2024-10-11 at 20.01.24.mpeg" type="audio/mpeg">
        Your browser does not support the audio tag.
    </audio>    

    <video id="backgroundVideo" autoplay muted loop>
        <source id="videoSource" src="GAMBARKUU/89875672691fe288d3a1c336019af9c4.mp4" type="video/mp4"> <!-- Video awal -->
        Your browser does not support the video tag.
    </video>

    <div class="container">
        <h1>Maafinn kajoo ya nalaa???</h1>
        <p id="maafMessage">OIYAA KAMU BUKA AGAK LAMA YA WEBNYA, ADA LAGUNYAAA. Kajo minta maaf karena lama gaa ngabarin kamu, kajo masih hectic, apalagi tugas yang merajalela, ospek jurusan, terus harus beradaptasi sama lingkungan baru, kajo tau nala pasti marah bangettt yaaa, maafin kajoo ya nalaa💖, oiyaa kamu apa kabarr?? hehehe kalo jelek maaf ya karna kajo juga baru belajar, kamu gimana belajarnya? lancarkann? udah mau kuliah lohh, kajo tau kajo salah ga ngabarin dan ilang-ilangan terus, kajo sadarrr banget kalo salah, jadi di sini kajo lagii berusaha buat ini biar nalaa ga marah ke kajoo❤️</p>
        
        <div class="button-container" id="buttonContainer">
            <button onclick="tanyaMemaafkan(true)">Nala maafinn kok kajooo</button>
            <button id="noForgiveButton" onclick="tanyaMemaafkan(false)" onmouseover="startMoving()">GA NALA MAAFIN!</button>
        </div>

        <div class="input-container" id="inputContainer" style="display: none;">
            <input type="text" id="reasonInput" placeholder="Alasanmu (jika mau)" />
            <button onclick="submitReason()">Kirim</button>
        </div>
    </div>  

    <script>
        const videoSource = document.getElementById("videoSource");
        const backgroundVideo = document.getElementById("backgroundVideo");
        const maafMessage = document.getElementById("maafMessage");
        const buttonContainer = document.getElementById("buttonContainer");
        const inputContainer = document.getElementById("inputContainer");
        const reasonInput = document.getElementById("reasonInput");
        const noForgiveButton = document.getElementById("noForgiveButton");
        let moveInterval;
        function startMoving() {
            if (!moveInterval) {
                moveInterval = setInterval(() => {
                    const buttonRect = noForgiveButton.getBoundingClientRect();
                    const x = Math.random() * (window.innerWidth - buttonRect.width);
                    const y = Math.random() * (window.innerHeight - buttonRect.height - 100); // Menghindari bagian bawah layar
                    noForgiveButton.style.position = 'absolute';
                    noForgiveButton.style.left = x + 'px';
                    noForgiveButton.style.top = y + 'px';
                }, 300); // Interval waktu untuk pergerakan
            }
        }

        function stopMoving() {
            clearInterval(moveInterval);
            moveInterval = null;
        }

        function tanyaMemaafkan(isMemaafkan) {
            // Sembunyikan tombol setelah memilih
            buttonContainer.style.display = 'none';
            stopMoving(); // Hentikan pergerakan tombol

            if (isMemaafkan) {
                videoSource.src = "GAMBARKUU/1.mp4.mp4"; // Ganti video latar belakang jika memaafkan
                maafMessage.textContent = "MAKASIII NALA UDAH MAAFIN KAJOOO 💖";
            } else {
                noForgiveButton.disabled = true; // Nonaktifkan tombol tidak memaafkan
                videoSource.src = "GAMBARKUU/1.mp4.mp4"; // Ganti video latar belakang jika tidak memaafkan
                maafMessage.textContent = "KAMU HARUS MAAFIN KAJOOO😢";
                inputContainer.style.display = 'flex'; // Tampilkan input alasan
            }
            backgroundVideo.load();
        }

        function submitReason() {
            const reason = reasonInput.value;
            if (reason) {
                maafMessage.textContent = `Terima kasih atas alasanmu: "${reason}". Aku akan berusaha lebih baik.`;
                inputContainer.style.display = 'none'; // Sembunyikan input setelah dikirim
            } else {
                alert("Tolong berikan alasanmu sebelum mengirim.");
            }
        }
    </script>

</body>
</html>
