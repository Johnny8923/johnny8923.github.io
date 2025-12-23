<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Énigme I</title>
<style>
body {
    margin: 0;
    font-family: 'Georgia', serif;
    background: linear-gradient(160deg, #000428, #004e92);
    color: #eee;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.box {
    background: rgba(0,0,0,0.7);
    border-radius: 25px;
    padding: 40px;
    max-width: 700px;
    width: 90%;
    text-align: center;
    box-shadow: 0 30px 60px rgba(0,0,0,0.6);
}

h1 {
    color: #ffcc70;
    margin-bottom: 20px;
}

.symbols {
    font-size: 3em;
    margin: 30px 0;
}

input {
    padding: 12px;
    width: 80%;
    max-width: 350px;
    border-radius: 12px;
    border: none;
    font-size: 1em;
}

button {
    margin-top: 15px;
    padding: 12px 40px;
    font-size: 1em;
    border-radius: 30px;
    border: none;
    background: #ffcc70;
    cursor: pointer;
}

.result {
    margin-top: 25px;
    font-weight: bold;
}
</style>
</head>
<body>

<div class="box">
    <h1>🎭 Énigme I</h1>

    <p>
        Il n’a ni murs ni scène fixe.<br>
        Il voyage, se transforme, émerveille.<br>
        Son cœur ne bat pas… il brûle.
    </p>

    <div class="symbols">
        🎭 🔄 ☀️
    </div>

    <p>Nom complet :</p>

    <input id="rep">
    <br>
    <button onclick="check()">Valider</button>

    <div id="res" class="result"></div>
</div>

<script>
function check() {
    const v = document.getElementById("rep").value
        .toLowerCase()
        .normalize("nfd")
        .replace(/[\u0300-\u036f]/g, "");

    if (v === "cirque du soleil") {
        document.getElementById("res").textContent = "✔️ Exact… poursuis le voyage.";
        setTimeout(() => {
            window.location.href = "enigme2.html";
        }, 2000);
    } else {
        document.getElementById("res").textContent = "❌ Observe ce qui se déplace…";
    }
}
</script>

</body>
</html>
