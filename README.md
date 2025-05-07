<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>Yannik Raul Heigl Fanpage</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #111;
      color: white;
      text-align: center;
      padding: 40px;
    }

    h1 {
      color: #00ffcc;
    }

    .dropdown {
      margin: 20px auto;
      display: inline-block;
    }

    select {
      font-size: 16px;
      padding: 10px;
      width: 260px;
    }

    .content {
      display: none;
      background: #222;
      padding: 20px;
      border-radius: 10px;
      width: 320px;
      margin: 20px auto;
      box-shadow: 0 2px 5px rgba(0,0,0,0.5);
      text-align: left;
    }

    img {
      max-width: 100%;
      border-radius: 10px;
      margin-top: 10px;
    }

    #gyatt-button {
      margin-top: 30px;
      padding: 12px 20px;
      background-color: #00ffcc;
      border: none;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
    }

    .gyatt {
      position: absolute;
      font-weight: bold;
      color: #00ffcc;
      animation: floatUp 2s ease-out forwards;
      pointer-events: none;
      font-size: 20px;
    }

    @keyframes floatUp {
      0% {
        opacity: 1;
        transform: translateY(0);
      }
      100% {
        opacity: 0;
        transform: translateY(-150px) rotate(360deg);
      }
    }
  </style>
</head>
<body>

  <h1>Yannik Raul Heigl Fanpage</h1>

  <div class="dropdown">
    <label for="menu"><strong>Kategorie wählen:</strong></label><br>
    <select id="menu" onchange="showContent()">
      <option value="">-- bitte wählen --</option>
      <option value="meme">Warum er ein wandelndes Meme ist</option>
      <option value="lisbeln">Warum er lispelt</option>
      <option value="infos">Allgemeine Infos</option>
    </select>
  </div>

  <div id="meme" class="content">
    <h2>Warum er ein wandelndes Meme ist</h2>
    <p>Rauli twerkt überall – im Klassenzimmer, auf dem Pausenhof, sogar im Sitzen.</p>
    <p>Er ruft „GYATT!“ in jeder Situation, in der normale Menschen einfach still bleiben würden.</p>
    <p>Seine Gesichtsausdrücke wirken wie aus einem Cartoon – kein Frame normal.</p>
    <p>Wenn man ihn ansieht, denkt man: „Das kann kein echter Mensch sein.“</p>
    <img src="IMG_0616.jpeg" alt="Meme-Bild von Yannik">
  </div>

  <div id="lisbeln" class="content">
    <h2>Warum er lispelt</h2>
    <p>Yannik trägt eine feste Zahnspange – und die sorgt für sein markantes Lispeln.</p>
    <p>Er versucht Sätze zu beenden, während die Spange einen eigenen Podcast aufnimmt.</p>
    <p>Er sagt: „Ich find das nicht schlimm.“ – alle anderen: „Doch.“</p>
    <img src="IMG_0234.jpeg" alt="Zahnspangen-Foto">
  </div>

  <div id="infos" class="content">
    <h2>Allgemeine Infos</h2>
    <p><strong>Voller Name:</strong> Yannik Raul Heigl</p>
    <p><strong>Spitznamen:</strong> Rauli, Gyattman (Gyatti)</p>
    <p>Er hatte mal einen Irokesenschnitt und lief damit rum, als wär er bei einer Metalband – leider war's nur 7. Klasse.</p>
    <p>Er diskutiert über alles, sogar über Dinge, die niemand angesprochen hat.</p>
    <p>Sein Talent? Diskussion starten – verlieren – trotzdem weitermachen.</p>
    <img src="PHOTO-2023-03-08-12-04-25.jpeg" alt="Irokesenbild">
    <img src="IMG_0273.png" alt="Zusatzbild von Yannik">
  </div>

  <button id="gyatt-button" onclick="spawnGyatts()">GYATT!</button>

  <script>
    function showContent() {
      document.getElementById("meme").style.display = "none";
      document.getElementById("lisbeln").style.display = "none";
      document.getElementById("infos").style.display = "none";

      const value = document.getElementById("menu").value;
      if (value) {
        document.getElementById(value).style.display = "block";
      }
    }

    function spawnGyatts() {
      for (let i = 0; i < 20; i++) {
        const gyatt = document.createElement("div");
        gyatt.className = "gyatt";
        gyatt.textContent = "GYATT";
        gyatt.style.left = Math.random() * 90 + "vw";
        gyatt.style.top = "60vh";
        document.body.appendChild(gyatt);

        setTimeout(() => {
          gyatt.remove();
        }, 2000);
      }
    }
  </script>

</body>
</html>
