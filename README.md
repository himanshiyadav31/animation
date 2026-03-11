<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inertia Trick - Junior Robo</title>
<style>
body {
    margin: 0;
    padding: 0;
    background-color: #0d0e15;
    color: #ffffff;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
}

.video-container {
    width: 100%;
    max-width: 450px;
    height: 100vh;
    background: linear-gradient(135deg, #1f1c2c, #928dab);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    text-align: center;
    position: relative;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
    overflow: hidden;
}

.title {
    font-size: 2.5rem;
    color: #ffde59;
    margin-top: 60px;
    padding: 0 20px;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
}

.subtitle {
    font-size: 1.5rem;
    color: #fff;
    background: rgba(0, 0, 0, 0.6);
    padding: 10px 20px;
    border-radius: 12px;
    opacity: 0;
    transition: opacity 0.5s;
    transform: translateY(-40px);
}

.branding {
    font-size: 1.8rem;
    font-weight: bold;
    color: #00ffcc;
    margin-bottom: 40px;
    letter-spacing: 1px;
}

.animation-area {
    position: relative;
    width: 100%;
    height: 480px;
    margin: auto 0;
    transition: opacity 1s, transform 1s;
}

.glass {
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    width: 110px;
    height: 170px;
    border: 5px solid rgba(255, 255, 255, 0.8);
    border-top: none;
    border-radius: 0 0 15px 15px;
    background: rgba(255, 255, 255, 0.05);
    box-shadow: inset 0 0 15px rgba(255, 255, 255, 0.2);
    transition: all 1s;
}

.water {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 40%;
    background: rgba(0, 191, 255, 0.5);
    border-radius: 0 0 10px 10px;
}

.card {
    position: absolute;
    bottom: 215px;
    left: 50%;
    transform: translateX(-50%);
    width: 160px;
    height: 8px;
    background: #fff;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
    transition: transform 0.15s ease-in;
}

.coin {
    position: absolute;
    bottom: 223px;
    left: 50%;
    transform: translateX(-50%);
    width: 50px;
    height: 50px;
    background: radial-gradient(circle, #ffd700, #b8860b);
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #4a3500;
    font-weight: 900;
    font-size: 1.2rem;
    box-shadow: inset -2px -2px 5px rgba(0, 0, 0, 0.4), 0 4px 5px rgba(0, 0, 0, 0.4);
    border: 2px solid #daa520;
    transition: bottom 0.4s cubic-bezier(0.5, 0, 1, 1), transform 1s, left 1s;
}

.finger {
    position: absolute;
    bottom: 160px;
    left: 10px;
    font-size: 4rem;
    transition: left 0.15s cubic-bezier(0, 0, 0.2, 1);
    opacity: 0;
    text-shadow: 0 4px 6px rgba(0, 0, 0, 0.5);
    z-index: 10;
}

/* Animation Classes */
.flick-card {
    transform: translateX(350px) rotate(60deg);
}

.drop-coin {
    bottom: 50px;
}

.move-finger {
    left: 110px;
}

.fade-out {
    opacity: 0;
    transform: translateY(20px);
}

.move-glass {
    opacity: 0.3;
    transform: translateX(-150%) scale(0.6);
}

/* Explanation Container */
.explanation-container {
    position: absolute;
    top: 55%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 85%;
    background: rgba(0, 0, 0, 0.85);
    border-radius: 15px;
    padding: 20px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.6);
    border: 2px solid #00ffcc;
    opacity: 0;
    pointer-events: none;
    transition: opacity 1s, top 1s;
    z-index: 20;
}

.explanation-container h3 {
    color: #ffde59;
    font-size: 1.8rem;
    margin: 0 0 15px 0;
}

.explanation-container p {
    font-size: 1.2rem;
    margin: 10px 0;
    line-height: 1.4;
}

.explanation-container p strong {
    color: #ff5757;
    font-size: 1.4rem;
    display: block;
    margin-bottom: 5px;
}

.show-explanation {
    opacity: 1;
    top: 50%;
}
</style>
</head>



<body>
    <div class="video-container">
        <h1 class="title" id="main-title">Can you beat Physics? 🪙🪄</h1>
        <div class="animation-area">
            <div class="glass" id="glass">
                <div class="water" id="water"></div>
            </div>
            <div class="card" id="card"></div>
            <div class="coin" id="coin">₹10</div>
            <div class="finger" id="finger">👇 Flick!</div>
        </div>

        <div class="explanation-container" id="explanation">
            <h3>Why did this happen? 🤔</h3>
            <p><strong>Newton's 1st Law: INERTIA</strong></p>
            <p>An object at rest stays at rest unless a force acts upon it.</p>
            <p>The coin was "lazy" and wanted to stay put.</p>
            <p>The quick flick moved the card, but didn't transfer enough friction to the coin before it fell away.</p>
            <p>Gravity pulled the lazy coin straight down!</p>
        </div>

        <h2 class="subtitle" id="subtitle">The "Lazy Coin" Trick</h2>
        
    
    <script>

document.addEventListener('DOMContentLoaded', () => {
    const card = document.getElementById('card');
    const coin = document.getElementById('coin');
    const finger = document.getElementById('finger');
    const subtitle = document.getElementById('subtitle');
    const mainTitle = document.getElementById('main-title');
    const animationArea = document.querySelector('.animation-area');
    const explanation = document.getElementById('explanation');
    const glass = document.getElementById('glass');

    // Sequence of animation
    setTimeout(() => {
        finger.style.opacity = '1';
        finger.style.left = '60px';
    }, 1500);

    setTimeout(() => {
        finger.classList.add('move-finger');
        card.classList.add('flick-card');
    }, 2800);

    setTimeout(() => {
        coin.classList.add('drop-coin');
        finger.style.opacity = '0';
    }, 2950);

    setTimeout(() => {
        mainTitle.innerHTML = "Newton's 1st Law:<br><span style='color:#00ffcc;'>INERTIA</span>";
        subtitle.textContent = "The coin stays at rest!";
        subtitle.style.opacity = '1';
    }, 3800);
    
    // Fade out main trick to begin explanation
    setTimeout(() => {
        subtitle.style.opacity = '0';
        glass.classList.add('move-glass');
    }, 6000);
    
    // Show detailed explanation
    setTimeout(() => {
        explanation.classList.add('show-explanation');
        mainTitle.style.transform = 'scale(0.8) translateY(-20px)';
        mainTitle.style.transition = 'transform 1s';
    }, 6500);

    // Final CTA
    setTimeout(() => {
        subtitle.innerHTML = "Physics with <b>@JuniorRobo</b>";
        subtitle.style.background = "#ffde59";
        subtitle.style.color = "#000";
        subtitle.style.opacity = '1';
    }, 12500);
});

</script>
</body>

</html>
