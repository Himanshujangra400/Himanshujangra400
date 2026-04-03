<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YouTube Title Generator</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', sans-serif;
}

body {
  background: linear-gradient(135deg, #0f172a, #020617);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  width: 420px;
  padding: 30px;
  border-radius: 16px;
  background: rgba(30, 41, 59, 0.7);
  backdrop-filter: blur(12px);
  box-shadow: 0 20px 60px rgba(0,0,0,0.5);
  text-align: center;
}

h1 {
  margin-bottom: 10px;
  font-size: 26px;
}

p {
  color: #94a3b8;
  margin-bottom: 20px;
}

input {
  width: 100%;
  padding: 14px;
  border-radius: 10px;
  border: none;
  outline: none;
  margin-bottom: 15px;
  font-size: 16px;
}

button {
  width: 100%;
  padding: 14px;
  border: none;
  border-radius: 10px;
  background: linear-gradient(45deg, #22c55e, #4ade80);
  color: black;
  font-weight: bold;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  transform: scale(1.05);
}

#results {
  margin-top: 20px;
  text-align: left;
  max-height: 250px;
  overflow-y: auto;
}

.title {
  background: #334155;
  padding: 10px;
  border-radius: 8px;
  margin-bottom: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.copy {
  background: #22c55e;
  border: none;
  padding: 5px 8px;
  border-radius: 6px;
  cursor: pointer;
  font-size: 12px;
}
</style>

</head>
<body>

<div class="container">
  <h1>🚀 Title Generator</h1>
  <p>Create high-retention YouTube titles</p>

  <input id="topic" type="text" placeholder="Enter topic (e.g. Mustang Engine)" />

  <button onclick="generateTitles()">Generate Titles</button>

  <div id="results"></div>
</div>

<script>
function generateTitles() {
  const topic = document.getElementById("topic").value;
  const results = document.getElementById("results");

  if (!topic) {
    results.innerHTML = "<p>Enter a topic first.</p>";
    return;
  }

  const templates = [
    `The Truth About ${topic} Nobody Tells You`,
    `Why ${topic} is Changing Everything`,
    `The Dark Side of ${topic}`,
    `${topic} Explained in 60 Seconds`,
    `This ${topic} Will Blow Your Mind`,
    `Top Secrets About ${topic}`,
    `How ${topic} Became So Powerful`,
    `${topic} vs Reality – What’s True?`
  ];

  results.innerHTML = "";

  templates.forEach(title => {
    const div = document.createElement("div");
    div.className = "title";

    const text = document.createElement("span");
    text.innerText = title;

    const btn = document.createElement("button");
    btn.innerText = "Copy";
    btn.className = "copy";
    btn.onclick = () => {
      navigator.clipboard.writeText(title);
      btn.innerText = "Copied!";
      setTimeout(() => btn.innerText = "Copy", 1000);
    };

    div.appendChild(text);
    div.appendChild(btn);
    results.appendChild(div);
  });
}
</script>

</body>
</html>
