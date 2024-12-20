# Puzzle-game-
This is very funny game 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Brain Teaser Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 20px;
      background: #f0f8ff;
    }
    .question {
      font-size: 20px;
      margin: 20px 0;
    }
    input {
      padding: 10px;
      font-size: 16px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      margin-top: 10px;
    }
    .result {
      font-size: 18px;
      margin-top: 20px;
      color: green;
    }
    .wrong {
      color: red;
    }
  </style>
</head>
<body>
  <h1>Brain Twister</h1>
  <div class="question" id="question">What has to be broken before you can use it?</div>
  <input type="text" id="answer" placeholder="Your answer here" />
  <br />
  <button onclick="checkAnswer()">Submit</button>
  <div class="result" id="result"></div>

  <script>
    const questions = [
      { question: "What has to be broken before you can use it?", answer: "egg" },
      { question: "I’m tall when I’m young, and I’m short when I’m old. What am I?", answer: "candle" },
      { question: "What has a head, a tail, but no body?", answer: "coin" },
    ];

    let currentQuestion = 0;

    function checkAnswer() {
      const userAnswer = document.getElementById("answer").value.toLowerCase().trim();
      const result = document.getElementById("result");

      if (userAnswer === questions[currentQuestion].answer) {
        result.textContent = "Correct! Moving to the next question.";
        result.className = "result";

        // Move to the next question
        currentQuestion++;
        if (currentQuestion < questions.length) {
          document.getElementById("question").textContent = questions[currentQuestion].question;
          document.getElementById("answer").value = "";
        } else {
          result.textContent = "Congratulations! You solved all the puzzles!";
        }
      } else {
        result.textContent = "Wrong answer. Try again!";
        result.className = "result wrong";
      }
    }
  </script>
</body>
</html>
