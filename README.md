# mediaplayer

<link rel="stylesheet" href="style.css">

<div id="player">
  <div id="album-art">
    <img src="album.jpg">
  </div>
  <div id="track-info">
    <span id="track-title"></span>
    <span id="artist"></span>
  </div>
  <div id="controls">
    <button id="play">Play</button>
    <button id="pause">Pause</button>
    <button id="stop">Stop</button>
  </div>
</div>

#player {
  width: 100%;
  height: 100%;
  position: relative;
}
#album-art {
  width: 100%;
  height: 300px;
  background-size: cover;
  background-position: center;
}
#track-info {
  position: absolute;
  top: 300px;
  left: 0;
  right: 0;
  padding: 10px;
  background: #fff;
}
#track-title {
  font-size: 18px;
  font-weight: bold;
}
#artist {
  font-size: 14px;
}
#controls {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 10px;
  background: #fff;
}
button {
  width: 50px;
  height: 50px;
  border: none;
  background: #000;
  color: #fff;
  cursor: pointer;
}
button:hover {
  background: #ccc;
}
var player = document.getElementById("player");
var albumArt = document.getElementById("album-art");
var trackTitle = document.getElementById("track-title");
var artist = document.getElementById("artist");
var controls = document.getElementById("controls");
var playButton = document.getElementById("play");
var pauseButton = document.getElementById("pause");
var stopButton = document.getElementById("stop");
var audio = new Audio();
audio.addEventListener("play", function() {
  playButton.disabled = true;
  pauseButton.disabled = false;
});
audio.addEventListener("pause", function() {
  playButton.disabled = false;
  pauseButton.disabled = true;
});
audio.addEventListener("stop", function() {
  playButton.disabled = false;
  pauseButton.disabled = true;
});
playButton.addEventListener("click", function() {
  audio.play();
});
pauseButton.addEventListener("click", function() {
  audio.pause();
});
stopButton.addEventListener("click", function() {
  audio.stop();
});
