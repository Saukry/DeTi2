# DeTi2
App
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DeTiler - Remonty</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="login" class="login-container">
        <h2>Logowanie</h2>
        <input type="password" id="password" placeholder="Hasło">
        <input type="text" id="securityQuestion" placeholder="Odpowiedź na pytanie">
        <input type="text" id="token" placeholder="Token">
        <button onclick="login()">Zaloguj</button>
        <p id="error" style="color: red;"></p>
    </div>
    <div id="app" class="app-container" style="display: none;">
        <header>
            <h2>Logo DeTiler</h2>
            <h1>DeTiler</h1>
        </header>
        <section id="ar-section">
            <h2>Skanowanie AR</h2>
            <p>Powierzchnia: <span id="area">0 m²</span></p>
            <button onclick="simulateAR()">Zeskanuj remont</button>
        </section>
        <section id="offer-section">
            <h2>Generuj ofertę</h2>
            <button onclick="generateOffer()">Stwórz ofertę</button>
            <p id="offer-result"></p>
        </section>
        <section id="norms-section">
            <h2>Normy</h2>
            <p>Zgodność: KNR 2-31, PN-EN 12056</p>
        </section>
    </div>
    <script src="script.js"></script>
</body>
</html>
// Zabezpieczenia
const PASSWORD = "12345";
const ANSWER = "yes";
const TOKEN = "xyz789";

function login() {
    const password = document.getElementById("password").value;
    const securityQuestion = document.getElementById("securityQuestion").value;
    const token = document.getElementById("token").value;
    const error = document.getElementById("error");

    if (password === PASSWORD && securityQuestion === ANSWER && token === TOKEN) {
        document.getElementById("login").style.display = "none";
        document.getElementById("app").style.display = "block";
        alert("Zalogowano!");
    } else {
        error.innerText = "Błędne dane logowania!";
    }
}

// Symulacja AR
function simulateAR() {
    const area = Math.random() * 10;
    document.getElementById("area").innerText = area.toFixed(1) + " m²";
    alert("Skanowanie AR: " + area.toFixed(1) + " m²");
}

// Generowanie oferty
function generateOffer() {
    const basePrice = 1950;
    const hiddenCosts = 150;
    const total = basePrice + hiddenCosts;
    document.getElementById("offer-result").innerText = `Oferta: ${basePrice} zł + ${hiddenCosts} zł = ${total} zł`;
    alert("Oferta wygenerowana!");
}
body {
    font-family: 'Bebas Neue', sans-serif;
    background-color: #000000;
    color: #ffffff;
    margin: 0;
    padding: 0;
    text-align: center;
}

.login-container, .app-container {
    padding: 20px;
}

input, button {
    margin: 10px;
    padding: 5px;
    font-size: 16px;
}

#app section {
    margin: 20px 0;
    border: 1px solid #FF9800;
    padding: 10px;
    border-radius: 5px;
}
