<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sushi Counter</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto:wght@400&family=Raleway:wght@700&display=swap">
    <style>
        body {
            font-family: 'Roboto', sans-serif;
            text-align: center;
            background-color: #fffbcc;
            margin: 0;
            padding: 0;
            position: relative;
        }

        h1 {
            text-transform: uppercase;
            color: #ff69b4;
            font-family: 'Raleway', sans-serif;
            font-weight: bold;
            margin-top: 20px;
            font-size: 2em;
            animation: blink 1s infinite alternate;
        }

        @keyframes blink {
            from {
                opacity: 1;
            }
            to {
                opacity: 0.5;
            }
        }

        .counter {
            position: relative;
            display: inline-block;
            margin: 20px;
            padding: 20px;
            border: 2px solid #ff69b4;
            border-radius: 20px;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.2s ease-in-out;
        }

        .counter:hover {
            transform: scale(1.05);
        }

        .action-button {
            font-size: 1.5em;
            width: 40px;
            height: 40px;
            margin: 10px;
            cursor: pointer;
            background-color: #ff69b4;
            color: #fff;
            border: none;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            transition: background-color 0.3s ease-in-out, transform 0.2s ease-in-out;
        }

        .action-button:hover {
            background-color: #ff4788;
            transform: scale(1.1);
        }

        .action-button i {
            font-size: 1.5em;
            border-radius: 50%;
            padding: 5px;
        }

        .image-container {
            margin-top: 20px;
            position: relative;
        }

        .sushi-image {
            width: 150px;
            height: 150px;
            object-fit: cover;
            border-radius: 20px;
        }

        .tooltip {
            visibility: hidden;
            width: 120px;
            background-color: #ff69b4;
            color: #fff;
            text-align: center;
            border-radius: 6px;
            padding: 5px;
            position: absolute;
            z-index: 1;
            bottom: 125%;
            left: 50%;
            margin-left: -60px;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .image-container:hover .tooltip {
            visibility: visible;
            opacity: 1;
        }

        .buttons-container {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 20px;
        }

        .count-container {
            font-size: 1.5em;
            margin: 0 10px;
        }

        hr {
            border: 1px solid #ff69b4;
            margin: 30px 0;
        }

        .footer {
            position: absolute;
            bottom: 10px;
            right: 10px;
            font-size: 1.2em;
            color: #ff69b4;
            cursor: pointer;
            transition: transform 0.3s ease-in-out;
        }

        .footer:hover {
            transform: scale(1.1);
        }
    </style>
</head>
<body>

    <h1>Sushi Counter</h1>

    <div class="counter" id="makiCounter">
        <h3>Maki</h3>
        <div class="image-container">
            <img class="sushi-image" src="maki.jpg" alt="Maki sushi">
            <div class="tooltip">Maki sushi</div>
        </div>
        <div class="buttons-container">
            <button class="action-button" onclick="decrement('maki')">-</button>
            <span class="count-container" id="makiCount">0</span>
            <button class="action-button" onclick="increment('maki')">+</button>
        </div>
    </div>

    <div class="counter" id="nigiriCounter">
        <h3>Nigiri</h3>
        <div class="image-container">
            <img class="sushi-image" src="nigiri.jpg" alt="Nigiri sushi">
            <div class="tooltip">Nigiri sushi</div>
        </div>
        <div class="buttons-container">
            <button class="action-button" onclick="decrement('nigiri')">-</button>
            <span class="count-container" id="nigiriCount">0</span>
            <button class="action-button" onclick="increment('nigiri')">+</button>
        </div>
    </div>

    <div class="counter" id="californiaRollCounter">
        <h3>California Roll</h3>
        <div class="image-container">
            <img class="sushi-image" src="california.jpg" alt="California Roll sushi">
            <div class="tooltip">California Roll sushi</div>
        </div>
        <div class="buttons-container">
            <button class="action-button" onclick="decrement('californiaRoll')">-</button>
            <span class="count-container" id="californiaRollCount">0</span>
            <button class="action-button" onclick="increment('californiaRoll')">+</button>
        </div>
    </div>

    <div class="counter" id="sashimiCounter">
        <h3>Sashimi</h3>
        <div class="image-container">
            <img class="sushi-image" src="sashimi.jpg" alt="Sashimi sushi">
            <div class="tooltip">Sashimi sushi</div>
        </div>
        <div class="buttons-container">
            <button class="action-button" onclick="decrement('sashimi')">-</button>
            <span class="count-container" id="sashimiCount">0</span>
            <button class="action-button" onclick="increment('sashimi')">+</button>
        </div>
    </div>

    <div class="counter" id="krevetyCounter">
        <h3>Krevety</h3>
        <div class="image-container">
            <img class="sushi-image" src="kreveta.jpg" alt="Kreveta sushi">
            <div class="tooltip">Kreveta sushi</div>
        </div>
        <div class="buttons-container">
            <button class="action-button" onclick="decrement('krevety')">-</button>
            <span class="count-container" id="krevetyCount">0</span>
            <button class="action-button" onclick="increment('krevety')">+</button>
        </div>
    </div>

    <div class="counter" id="sladkeCounter">
        <h3>Sladké</h3>
        <div class="image-container">
            <img class="sushi-image" src="sweet.jpg" alt="Sladké sushi">
            <div class="tooltip">Sladké sushi</div>
        </div>
        <div class="buttons-container">
            <button class="action-button" onclick="decrement('sladke')">-</button>
            <span class="count-container" id="sladkeCount">0</span>
            <button class="action-button" onclick="increment('sladke')">+</button>
        </div>
    </div>

    <hr>

    <div>
        <h3>Celkový počet snězených kousků</h3>
        <span id="totalCount">0</span>
    </div>

    <div class="footer" onclick="showCredits()">
        By Anet
    </div>

    <script>
        const counts = {
            maki: 0,
            nigiri: 0,
            californiaRoll: 0,
            sashimi: 0,
            krevety: 0,
            sladke: 0
        };

        function increment(category) {
            counts[category]++;
            updateCount(category);
        }

        function decrement(category) {
            if (counts[category] > 0) {
                counts[category]--;
                updateCount(category);
            }
        }

        function updateCount(category) {
            const countElement = document.getElementById(`${category}Count`);
            countElement.textContent = counts[category];

            const totalCountElement = document.getElementById('totalCount');
            totalCountElement.textContent = Object.values(counts).reduce((total, count) => total + count, 0);
        }

        function showCredits() {
            alert("Designed by Anet");
        }
    </script>
</body>
</html>
