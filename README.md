<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Rébus mystérieux</title>
<style>
    body {
        margin: 0;
        font-family: 'Segoe UI', sans-serif;
        background: linear-gradient(135deg, #1d2671, #c33764);
        color: #fff;
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .card {
        background: rgba(255, 255, 255, 0.95);
        color: #333;
        border-radius: 25px;
        padding: 35px 45px;
        max-width: 600px;
        width: 90%;
        text-align: center;
        box-shadow: 0 25px 50px rgba(0,0,0,0.35);
    }

    h1 {
        margin-top: 0;
        font-size: 2.3em;
        color: #c33764;
    }

    .rebus {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 30px;
        font-size: 4.2em;
        margin: 35px 0;
    }

    .plus {
        font-size: 0.6em;
        color: #bbb;
    }

    input {
        padding: 12px;
        width: 80%;
        max-width: 320px;
        font-size: 1em;
        border-radius: 12px;
        border: 2px solid #ddd;
        outline: none;
        margin-top: 10px;
    }

    button {
        margin-top: 18px;
        padding: 12px 35px;
        font-size: 1em;
        border: none;
        border-radius: 30px;
        background: #c33764;
        color: white;
        cursor: pointer;
        transition: transform 0.2s, box-shadow 0.2s;
    }

    button:hover {
        transform: translateY(-2px);
        box-shadow: 0 10px 18px rgba(0,0,0,0.25);
    }

    .result {
        margin-top: 22px;
        font-weight: bold;
        font-size: 1.1em;
    }

    .success {
        color: #2e7d32;
    }

    .error {
        color: #c62828;
    }
</style>
</head>
<body>

<div class="card">
    <h1>🧩 Déchiffre le rébus</h1>

    <div class="rebus">
        🎪 <span class="plus">+</span> 🌞
    </div>

    <p>Entre le nom complet :</p>

    <input type="text" id="answer" placeholder="Ta réponse ici">
    <br>
    <button onclick="check()">Valider</button>

    <div id="result" class="result"></div>
</div>

<script>
function check() {
    const value = document.getElementById("answer").value
        .toLowerCase()
        .normalize("NFD")
        .replace(/[\u0300-\u036f]/g, "");

    const result = document.getElementById("result");

    if (value === "cirque du soleil") {
        result.textContent = "🎉 Bravo ! Tu as trouvé le Cirque du Soleil 🎪🌞";
        result.className = "result success";
    } else {
        result.textContent = "❌ Ce n'est pas encore la bonne réponse…";
        result.className = "result error";
    }
}
</script>

</body>
</html>
