---
layout: home
author_profile: true
entries_layout: grid
---

<!-- Minimal Mistakes標準の最新記事一覧がここに自動で表示されます -->

<style>
/* ==========================================
   TOPページ（最新記事一覧）のレトロRPG風カスタマイズ
   ========================================== */

/* メインコンテンツ全体のフォント・色味の調整 */
.archive {
  font-family: 'Courier New', Courier, monospace;
}
   
///* 「Recent Posts」を非表示にして、RPG風のタイトルに書き換える */
//.archive__subtitle {
//  font-size: 0 !important; /* 元の文字を隠す */
//}

//.archive__subtitle::after {
//  content: "📖 冒険の書（最新の投稿）"; 
//  font-size: 1rem !important;
//  color: #ffcc00 !important;
//  font-weight: bold;
//}
   
/* 記事一覧のタイトル（「Recent Posts」など）をRPG風に装飾 */
.archive__subtitle {
  font-size: 1rem !important;
  font-weight: bold;
  color: #ffcc00 !important;
  border-bottom: 2px dashed #444466;
  padding-bottom: 8px;
  margin-bottom: 20px;
  letter-spacing: 1px;
}
.archive__subtitle::before {
  content: "📖 ";
}

/* 各記事のカード（リストアイテム）をRPGのウィンドウ風にする */
.list__item {
  background-color: #15152b !important;
  border: 2px solid #444466 !important;
  border-radius: 4px;
  padding: 15px !important;
  margin-bottom: 15px !important;
  transition: all 0.1s;
}

.list__item:hover {
  border-color: #ffcc00 !important;
  transform: translateY(-2px);
  box-shadow: 4px 4px 0px #000000;
}

/* 記事タイトル */
.archive__item-title {
  font-size: 1.05rem !important;
  font-family: 'Courier New', Courier, monospace;
}

.archive__item-title a {
  color: #00ffcc !important;
  text-decoration: none !important;
}

.archive__item-title a:hover {
  color: #ffcc00 !important;
}

/* 記事の抜粋文（excerpt） */
.archive__item-excerpt {
  font-size: 0.85rem !important;
  color: #d1d5db !important;
  font-family: 'Courier New', Courier, monospace;
}

/* 投稿日時などのメタ情報 */
.page__meta {
  font-size: 0.75rem !important;
  color: #8888aa !important;
  font-family: 'Courier New', Courier, monospace;
}
</style>

<script>
document.addEventListener("DOMContentLoaded", function() {
  // ページ内を走査して "Recent Posts" という文字を探し、RPG風に書き換える
  document.querySelectorAll('*').forEach(function(el) {
    el.childNodes.forEach(function(node) {
      if (node.nodeType === Node.TEXT_NODE && node.nodeValue.includes('Recent Posts')) {
        node.nodeValue = node.nodeValue.replace('Recent Posts', ' 冒険の書（最新の記録）📖');
      }
    });
  });
});
</script>
