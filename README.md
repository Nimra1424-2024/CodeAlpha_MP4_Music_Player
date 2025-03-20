# CodeAlpha_MP4_Music_Player
A web-based MP4 audio player that supports multiple songs, offering play, pause, volume control, and a playlist selection for a seamless listening experience.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MP4 Audio Player</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: pink;
            margin: 0;
        }

        .player-container {
            background: #4a154b;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            width: 400px;
            color: white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        h2 {
            margin-bottom: 10px;
        }

        audio {
            width: 100%;
            margin-top: 10px;
        }

        .controls {
            margin-top: 10px;
        }

        .controls button {
            background: #ff6699;
            color: white;
            border: none;
            padding: 10px 15px;
            margin: 5px;
            border-radius: 5px;
            cursor: pointer;
        }

        .controls button:hover {
            background: #ff3366;
        }

        select {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
            border: none;
            font-size: 16px;
        }
    </style>
</head>
<body>

    <div class="player-container">
        <h2>🎵 MP4 Audio Player</h2>
        <select id="audioList" onchange="changeAudio()">
            <option value="audio1.mp4"> Nashe_Si_Chadh_Gayi___Full_Song___Befikre</option>
            <option value="audio2.mp4">Oh_Ho_Ho_Ho__Remix__Song___Irrfan_Khan_</option>
            <option value="audio3.mp4">__Nach_panjapan</option>
        </select>
        <audio id="audioPlayer" controls>
            <source id="audioSource" src="./Nashe_Si_Chadh_Gayi___Full_Song___Befikre,_Ranveer_Singh,_Vaani_Kapoor,_Arijit_Singh,_Vishal-Shekhar(128k).m4a" type="audio/mp4">
        </audio>
        <audio id="audioPlayer" controls>
            <source id="audioSource" src="./Oh_Ho_Ho_Ho__Remix__Song___Irrfan_Khan_,Saba_Qamar___Sukhbir,_Ikka(0).m4a" type="audio/mp4">
        </audio>
        <audio id="audioPlayer" controls>
            <source id="audioSource" src="./Coke_studio.__Abrar_ul_haq.__Nach_panjapan(128k).m4a" type="audio/mp4">
        </audio>
        <div class="controls">
            <button onclick="playAudio()">▶ Play</button>
            <button onclick="pauseAudio()">⏸ Pause</button>
            <button onclick="stopAudio()">⏹ Stop</button>
        </div>
    </div>

    <script>
        let audioPlayer = document.getElementById("audioPlayer");
        let audioSource = document.getElementById("audioSource");
        let audioList = document.getElementById("audioList");

        function changeAudio() {
            audioSource.src = audioList.value;
            audioPlayer.load();
            audioPlayer.play();
        }

        function playAudio() {
            audioPlayer.play();
        }

        function pauseAudio() {
            audioPlayer.pause();
        }

        function stopAudio() {
            audioPlayer.pause();
            audioPlayer.currentTime = 0; // Reset to start
        }
    </script>

</body>
</html>
