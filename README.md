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

### 🎮 Play a Simple Game! 🕹️

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
  <h3>Click to move the box!</h3>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
  <script>
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");
    let x = 50, y = 50;

    function getMousePos(canvas, event) {
      const rect = canvas.getBoundingClientRect();
      return {
        x: event.clientX - rect.left,
        y: event.clientY - rect.top
      };
    }

    canvas.addEventListener("click", (e) => {
      const pos = getMousePos(canvas, e);
      x = pos.x - 15; // Adjust for centering
      y = pos.y - 15;
      draw();
    });

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.fillStyle = "red";
      ctx.fillRect(x, y, 30, 30);
    }

    draw();
  </script>
</body>
</html>
```
