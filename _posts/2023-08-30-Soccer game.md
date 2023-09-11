---
toc: true
comments: false
layout: post
title: Soccer game
type: tangibles
courses: { compsci: {week: 2} }
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Penalty Shootout Game</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
        }

        #goal {
            width: 400px;
            height: 200px;
            background-color: #22cc22;
            margin: 50px auto;
            position: relative;
        }

        #ball {
            width: 50px;
            height: 50px;
            background-color: #ff0000;
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
    </style>
</head>
<body>
    <h1>Penalty Shootout Game</h1>
    <p>Click to shoot the ball into the goal!</p>
    <div id="goal">
        <div id="ball"></div>
    </div>
    <p>Score: <span id="score">0</span></p>
    <p id="message"></p>

    <script>
        const goal = document.getElementById('goal');
        const ball = document.getElementById('ball');
        const scoreDisplay = document.getElementById('score');
        const messageDisplay = document.getElementById('message');
        let score = 0;
        let isBallMoving = false;

        goal.addEventListener('click', () => {
            if (!isBallMoving) {
                score++;
                scoreDisplay.textContent = score;
                shootBall();
            } else {
                messageDisplay.textContent = "Wait for the next penalty!";
            }
        });

        function shootBall() {
            isBallMoving = true;
            messageDisplay.textContent = "";
            ball.style.transition = 'bottom 1s, left 1s';
            ball.style.bottom = '80%';
            setTimeout(() => {
                ball.style.transition = 'none';
                ball.style.bottom = '0';
                ball.style.left = '50%';
                setTimeout(() => {
                    isBallMoving = false;
                }, 500);
            }, 1000);
        }
    </script>
</body>
</html>
