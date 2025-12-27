<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Music Player UI</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family: Arial, sans-serif;
  color:white;
}

body{
  height:100vh;
  background: radial-gradient(circle at top, #1a1a1a, #000);
  display:flex;
  justify-content:center;
  align-items:center;
}

@keyframes float {
  0%,100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}

#menuToggle{
  display:none;
}

.wrapper{
  position:relative;
  width:520px;
}

.player{
  background: rgba(25,25,25,0.75);
  backdrop-filter: blur(12px);
  border-radius:20px;
  padding:22px;

  box-shadow:
    0 40px 120px rgba(0,0,0,0.95),
    0 20px 40px rgba(0,0,0,0.7),
    inset 0 1px 1px rgba(255,255,255,0.08);

  border:1px solid rgba(255,255,255,0.15);
  animation: float 5s ease-in-out infinite;
}

.top{
  display:flex;
  justify-content:space-between;
  margin-bottom:16px;
}

.menu-btn{
  cursor:pointer;
  font-size:22px;
}

.song{
  text-align:center;
  margin-bottom:16px;
}

.song h3{
  font-size:18px;
}

.song p{
  font-size:13px;
  opacity:0.9;
}

.controls{
  display:flex;
  justify-content:center;
  gap:16px;
  margin-bottom:16px;
}

.controls div{
  width:48px;
  height:48px;
  background:linear-gradient(145deg,#1e1e1e,#0f0f0f);
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
  cursor:pointer;

  box-shadow:
    0 10px 25px rgba(0,0,0,0.9),
    inset 0 1px 1px rgba(255,255,255,0.1);

  transition:0.25s;
}

.controls div:hover{
  transform: translateY(-4px);
}

.controls div:active{
  transform: translateY(2px);
}

.progress{
  display:flex;
  align-items:center;
  gap:10px;
  font-size:12px;
}

.bar{
  flex:1;
  height:8px;
  background:#222;
  border-radius:10px;
  overflow:hidden;
  box-shadow: inset 0 2px 6px rgba(0,0,0,0.8);
}

.fill{
  width:50%;
  height:100%;
  background: linear-gradient(90deg,#ffffff,#bfbfbf);
  box-shadow: 0 0 10px rgba(255,255,255,0.6);
}

.playlist{
  position:absolute;
  top:0;
  right:-240px;
  width:220px;
  height:100%;
  background:#181818;
  padding:15px;
  border-radius:20px;
  box-shadow:0 30px 80px rgba(0,0,0,0.9);
  transition:0.4s;
}

#menuToggle:checked ~ .playlist{
  right:0;
}

.playlist h4{
  margin-bottom:10px;
  border-bottom:1px solid white;
  padding-bottom:6px;
}

.track{
  padding:8px;
  cursor:pointer;
  border-radius:6px;
}

.track:hover{
  background:#333;
}
</style>
</head>

<body>

<div class="wrapper">

  <input type="checkbox" id="menuToggle">

  <div class="player">

    <div class="top">
      <label for="menuToggle" class="menu-btn">☰</label>
      <div>♡</div>
    </div>

    <div class="song">
      <h3>Now Playing</h3>
      <p>Electronic • Chill</p>
    </div>

    <div class="controls">
      <div>⏮</div>
      <div>▶</div>
      <div>⏭</div>
    </div>

    <div class="progress">
      <span>1:20</span>
      <div class="bar">
        <div class="fill"></div>
      </div>
      <span>3:40</span>
    </div>

  </div>

  <div class="playlist">
    <h4>Playlist</h4>
    <div class="track">Track One</div>
    <div class="track">Track Two</div>
    <div class="track">Track Three</div>
    <div class="track">Track Four</div>
  </div>

</div>

</body>
</html>
