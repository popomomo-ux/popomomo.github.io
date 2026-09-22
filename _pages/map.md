---
layout: single
title: "行ってよかった場所と行きたい場所マップ"
permalink: /map/
author_profile: true
---
<!-- フィルター用のボタンエリア -->
<div id="map-filters">
  <button class="filter-btn active" data-category="all">すべて</button>
  <button class="filter-btn" data-category="spot">観光</button>
  <button class="filter-btn" data-category="cafe">カフェ</button>
  <button class="filter-btn" data-category="hotel">ホテル</button>
</div>

<div id="blog-map"></div>
<!-- Leaflet CSS & JS の読み込み -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<style>
  <!-- フィルター用のボタンエリア -->
  <div id="map-filters">
  <button class="filter-btn active" data-category="all">すべて</button>
  <button class="filter-btn" data-category="spot">観光</button>
  <button class="filter-btn" data-category="cafe">カフェ</button>
  <button class="filter-btn" data-category="hotel">ホテル</button>
  </div>
  
  /* 地図のスタイル */
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

  //アイコン一覧
  //頻出
  //カメラ: fas fa-camera
  //カフェ・コーヒー: fas fa-coffee
  //ご飯・レストラン: fas fa-utensils
  //ホテル・ベッド: fas fa-bed
  //ショッピング: fas fa-shopping-bag
  //温泉・お風呂: fas fa-hot-tub （または fas fa-bath）

  //交通系
  //電車、駅：fas fa-train
  //飛行機、空港：fas fa-plane
  //車、ドライブスポット、駐車場：fas fa-car
  //バス停、高速バス乗り場：fas fa-bus
  //船、フェリー乗り場、港：fas fa-ship 
  //グルメ・お酒・スイーツ系
  //ビール、居酒屋、パブ：fas fa-beer
  //バー、おしゃれなカクテルが飲める店：fas fa-cocktail
  //アイス、ジェラート、スイーツ店：fas fa-ice-cream
  //その他・お出かけ系
  //チケット売り場、美術館・テーマパークの入場口：fas fa-ticket-alt
  //一般的なお店、お土産屋さん、商店街：fas fa-store
  //大きな商業施設、ビル、デパート：fas fa-building

  //カラー一覧
  // 赤・ピンク系（お気に入り・重要スポット）
  //#ff4d4f （鮮やかな赤 ※一番目立つので、最重要スポットやお気に入りに最適）
  // オレンジ・黄色系（グルメ・カフェ・ポップ）
  //#fa8c16 （明るいオレンジ ※カフェや飲食店、スイーツ店にぴったり）
  // 緑系（自然・公園・リラックス）
  //#52c41a （爽やかな黄緑 ※公園や植物園、アウトドアスポットに）
  // 青・水色系（ホテル・交通・クール）
  //#1890ff （すっきりした青 ※ホテルや商業施設、ビジネス系に）
  // 紫・その他（ショップ・特別）
  //#722ed1 （深みのある紫 ※おしゃれな雑貨店や特別なスポットに）
  // モノトーン系（通常ピン・控えめなスポット）
  //#595959 （ダークグレー ※あまり目立たせたくない一般的なピンに）

  
 // アイコンの定義
  const spotIcon = L.divIcon({
    className: 'custom-pin',
    html: '<div class="pin-circle" style="background-color: #ff4d4f;"><i class="fas fa-camera"></i></div>',
    iconSize: [34, 34],
    iconAnchor: [17, 17]
  });

  const cafeIcon = L.divIcon({
    className: 'custom-pin',
    html: '<div class="pin-circle" style="background-color: #fa8c16;"><i class="fas fa-coffee"></i></div>',
    iconSize: [34, 34],
    iconAnchor: [17, 17]
  });

  const hotelIcon = L.divIcon({
    className: 'custom-pin',
    html: '<div class="pin-circle" style="background-color: #1890ff;"><i class="fas fa-bed"></i></div>',
    iconSize: [34, 34],
    iconAnchor: [17, 17]
  });

  // すべてのスポットデータ（ここに場所を追加していきます）
  const locations = [
    { lat: 34.7024, lng: 135.4959, category: 'spot', icon: spotIcon, popup: '<b>大阪駅</b><br>観光スポット' },
    { lat: 34.7026, lng: 135.4947, category: 'cafe', icon: cafeIcon, popup: '<b>カフェ</b><br>美味しいコーヒーのお店' },
    { lat: 34.7058, lng: 135.4891, category: 'hotel', icon: hotelIcon, popup: '<b>ホテル</b><br>宿泊先候補' }
  ];

  let currentMarkers = [];

  // マップにピンを描画する関数
  function updateMarkers(category) {
    // 既存のピンを削除
    currentMarkers.forEach(marker => map.removeLayer(marker));
    currentMarkers = [];

    // 条件に合うピンを追加
    locations.forEach(loc => {
      if (category === 'all' || loc.category === category) {
        const marker = L.marker([loc.lat, loc.lng], { icon: loc.icon })
          .addTo(map)
          .bindPopup(loc.popup);
        currentMarkers.push(marker);
      }
    });
  }

  // 初期表示（すべて表示）
  updateMarkers('all');

  // ボタンのクリックイベント設定
  document.querySelectorAll('.filter-btn').forEach(button => {
    button.addEventListener('click', (e) => {
      document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
      e.target.classList.add('active');
      updateMarkers(e.target.getAttribute('data-category'));
    });
  });
});
</script>
