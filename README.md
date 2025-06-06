<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MDT Police Nationale</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: white;
      color: #202124;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    header {
      background-color: #1a73e8;
      color: white;
      padding: 20px;
      width: 100%;
      text-align: center;
    }

    .search-box {
      margin-top: 40px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    input[type="text"] {
      width: 400px;
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }

    button {
      margin-top: 15px;
      padding: 10px 20px;
      font-size: 16px;
      background-color: #1a73e8;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    button:hover {
      background-color: #155ab6;
    }

    .results {
      margin-top: 40px;
      width: 60%;
      max-width: 800px;
    }

    .card {
      background: #f1f3f4;
      padding: 20px;
      margin: 15px 0;
      border-radius: 6px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }
  </style>
</head>
<body>

  <header>
    <h1>MDT Police Nationale</h1>
    <p>Système de gestion des dossiers et recherches RP</p>
  </header>

  <div class="search-box">
    <input type="text" id="searchInput" placeholder="Nom, Prénom, Plaque, etc..." />
    <button onclick="search()">Rechercher</button>
  </div>

  <div class="results" id="results">
    <!-- Résultats affichés ici -->
  </div>

  <script>
    function search() {
      const input = document.getElementById("searchInput").value;
      const resultsDiv = document.getElementById("results");

      // Exemples statiques (à remplacer par une base de données plus tard)
      const fakeDB = {
        "jean dupont": {
          nom: "Jean Dupont",
          age: "28",
          casier: "Condamnation pour excès de vitesse",
          plaque: "AB-123-CD"
        },
        "emma leroy": {
          nom: "Emma Leroy",
          age: "34",
          casier: "Aucun antécédent",
          plaque: "XY-456-ZT"
        }
      };

      const data = fakeDB[input.toLowerCase()];

      if (data) {
        resultsDiv.innerHTML = `
          <div class="card">
            <h3>${data.nom}</h3>
            <p><strong>Âge :</strong> ${data.age}</p>
            <p><strong>Casier :</strong> ${data.casier}</p>
            <p><strong>Plaque :</strong> ${data.plaque}</p>
          </div>
        `;
      } else {
        resultsDiv.innerHTML = `<p>Aucun résultat trouvé pour "${input}".</p>`;
      }
    }
  </script>

</body>
</html>
