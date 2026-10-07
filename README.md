<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Our Little Universe</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html, body {
    width: 100%;
    height: 100%;
}

body {
    overflow: hidden;
    font-family: Arial, sans-serif;
    background: #02030b;
    color: white;
}

/* =========================
   GENERAL PAGES
========================= */

.page {
    position: fixed;
    inset: 0;
    display: none;
    overflow: hidden;
}

.page.active {
    display: block;
}

/* =========================
   PAGE 1 — ENTER
========================= */

#enterPage {
    background:
        radial-gradient(circle at center, #111642 0%, #050718 45%, #010106 100%);
    justify-content: center;
    align-items: center;
}

#enterPage.active {
    display: flex;
}

.enter-stars,
.universe-stars {
    position: absolute;
    inset: 0;
    background-image:
        radial-gradient(circle, white 1px, transparent 1px),
        radial-gradient(circle, white 1px, transparent 1px);
    background-size: 80px 80px, 130px 130px;
    background-position: 10px 20px, 50px 70px;
    opacity: .5;
    animation: drift 20s linear infinite;
}

@keyframes drift {
    from {
        transform: translateY(0);
    }
    to {
        transform: translateY(80px);
    }
}

.enter-content {
    position: relative;
    z-index: 2;
    text-align: center;
    padding: 20px;
}

.enter-content h1 {
    font-size: clamp(45px, 12vw, 100px);
    letter-spacing: 15px;
    font-weight: 300;
    text-shadow: 0 0 30px #9ca8ff;
}

.enter-content p {
    margin-top: 15px;
    opacity: .65;
    letter-spacing: 3px;
    line-height: 1.6;
}

.enter-btn {
    margin-top: 45px;
    padding: 16px 45px;
    border: 1px solid rgba(255,255,255,.5);
    border-radius: 50px;
    background: rgba(255,255,255,.06);
    color: white;
    font-size: 17px;
    letter-spacing: 4px;
    cursor: pointer;
    transition: .3s;
    backdrop-filter: blur(10px);
}

.enter-btn:hover {
    transform: scale(1.08);
    background: rgba(255,255,255,.15);
    box-shadow: 0 0 35px rgba(150,170,255,.6);
}

/* =========================
   PAGE 2 — UNIVERSE
========================= */

#universePage {
    background:
        radial-gradient(circle at 50% 50%, #10183e 0%, #050717 45%, #010106 100%);
}

.universe-stars {
    opacity: .35;
}

.instruction {
    position: absolute;
    top: 25px;
    left: 50%;
    transform: translateX(-50%);
    width: 90%;
    text-align: center;
    z-index: 10;
}

.instruction h2 {
    font-size: clamp(20px, 5vw, 30px);
    font-weight: 400;
}

.instruction p {
    margin-top: 8px;
    opacity: .65;
    font-size: 14px;
}

/* =========================
   OBJECTS
========================= */

.object {
    position: absolute;
    cursor: pointer;
    transition: transform .3s;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
}

.object:hover {
    transform: scale(1.2);
}

.planet {
    border-radius: 50%;
    box-shadow:
        inset -15px -15px 25px rgba(0,0,0,.5),
        0 0 25px rgba(130,150,255,.5);
}

/* Planet 1 */

.p1 {
    width: 85px;
    height: 85px;
    left: 12%;
    top: 28%;
    background:
        radial-gradient(
            circle at 30% 30%,
            #ffb56b,
            #a94754 55%,
            #29142f
        );
}

/* Planet 2 */

.p2 {
    width: 65px;
    height: 65px;
    right: 15%;
    top: 23%;
    background:
        radial-gradient(
            circle at 35% 30%,
            #7cf0ff,
            #2666a6 60%,
            #10204c
        );
}

/* Planet 3 */

.p3 {
    width: 110px;
    height: 110px;
    right: 10%;
    bottom: 18%;
    background:
        radial-gradient(
            circle at 35% 30%,
            #e6a6ff,
            #703c9c 60%,
            #21132e
        );
}

/* Planet 4 */

.p4 {
    width: 55px;
    height: 55px;
    left: 22%;
    bottom: 20%;
    background:
        radial-gradient(
            circle at 30% 25%,
            #fff0a1,
            #c8792e 60%,
            #40201a
        );
}

/* =========================
   MOON
========================= */

.moon {
    width: 85px;
    height: 85px;
    right: 34%;
    top: 45%;
    border-radius: 50%;
    background: #e7e9ed;
    box-shadow: 0 0 35px rgba(255,255,255,.5);
}

.moon::after {
    content: "";
    position: absolute;
    width: 22px;
    height: 22px;
    background: #c5c8cf;
    border-radius: 50%;
    left: 20px;
    top: 18px;
    box-shadow:
        30px 25px 0 5px #c8cad0,
        12px 48px 0 2px #bfc2c9;
}

/* =========================
   STARS
========================= */

.star {
    font-size: 38px;
    text-shadow:
        0 0 15px white,
        0 0 30px #aab9ff;
    animation: twinkle 2s infinite alternate;
}

.s1 {
    left: 40%;
    top: 24%;
}

.s2 {
    left: 8%;
    bottom: 32%;
    font-size: 28px;
}

.s3 {
    right: 7%;
    top: 52%;
    font-size: 32px;
}

.s4 {
    left: 48%;
    bottom: 12%;
    font-size: 27px;
}

@keyframes twinkle {
    from {
        opacity: .45;
        transform: scale(.85);
    }

    to {
        opacity: 1;
        transform: scale(1.15);
    }
}

/* =========================
   PLANT
========================= */

.plant {
    left: 42%;
    bottom: 20%;
    font-size: 48px;
}

/* =========================
   COMET
========================= */

.comet {
    top: 70%;
    left: -100px;
    font-size: 45px;
    animation: cometMove 14s linear infinite;
}

@keyframes cometMove {
    from {
        left: -100px;
    }

    to {
        left: 110%;
    }
}

/* =========================
   SATELLITE
========================= */

.satellite {
    top: 15%;
    left: 48%;
    font-size: 38px;
    animation: satelliteFloat 5s ease-in-out infinite;
}

@keyframes satelliteFloat {
    0%,100% {
        transform: translateY(0) rotate(-5deg);
    }

    50% {
        transform: translateY(20px) rotate(5deg);
    }
}

/* =========================
   HIDDEN BUTTON
========================= */

.hidden-btn {
    position: absolute;
    right: 5%;
    bottom: 6%;
    border: none;
    background: transparent;
    color: rgba(255,255,255,.18);
    font-size: 12px;
    cursor: pointer;
    z-index: 20;
}

.hidden-btn:hover {
    color: white;
}

/* =========================
   POPUP
========================= */

.popup {
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,.65);
    backdrop-filter: blur(8px);
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 50;
    padding: 25px;
}

.popup.show {
    display: flex;
}

.popup-box {
    max-width: 450px;
    width: 100%;
    padding: 35px 25px;
    border-radius: 25px;
    text-align: center;
    background: rgba(20,25,60,.9);
    border: 1px solid rgba(255,255,255,.15);
    box-shadow: 0 0 50px rgba(100,120,255,.25);
}

.popup-box h2 {
    margin-bottom: 18px;
    font-weight: 400;
}

.popup-box p {
    line-height: 1.7;
    opacity: .85;
}

.close-btn,
.game-btn {
    margin-top: 25px;
    padding: 11px 25px;
    border-radius: 30px;
    border: 1px solid rgba(255,255,255,.3);
    background: rgba(255,255,255,.08);
    color: white;
    cursor: pointer;
}

/* =========================
   GAME PAGE
========================= */

#gamePage {
    background:
        radial-gradient(circle at center, #151c48, #03040d 70%);
}

.game-title {
    text-align: center;
    margin-top: 30px;
    padding: 0 20px;
}

.game-title h1 {
    font-size: 30px;
    font-weight: 400;
}

.game-title p {
    opacity: .65;
    margin-top: 8px;
}

.score {
    text-align: center;
    margin-top: 12px;
    font-size: 18px;
}

.game-star {
    position: fixed;
    font-size: 35px;
    cursor: pointer;
    animation: gameStar 1s infinite alternate;
    z-index: 30;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
}

@keyframes gameStar {
    from {
        transform: scale(.8);
    }

    to {
        transform: scale(1.2);
    }
}

.back-btn {
    position: absolute;
    bottom: 25px;
    left: 50%;
    transform: translateX(-50%);
    padding: 10px 25px;
    border-radius: 25px;
    background: rgba(255,255,255,.08);
    border: 1px solid rgba(255,255,255,.2);
    color: white;
    cursor: pointer;
    z-index: 40;
}

/* =========================
   SECRET PAGE
========================= */

#secretPage {
    background:
        radial-gradient(circle, #171b42, #03030a 70%);
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 30px;
}

#secretPage.active {
    display: flex;
}

.secret-content {
    max-width: 600px;
}

.secret-content .big-star {
    font-size: 80px;
    animation: twinkle 2s infinite alternate;
}

.secret-content h1 {
    margin-top: 20px;
    font-weight: 400;
}

.secret-content p {
    margin-top: 20px;
    line-height: 1.8;
    opacity: .75;
}

.restart {
    margin-top: 30px;
    padding: 12px 28px;
    border-radius: 30px;
    border: 1px solid rgba(255,255,255,.3);
    background: rgba(255,255,255,.08);
    color: white;
    cursor: pointer;
}

/* =========================
   MOBILE
========================= */

@media (max-width: 600px) {

    .enter-content h1 {
        letter-spacing: 8px;
    }

    .enter-content p {
        font-size: 13px;
        letter-spacing: 1px;
    }

    .p1 {
        left: 8%;
        top: 30%;
    }

    .p2 {
        right: 10%;
        top: 27%;
    }

    .p3 {
        right: 7%;
        bottom: 16%;
    }

    .p4 {
        left: 15%;
        bottom: 18%;
    }

    .moon {
        right: 35%;
        top: 46%;
        width: 70px;
        height: 70px;
    }

    .plant {
        left: 43%;
        bottom: 20%;
    }

    .satellite {
        left: 45%;
        top: 17%;
    }

    .instruction {
        top: 20px;
    }
}
</style>
</head>

<body>

<!-- ==================================================
     PAGE 1 — ENTER
================================================== -->

<section id="enterPage" class="page active">

    <div class="enter-stars"></div>

    <div class="enter-content">

        <h1>ENTER</h1>

        <p>
            A little universe made for two friends far apart.
        </p>

        <button class="enter-btn" onclick="enterUniverse()">
            ENTER ✦
        </button>

    </div>

</section>


<!-- ==================================================
     PAGE 2 — UNIVERSE
================================================== -->

<section id="universePage" class="page">

    <div class="universe-stars"></div>

    <div class="instruction">

        <h2>🌌 Godwin says...</h2>

        <p>
            Click the planets. You never know what you'll find.
        </p>

    </div>


    <!-- PLANET 1 -->

    <div
        class="object planet p1"
        onclick="showMessage(
            'Planet of Distance',
            'I can’t always meet you in person, but distance doesn’t stop a friendship from growing.'
        )">
    </div>


    <!-- PLANET 2 -->

    <div
        class="object planet p2"
        onclick="showMessage(
            'Planet of Knowing',
            'There is still so much about you I want to know. Different places don’t mean we have to stay strangers.'
        )">
    </div>


    <!-- PLANET 3 -->

    <div
        class="object planet p3"
        onclick="showMessage(
            'Planet of Friendship',
            'Some people are close because they live nearby. Some are close because they simply matter.'
        )">
    </div>


    <!-- PLANET 4 -->

    <div
        class="object planet p4"
        onclick="showMessage(
            'Tiny Planet',
            'Even the smallest things can become big memories.'
        )">
    </div>


    <!-- MOON -->

    <div
        class="object moon"
        onclick="showMessage(
            'The Moon',
            'Whenever you look at the night sky, remember that we can both look at the same moon from completely different places.'
        )">
    </div>


    <!-- STAR 1 -->

    <div
        class="object star s1"
        onclick="showMessage(
            'A Little Star',
            'You made an ordinary part of my life a little more interesting just by being in it.'
        )">
        ✦
    </div>


    <!-- STAR 2 -->

    <div
        class="object star s2"
        onclick="showMessage(
            'Another Star',
            'Friendship doesn’t need the same timezone, the same city, or the same room.'
        )">
        ★
    </div>


    <!-- STAR 3 -->

    <div
        class="object star s3"
        onclick="showMessage(
            'Hidden Star',
            'If you ever feel far away, remember: far away is a distance, not a goodbye.'
        )">
        ✧
    </div>


    <!-- STAR 4 -->

    <div
        class="object star s4"
        onclick="showMessage(
            'One More',
            'Here’s a random reminder: I’m glad our paths crossed.'
        )">
        ✦
    </div>


    <!-- PLANT -->

    <div
        class="object plant"
        onclick="showMessage(
            'The Little Plant 🌱',
            'Friendships are kind of like this. Give them time, care, and a little patience, and they keep growing.'
        )">
        🌱
    </div>


    <!-- SATELLITE -->

    <div
        class="object satellite"
        onclick="showMessage(
            'Satellite Signal',
            '📡 Signal received: Hey, I’m still here.'
        )">
        🛰️
    </div>


    <!-- COMET -->

    <div
        class="object comet"
        onclick="showMessage(
            'The Comet',
            'Some moments are quick, but that doesn’t make them meaningless.'
        )">
        ☄️
    </div>


    <!-- HIDDEN BUTTON -->

    <button
        class="hidden-btn"
        onclick="openGame()">
        click me
    </button>

</section>


<!-- ==================================================
     POPUP
================================================== -->

<div id="popup" class="popup">

    <div class="popup-box">

        <h2 id="popupTitle"></h2>

        <p id="popupText"></p>

        <button
            class="close-btn"
            onclick="closePopup()">
            Keep exploring ✦
        </button>

    </div>

</div>


<!-- ==================================================
     GAME PAGE
================================================== -->

<section id="gamePage" class="page">

    <div class="game-title">

        <h1>⭐ Catch the Stars</h1>

        <p>
            Catch 7 stars to unlock something.
        </p>

    </div>


    <div class="score">

        Stars:
        <span id="score">0</span>
        / 7

    </div>


    <button
        class="back-btn"
        onclick="backToUniverse()">
        Back to the universe
    </button>

</section>


<!-- ==================================================
     SECRET PAGE
================================================== -->

<section id="secretPage" class="page">

    <div class="secret-content">

        <div class="big-star">
            ✨
        </div>

        <h1>
            You found the secret.
        </h1>

        <p>
            Maybe this little universe was never really about
            the planets, stars, or distance.
        </p>

        <p>
            It was just a small way of saying:
            <br><br>

            <strong>
                I’m glad you're my friend.
            </strong>
        </p>

        <button
            class="restart"
            onclick="restart()">
            Explore again 🌌
        </button>

    </div>

</section>


<script>

/* ==================================================
   PAGE SWITCHING
================================================== */

function changePage(pageId) {

    document.querySelectorAll(".page").forEach(function(page) {
        page.classList.remove("active");
    });

    const page = document.getElementById(pageId);

    if (page) {
        page.classList.add("active");
    }
}


/* ==================================================
   ENTER UNIVERSE
================================================== */

function enterUniverse() {

    changePage("universePage");

}


/* ==================================================
   POPUP
================================================== */

function showMessage(title, message) {

    const titleElement =
        document.getElementById("popupTitle");

    const textElement =
        document.getElementById("popupText");

    const popup =
        document.getElementById("popup");

    titleElement.textContent = title;

    textElement.textContent = message;

    popup.classList.add("show");

}


function closePopup() {

    document
        .getElementById("popup")
        .classList.remove("show");

}


/* ==================================================
   CLOSE POPUP WHEN CLICKING OUTSIDE
================================================== */

document
    .getElementById("popup")
    .addEventListener("click", function(event) {

        if (event.target === this) {
            closePopup();
        }

    });


/* ==================================================
   GAME
================================================== */

let score = 0;

let gameRunning = false;


function openGame() {

    changePage("gamePage");

    score = 0;

    document
        .getElementById("score")
        .textContent = score;

    gameRunning = true;

    createGameStar();

}


function createGameStar() {

    if (!gameRunning) {
        return;
    }


    const star =
        document.createElement("div");


    star.className = "game-star";

    star.textContent = "⭐";


    const randomLeft =
        Math.random() * 80 + 10;

    const randomTop =
        Math.random() * 65 + 15;


    star.style.left =
        randomLeft + "%";

    star.style.top =
        randomTop + "%";


    star.onclick = function() {

        if (!gameRunning) {
            return;
        }


        score++;


        document
            .getElementById("score")
            .textContent = score;


        star.remove();


        if (score >= 7) {

            gameRunning = false;


            setTimeout(function() {

                changePage("secretPage");

            }, 500);


        } else {

            createGameStar();

        }

    };


    document
        .getElementById("gamePage")
        .appendChild(star);

}


/* ==================================================
   BACK TO UNIVERSE
================================================== */

function backToUniverse() {

    gameRunning = false;


    document
        .querySelectorAll(".game-star")
        .forEach(function(star) {

            star.remove();

        });


    changePage("universePage");

}


/* ==================================================
   RESTART
================================================== */

function restart() {

    score = 0;

    gameRunning = false;


    document
        .querySelectorAll(".game-star")
        .forEach(function(star) {

            star.remove();

        });


    changePage("enterPage");

}

</script>

</body>
</html>
