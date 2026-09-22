---
layout: single
title: "行きたい場所マップ"
permalink: /map/
author_profile: false
---

<div id="blog-map"></div>

<!-- Leaflet CSS & JS の読み込み -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<style>
  #blog-map {
    width: 100%;
    height: 600px;
    border-radius: 8px;
    margin: 20px 0;
    z-index: 1;
  }
  /* アイコンピンの見た目を整えるCSS */
  .custom-pin {
    background: transparent;
    border: none;
  }
  .pin-circle {
    width: 34px;
    height: 34px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 14px;
    box-shadow: 0 3px 8px rgba(0,0,0,0.3);
    border: 2px solid white;
  }
</style>

<script>
document.addEventListener("DOMContentLoaded", () => {
  const map = L.map('blog-map').setView([34.7024, 135.4959], 14);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
  }).addTo(map);

  // --- 1. 観光・お出かけ用アイコンピン（例：カメラ） ---
  const spotIcon = L.divIcon({
    className: 'custom-pin',
    html: '<div class="pin-circle" style="background-color: #ff4d4f;"><i class="fas fa-camera"></i></div>',
    iconSize: [34, 34],
    iconAnchor: [17, 17]
  });
  L.marker([34.7024, 135.4959], { icon: spotIcon }).addTo(map).bindPopup("<b>大阪駅</b><br>観光スポット");

  // --- 2. グルメ・カフェ用アイコンピン（例：コーヒーカップ） ---
  const cafeIcon = L.divIcon({
    className: 'custom-pin',
    html: '<div class="pin-circle" style="background-color: #fa8c16;"><i class="fas fa-coffee"></i></div>',
    iconSize: [34, 34],
    iconAnchor: [17, 17]
  });
  L.marker([34.7026, 135.4947], { icon: cafeIcon }).addTo(map).bindPopup("<b>カフェ</b><br>美味しいコーヒーのお店");

  // --- 3. ホテル・宿泊用アイコンピン（例：ベッド） ---
  const hotelIcon = L.divIcon({
    className: 'custom-pin',
    html: '<div class="pin-circle" style="background-color: #1890ff;"><i class="fas fa-bed"></i></div>',
    iconSize: [34, 34],
    iconAnchor: [17, 17]
  });
  L.marker([34.7058, 135.4891], { icon: hotelIcon }).addTo(map).bindPopup("<b>ホテル</b><br>宿泊先候補");
});
</script>
