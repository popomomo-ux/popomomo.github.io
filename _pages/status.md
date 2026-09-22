---
layout: single
title: "プロフィール"
permalink: /status/
author_profile: true
---


<div class="rpg-status-card">
  <div class="rpg-header">
    <h3>冒険者のステータス</h3>
    <span class="rpg-level">Lv. 18</span>
  </div>
  
  <div class="rpg-body">
    <!-- 基本ステータス -->
    <ul class="rpg-stats-list">
      <li><span>称号 / 職業:</span> <strong>リモートワーカー / ポイ活士</strong></li>
      <li><span>HP:</span> 1200 / 1200</li>
      <li><span>MP:</span> 450 / 450</li>
      <li><span>攻撃力 (ATK):</span> 120</li>
      <li><span>防御力 (DEF):</span> 95</li>
      <li><span>素早さ (AGI):</span> 150</li>
    </ul>

    <!-- 装備品セクション -->
    <h4 class="rpg-section-title"><i class="fas fa-shield-alt"></i> 装備品 & アイテム</h4>
    <table class="rpg-equipment-table">
      <tr>
        <th><i class="fas fa-magic"></i> 武器</th>
        <td>メカニカルキーボード <span>(ATK +50)</span></td>
      </tr>
      <tr>
        <th><i class="fas fa-tshirt"></i> 防具</th>
        <td>エルゴノミックメッシュチェア <span>(DEF +40 / 疲労軽減)</span></td>
      </tr>
      <tr>
        <th><i class="fas fa-ring"></i> 装飾品</th>
        <td>三井住友ゴールドカード <span>(LUCK +99 / ポイント倍増)</span></td>
      </tr>
      <tr>
        <th><i class="fas fa-box"></i> 所持品</th>
        <td>ベランダのミョウガ <span>(HP回復・栽培中)</span></td>
      </tr>
    </table>
  </div>
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
