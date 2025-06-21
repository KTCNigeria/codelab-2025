# Marvel Character Website
In this session, you will be building a website where you can search for and see a lot of superheroes and information about them. This is a fun project you can build an dshow to your friends, and we'll be building it together.

### Requirements
1. Create a github account (github.com)
2. Get an access token from superhero API (superheroapi.com)
3. Create a Codepen account (codepen.io)
4. Paste in this code
   
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Superhero Search</title>
  <style>
    body {
      font-family: sans-serif;
      padding: 2rem;
      background: #f5f5f5;
    }
    input {
      padding: 0.5rem;
      width: 250px;
    }
    button {
      padding: 0.5rem;
      margin-left: 0.5rem;
    }
    .card {
      margin-top: 2rem;
      padding: 1rem;
      background: white;
      border-radius: 8px;
      box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
      max-width: 400px;
    }
    img {
      max-width: 100%;
      border-radius: 6px;
    }
    .stats {
      margin-top: 1rem;
    }
  </style>
</head>
<body>

  <h2>Search for a Superhero</h2>
  <input type="text" id="heroName" placeholder="Enter superhero name" />
  <button onclick="searchHero()">Search</button>

  <div id="result" class="card" style="display: none;">
    <h3 id="name"></h3>
    <img id="image" src="" alt="Superhero Image" />
    <div class="stats">
      <p><strong>Intelligence:</strong> <span id="intelligence"></span></p>
      <p><strong>Strength:</strong> <span id="strength"></span></p>
      <p><strong>Speed:</strong> <span id="speed"></span></p>
      <p><strong>Power:</strong> <span id="power"></span></p>
    </div>
  </div>

  <script>
    const token = "68991e742e4cda24326eebb6c875fe1a";

    async function searchHero() {
      const name = document.getElementById("heroName").value.trim();
      if (!name) return;

      const response = await fetch(`https://www.superheroapi.com/api.php/${token}/search/${name}`);
      const data = await response.json();

      if (data.response === "success") {
        const hero = data.results[0];
        document.getElementById("name").textContent = hero.name;
        document.getElementById("image").src = hero.image.url;
        document.getElementById("intelligence").textContent = hero.powerstats.intelligence;
        document.getElementById("strength").textContent = hero.powerstats.strength;
        document.getElementById("speed").textContent = hero.powerstats.speed;
        document.getElementById("power").textContent = hero.powerstats.power;
        document.getElementById("result").style.display = "block";
      } else {
        alert("Superhero not found.");
      }
    }
  </script>

</body>
</html>
</body>

```

```
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
```
</code>


