<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beer Soul Contract</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #222;
            color: #fff;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: #333;
            padding: 20px;
            border-radius: 10px;
        }
        input, button {
            font-size: 18px;
            padding: 10px;
            margin: 10px;
        }
        .result {
            font-size: 22px;
            margin-top: 20px;
            padding: 10px;
            background: #444;
            border-radius: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Discover Your Beer Soul Contract 🍺</h1>
        <p>Enter your name and birthdate to reveal your beer destiny!</p>
        <input type="text" id="name" placeholder="Your Name">
        <input type="date" id="birthdate">
        <button onclick="calculateBeerContract()">Find My Beer Fate</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculateBeerContract() {
            let name = document.getElementById('name').value;
            let birthdate = document.getElementById('birthdate').value;
            if (!name || !birthdate) {
                alert("Please enter both your name and birthdate!");
                return;
            }
            
            let num = birthdate.replace(/-/g, '').split('').reduce((a, b) => a + parseInt(b), 0);
            while (num > 9) {
                num = num.toString().split('').reduce((a, b) => a + parseInt(b), 0);
            }
            
            let beerTypes = [
                "The Bold Pioneer - Try our experimental Wild Workshop brews!",
                "The Smooth Operator - You need a crisp, balanced Pilsner!",
                "The Hazy Visionary - A juicy, hop-forward Hazy IPA awaits!",
                "The Dark Master - A rich Stout or Black IPA is your destiny!",
                "The Wild Wanderer - Explore funky Sours and barrel-aged blends!",
                "The Party Alchemist - You thrive on sessionable, easy-drinking beers!",
                "The Beer Philosopher - Saisons & Farmhouse Ales are your calling!",
                "The Power Drinker - Bold, high-ABV brews like Triple IPAs are yours!",
                "The Eternal Brewer - A classic Bitter or Belgian Dubbel is your fate!"
            ];
            
            document.getElementById('result').innerHTML = `<strong>${name},</strong> your Beer Soul Contract is:<br><br> ${beerTypes[num - 1]}`;
        }
    </script>
</body>
</html>
