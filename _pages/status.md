---
layout: single
title: "プロフィール"
permalink: /status/
author_profile: true
---
<div class="rpg-party-container">
  <div class="board-header-title">
    <span><i class="fas fa-users" style="color: #ffcc00;"></i> 冒険者パーティ ステータス <i class="fas fa-users" style="color: #ffcc00;"></i></span>
  </div>

  <!--ここから2カラム用の枠で囲む -->
  <div class="rpg-party-grid">

<div class="rpg-status-card">
  <div class="rpg-header">
    <h3>ぽぽのステータス</h3>
    <span class="rpg-level">Lv. 永遠の18歳</span>
  </div>
  
  <div class="rpg-body">
    <!-- 基本ステータス -->
    <ul class="rpg-stats-list">
      <li><span>称号 / 職業:</span> <strong>リモートワーカー / ポイ活士</strong></li>
      <li><span>HP:</span> 1200 / 1200</li>
      <li><span>MP（総保有ポイント）:</span> <strong id="total-magic" style="color: #0077cc;">0</strong> Pt</li>
      <li><span>攻撃力 (ATK):</span> 120</li>
      <li><span>防御力 (DEF):</span> 95</li>
      <li><span>素早さ (AGI):</span> 150</li>
    </ul>

    <!-- 6大魔石グリッド (2列×3行 / レトロ風) -->
    <h4 class="rpg-section-title"><i class="fas fa-gem"></i> 6大魔石（保有ポイント収蔵庫）</h4>
    <div class="rpg-stone-grid">
      <!-- 1: Vポイント -->
      <div class="rpg-stone-card" data-points="15000">
        <div class="stone-icon">💎</div>
        <div class="stone-info">
          <div class="stone-name">Vポイント</div>
          <div class="stone-value">15,000 Pt</div>
        </div>
      </div>
      <!-- 2: PayPayポイント -->
      <div class="rpg-stone-card" data-points="8400">
        <div class="stone-icon">🔥</div>
        <div class="stone-info">
          <div class="stone-name">PayPayポイント</div>
          <div class="stone-value">8,400 Pt</div>
        </div>
      </div>
      <!-- 3: Pontaポイント -->
      <div class="rpg-stone-card" data-points="12000">
        <div class="stone-icon">✨</div>
        <div class="stone-info">
          <div class="stone-name">Pontaポイント</div>
          <div class="stone-value">12,000 Pt</div>
        </div>
      </div>
      <!-- 4: 楽天ポイント -->
      <div class="rpg-stone-card" data-points="6500">
        <div class="stone-icon">🌟</div>
        <div class="stone-info">
          <div class="stone-name">楽天ポイント</div>
          <div class="stone-value">100 Pt</div>
        </div>
      </div>
      <!-- 5: dポイント -->
      <div class="rpg-stone-card" data-points="9300">
        <div class="stone-icon">🌀</div>
        <div class="stone-info">
          <div class="stone-name">dポイント</div>
          <div class="stone-value">9,300 Pt</div>
        </div>
      </div>
      <!-- 6: Microsoftポイント -->
      <div class="rpg-stone-card" data-points="5000">
        <div class="stone-icon">🔮</div>
        <div class="stone-info">
          <div class="stone-name">Microsoftポイント（1/10）</div>
          <div class="stone-value">1,000 Pt</div>
        </div>
      </div>
    </div>

    <!-- 装備品セクション -->
    <h4 class="rpg-section-title"><i class="fas fa-shield-alt"></i> 装備品 & アイテム</h4>
    <table class="rpg-equipment-table">
      <tr>
        <th><i class="fas fa-magic"></i> 武器（メインクレカ）</th>
        <td>三井住友ゴールドカード <span>(ATK +50)</span></td>
      </tr>
      <tr>
        <th><i class="fas fa-tshirt"></i> 防具（メインバンク）</th>
        <td>ドコモSMTBネット銀行 <span>(DEF +40 / 疲労軽減)</span></td>
      </tr>
      <tr>
      <tr>
        <th><i class="fas fa-shield-alt"></i> 盾（携帯電話）</th>
        <td>楽天モバイル <span>(DEF +40 / 疲労軽減)</span></td>
      </tr>
      <tr>
        <th><i class="fas fa-ring"></i> 装飾品（サブスク）</th>
        <td>Amazonプライム <span>(LUCK +99 / ポイント倍増)</span></td>
      </tr>
      <tr>
        <th><i class="fas fa-box"></i> 所持品</th>
        <td>世帯主の大葉（家庭菜園） <span>(HP回復・栽培中)</span></td>
      </tr>
      
<!--2人目（パートナー）のカードを丸ごとコピーして追加 -->
    <div class="rpg-status-card">
      <div class="rpg-header" style="background: #2d2340;">
        <h3>冒険者 2号 (相棒)</h3>
        <span class="rpg-level" style="background: #4a90e2;">Lv. 旅の同行者</span>
      </div>
      <div class="rpg-body">
        <!-- 2人目のステータスや装備品を記述 -->
        <ul class="rpg-stats-list">
          <li><span>職業:</span> <strong>トラベラー</strong></li>
          <li><span>HP:</span> 1200 / 1200</li>
          <!-- 略 -->
        </ul>
      </div>
    </div>
　</div> <!-- /.rpg-party-grid -->
</div>

<style>
  /* RPG風ステータスカードのデザイン */
  .rpg-status-card {
    border: 2px solid #333;
    border-radius: 8px;
    background: #fdfbf7;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    margin: 20px 0;
    overflow: hidden;
  }
  .rpg-header {
    background: #333;
    color: #fff;
    padding: 12px 18px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .rpg-header h3 {
    margin: 0;
    font-size: 16px;
    color: #fff;
    border: none;
    padding: 0;
  }
  .rpg-level {
    background: #ff4d4f;
    color: #fff;
    padding: 2px 10px;
    border-radius: 4px;
    font-size: 14px;
    font-weight: bold;
  }
  .rpg-body {
    padding: 20px;
  }
  .rpg-stats-list {
    list-style: none;
    padding: 0;
    margin: 0 0 20px 0;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  .rpg-stats-list li {
    font-size: 14px;
    border-bottom: 1px dashed #ddd;
    padding-bottom: 6px;
    display: flex;
    justify-content: space-between;
  }
  .rpg-stats-list li span {
    color: #666;
  }
  .rpg-section-title {
    font-size: 15px;
    border-bottom: 2px solid #333;
    padding-bottom: 4px;
    margin-top: 20px;
    margin-bottom: 10px;
    color: #333;
  }

  /* 6大魔石グリッド (2列×3行・レトロ風テイスト) */
  .rpg-stone-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
    margin-bottom: 20px;
  }
  .rpg-stone-card {
    background-color: #15152b;
    border: 2px solid #444466;
    color: #fff;
    padding: 8px 10px;
    display: flex;
    align-items: center;
    gap: 10px;
    border-radius: 4px;
    transition: transform 0.1s, border-color 0.1s;
  }
  .rpg-stone-card:hover {
    border-color: #ffcc00;
    transform: translateY(-2px);
  }
  .stone-icon {
    font-size: 1.2rem;
    background: #090913;
    padding: 4px 6px;
    border: 1px solid #33334d;
  }
  .stone-info {
    display: flex;
    flex-direction: column;
  }
  .stone-name {
    font-size: 0.7rem;
    color: #aaaaaa;
  }
  .stone-value {
    font-size: 0.85rem;
    font-weight: bold;
    color: #ffeb3b;
    font-family: 'Courier New', Courier, monospace;
  }

  
  .rpg-equipment-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 14px;
  }
  .rpg-equipment-table th, .rpg-equipment-table td {
    padding: 8px 10px;
    border-bottom: 1px solid #eee;
    text-align: left;
  }
  .rpg-equipment-table th {
    width: 30%;
    color: #555;
    font-weight: normal;
  }
  .rpg-equipment-table td span {
    color: #888;
    font-size: 12px;
    margin-left: 6px;
  }

  /* スマホ対応（1列表示にする） */
  @media screen and (max-width: 600px) {
    .rpg-stats-list {
      grid-template-columns: 1fr;
    }
  }
</style>

<script>
/* 各魔石のポイントを自動合算して「総魔力値」に反映するスクリプト */
document.addEventListener("DOMContentLoaded", function() {
  const cards = document.querySelectorAll('.rpg-stone-card');
  let total = 0;
  cards.forEach(card => {
    const pts = parseInt(card.getAttribute('data-points')) || 0;
    total += pts;
  });
  const totalEl = document.getElementById('total-magic');
  if (totalEl) {
    totalEl.textContent = total.toLocaleString();
  }
});
</script>
