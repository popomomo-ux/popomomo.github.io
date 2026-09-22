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
  /* 地図を画面いっぱいに広く、見やすく表示するスタイル */
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


<script>
document.addEventListener("DOMContentLoaded", () => {
  // 1. 初期表示の中心を「大阪駅」に設定（ズーム倍率: 14）
  const map = L.map('blog-map').setView([34.7024, 135.4959], 14);

  // 2. 地図のタイルデザインを読み込み
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
  }).addTo(map);

  // 3. マーカー（ピン）の追加
  // 青：#0366d6
  // 水色：#40a9ff
  // 赤：#ff4d4f
  // 緑：#52c41a
  // オレンジ：#fa8c16
  
  // 大阪駅
  L.circleMarker([34.7024, 135.4959], {
    color: '#ff4d4f',      // 枠線の色
    fillColor: '#ff4d4f',  // 塗りつぶしの色
    fillOpacity: 0.8,      // 不透明度
    radius: 10             // 大きさ
  }).addTo(map).bindPopup("<b>大阪駅</b><br>ここが中心地点です");

  // グランフロント大阪の例
  L.circleMarker([34.7026, 135.4947], {
    color: '#1890ff',
    fillColor: '#1890ff',
    fillOpacity: 0.8,
    radius: 10
  }).addTo(map).bindPopup("<b>グランフロント大阪</b><br>ショッピングやカフェ");

  // 梅田スカイビルの例
  L.circleMarker([34.7058, 135.4891], {
    color: '#52c41a',
    fillColor: '#52c41a',
    fillOpacity: 0.8,
    radius: 10
  }).addTo(map).bindPopup("<b>梅田スカイビル</b><br>空中庭園展望台");
});
</script>
