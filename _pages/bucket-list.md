---
layout: single
title: "クエストボード（バケットリスト）"
permalink: /bucket-list/
author_profile: true
---

<div class="rpg-party-container">
  <!-- クエストボードのタイトルとカウンターを並べる -->
  <div class="board-header-title" style="display: flex; justify-content: space-between; align-items: center;">
    <span><i class="fas fa-scroll" style="color: #ffcc00;"></i> 討伐クエストボード</span>
    <!-- 常時表示するカウンター（JavaScriptで自動入力されます） -->
    <span style="font-size: 20px; color: #00ffcc;">
      討伐済: <strong id="completed-count" style="color: #ffcc00; font-size: 20px;">0</strong> 個
    </span>
  </div>

  <!-- タブ切り替えボタン -->
  <div class="rpg-tabs">
    <button class="rpg-tab-btn active" onclick="switchTab(event, 'tab-board')">📜 クエストボード (進行中)</button>
    <button class="rpg-tab-btn" onclick="switchTab(event, 'tab-completed')">🏆 完了クエスト</button>
  </div>

  <!-- ========================================== -->
  <!-- タブ1：クエストボード (進行中・レベル別) -->
  <!-- ========================================== -->
  <div id="tab-board" class="rpg-tab-content active-content">
    
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
          <h4>[ 完了済ピックアップ ]</h4>
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
          <h4>[ 完了済ピックアップ ]</h4>
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
          <h4>[ 完了済ピックアップ ]</h4>
          <ul>
            <li><span class="quest-icon">✨</span> <del>（なし）</del></li>
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
          <h4>[ 完了済ピックアップ ]</h4>
          <ul>
            <li><span class="quest-icon">✨</span> <del>（なし）</del></li>
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
          <h4>[ 完了済ピックアップ ]</h4>
          <ul>
            <li><span class="quest-icon">✨</span> <del>（なし）</del></li>
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
          <h4>[ 完了済ピックアップ ]</h4>
          <ul>
            <li><span class="quest-icon">✨</span> <del>（なし）</del></li>
          </ul>
        </div>
      </div>
    </div>

  </div> <!-- /tab-board -->


  <!-- ========================================== -->
  <!-- タブ2：完了クエスト一覧（ここを自動集計します） -->
  <!-- ========================================== -->
  <div id="tab-completed" class="rpg-tab-content">
    
    <div class="completed-section">
      <h3 class="completed-category-title"><i class="fas fa-medal" style="color: #ffcc00;"></i> 今年・直近の達成クエスト</h3>
      <ul class="completed-list">
        <li>
          <span class="clear-badge">達成</span>
          <span class="quest-text">ブログのRPG風カスタマイズ＆デザイン構築</span>
          <span class="quest-date">2026.08</span>
        </li>
        <li>
          <span class="clear-badge">達成</span>
          <span class="quest-text">資産管理・ポイ活ルートの最適化</span>
          <span class="quest-date">2026.07</span>
        </li>
      </ul>
    </div>

    <div class="completed-section">
      <h3 class="completed-category-title"><i class="fas fa-shield-alt" style="color: #00ffcc;"></i> Lv.45 ~ Lv.50 帯の達成クエスト</h3>
      <ul class="completed-list">
        <li>
          <span class="clear-badge">達成</span>
          <span class="quest-text">リモートワーク環境のエルゴノミクス化（チェア・デスク導入）</span>
          <span class="quest-date">達成済</span>
        </li>
        <li>
          <span class="clear-badge">達成</span>
          <span class="quest-text">ベランダ菜園でのミョウガ栽培・育成体制の確立</span>
          <span class="quest-date">達成済</span>
        </li>
      </ul>
    </div>

    <div class="completed-section">
      <h3 class="completed-category-title"><i class="fas fa-compass" style="color: #ff8080;"></i> Lv.60 以上の達成クエスト</h3>
      <ul class="completed-list">
        <li>
          <span class="clear-badge">達成</span>
          <span class="quest-text">国内外の温泉・名所スタンプラリーの基盤構築</span>
          <span class="quest-date">達成済</span>
        </li>
      </ul>
    </div>

  </div> <!-- /tab-completed -->

</div>


<style>
/* レトロRPG風クエストボード＆タブのスタイル */
.rpg-party-container {
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
  padding-bottom: 12px;
  margin-bottom: 15px;
  letter-spacing: 1px;
}

/* タブボタンのデザイン */
.rpg-tabs {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
  border-bottom: 2px solid #444466;
  padding-bottom: 12px;
}

.rpg-tab-btn {
  background-color: #15152b;
  border: 2px solid #444466;
  color: #aaaaaa;
  padding: 8px 14px;
  font-family: 'Courier New', Courier, monospace;
  font-size: 0.85rem;
  cursor: pointer;
  border-radius: 4px;
  transition: all 0.1s;
}

.rpg-tab-btn:hover {
  border-color: #ffcc00;
  color: #fff;
}

.rpg-tab-btn.active {
  background-color: #ffcc00;
  color: #0d0d1a;
  border-color: #ffcc00;
  font-weight: bold;
}

/* タブコンテンツの表示切替 */
.rpg-tab-content {
  display: none;
}

.rpg-tab-content.active-content {
  display: block;
}

/* クエストセクション等 */
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
  color: #ff8080;
}

.completed-quests h4 {
  color: #80ff80;
}

.quest-column ul, .completed-list {
  list-style: none;
  padding: 0;
  margin: 0;
  font-size: 0.85rem;
}

.quest-column li, .completed-list li {
  padding: 6px 0;
  border-bottom: 1px dashed #22233b;
  display: flex;
  align-items: center;
  gap: 8px;
}

.quest-column li:last-child, .completed-list li:last-child {
  border-bottom: none;
}

.completed-quests li {
  color: #8888aa;
}

/* 殿堂入り一覧のスタイル */
.completed-section {
  background-color: #15152b;
  border: 2px solid #444466;
  margin-bottom: 15px;
  padding: 15px;
  border-radius: 4px;
}

.completed-category-title {
  font-size: 0.95rem;
  color: #00ffcc;
  margin-top: 0;
  margin-bottom: 10px;
  border-bottom: 1px solid #33334d;
  padding-bottom: 6px;
}

.clear-badge {
  background-color: #1a4d2e;
  color: #4ef090;
  border: 1px solid #2e8b57;
  padding: 2px 6px;
  font-size: 0.75rem;
  font-weight: bold;
  border-radius: 2px;
  flex-shrink: 0;
}

.quest-text {
  flex-grow: 1;
  color: #d1d5db;
}

.quest-date {
  font-size: 0.75rem;
  color: #8888aa;
  flex-shrink: 0;
}

/* スマホ対応 */
@media screen and (max-width: 768px) {
  .quest-columns {
    grid-template-columns: 1fr;
  }
  .rpg-tabs {
    flex-direction: column;
  }
}
</style>

<script>
/* タブ切り替え用JavaScript関数 */
function switchTab(evt, tabId) {
  const contents = document.querySelectorAll('.rpg-tab-content');
  contents.forEach(content => {
    content.classList.remove('active-content');
  });

  const buttons = document.querySelectorAll('.rpg-tab-btn');
  buttons.forEach(button => {
    button.classList.remove('active');
  });

  document.getElementById(tabId).classList.add('active-content');
  evt.currentTarget.classList.add('active');
}

/* ページ読み込み時に完了クエスト数を自動で数えて表示する処理 */
document.addEventListener("DOMContentLoaded", function() {
  // タブ2にある「.completed-list」の中の「li」の数をすべて数える
  const completedItems = document.querySelectorAll('.completed-list li');
  const countEl = document.getElementById('completed-count');
  
  if (countEl) {
    countEl.textContent = completedItems.length;
  }
});
</script>
