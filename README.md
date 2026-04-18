<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Свадебное приглашение</title>

<style>
body {
margin: 0;
font-family: 'Georgia', serif;
color: #333;
scroll-behavior: smooth;
}

section {
padding: 80px 20px;
text-align: center;
opacity: 0;
transform: translateY(40px);
transition: all 1s ease;
}

section.show {
opacity: 1;
transform: translateY(0);
}

.hero {
background: url('https://drive.google.com/file/d/1rnHhPRFA5JbGUZxCi33648fJEuYD8QXT/view?usp=drive_link') center/cover no-repeat;
color: white;
height: 100vh;
display: flex;
flex-direction: column;
justify-content: center;
}

.hero h1 {
font-size: 48px;
margin-bottom: 20px;
}

.hero p {
max-width: 600px;
margin: 0 auto;
}

.gray {
background: #f5f5f5;
}

.date {
font-size: 36px;
margin-bottom: 20px;
}

.timer {
font-size: 28px;
margin-top: 20px;
}

.timeline {
display: flex;
justify-content: center;
gap: 40px;
flex-wrap: wrap;
align-items: center;
}

.timeline div {
position: relative;
}

.timeline div::after {
content: "→";
position: absolute;
right: -25px;
}

.timeline div:last-child::after {
display: none;
}

.map iframe {
width: 100%;
max-width: 600px;
height: 300px;
border: 0;
}

.dresscode {
background: url('https://drive.google.com/file/d/1H4_Iyioa52-RHiCb6Nzaqj34i2PI_j4A/view?usp=drive_link') center/cover no-repeat;
color: white;
}

.colors {
display: flex;
justify-content: center;
gap: 15px;
flex-wrap: wrap;
}

.color {
width: 80px;
height: 80px;
border-radius: 50%;
border: 2px solid #fff;
}

.pink { background: #f8c8dc; }
.blue { background: #c8e6f8; }
.yellow { background: #fff3b0; }
.green { background: #c8f8d8; }
.olive { background: #9fa86b; }

button {
padding: 15px 30px;
font-size: 16px;
border: none;
background: #d4a373;
color: white;
cursor: pointer;
border-radius: 5px;
}

footer {
padding: 60px;
font-size: 24px;
}
</style>

</head>

<body>

<!-- 1 экран -->
<section class="hero show">
<h1>Дарья & Сергей</h1>
<p>
Дорогие наши родные и друзья!<br><br>
Позвольте пригласить вас разделить с нами столь важный день —
торжество, посвященное нашему бракосочетанию.<br><br>
Наша свадьба состоится:
</p>
</section>

<!-- 2 экран -->
<section class="gray">
<div class="date">20 августа 2026</div>
<img src="https://drive.google.com/file/d/1LK3IIja6OupMa-0ykw8tbYjfm3PZFzIx/view?usp=drive_link" width="300">
<div class="timer" id="timer"></div>
</section>

<!-- 3 экран -->
<section>
<h2>Тайминг</h2>
<div class="timeline">
<div>12:00<br>Церемония</div>
<div>13:00<br>Фотосессия</div>
<div>17:00<br>Ужин</div>
<div>23:00<br>Завершение</div>
</div>
</section>

<!-- 4 экран -->
<section class="gray">
<h2>Место проведения</h2>
<p>Управление ЗАГС</p>
<div class="map">
<iframe src="https://maps.google.com/maps?q=Белгород,Попова,14&output=embed"></iframe>
</div>
</section>

<!-- 5 экран -->
<section class="dresscode">
<h2>Дресс-код</h2>
<p>
Мы очень ждём наше торжество и будем рады,
если вы выберете наряды в данной цветовой гамме
</p>

<div class="colors">
<div class="color pink"></div>
<div class="color blue"></div>
<div class="color yellow"></div>
<div class="color green"></div>
<div class="color olive"></div>
</div>
</section>

<!-- 6 экран -->
<section class="gray">
<button onclick="window.location.href='https://forms.gle/wBGfkj6pEau3Drqj9'">
Подтвердить присутствие
</button>
</section>

<footer>
С нетерпением ждём вас!
</footer>

<script>
// Таймер
const weddingDate = new Date("Aug 20, 2026 00:00:00").getTime();

setInterval(() => {
const now = new Date().getTime();
const diff = weddingDate - now;

const days = Math.floor(diff / (1000 * 60 * 60 * 24));
const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
const minutes = Math.floor((diff / (1000 * 60)) % 60);

document.getElementById("timer").innerHTML =
`${days} дней ${hours} часов ${minutes} минут`;
}, 1000);

// Анимация при скролле
const sections = document.querySelectorAll("section");

window.addEventListener("scroll", () => {
sections.forEach(sec => {
const pos = sec.getBoundingClientRect().top;
if (pos < window.innerHeight - 100) {
sec.classList.add("show");
}
});
});
</script>

</body>
</html>
