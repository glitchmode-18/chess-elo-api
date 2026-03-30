const express = require("express");
const app = express();

app.get("/", async (req, res) => {
  try {
    const response = await fetch("https://api.chess.com/pub/player/ItsJessedfe/stats");
    const data = await response.json();

    const rapid = data.chess_rapid?.last?.rating || "N/A";
    const blitz = data.chess_blitz?.last?.rating || "N/A";
    const bullet = data.chess_bullet?.last?.rating || "N/A";

    res.send(`Rapid: ${rapid} | Blitz: ${blitz} | Bullet: ${bullet}`);
  } catch {
    res.send("Error fetching rating");
  }
});

app.listen(3000, () => console.log("Server running"));