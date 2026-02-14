<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Romantik Sürpriz 💖</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        background: linear-gradient(135deg,#ffc0d0, #ff79a0, #ff5c8a);
        display: flex;
        justify-content: center;
        align-items: center;
        font-family: "Poppins", sans-serif;
        overflow: hidden;
        transition: 0.8s;
    }

    .card {
        text-align: center;
        background: rgba(255,255,255,0.15);
        padding: 25px;
        border-radius: 25px;
        box-shadow: 0 0 30px rgba(255,255,255,0.4);
        backdrop-filter: blur(10px);
        animation: fadeIn 1.5s;
        width: 80%;
        max-width: 350px;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(30px); }
        to { opacity: 1; transform: translateY(0); }
    }

    input {
        width: 100%;
        padding: 14px;
        border-radius: 20px;
        border: none;
        margin-top: 15px;
        outline: none;
        font-size: 17px;
        text-align: center;
    }

    button {
        width: 100%;
        padding: 14px;
        border-radius: 20px;
        border: none;
        margin-top: 15px;
        font-size: 18px;
        background: white;
        color: #ff1e6e;
        font-weight: 600;
        cursor: pointer;
        transition: 0.3s;
    }
    button:active { transform: scale(0.95); }

    #main {
        display: none;
        text-align: center;
        flex-direction: column;
        align-items: center;
        color: white;
    }

    h1 {
        font-size: 36px;
        text-shadow: 0 0 20px #fff, 0 0 40px #ff90d0;
        margin: 25px 0;
    }

    #message {
        margin-top: 25px;
        font-size: 22px;
        min-height: 50px;
        line-height: 1.4;
        text-shadow: 0 0 15px rgba(255,255,255,0.7);
        transition: transform 0.3s;
    }

    .heart {
        position: absolute;
        font-size: 26px;
        animation: floatUp 2.8s ease-out forwards;
        pointer-events: none;
        color: red;
    }

    @keyframes floatUp {
        0% { transform: translateY(0) scale(1); opacity: 1; }
        100% { transform: translateY(-300px) scale(2); opacity: 0; }
    }
</style>
</head>
<body>

<!-- GİRİŞ EKRANI -->
<div class="card" id="loginCard">
    <h2>🔐 Romantik Sürprize Giriş</h2>
    <p>Şifreyi Gir:</p>
    <input type="password" id="password" placeholder="••••••">
    <button onclick="login()">Giriş Yap 💕</button>
    <p id="error" style="color:#fff;margin-top:10px;"></p>
</div>

<!-- ANA EKRAN -->
<div id="main">
    <h1>💖 Seni seviyorum Deniz’İm ❤‍🔥 💖</h1>
    <button onclick="showLove()">Bana Dokun 💘</button>
    <div id="message"></div>
</div>

<script>
function login() {
    let pass = document.getElementById("password").value.trim().toLowerCase();

    if (pass === "yaşak") {
        document.getElementById("loginCard").style.display = "none";
        document.getElementById("main").style.display = "flex";
    } else {
        document.getElementById("error").innerText = "Yanlış şifre 😳";
    }
}

function showLove() {
    const messages = [
        "Seninle her an bir masal gibi 💗",
        "Gülüşün, ruhumun en güzel melodisi 💖",
        "Senin yanında dünya daha huzurlu 🤍",
        "Kalbim sadece seninle tamamlanıyor 💌",
        "Her nefesimde sen varsın 💗",
        "Sen benim en güzel tesadüfümsün 💖",
        "Sana bakınca zaman duruyor, sadece biz varız 🤍",
        "Seninle her an, kalbim heyecanla atıyor 💗","Seninle her an, yıldızlar bile kıskanıyor; kalbim sadece seninle tamamlanıyor, Deniz’İm ❤‍🔥"
    ];

    const msg = messages[Math.floor(Math.random() * messages.length)];
    const messageDiv = document.getElementById("message");
    messageDiv.innerText = msg;

    // Büyüme efekti
    messageDiv.style.transform = "scale(1.4)";
    setTimeout(() => messageDiv.style.transform = "scale(1)", 300);

    // Kalp efekti
    for (let i = 0; i < 8; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerText = "❤️";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.top = window.innerHeight + "px";
        heart.style.fontSize = (22 + Math.random()*18) + "px";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 3000);
    }
}
</script>

</body>
</html> 