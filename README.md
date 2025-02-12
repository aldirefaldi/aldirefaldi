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
    canvas { border: 2px solid white; margin-top: 20px; }
  </style>
</head>
<body>
  <h3>Snake Game - Eat to Score!</h3>
  <p>Use arrow keys to move</p>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
  <script>
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");
    
    let snake = [{ x: 200, y: 200 }];
    let food = { x: 100, y: 100 };
    let direction = "RIGHT";
    let score = 0;
    let health = 3;

    function drawSnake() {
      ctx.fillStyle = "lime";
      snake.forEach((segment) => ctx.fillRect(segment.x, segment.y, 20, 20));
    }

    function drawFood() {
      ctx.fillStyle = "red";
      ctx.fillRect(food.x, food.y, 20, 20);
    }

    function updateGame() {
      let head = { ...snake[0] };
      if (direction === "UP") head.y -= 20;
      if (direction === "DOWN") head.y += 20;
      if (direction === "LEFT") head.x -= 20;
      if (direction === "RIGHT") head.x += 20;

      if (head.x === food.x && head.y === food.y) {
        score++;
        food = { x: Math.floor(Math.random() * 20) * 20, y: Math.floor(Math.random() * 20) * 20 };
      } else {
        snake.pop();
      }
      if (head.x < 0 || head.y < 0 || head.x >= canvas.width || head.y >= canvas.height) {
        health--;
        if (health <= 0) {
          alert("Game Over! Score: " + score);
          location.reload();
        }
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
      ctx.fillText("Health: " + health, 10, 40);
    }

    document.addEventListener("keydown", (event) => {
      if (event.key === "ArrowUp" && direction !== "DOWN") direction = "UP";
      if (event.key === "ArrowDown" && direction !== "UP") direction = "DOWN";
      if (event.key === "ArrowLeft" && direction !== "RIGHT") direction = "LEFT";
      if (event.key === "ArrowRight" && direction !== "LEFT") direction = "RIGHT";
    });

    setInterval(updateGame, 150);
  </script>
</body>
</html>
```
