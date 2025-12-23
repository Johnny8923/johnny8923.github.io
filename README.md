<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Énigme I</title>
<style>
body {
    margin: 0;
    font-family: Georgia, serif;
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
}
input {
    padding: 12px;
    width: 80%;
    max-width: 350px;
    border-radius: 12px;
    border: none;
}
button {
    margin-top: 15px;
    padding: 12px 40px;
    border-radius: 30px;
    border: none;
    background: #ffcc70;
    cursor: pointer;
}
.result {
    margin-top: 20px;
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

    <p>Nom complet :</p>

    <input id="rep">
    <br>
    <button type="button" onclick="check()">Valider</button>

    <div id="res" class="result"></div>
</div>

<script>
function check() {
    const v = document.getElementById("rep").value
        .toLowerCase()
        .normalize("NFD")
        .replace(/[\u0300-\u036f]/g, "");

    const res = document.getElementById("res");

    if (v === "cirque du soleil") {
        res.textContent = "✔️ Exact… poursuis le voyage.";
        setTimeout(() => {
            window.location.href = "enigme2.html";
        }, 2000);
    } else {
        res.textContent = "❌ Observe ce qui se déplace…";
    }
}
</script>

</body>
</html>
