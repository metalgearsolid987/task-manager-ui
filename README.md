# task-manager-ui

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Zadaci</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .tasks-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 20px;
      width: 80%;
    }

    .card {
      background: #fff;
      border: 1px solid #ddd;
      border-radius: 8px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      padding: 20px;
    }

    .title {
      font-size: 1.2rem;
      margin-bottom: 10px;
    }

    .checkbox-container {
      display: flex;
      align-items: center;
      gap: 10px;
    }
  </style>
</head>
<body>
  <div id="tasks-container" class="tasks-container"></div>
  <script>
     // JavaScript kod za dinamičko kreiranje kartica
     // Niz objekata sa podacima o zadacima
    const tasks = [
      { userId: 1, id: 1, title: "Silent Hill 2", completed: false },
      { userId: 1, id: 2, title: "STALKER", completed: false },
      { userId: 1, id: 3, title: "GameGround", completed: false },
      { userId: 1, id: 4, title: "UFC", completed: true },
      { userId: 1, id: 5, title: "UFL", completed: false },
      { userId: 1, id: 6, title: "FIFA 25", completed: false },
      { userId: 1, id: 7, title: "The Legend of Zelda: Breath of the Wild", completed: false },
      { userId: 1, id: 8, title: "God of War", completed: true },
      { userId: 1, id: 9, title: "Minecraft", completed: false },
      { userId: 1, id: 10, title: "Red Dead Redemption 2", completed: true },
      { userId: 1, id: 11, title: "The Witcher 3: Wild Hunt", completed: false },
      { userId: 1, id: 12, title: "Elden Ring", completed: true },
      { userId: 1, id: 13, title: "Grand Theft Auto V", completed: false },
      { userId: 1, id: 14, title: "Cyberpunk 2077", completed: true },
      { userId: 1, id: 15, title: "Assassin's Creed Valhalla", completed: false },
      { userId: 1, id: 16, title: "Fortnite", completed: false },
      { userId: 1, id: 17, title: "Call of Duty: Modern Warfare II", completed: true },
      { userId: 1, id: 18, title: "Horizon Forbidden West", completed: false },
      { userId: 1, id: 19, title: "Resident Evil Village", completed: true },
      { userId: 1, id: 20, title: "Among Us", completed: false }
    ];

    const container = document.getElementById("tasks-container"); // Dohvati kontejner u koji ćemo dodati kartice

tasks.forEach(task => { // Iteriraj kroz svaki zadatak u nizu
  const card = document.createElement("div"); // Kreiraj div element za karticu
  card.className = "card"; // Dodaj klasu za stilizaciju kartice

  const title = document.createElement("h2"); // Kreiraj h2 element za naslov
  title.className = "title"; // Dodaj klasu za stilizaciju naslova
  title.textContent = task.title; // Postavi tekst naslova

  const checkboxContainer = document.createElement("div"); // Kreiraj div za checkbox i labelu
  checkboxContainer.className = "checkbox-container"; // Dodaj klasu za stilizaciju

  const label = document.createElement("label"); // Kreiraj labelu za checkbox
  label.setAttribute("for", `task-${task.id}`); // Poveži labelu sa checkbox-om pomoću ID-a
  label.textContent = "Completed:"; // Postavi tekst label-e

  const checkbox = document.createElement("input"); // Kreiraj checkbox
  checkbox.type = "checkbox"; // Postavi tip elementa na checkbox
  checkbox.id = `task-${task.id}`; // Postavi jedinstveni ID za svaki checkbox
  checkbox.checked = task.completed; // Postavi da li je checkbox čekiran na osnovu vrednosti "completed"

  checkboxContainer.appendChild(label); // Dodaj labelu u container za checkbox
  checkboxContainer.appendChild(checkbox); // Dodaj checkbox u container za checkbox

  card.appendChild(title); // Dodaj naslov u karticu
  card.appendChild(checkboxContainer); // Dodaj container za checkbox u karticu

  container.appendChild(card); // Dodaj karticu u kontejner
});
</script>
</body>
</html>
