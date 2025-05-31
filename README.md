<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Easy Python</title>
  <style>
    body { font-family: sans-serif; padding: 20px; background: #f9f9f9; color: #333; }
    h1 { color: #2c3e50; }
    .lesson { background: white; border-radius: 10px; padding: 15px; margin-bottom: 15px; box-shadow: 0 2px 6px rgba(0,0,0,0.1); }
    .lesson h2 { margin-top: 0; }
    .completed { text-decoration: line-through; color: #999; }
    input[type="checkbox"] { margin-right: 10px; }
  </style>
</head>
<body>
  <h1>📘 Easy Python</h1>
  <p>Welcome! Learn Python one day at a time.</p>  <div class="lesson">
    <label><input type="checkbox" onchange="saveProgress(this, 1)"> <strong>Day 1:</strong> Hello World & Print Function</label>
    <pre><code>print("Hello, world!")</code></pre>
  </div>  <div class="lesson">
    <label><input type="checkbox" onchange="saveProgress(this, 2)"> <strong>Day 2:</strong> Variables and Types</label>
    <pre><code>name = "Alice"
age = 25
print(name, age)</code></pre>
  </div>  <script>
    function saveProgress(checkbox, day) {
      localStorage.setItem("day" + day, checkbox.checked);
      if (checkbox.checked) checkbox.parentElement.classList.add("completed");
      else checkbox.parentElement.classList.remove("completed");
    }

    window.onload = function() {
      [1, 2].forEach(day => {
        const checked = localStorage.getItem("day" + day) === "true";
        const box = document.querySelector(`input[onchange*='${day}']`);
        if (box) {
          box.checked = checked;
          if (checked) box.parentElement.classList.add("completed");
        }
      });
    }
  </script></body>
</html>
