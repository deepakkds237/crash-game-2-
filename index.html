# ==============================
# 🎮 Crash Multiplier Web App
# ==============================
# How to Run:
# 1. Install Flask -> pip install flask
# 2. Save this file as app.py
# 3. Run -> python app.py
# 4. Open browser -> http://127.0.0.1:5000

from flask import Flask, request, jsonify, render_template_string
import hashlib

app = Flask(__name__)

# ==============================
# 🔥 Core Crash Logic (Your Code)
# ==============================



def generate_crash(user_input):
    user_input = float(user_input)
    house_edge = 0.99

    # Step 1: Normalize input influence (0–1)
    influence = min(user_input / 1000.0, 1.0)

    # Step 2: Deterministic hash randomness
    hash_value = hashlib.sha256(str(user_input).encode()).hexdigest()
    int_value = int(hash_value[:16], 16)
    random_factor = int_value / float(0xFFFFFFFFFFFFFFFF)

    # Step 3: Blend randomness + input influence
    blended = (0.6 * random_factor) + (0.4 * influence)

    # Step 4: Safe crash range mapping
    r = blended * 0.666666

    multiplier = house_edge / (1 - r)

    return round(multiplier, 2)



# ==============================
# 🌐 Frontend UI (Embedded HTML)
# ==============================

HTML_PAGE = """
<!DOCTYPE html>
<html>
<head>
    <title>Crash Multiplier 3D Game</title>
    <style>
        * { box-sizing: border-box; margin:0; padding:0; }

        body {
            height: 100vh;
            overflow: hidden;
            font-family: 'Segoe UI', sans-serif;
            background: radial-gradient(circle at bottom, #0f2027, #203a43, #2c5364);
            color: white;
            display:flex;
            justify-content:center;
            align-items:center;
            flex-direction:column;
        }

        .sky {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events:none;
        }

        .plane {
            position: absolute;
            font-size: 100px;   /* Bigger Plane */
            top: 50%;
            left: -150px;
            transform: rotateY(20deg);
        }

        .panel {
            position: relative;
            background: rgba(0,0,0,0.65);
            padding: 30px 50px;
            border-radius: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            box-shadow: 0 0 25px rgba(0,255,150,0.4);
            z-index:2;
        }

        h2{
            margin-bottom:15px;
        }

        input {
            padding: 10px 14px;
            border-radius: 10px;
            border: none;
            margin-bottom: 15px;
            width: 250px;
            font-size:16px;
        }

        button {
            padding: 10px 20px;
            border-radius: 10px;
            border: none;
            background: linear-gradient(45deg,#00c6ff,#0072ff);
            color: white;
            font-weight: bold;
            cursor: pointer;
            font-size:16px;
        }

        #multiplier {
            margin-top: 15px;
            font-size: 36px;
            font-weight: bold;
            color: #00ff99;
            text-shadow: 0 0 15px #00ff99;
            min-height:40px;
        }

        @keyframes fly {
            from { left: -150px; }
            to { left: 110%; }
        }

        @keyframes crash {
            0% { transform: rotate(0deg); }
            50% { transform: rotate(90deg); }
            100% { transform: translateY(400px) rotate(180deg); opacity:0; }
        }
    </style>
</head>
<body>

<div class="sky">
    <div id="plane" class="plane">✈️</div>
</div>

<div class="panel">
    <h2>🚀 3D Crash Game</h2>
    <input type="text" id="number" placeholder="Enter any number" required>
    <br>
    <button onclick="startGame()">Generate & Fly</button>
    <div id="multiplier"></div>
</div>

<script>
function startGame() {
    let number = document.getElementById("number").value;
    let plane = document.getElementById("plane");
    let multiplierText = document.getElementById("multiplier");

    if(number.trim() === ""){
        alert("Please enter a number first!");
        return;
    }

    plane.style.animation = "none";
    plane.style.left = "-150px";
    plane.style.top = "50%";
    plane.style.opacity = "1";

    fetch("/crash", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ number: number })
    })
    .then(response => response.json())
    .then(data => {
        let multiplier = data.multiplier;
        multiplierText.innerText = multiplier + "x";

        let duration = multiplier * 2;

        plane.style.animation = `fly ${duration}s linear forwards`;

        setTimeout(() => {
            plane.style.animation = `crash 1.5s ease-in forwards`;
        }, duration * 1000);
    });
}
</script>

</body>
</html>
"""

# ==============================
# 🚀 Routes
# ==============================

@app.route("/")
def home():
    return render_template_string(HTML_PAGE)

@app.route("/crash", methods=["POST"])
def crash():
    data = request.get_json()
    user_input = data.get("number", "0")
    result = generate_crash(user_input)
    return jsonify({"multiplier": result})

# ==============================
# ▶ Run Server
# ==============================

if __name__ == "__main__":
    app.run(debug=True)
