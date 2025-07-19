<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>360 Render Üzerinde Küpler</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      overflow: hidden;
    }

    #viewer {
      width: 100vw;
      height: 100vh;
      background-image: url('11.jpg'); /* Kendi renderın */
      background-size: cover;
      background-position: center;
      position: relative;
    }

    .btn {
      position: absolute;
      padding: 8px 12px;
      font-size: 14px;
      border-radius: 8px;
      background-color: rgba(255, 255, 255, 0.9);
      border: 1px solid #ccc;
      cursor: pointer;
      transition: background 0.3s;
    }

    .btn:hover {
      background-color: #ddd;
    }

    .cube {
      position: absolute;
      width: 60px;
      height: 60px;
      transform: rotateX(15deg) rotateY(15deg);
      box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.3);
      transition: background-color 0.3s;
    }
  </style>
</head>
<body>

<div id="viewer">
  <!-- Küp 1 (Sol) -->
  <button class="btn" style="top: 70%; left: 24%;" onclick="changeColor('cube1')">Küp 1 Renk</button>
  <div id="cube1" class="cube" style="top: 59%; left: 27%; background-color: red;"></div>

  <!-- Küp 2 (Orta) -->
  <button class="btn" style="top: 70%; left: 46%;" onclick="changeColor('cube2')">Küp 2 Renk</button>
  <div id="cube2" class="cube" style="top: 59%; left: 49%; background-color: blue;"></div>

  <!-- Küp 3 (Sağ) -->
  <button class="btn" style="top: 70%; left: 67%;" onclick="changeColor('cube3')">Küp 3 Renk</button>
  <div id="cube3" class="cube" style="top: 59%; left: 70%; background-color: purple;"></div>
</div>

<script>
  const renkler = ['red', 'green', 'blue', 'orange', 'pink', 'yellow'];
  const index = { cube1: 0, cube2: 0, cube3: 0 };

  function changeColor(id) {
    index[id] = (index[id] + 1) % renkler.length;
    document.getElementById(id).style.backgroundColor = renkler[index[id]];
  }
</script>

</body>
</html>
