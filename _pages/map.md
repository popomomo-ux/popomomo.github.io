---
layout: single
title: "行きたい・行った場所マップ"
permalink: /map/
author_profile: true
---


<!-- フィルターグループ1：カテゴリ -->
<div class="filter-section">
  <span class="filter-label">カテゴリ:</span>
  <div class="filter-buttons" id="category-filters">
    <button class="filter-btn category-btn active" data-category="all">すべて</button>
    <button class="filter-btn category-btn" data-category="spot">観光</button>
    <button class="filter-btn category-btn" data-category="cafe">カフェ</button>
    <button class="filter-btn category-btn" data-category="hotel">宿</button>
    <button class="filter-btn category-btn" data-category="gourmet">グルメ</button>
    <button class="filter-btn category-btn" data-category="spa">温泉</button>
    <button class="filter-btn category-btn" data-category="temple">神社・お寺</button>
    <button class="filter-btn category-btn" data-category="festival">お祭り</button>
  </div>
</div>

<!-- フィルターグループ2：ステータス（行きたい / 行った） -->
<div class="filter-section" style="margin-top: 8px;">
  <span class="filter-label">状態:</span>
  <div class="filter-buttons" id="status-filters">
    <button class="filter-btn status-btn active" data-status="all">すべて</button>
    <button class="filter-btn status-btn" data-status="want">行きたい</button>
    <button class="filter-btn status-btn" data-status="visited">行った</button>
  </div>
</div>

<div id="blog-map"></div>

<!-- Leaflet CSS & JS の読み込み -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<style>
  /* フィルターのレイアウト */
  .filter-section {
    display: flex;
    align-items: center;
    gap: 10px;
    flex-wrap: wrap;
    margin-bottom: 8px;
  }
  .filter-label {
    font-weight: bold;
    font-size: 13px;
    color: #555;
    min-width: 60px;
  }
  .filter-buttons {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }
  .filter-btn {
    padding: 5px 12px;
    border: 1px solid #d9d9d9;
    background: #fff;
    border-radius: 16px;
    cursor: pointer;
    font-size: 13px;
    transition: all 0.2s;
  }
  .filter-btn:hover {
    border-color: #1890ff;
    color: #1890ff;
  }
  .filter-btn.active {
    background: #1890ff;
    color: #fff;
    border-color: #1890ff;
  }

  /* 地図のスタイル */
  #blog-map {
    width: 100%;
    height: 600px;
    border-radius: 8px;
    margin-top: 15px;
    margin-bottom: 20px;
    z-index: 1;
  }
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

  // --- アイコンを自動生成する関数 ---
  // ステータスで色（行きたい=赤, 行った=緑）、カテゴリでアイコンの形を決める
  function createPinIcon(category, status) {
    const color = (status === 'want') ? '#ff4d4f' : '#52c41a'; // 行きたい: 赤, 行った: 緑

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
  //#595959 （ダークグレー ※あまり目立たせたくない一般的なピンに）****
    
    let iconClass = 'fas fa-map-marker-alt';
    if (category === 'spot') iconClass = 'fas fa-camera';
    else if (category === 'cafe') iconClass = 'fas fa-coffee';
    else if (category === 'hotel') iconClass = 'fas fa-bed';
    else if (category === 'gourmet') iconClass = 'fas fa-utensils';
    else if (category === 'spa') iconClass = 'fas fa-hot-tub';
    else if (category === 'temple') iconClass = 'fas fa-torii-gate';
    else if (category === 'festival') iconClass = 'fas fa-drum';

    return L.divIcon({
      className: 'custom-pin',
      html: `<div class="pin-circle" style="background-color: ${color};"><i class="${iconClass}"></i></div>`,
      iconSize: [34, 34],
      iconAnchor: [17, 17]
    });
  }

  //////////////////////////////// --- スポットデータ一覧 --- ////////////////////////////////
  
  const locations = [
    /////// 観光地（spot）///////
    { 
      lat: 34.7024, lng: 135.4959, 
      category: 'spot', status: 'want', 
      popup: '<b>大阪駅</b><br><span style="color:#ff4d4f;">【行きたい・観光】</span>' 
    },
    /////// カフェ（cafe）///////
    { 
      lat: 34.7026, lng: 135.4947, 
      category: 'cafe', status: 'want', 
      popup: '<b>おしゃれカフェ</b><br><span style="color:#ff4d4f;">【行きたい・カフェ】</span>' 
    },
    /////// 宿（hotel）///////
    { 
      lat: 34.7058, lng: 135.4891, 
      category: 'hotel', status: 'visited', 
      popup: '<b>宿泊したホテル</b><br><span style="color:#52c41a;">【行った・ホテル】</span>' 
    }
    /////// グルメ（gourmet）///////
    // { 
    //   lat: 34.7058, lng: 135.4891, 
    //   category: 'gourmet', status: 'visited', 
    //   popup: '<b>おすすめランチ</b><br><span style="color:#52c41a;">【行った・ランチ】</span>' 
    // }

    /////// 温泉（spa）///////
    // { 
    //   lat: 34.7058, lng: 135.4891, 
    //   category: 'spa', status: 'visited', 
    //   popup: '<b>おすすめ温泉</b><br><span style="color:#52c41a;">【行った・温泉】</span>' 
    // }
    
   /////// 神社・お寺（temple）///////
    // { 
    //   lat: 34.7058, lng: 135.4891, 
    //   category: 'temple', status: 'visited', 
    //   popup: '<b>おすすめ神社</b><br><span style="color:#52c41a;">【行った・神社】</span>' 
    // }
    
   /////// お祭り（festival）///////
    // { 
    //   lat: 34.7058, lng: 135.4891, 
    //   category: 'festival', status: 'visited', 
    //   popup: '<b>おすすめお祭り</b><br><span style="color:#52c41a;">【行った・お祭り】</span>' 
    // }
    
  ];

  let currentCategory = 'all';
  let currentStatus = 'all';
  let currentMarkers = [];

  // マップのピンを更新する関数（AND条件でフィルタリング）
  function updateMarkers() {
    currentMarkers.forEach(marker => map.removeLayer(marker));
    currentMarkers = [];

    locations.forEach(loc => {
      const matchCategory = (currentCategory === 'all' || loc.category === currentCategory);
      const matchStatus = (currentStatus === 'all' || loc.status === currentStatus);

      // 両方の条件に一致する場合のみピンを表示 (AND条件)
      if (matchCategory && matchStatus) {
        const icon = createPinIcon(loc.category, loc.status);
        const marker = L.marker([loc.lat, loc.lng], { icon: icon })
          .addTo(map)
          .bindPopup(loc.popup);
        currentMarkers.push(marker);
      }
    });
  }

  // 初期表示
  updateMarkers();

  // カテゴリボタンのイベント
  document.querySelectorAll('.category-btn').forEach(button => {
    button.addEventListener('click', (e) => {
      document.querySelectorAll('.category-btn').forEach(b => b.classList.remove('active'));
      e.target.classList.add('active');
      currentCategory = e.target.getAttribute('data-category');
      updateMarkers();
    });
  });

  // ステータスボタンのイベント
  document.querySelectorAll('.status-btn').forEach(button => {
    button.addEventListener('click', (e) => {
      document.querySelectorAll('.status-btn').forEach(b => b.classList.remove('active'));
      e.target.classList.add('active');
      currentStatus = e.target.getAttribute('data-status');
      updateMarkers();
    });
  });
});
</script>
