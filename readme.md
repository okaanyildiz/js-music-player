js-music-player

steps to take

MAKING THE PLAYER CONTAINER UI

1) Make the Song part of the index.html. 
2) Make the initial CSS
3) Use Google Fonts: 
Google fonts - league spartan
Regular 400
Bold 700
4) Photos from unsplash.com

index.html: 
```
<!DOCTYPE html>
<html lang="en">
 
<head>
   <meta charset="UTF-8">
   <meta http-equiv="X-UA-Compatible" content="IE=edge">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <link rel="stylesheet" href="styles.css">
   <title>Music Player</title>
</head>
 
<body>
 
   <div class='player-container'>
       <!-- Song -->
       <div class='img-container'>
           <img src='img/misc1.jpg' alt='Album Art'>
       </div>
       <h2 id='title'>Chill Machine</h2>
       <h3 id='artist'>Miscellaneous</h3>
       <audio src='music/misc1.mp3' controls></audio>
   </div>
 
   <!-- script -->
   <script src="script.js"></script>
</body>.
 
</html>
```
styles.css:
```
/* Images created by: https://unsplash.com/@pawel_czerwinski */
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@400;700&family=Source+Sans+Pro:wght@200;300;400;600;700;900&display=swap');
 
html {
   box-sizing: border-box;
}
 
body {
   margin: 0;
   min-height: 100vh;
   background: #c9ced3;
   display: flex;
   justify-content: center;
   align-items: center;
   font-family: 'League Spartan', sans-serif;
   font-size: 12px;
}
 
.player-container {
   height: 500px;
   width: 400px;
   background: #e7e7e7;
   border-radius: 20px;
   box-shadow: 0 15px 30px 5px rgba(0, 0, 0, .3);
}
 
.img-container {
   height: 300px;
   width: 300px;
   position: relative;
   top: -50px;
   left: 50px;
}
 
.img-container img {
   height: 100%;
   width: 100%;
   object-fit: cover;
   border-radius: 20px;
   box-shadow: 0 5px 30px rgba(0, 0, 0, .5);
}
 
h2 {
   font-size: 25px;
   text-align: center;
   margin: 0;
}
 
h3 {
   font-size: 20px;
   text-align: center;
   font-weight: 400;
   margin: 5px 0 0;
}
 
/* Controls */
.player-controls {
   position: relative;
   top: -15px;
   left: 120px;
   width: 200px;
}
 
.fas {
   font-size: 30px;
   color: rgb(129, 129, 129);
   margin-right: 30px;
 
}
 
.main-button {
   font-size: 40px;
   position: relative;
   top: 3px;
}
 
/* Media Query: iPhone (Vertical) */
@media screen and (max-width: 376px) {
 
   .player-container {
       width: 95vw;
   }
 
 
   .img-container {
       left: 29px;
   }
 
   h2 {
       font-size: 20px;
   }
 
   h3 {
       font-size: 15px;
   }
 
   .player-controls {
       top: -10px;
       left: 100px;
   }
}
```
MAKING THE  PROGRESS CONTAINER AND CONTROLS UI

Make the Progress and Controls part of the index.html
Use font-awesome for the control icons. 
Add styles for Progress Bar.

index.html: 
```
<!DOCTYPE html>
<html lang="en">
 
<head>
   <meta charset="UTF-8">
   <meta http-equiv="X-UA-Compatible" content="IE=edge">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.10.2/css/all.min.css" />
   <link rel="stylesheet" href="styles.css">
   <title>Music Player</title>
</head>
 
<body>
 
   <div class='player-container'>
       <!-- Song -->
       <div class='img-container'>
           <img src='img/misc1.jpg' alt='Album Art'>
       </div>
       <h2 id='title'>Chill Machine</h2>
       <h3 id='artist'>Miscellaneous</h3>
       <audio src='music/misc1.mp3'></audio>
 
       <!-- Progress -->
       <div class="progress-container" id="progress-container">
           <div class="progress" id="progress"></div>
           <div class="duration-wrapper">
               <span id="current-time">0:00</span>
               <span id="duration">2:06</span>
           </div>
       </div>
 
       <!-- Controls -->
       <div class="player-controls">
           <i class="fas fa-backward" id="prev" title="Previous"></i>
           <i class="fas fa-play main-button" id="play" title="Play"></i>
           <i class="fas fa-forward" id="next" title="Next"></i>
       </div>
   </div>
   <!-- script -->
   <script src="script.js"></script>
</body>
 
</html>
```
styles.css: 
```
/* Images created by: https://unsplash.com/@pawel_czerwinski */
@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@400;700&family=Source+Sans+Pro:wght@200;300;400;600;700;900&display=swap');
 
html {
   box-sizing: border-box;
}
 
body {
   margin: 0;
   min-height: 100vh;
   background: #c9ced3;
   display: flex;
   justify-content: center;
   align-items: center;
   font-family: 'League Spartan', sans-serif;
   font-size: 12px;
}
 
.player-container {
   height: 500px;
   width: 400px;
   background: #e7e7e7;
   border-radius: 20px;
   box-shadow: 0 15px 30px 5px rgba(0, 0, 0, .3);
}
 
.img-container {
   height: 300px;
   width: 300px;
   position: relative;
   top: -50px;
   left: 50px;
}
 
.img-container img {
   height: 100%;
   width: 100%;
   object-fit: cover;
   border-radius: 20px;
   box-shadow: 0 5px 30px rgba(0, 0, 0, .5);
}
 
h2 {
   font-size: 25px;
   text-align: center;
   margin: 0;
}
 
h3 {
   font-size: 20px;
   text-align: center;
   font-weight: 400;
   margin: 5px 0 0;
}
 
/* Progress */
.progress-container {
   background: #fff;
   border-radius: 5px;
   cursor: pointer;
   margin: 40px 20px;
   height: 4px;
   width: 90%;
}
 
.progress {
   background: #242323;
   border-radius: 5px;
   height: 100%;
   /* change this to show progress */
   width: 66%;
   transition: width 0.1s linear;
}
 
.duration-wrapper {
   position: relative;
   top: -25px;
   display: flex;
   justify-content: space-between;
}
 
/* Controls */
.player-controls {
   position: relative;
   top: -15px;
   left: 120px;
   width: 200px;
}
 
.fas {
   font-size: 30px;
   color: rgb(129, 129, 129);
   margin-right: 30px;
   cursor: pointer;
   user-select: none;
}
 
.fas:hover {
   filter: brightness(80%);
}
 
.main-button {
   font-size: 40px;
   position: relative;
   top: 3px;
}
 
/* Media Query: iPhone (Vertical) */
@media screen and (max-width: 376px) {
 
   .player-container {
       width: 95vw;
   }
 
 
   .img-container {
       left: 29px;
   }
 
   h2 {
       font-size: 20px;
   }
 
   h3 {
       font-size: 15px;
   }
 
   .player-controls {
       top: -10px;
       left: 100px;
   }
}
```

MAKING THE PLAY-PAUSE FUNCTIONALITY

Declare the consts for buttons and audio. 
Add the event listener to the play button. 
Make the playSong() function.
Make the pauseSong() function.

script.js:

```
const music = document.querySelector('audio');
const prevBtn = document.getElementById('prev');
const playBtn = document.getElementById('play');
const nextBtn = document.getElementById('next');
 
// Check if playing
let isPlaying = false;
 
// Play
function playSong() {
   isPlaying = true;
   playBtn.classList.replace('fa-play', 'fa-pause')
   playBtn.setAttribute('title', 'pause')
   music.play();
}
 
// Pause
function pauseSong() {
   isPlaying = false;
   playBtn.classList.replace('fa-pause', 'fa-play')
   playBtn.setAttribute('title', 'play')
   music.pause();
}
 
// Play-Pause Event Listener
playBtn.addEventListener('click', () => (isPlaying ? pauseSong() : playSong()));
```

MAKING THE PREVIOUS-NEXT FUNCTIONALITY

Declare the consts for image, title and the artist. 
Declare the songs array with song objects. 
Make the loadSong(song) function.
Check out some songs, titles and images manually with loadSong(). 
 
script.js: 
```
const image = document.querySelector('img');
const title = document.getElementById('title');
const artist = document.getElementById('artist');
const music = document.querySelector('audio');
const prevBtn = document.getElementById('prev');
const playBtn = document.getElementById('play');
const nextBtn = document.getElementById('next');
 
// Music
const songs = [
   {
       name: 'misc1',
       displayName: 'Electric Chill Machine',
       artist: 'Mugu'
   },
   {
       name: 'misc2',
       displayName: 'Seven Nation Army (Remix)',
       artist: 'Mugu'
   },
   {
       name: 'misc3',
       displayName: 'Goodnight, Disco Queen',
       artist: 'Mugu'
   },
   {
       name: 'misc4',
       displayName: 'Front Row (Remix)',
       artist: 'Mugu'
   }
]
 
// Check if playing
let isPlaying = false;
 
// Play
function playSong() {
   isPlaying = true;
   playBtn.classList.replace('fa-play', 'fa-pause')
   playBtn.setAttribute('title', 'pause')
   music.play();
}
 
// Pause
function pauseSong() {
   isPlaying = false;
   playBtn.classList.replace('fa-pause', 'fa-play')
   playBtn.setAttribute('title', 'play')
   music.pause();
}
 
// Play-Pause Event Listener
playBtn.addEventListener('click', () => (isPlaying ? pauseSong() : playSong()));
 
// Update DOM
function loadSong(song) {
   title.textContent = song.displayName;
   artist.textContent = song.artist;
   music.src = `music/${song.name}.mp3`;
   image.src = `img/${song.name}.jpg`;
}
 
// On Load - Select First Song
loadSong(songs[3]);
```
Add event listeners for prev and next buttons. 
Declare the current song index with a variable.
Make nextSong() function.
Make prevSong() function.

script.js: 
```
const image = document.querySelector('img');
const title = document.getElementById('title');
const artist = document.getElementById('artist');
const music = document.querySelector('audio');
const prevBtn = document.getElementById('prev');
const playBtn = document.getElementById('play');
const nextBtn = document.getElementById('next');
 
// Music
const songs = [
   {
       name: 'misc1',
       displayName: 'Electric Chill Machine',
       artist: 'Mugu'
   },
   {
       name: 'misc2',
       displayName: 'Seven Nation Army (Remix)',
       artist: 'Mugu'
   },
   {
       name: 'misc3',
       displayName: 'Goodnight, Disco Queen',
       artist: 'Mugu'
   },
   {
       name: 'misc4',
       displayName: 'Front Row (Remix)',
       artist: 'Mugu'
   }
]
 
// Check if playing
let isPlaying = false;
 
// Play
function playSong() {
   isPlaying = true;
   playBtn.classList.replace('fa-play', 'fa-pause')
   playBtn.setAttribute('title', 'pause')
   music.play();
}
 
// Pause
function pauseSong() {
   isPlaying = false;
   playBtn.classList.replace('fa-pause', 'fa-play')
   playBtn.setAttribute('title', 'play')
   music.pause();
}
 
// Play-Pause Event Listener
playBtn.addEventListener('click', () => (isPlaying ? pauseSong() : playSong()));
 
// Update DOM
function loadSong(song) {
   title.textContent = song.displayName;
   artist.textContent = song.artist;
   music.src = `music/${song.name}.mp3`;
   image.src = `img/${song.name}.jpg`;
}
 
// Current Song
let songIndex = 0;
 
// Previous Song
function prevSong() {
   songIndex--;
   if (songIndex < 0) {
       songIndex = songs.length - 1;
   }
   console.log(songIndex);
   loadSong(songs[songIndex]);
   playSong();
}
 
// Next Song
function nextSong() {
   songIndex++;
   if (songIndex > songs.length - 1) {
       songIndex = 0;
   }
   console.log(songIndex);
   loadSong(songs[songIndex]);
   playSong();
}
 
// On Load - Select First Song
loadSong(songs[0]);
 
// Prev-Next Event Listener
prevBtn.addEventListener('click', prevSong);
nextBtn.addEventListener('click', nextSong);
 
 
```

UPDATING THE PROGRESS BAR

Change the progress value to 0 in styles.css.
Declare the consts for progress and progress-container.
Add the  event listener for the music. 
Make the updateProgressBar(e) function. 
Console.log(e) to display the progress properties.
Console.log these properties to display progress. 
Make progress percentage with progress properties to update the progress bar width.

script.js: 
```
const image = document.querySelector('img');
const title = document.getElementById('title');
const artist = document.getElementById('artist');
const music = document.querySelector('audio');
const progressContainer = document.getElementById('progress-container');
const progress = document.getElementById('progress');
const prevBtn = document.getElementById('prev');
const playBtn = document.getElementById('play');
const nextBtn = document.getElementById('next');
 
// Music
const songs = [
   {
       name: 'misc1',
       displayName: 'Electric Chill Machine',
       artist: 'Mugu'
   },
   {
       name: 'misc2',
       displayName: 'Seven Nation Army (Remix)',
       artist: 'Mugu'
   },
   {
       name: 'misc3',
       displayName: 'Goodnight, Disco Queen',
       artist: 'Mugu'
   },
   {
       name: 'misc4',
       displayName: 'Front Row (Remix)',
       artist: 'Mugu'
   }
]
 
// Check if playing
let isPlaying = false;
 
// Play
function playSong() {
   isPlaying = true;
   playBtn.classList.replace('fa-play', 'fa-pause')
   playBtn.setAttribute('title', 'pause')
   music.play();
}
 
// Pause
function pauseSong() {
   isPlaying = false;
   playBtn.classList.replace('fa-pause', 'fa-play')
   playBtn.setAttribute('title', 'play')
   music.pause();
}
 
// Play-Pause Event Listener
playBtn.addEventListener('click', () => (isPlaying ? pauseSong() : playSong()));
 
// Update DOM
function loadSong(song) {
   title.textContent = song.displayName;
   artist.textContent = song.artist;
   music.src = `music/${song.name}.mp3`;
   image.src = `img/${song.name}.jpg`;
}
 
// Current Song
let songIndex = 0;
 
// Previous Song
function prevSong() {
   songIndex--;
   if (songIndex < 0) {
       songIndex = songs.length - 1;
   }
   loadSong(songs[songIndex]);
   playSong();
}
 
// Next Song
function nextSong() {
   songIndex++;
   if (songIndex > songs.length - 1) {
       songIndex = 0;
   }
   loadSong(songs[songIndex]);
   playSong();
}
 
// On Load - Select First Song
loadSong(songs[0]);
 
// Update Progress Bar & Time
function updateProgressBar(e) {
   if (isPlaying) {
       const { duration, currentTime } = e.srcElement;
       console.log(duration, currentTime);
       // Update progress bar width
       const progressPercent = (currentTime / duration) * 100;
       progress.style.width = `${progressPercent}%`;
   }
}
 
// Event Listeners
prevBtn.addEventListener('click', prevSong);
nextBtn.addEventListener('click', nextSong);
music.addEventListener('timeupdate', updateProgressBar);
 
 
```

POPULATING THE DURATION

Declare the duration and current time consts.
Update the “updateProgressBar(e)” function.
Calculate display for duration. 
Delay switching duration Element to avoid NaN
Calculate display for the current time. 

script.js:
```
​​const image = document.querySelector('img');
const title = document.getElementById('title');
const artist = document.getElementById('artist');
const music = document.querySelector('audio');
const progressContainer = document.getElementById('progress-container');
const progress = document.getElementById('progress');
const currentTimeEl = document.getElementById('current-time');
const durationEl = document.getElementById('duration');
const prevBtn = document.getElementById('prev');
const playBtn = document.getElementById('play');
const nextBtn = document.getElementById('next');
 
// Music
const songs = [
   {
       name: 'misc1',
       displayName: 'Electric Chill Machine',
       artist: 'Mugu'
   },
   {
       name: 'misc2',
       displayName: 'Seven Nation Army (Remix)',
       artist: 'Mugu'
   },
   {
       name: 'misc3',
       displayName: 'Goodnight, Disco Queen',
       artist: 'Mugu'
   },
   {
       name: 'misc4',
       displayName: 'Front Row (Remix)',
       artist: 'Mugu'
   }
]
 
// Check if playing
let isPlaying = false;
 
// Play
function playSong() {
   isPlaying = true;
   playBtn.classList.replace('fa-play', 'fa-pause')
   playBtn.setAttribute('title', 'pause')
   music.play();
}
 
// Pause
function pauseSong() {
   isPlaying = false;
   playBtn.classList.replace('fa-pause', 'fa-play')
   playBtn.setAttribute('title', 'play')
   music.pause();
}
 
// Play-Pause Event Listener
playBtn.addEventListener('click', () => (isPlaying ? pauseSong() : playSong()));
 
// Update DOM
function loadSong(song) {
   title.textContent = song.displayName;
   artist.textContent = song.artist;
   music.src = `music/${song.name}.mp3`;
   image.src = `img/${song.name}.jpg`;
}
 
// Current Song
let songIndex = 0;
 
// Previous Song
function prevSong() {
   songIndex--;
   if (songIndex < 0) {
       songIndex = songs.length - 1;
   }
   loadSong(songs[songIndex]);
   playSong();
}
 
// Next Song
function nextSong() {
   songIndex++;
   if (songIndex > songs.length - 1) {
       songIndex = 0;
   }
   loadSong(songs[songIndex]);
   playSong();
}
 
// On Load - Select First Song
loadSong(songs[0]);
 
// Update Progress Bar & Time
function updateProgressBar(e) {
   if (isPlaying) {
       const { duration, currentTime } = e.srcElement;
       // Update progress bar width
       const progressPercent = (currentTime / duration) * 100;
       progress.style.width = `${progressPercent}%`;
       // Calculate display for duration
       const durationMinutes = Math.floor(duration / 60);
       console.log('minutes', durationMinutes);
       let durationSeconds = Math.floor(duration % 60);
       if (durationSeconds < 10) {
           durationSeconds = `0${durationSeconds}`;
       }
       console.log('seconds', durationSeconds);
       // Delay switching duration Element to avoid NaN
       if (durationSeconds) {
           durationEl.textContent = `${durationMinutes}:${durationSeconds}`;
       }
       // Calculate display for the current
       const currentMinutes = Math.floor(currentTime / 60);
       console.log('minutes', currentMinutes);
       let currentSeconds = Math.floor(currentTime % 60);
       if (currentSeconds < 10) {
           currentSeconds = `0${currentSeconds}`;
       }
       console.log('seconds', currentSeconds);
       currentTimeEl.textContent = `${currentMinutes}:${currentSeconds}`;
   }
}
 
// Event Listeners
prevBtn.addEventListener('click', prevSong);
nextBtn.addEventListener('click', nextSong);
music.addEventListener('timeupdate', updateProgressBar);
 
 
```

JUMPING THROUGH THE PROGRESS BAR

Add the event listener to the progress container. 
Make the setProgressBar(e) function.    
Add the ended event listener to the music. 

script.js: 

```
const image = document.querySelector('img');
const title = document.getElementById('title');
const artist = document.getElementById('artist');
const music = document.querySelector('audio');
const progressContainer = document.getElementById('progress-container');
const progress = document.getElementById('progress');
const currentTimeEl = document.getElementById('current-time');
const durationEl = document.getElementById('duration');
const prevBtn = document.getElementById('prev');
const playBtn = document.getElementById('play');
const nextBtn = document.getElementById('next');
 
// Music
const songs = [
   {
       name: 'misc1',
       displayName: 'Electric Chill Machine',
       artist: 'Mugu'
   },
   {
       name: 'misc2',
       displayName: 'Seven Nation Army (Remix)',
       artist: 'Mugu'
   },
   {
       name: 'misc3',
       displayName: 'Goodnight, Disco Queen',
       artist: 'Mugu'
   },
   {
       name: 'misc4',
       displayName: 'Front Row (Remix)',
       artist: 'Mugu'
   }
]
 
// Check if playing
let isPlaying = false;
 
// Play
function playSong() {
   isPlaying = true;
   playBtn.classList.replace('fa-play', 'fa-pause')
   playBtn.setAttribute('title', 'pause')
   music.play();
}
 
// Pause
function pauseSong() {
   isPlaying = false;
   playBtn.classList.replace('fa-pause', 'fa-play')
   playBtn.setAttribute('title', 'play')
   music.pause();
}
 
// Play-Pause Event Listener
playBtn.addEventListener('click', () => (isPlaying ? pauseSong() : playSong()));
 
// Update DOM
function loadSong(song) {
   title.textContent = song.displayName;
   artist.textContent = song.artist;
   music.src = `music/${song.name}.mp3`;
   image.src = `img/${song.name}.jpg`;
}
 
// Current Song
let songIndex = 0;
 
// Previous Song
function prevSong() {
   songIndex--;
   if (songIndex < 0) {
       songIndex = songs.length - 1;
   }
   loadSong(songs[songIndex]);
   playSong();
}
 
// Next Song
function nextSong() {
   songIndex++;
   if (songIndex > songs.length - 1) {
       songIndex = 0;
   }
   loadSong(songs[songIndex]);
   playSong();
}
 
// On Load - Select First Song
loadSong(songs[0]);
 
// Update Progress Bar & Time
function updateProgressBar(e) {
   if (isPlaying) {
       const { duration, currentTime } = e.srcElement;
       // Update progress bar width
       const progressPercent = (currentTime / duration) * 100;
       progress.style.width = `${progressPercent}%`;
       // Calculate display for duration
       const durationMinutes = Math.floor(duration / 60);
       let durationSeconds = Math.floor(duration % 60);
       if (durationSeconds < 10) {
           durationSeconds = `0${durationSeconds}`;
       }
       // Delay switching duration Element to avoid NaN
       if (durationSeconds) {
           durationEl.textContent = `${durationMinutes}:${durationSeconds}`;
       }
       // Calculate display for the current
       const currentMinutes = Math.floor(currentTime / 60);
       let currentSeconds = Math.floor(currentTime % 60);
       if (currentSeconds < 10) {
           currentSeconds = `0${currentSeconds}`;
       }
       currentTimeEl.textContent = `${currentMinutes}:${currentSeconds}`;
   }
}
 
// Set Progress Bar
function setProgressBar(e) {
   const width = this.clientWidth;
   const clickX = e.offsetX;
   const { duration } = music;
   music.currentTime = (clickX / width) * duration;
}
 
// Event Listeners
prevBtn.addEventListener('click', prevSong);
nextBtn.addEventListener('click', nextSong);
music.addEventListener('ended', nextSong);
music.addEventListener('timeupdate', updateProgressBar);
progressContainer.addEventListener('click', setProgressBar)
```