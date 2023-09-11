
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML and Python Quiz</title>
</head>
<body>
    <h1>HTML and Python Quiz</h1>
    <form id="quiz-form">
        <div class="question">
            <p>1. HTML stands for Hypertext Markup Language.</p>
            <label>
                <input type="radio" name="q1" value="yes"> Yes
            </label>
            <label>
                <input type="radio" name="q1" value="no"> No
            </label>
        </div>

        <div class="question">
            <p>2. Python is a compiled language.</p>
            <label>
                <input type="radio" name="q2" value="yes"> Yes
            </label>
            <label>
                <input type="radio" name="q2" value="no"> No
            </label>
        </div>

        <div class="question">
            <p>3. HTML is used for creating web pages.</p>
            <label>
                <input type="radio" name="q3" value="yes"> Yes
            </label>
            <label>
                <input type="radio" name="q3" value="no"> No
            </label>
        </div>

        <div class="question">
            <p>4. Python is a dynamically typed language.</p>
            <label>
                <input type="radio" name="q4" value="yes"> Yes
            </label>
            <label>
                <input type="radio" name="q4" value="no"> No
            </label>
        </div>

        <div class="question">
            <p>5. HTML is a programming language.</p>
            <label>
                <input type="radio" name="q5" value="yes"> Yes
            </label>
            <label>
                <input type="radio" name="q5" value="no"> No
            </label>
        </div>

        <br>
        <button type="button" onclick="gradeQuiz()">Submit</button>
    </form>

    <div id="quiz-results" style="display: none;">
        <h2>Quiz Results</h2>
        <p id="score"></p>
    </div>

    <script>
        function gradeQuiz() {
            const correctAnswers = ["yes", "no", "yes", "yes", "no"];
            let score = 0;

            for (let i = 1; i <= 5; i++) {
                const userAnswer = document.querySelector(`input[name="q${i}"]:checked`).value;
                if (userAnswer === correctAnswers[i - 1]) {
                    score++;
                }
            }

            const resultDiv = document.getElementById("quiz-results");
            const scoreParagraph = document.getElementById("score");
            scoreParagraph.textContent = `You scored ${score} out of 5 good job ! 
            
            
            
            `;
            resultDiv.style.display = "block";
        }
    </script>
</body>
</html>
