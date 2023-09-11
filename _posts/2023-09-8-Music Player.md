---
toc: true
comments: false
layout: post
title: Music Player 
type: tangibles
courses: { compsci: {week: 3} }
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YouTube Song Player</title>
</head>
<body>
    <h1>YouTube Song Player</h1>
    <p>Enter a song name and click "Play" to watch the video:</p>

    <input type="text" id="songName" placeholder="Enter song name">
    <button id="playButton">Play</button>

    <div id="playerContainer">
        <!-- YouTube Embedded Player -->
        <iframe id="youtubePlayer" width="560" height="315" frameborder="0" allowfullscreen></iframe>
    </div>

    <script>
        const apiKey ='AIzaSyBa4nJQtcJMyLNW9tDY0pH2NHwHCdt7fUE'; 
        const playButton = document.getElementById("playButton");
        const songNameInput = document.getElementById("songName");
        const youtubePlayer = document.getElementById("youtubePlayer");

        playButton.addEventListener("click", () => {
            // Get the song name entered by the user
            const songName = songNameInput.value;

            // Use the YouTube Data API to search for the video
            fetch(`https://www.googleapis.com/youtube/v3/search?key=${apiKey}&q=${encodeURIComponent(songName)}&type=video`)
                .then(response => response.json())
                .then(data => {
                    if (data.items && data.items.length > 0) {
                        // Get the video ID of the first search result
                        const videoId = data.items[0].id.videoId;

                        // Set the video source in the embedded player
                        youtubePlayer.src = `https://www.youtube.com/embed/${videoId}`;
                    } else {
                        alert("No matching videos found.");
                    }
                })
                .catch(error => {
                    console.error("Error fetching video data:", error);
                    alert("An error occurred while fetching video data.");
                });
        });
    </script>
</body>
</html>
