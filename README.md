<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Where Winds Meet - Map & Walkthroughs</title>
    <style>
        :root {
            --wuxia-gold: #d4af37;
            --dark-ink: #1a1a1b;
            --silk-white: #f5f5f5;
        }
        body { font-family: 'Segoe UI', sans-serif; background: var(--dark-ink); color: var(--silk-white); margin: 0; }
        header { background: #000; padding: 20px; text-align: center; border-bottom: 2px solid var(--wuxia-gold); }
        
        /* Map Section */
        #map-container { position: relative; width: 90%; margin: 20px auto; border: 1px solid #444; }
        #game-map { width: 100%; display: block; filter: brightness(0.8); }
        .marker { position: absolute; width: 15px; height: 15px; background: red; border-radius: 50%; transform: translate(-50%, -50%); cursor: pointer; }
        
        /* Search Bar */
        .search-box { text-align: center; margin: 20px 0; }
        #locationSearch { padding: 12px; width: 300px; border-radius: 5px; border: none; }

        /* Video Grid */
        .video-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; padding: 20px; }
        .video-card { background: #2a2a2a; border-radius: 8px; overflow: hidden; transition: 0.3s; }
        .video-card:hover { transform: translateY(-5px); border: 1px solid var(--wuxia-gold); }
        .video-card img { width: 100%; height: 180px; object-fit: cover; }
        .video-card h3 { padding: 10px; font-size: 1.1rem; }
    </style>
</head>
<body>

<header>
    <h1>WHERE WINDS MEET - EXPLORER HUB</h1>
</header>

<section class="search-box">
    <input type="text" id="locationSearch" placeholder="Search for hidden objects (e.g. 'Oddity', 'Skill Scroll')..." onkeyup="filterMap()">
</section>

<div id="map-container">
    <img src="https://via.placeholder.com/1200x600/222/888?text=WWM+Game+Map+Grid" id="game-map">
    
    <div class="marker" style="top: 30%; left: 45%;" data-name="Qinghe Oddity"></div>
    <div class="marker" style="top: 55%; left: 20%;" data-name="Hidden Skill Scroll"></div>
    <div class="marker" style="top: 70%; left: 80%;" data-name="Golden Treasure Chest"></div>
</div>

<hr style="border: 0.5px solid #444; width: 90%;">

<h2 style="text-align: center; color: var(--wuxia-gold);">Mission Walkthroughs</h2>
<div class="video-grid">
    <div class="video-card">
        <img src="https://via.placeholder.com/300x180/333/fff?text=Walkthrough+1" alt="Mission 1">
        <h3>Main Quest: The Silent Shore</h3>
    </div>
    <div class="video-card">
        <img src="https://via.placeholder.com/300x180/333/fff?text=Walkthrough+2" alt="Mission 2">
        <h3>Career Quest: The Physician's Path</h3>
    </div>
    <div class="video-card">
        <img src="https://via.placeholder.com/300x180/333/fff?text=Walkthrough+3" alt="Mission 3">
        <h3>Hidden Boss: The Void King</h3>
    </div>
</div>

<script>
    function filterMap() {
        let input = document.getElementById('locationSearch').value.toLowerCase();
        let markers = document.querySelectorAll('.marker');
        
        markers.forEach(marker => {
            let name = marker.getAttribute('data-name').toLowerCase();
            if (name.includes(input)) {
                marker.style.display = "block";
                marker.style.boxShadow = "0 0 10px yellow"; // Highlight found item
            } else {
                marker.style.display = "none";
            }
        });
    }
</script>

</body>
</html>

