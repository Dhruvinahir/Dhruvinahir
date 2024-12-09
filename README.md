<!DOCTYPE html>
<html>
<head>
<title>Simple Click Game</title>
<style>
body {
  font-family: sans-serif;
  text-align: center;
}
#square {
  width: 100px;
  height: 100px;
  background-color: blue;
  margin: 50px auto;
  cursor: pointer;
}
</style>
</head>
<body>
  <h1>Click the Square!</h1>
  <p>Score: <span id="score">0</span></p>
  <div id="square"></div>

  <script>
  const square = document.getElementById("square");
  const scoreDisplay = document.getElementById("score");
  let score = 0;

  square.addEventListener("click", () => {
    score++;
    scoreDisplay.textContent = score;
    moveSquare();
  });


  function moveSquare() {
    const maxX = window.innerWidth - 100; // Subtract square width
    const maxY = window.innerHeight - 100; // Subtract square height
    const randomX = Math.floor(Math.random() * maxX);
    const randomY = Math.floor(Math.random() * maxY);
    square.style.left = randomX + "px";
    square.style.top = randomY + "px";
    square.style.position = "absolute"; // Needed for positioning
  }

  moveSquare(); // Initial placement
  </script>

</body>
</html>
