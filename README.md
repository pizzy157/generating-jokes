<html lang="en">
    <head>
        <title>Generating jokes</title>
        <style>
            body {
                background-image: url("file:///C:/Users/tonda/Downloads/N%C3%A1vrh%20bez%20n%C3%A1zvu%20(9).png");
                background-size: cover;
                background-position: center;
            }
            h1 {
                text-align: center;
                color: #ffffff;
                font-size: 65px;
                font-family: "italic", cursive;
                margin-top: 100px;
            }
            p {
                text-align: center;
                font-size: 40px;
                color: rgb(255, 255, 255);
                font-family: bold, italic;
                margin-top: 10px;
            }
            p {
                margin-top: 20px;
            }
            button {
                display: block;
                margin: 45px auto;
                font-size: 40px; /* Zvětšeno z 30px na 40px */
                padding: 20px 60px; /* Přidáno pro větší tlačítko */
                color: rgb(0, 0, 0);
                background-color: skyblue;
                border-radius: 15px; /* Volitelné, zaoblení rohů */
                border: none;        /* Volitelné, odstraní rámeček */
            }
        </style>
    </head>
    <body>
        <h1>Jokes</h1>
        <p id="setup"></p>
        <p id="punchline"></p>
        <button id="newJokeBtn">Generate new joke</button>
        <script>
            async function showRandomJoke() {
                try {
                    const response = await fetch('https://official-joke-api.appspot.com/random_joke');
                    const joke = await response.json();
                    document.getElementById('setup').textContent = joke.setup;
                    document.getElementById('punchline').textContent = joke.punchline;
                } catch (error) {
                    document.getElementById('setup').textContent = "Nepodařilo se načíst vtip.";
                    document.getElementById('punchline').textContent = "";
                }
            }

            document.getElementById('newJokeBtn').onclick = showRandomJoke;

            showRandomJoke();
        </script>
    </body>
</html>
