---
toc: true
comments: false
layout: post
title: rock paper scissors
type: hacks
courses: { compsci: {week: 2} }
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rock, Paper, Scissors Game</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
        }

        #result {
            font-size: 24px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Rock, Paper, Scissors Game</h1>
    <p>Choose your move:</p>
    <button id="rock">Rock</button>
    <button id="paper">Paper</button>
    <button id="scissors">Scissors</button>
    <p id="result">Result: </p>

    <script>
        const choices = ["rock", "paper", "scissors"];
        const resultDisplay = document.getElementById("result");

        function computerChoice() {
            const randomIndex = Math.floor(Math.random() * choices.length);
            return choices[randomIndex];
        }

        function playGame(playerChoice) {
            const computer = computerChoice();
            const player = playerChoice;

            if (player === computer) {
                resultDisplay.textContent = "It's a tie!";
            } else if (
                (player === "rock" && computer === "scissors") ||
                (player === "paper" && computer === "rock") ||
                (player === "scissors" && computer === "paper")
            ) {
                resultDisplay.textContent = `You win! Computer chose ${computer}.`;
            } else {
                resultDisplay.textContent = `You lose! Computer chose ${computer}.`;
            }
        }

        document.getElementById("rock").addEventListener("click", () => playGame("rock"));
        document.getElementById("paper").addEventListener("click", () => playGame("paper"));
        document.getElementById("scissors").addEventListener("click", () => playGame("scissors"));
    </script>
</body>
</html>
