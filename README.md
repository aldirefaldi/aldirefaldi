### Hi there! 👋 Welcome to my GitHub Profile!  

![DevOps GIF](https://media.giphy.com/media/QTfX9Ejfra3ZmNxh6B/giphy.gif)

---

### 🌱 About Me  
I’m a beginner programmer who is currently diving into the world of **IT Monitoring** and **DevOps**. I love learning new technologies and building solutions that enhance system performance and reliability.

🚀 Technologies & Tools I Use:

<p align="left">
  <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" />
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white" />
</p>

---

### 📚 What I’m Learning
- 📌 **Grafana & Prometheus** for monitoring and visualization
- 📌 **Kubernetes** for container orchestration
- 📌 **Terraform** for Infrastructure as Code (IaC)

---

### 📫 Connect with Me  
Let's connect and grow together in the world of DevOps! Feel free to reach out! 😊

📧 **Email: your.email@example.com**  
📂 **[Portfolio](#)** *(Coming Soon!)*  

---

💻 *Always Learning | Always Building | Always Improving* 🚀

---

### 🎮 Play Snake Game! 🕹️

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body { background-color: black; color: white; text-align: center; font-family: Arial, sans-serif; }
    .game-container { display: flex; flex-direction: column; align-items: center; }
    canvas { border: 4px solid white; background-color: #222; }
    button { margin-top: 10px; padding: 10px 20px; font-size: 16px; background: lime; border: none; cursor: pointer; }
  </style>
</head>
<body>
  <div class="game-container">
    <h3>Snake Game - Eat to Score!</h3>
    <p>Use arrow keys to move</p>
    <button onclick="startGame()">Start Game</button>
    <canvas id="gameCanvas" width="400" height="400"></canvas>
  </div>
  <script>
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");
    let snake, food, direction, score, gameRunning, snakeColor;

    function startGame() {
      snake = [{ x: 200, y: 200 }];
      food = { x: 100, y: 100 };
      direction = "RIGHT";
      score = 0;
      gameRunning = true;
      snakeColor = "lime";
      gameLoop();
    }

    function drawSnake() {
      ctx.fillStyle = snakeColor;
      snake.forEach((segment) => ctx.fillRect(segment.x, segment.y, 20, 20));
    }

    function drawFood() {
      ctx.fillStyle = "red";
      ctx.fillRect(food.x, food.y, 20, 20);
    }

    function getRandomColor() {
      const colors = ["lime", "cyan", "yellow", "orange", "purple", "blue"];
      return colors[Math.floor(Math.random() * colors.length)];
    }

    function updateGame() {
      if (!gameRunning) return;
      let head = { ...snake[0] };
      if (direction === "UP") head.y -= 20;
      if (direction === "DOWN") head.y += 20;
      if (direction === "LEFT") head.x -= 20;
      if (direction === "RIGHT") head.x += 20;

      // Wrap around edges
      if (head.x < 0) head.x = canvas.width - 20;
      if (head.y < 0) head.y = canvas.height - 20;
      if (head.x >= canvas.width) head.x = 0;
      if (head.y >= canvas.height) head.y = 0;

      // Check collision with food
      if (head.x === food.x && head.y === food.y) {
        score++;
        food = { x: Math.floor(Math.random() * 20) * 20, y: Math.floor(Math.random() * 20) * 20 };
        if (score % 10 === 0) {
          snakeColor = getRandomColor();
          snake.push({}); // Increase snake size every 10 points
        }
      } else {
        snake.pop();
      }

      // Check collision with itself
      if (snake.some(segment => segment.x === head.x && segment.y === head.y)) {
        alert("Game Over! Score: " + score);
        gameRunning = false;
        return;
      }

      snake.unshift(head);
      drawGame();
    }

    function drawGame() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      drawSnake();
      drawFood();
      ctx.fillStyle = "white";
      ctx.fillText("Score: " + score, 10, 20);
    }

    document.addEventListener("keydown", (event) => {
      if (event.key === "ArrowUp" && direction !== "DOWN") direction = "UP";
      if (event.key === "ArrowDown" && direction !== "UP") direction = "DOWN";
      if (event.key === "ArrowLeft" && direction !== "RIGHT") direction = "LEFT";
      if (event.key === "ArrowRight" && direction !== "LEFT") direction = "RIGHT";
    });

    function gameLoop() {
      if (gameRunning) {
        updateGame();
        setTimeout(gameLoop, 150);
      }
    }
  </script>
</body>
</html>
```
