---
layout: single
title: "クエストボード（バケットリスト）"
permalink: /bucket-list/
author_profile: true
---

<div class="rpg-quest-board-container">
  <!-- ボードタイトル -->
  <div class="board-header-title">
    <span>📜 冒険者のクエストボード（バケットリスト） 📜</span>
  </div>

  <!-- 1. 今年のクエスト -->
  <div class="quest-section">
    <h3 class="section-level-title">🔥 今年のクエスト</h3>
    <div class="quest-columns">
      <div class="quest-column active-quests">
        <h4>[ 受注クエスト (進行中) ]</h4>
        <ul>
          <li><span class="quest-icon">⚔️</span> 新スキルの習得と実践</li>
          <li><span class="quest-icon">⚔️</span> 年間目標・ライフプランの推敲</li>
        </ul>
      </div>
      <div class="quest-column completed-quests">
        <h4>[ 完了クエスト (達成済) ]</h4>
        <ul>
          <li><span class="quest-icon">✨</span> <del>ブログのRPG風カスタマイズ</del></li>
        </ul>
      </div>
    </div>
  </div>

  <!-- 2. Lv.45クエスト -->
  <div class="quest-section">
    <h3 class="section-level-title">🛡️ Lv.45 クエスト</h3>
    <div class="quest-columns">
      <div class="quest-column active-quests">
        <h4>[ 受注クエスト (進行中) ]</h4>
        <ul>
          <li><span class="quest-icon">⚔️</span> 体力維持のための運動習慣化</li>
        </ul>
      </div>
      <div class="quest-column completed-quests">
        <h4>[ 完了クエスト (達成済) ]</h4>
        <ul>
          <li><span class="quest-icon">✨</span> <del>資産管理ルートの最適化</del></li>
        </ul>
      </div>
    </div>
  </div>

  <!-- 3. Lv.50クエスト -->
  <div class="quest-section">
    <h3 class="section-level-title">💎 Lv.50 クエスト</h3>
    <div class="quest-columns">
      <div class="quest-column active-quests">
        <h4>[ 受注クエスト (進行中) ]</h4>
        <ul>
          <li><span class="quest-icon">⚔️</span> 海外ロングステイ・旅行計画の立案</li>
        </ul>
      </div>
      <div class="quest-column completed-quests">
        <h4>[ 完了クエスト (達成済) ]</h4>
        <ul>
          <li><span class="quest-icon">✨</span> <del>ここに完了したクエストが入ります</del></li>
        </ul>
      </div>
    </div>
  </div>

  <!-- 4. Lv.60クエスト -->
  <div class="quest-section">
    <h3 class="section-level-title">🔮 Lv.60 クエスト</h3>
    <div class="quest-columns">
      <div class="quest-column active-quests">
        <h4>[ 受注クエスト (進行中) ]</h4>
        <ul>
          <li><span class="quest-icon">⚔️</span> 理想の書斎（リモートワーク環境）の完成</li>
        </ul>
      </div>
      <div class="quest-column completed-quests">
        <h4>[ 完了クエスト (達成済) ]</h4>
        <ul>
          <li><span class="quest-icon">✨</span> <del>ここに完了したクエストが入ります</del></li>
        </ul>
      </div>
    </div>
  </div>

  <!-- 5. Lv.70クエスト -->
  <div class="quest-section">
    <h3 class="section-level-title">⭐ Lv.70 クエスト</h3>
    <div class="quest-columns">
      <div class="quest-column active-quests">
        <h4>[ 受注クエスト (進行中) ]</h4>
        <ul>
          <li><span class="quest-icon">⚔️</span> 国内外の温泉・名所制覇の旅</li>
        </ul>
      </div>
      <div class="quest-column completed-quests">
        <h4>[ 完了クエスト (達成済) ]</h4>
        <ul>
          <li><span class="quest-icon">✨</span> <del>ここに完了したクエストが入ります</del></li>
        </ul>
      </div>
    </div>
  </div>

  <!-- 6. Lv.80クエスト -->
  <div class="quest-section">
    <h3 class="section-level-title">👑 Lv.80 クエスト</h3>
    <div class="quest-columns">
      <div class="quest-column active-quests">
        <h4>[ 受注クエスト (進行中) ]</h4>
        <ul>
          <li><span class="quest-icon">⚔️</span> 悠々自適のスローライフ基盤づくり</li>
        </ul>
      </div>
      <div class="quest-column completed-quests">
        <h4>[ 完了クエスト (達成済) ]</h4>
        <ul>
          <li><span class="quest-icon">✨</span> <del>ここに完了したクエストが入ります</del></li>
        </ul>
      </div>
    </div>
  </div>
</div>

<style>
/* レトロRPG風クエストボードのスタイル */
.rpg-quest-board-container {
  font-family: 'Courier New', Courier, monospace;
  color: #f3f3f3;
  background-color: #0d0d1a;
  border: 4px solid #ffffff;
  box-shadow: 6px 6px 0px #000000;
  padding: 20px;
  margin: 20px 0;
  image-rendering: pixelated;
}

.board-header-title {
  text-align: center;
  font-size: 1.1rem;
  font-weight: bold;
  color: #ffcc00;
  border-bottom: 2px dashed #444466;
  padding-bottom: 15px;
  margin-bottom: 20px;
  letter-spacing: 1px;
}

.quest-section {
  background-color: #15152b;
  border: 2px solid #444466;
  margin-bottom: 20px;
  padding: 15px;
  border-radius: 4px;
}

.section-level-title {
  font-size: 1rem;
  color: #00ffcc;
  margin-top: 0;
  margin-bottom: 12px;
  border-bottom: 1px solid #33334d;
  padding-bottom: 6px;
}

.quest-columns {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
}

.quest-column {
  background-color: #0d0d1a;
  border: 1px solid #33334d;
  padding: 10px;
  border-radius: 4px;
}

.quest-column h4 {
  font-size: 0.8rem;
  margin-top: 0;
  margin-bottom: 10px;
  text-align: center;
  letter-spacing: 1px;
}

.active-quests h4 {
  color: #ff8080; /* 受注中：赤系 */
}

.completed-quests h4 {
  color: #80ff80; /* 完了：緑系 */
}

.quest-column ul {
  list-style: none;
  padding: 0;
  margin: 0;
  font-size: 0.85rem;
}

.quest-column li {
  padding: 6px 0;
  border-bottom: 1px dashed #22233b;
  display: flex;
  align-items: center;
  gap: 8px;
}

.quest-column li:last-child {
  border-bottom: none;
}

.completed-quests li {
  color: #8888aa;
}

/* スマホ対応：画面幅が狭いときは1カラムに切り替わる */
@media screen and (max-width: 768px) {
  .quest-columns {
    grid-template-columns: 1fr;
  }
}
</style>
