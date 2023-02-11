# AMTICS-PC-LAB
<html>

<head>
    <title>AMTICS Workship</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.3/dist/leaflet.css"
        integrity="sha256-kLaT2GOSpHechhsozzB+flnD+zUyjE2LlfWPgU04xyI=" crossorigin="" />

    <!-- Make sure you put this AFTER Leaflet's CSS -->
    <script src="https://unpkg.com/leaflet@1.9.3/dist/leaflet.js"
        integrity="sha256-WBkoXOwTeyKclOHuWtc+i2uENFpDZ9YPdf5Hf+D7ewM=" crossorigin=""></script>

    <style>
        #map {
            height: 500px;
        }
    </style>
</head>

<body>
    <div id="map"></div>
    <script>

        const map = L.map('map').setView([21.1190193, 72.9077824], 10);

        const tiles = L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
            maxZoom: 19,
            attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
        }).addTo(map);

        let cities = [
            {
                name:"dumas"
                lat:20.3974,
                long:72.8328
            },
            {
                name: "Surat",
                lat: 21.1190193,
                long: 72.9077824
            },
            {
                name: "Bardoli",
                lat: 21.1363602,
                long: 73.098641
            },
            {
                name: "Kamrej",
                lat: 21.269354,
                long: 72.962955
            },
          {
                name: "Limla",
                lat: 21.1715,
                long: 72.7031
            },
        ];

        cities.forEach(city => {
            const marker = L.marker([city.lat, city.long]).addTo(map)
                .bindPopup(city.name).openPopup();
        })

    </script>
</body>

</html>
