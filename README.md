<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Énigme cryptique</title>
<style>
    body {
        margin: 0;
        font-family: 'Georgia', serif;
        background: radial-gradient(circle at top, #0f2027, #203a43, #2c5364);
        color: #eee;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .enigme {
        background: rgba(0,0,0,0.65);
        border-radius: 25px;
        padding: 40px;
        max-width: 700px;
        width: 90%;
        box-shadow: 0 30px 60px rgba(0,0,0,0.6);
        text-align: center;
    }

    h1 {
        font-size: 2.4em;
        margin-bottom: 10px;
        color: #ffcc70;
    }

    .subtitle {
        font-style: italic;
        color: #bbb;
        margin-bottom: 30px;
    }

    .rebus {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
        gap: 25px;
        font-size: 2.6em;
        margin-bottom: 30px;
    }

    .case {
        background: rgba(255,255,255,0.08);
        border-radius: 18px;
        padding: 20px;
        box-shadow: inset 0 0 20px rgba(255,255,255,0.05);
    }

    .hint {
        font-size: 0.9em;
        margin-top: 25px;
        color: #aaa;
    }

    input {
        margin-top: 20px;
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
        color: #222;
        cursor: pointer;
        transition: transform 0.2s, box-shadow 0.2s;
    }

    button:hover {
        transform: translateY(-2px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.4);
    }

    .result {
        margin-top: 25px;
        font-weight: bold;
        font-size: 1.2em;
    }

    .success { color: #7CFF7C; }
    .error { color: #FF6B6B; }
</style>
</head>
<body>

<div class="enigme">
    <h1>🎭 L'Énigme du Chapiteau</h1>
    <div class="subtitle">Tout n’est pas à prendre tel quel…</div>

    <div class="rebus">
        <div class="case">CIR🪚</div>
        <div class="case">🧊 + QUE</div>
        <div class="case">DU</div>
        <div class="case">SO🔑</div>
        <div class="case">☀️</div>
    </div>

    <div class="hint">
        Indice : enlève, écoute, assemble.
    </div>

    <input id="answer" placeholder="Nom complet recherché">
    <br>
    <button onclick="verifier()">Valider</button>

    <div id="result" class="result"></div>
</div>

<script>
function verifier() {
    const val = document.getElementById("answer").value
        .toLowerCase()
        .normalize("NFD")
        .replace(/[\u0300-\u036f]/g, "");

    const res = document.getElementById("result");

    if (val === "cirque du soleil") {
        res.textContent = "🎉 Exact ! Le mystère mène au Cirque du Soleil 🎪🌞";
        res.className = "result success";
    } else {
        res.textContent = "❌ Ce n’est pas encore ça… observe autrement.";
        res.className = "result error";
    }
}
</script>

</body>
</html>
