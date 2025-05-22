<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My Anime List</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>My Anime List</h1>
    <form id="animeForm">
      <input type="text" id="animeInput" placeholder="Enter anime name" required />
      <button type="submit">Add</button>
    </form>
    <ul id="animeList"></ul>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background-color: #f9f9f9;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.container {
  background: white;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  width: 350px;
  text-align: center;
}

h1 {
  margin-bottom: 20px;
}

form {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

input[type="text"] {
  flex: 1;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 6px;
}

button {
  padding: 8px 12px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 6px;
  margin-bottom: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.favorite {
  color: gold;
  font-weight: bold;
}
const form = document.getElementById("animeForm");
const input = document.getElementById("animeInput");
const list = document.getElementById("animeList");

form.addEventListener("submit", function (e) {
  e.preventDefault();
  const animeName = input.value.trim();
  if (animeName === "") return;
  addAnime(animeName);
  input.value = "";
});

function addAnime(name) {
  const li = document.createElement("li");
  li.textContent = name;

  const favoriteBtn = document.createElement("button");
  favoriteBtn.textContent = "★";
  favoriteBtn.onclick = () => li.classList.toggle("favorite");

  const removeBtn = document.createElement("button");
  removeBtn.textContent = "Remove";
  removeBtn.onclick = () => li.remove();

  li.appendChild(favoriteBtn);
  li.appendChild(removeBtn);
  list.appendChild(li);
}
# Anime List Web App

This is a simple web application that allows users to create and manage a personal anime list. Users can add anime titles, mark favorites, and remove entries.

## Features

- Add anime titles to the list
- Mark anime as favorite by toggling a star
- Remove anime from the list
- Clean and responsive design

## Technologies Used

- HTML for structure
- CSS for styling
- JavaScript for interactivity

## Purpose

This project was created as a learning exercise to practice web development skills including DOM manipulation and event handling. It demonstrates my ability to build interactive web applications.

---

Feel free to explore and modify the code!
