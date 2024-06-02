<!DOCTYPE html>
        <html lang="en">
        <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
        <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
        <style>
        #map,body {
        border: none;
        margin: 0;
        height: 100vh;
        width: 100vw;
        }
        </style>
        </head>
        <body>
        <div id="map"></div>
        <script>
    
                //ONLY TO TEST OUT THE HTML Structure
        var map = L.map("map").setView([0, 0], 4);
        L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
        attribution: `&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors`}).addTo(map);
        var geoJSONString = ``
        var arrayofall = geoJSONString.split("|");

        arrayofall.forEach((v,i,a)=>{
            const land = JSON.parse(v);


      
        
        const geo = L.geoJSON(land, {
         style: {
        fillColor: 'black', color: "black", weight: 1,fillOpacity: 0.9
          }
         });
        geo.addTo(map);
        map.fitBounds(geo.getBounds());
        var currentZoom = map.getZoom();
        var zoomOutLevel = currentZoom - 4;
        map.setZoom(zoomOutLevel);


        });

    
        </script>
        </body>
        </html>
