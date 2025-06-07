# BeastStyle ドキュメント

## 1. 概要  
このスタイルガイドは、BeastStyleプロジェクトで使用されるCSSクラスとスタイルの命名規則、デザイン原則を示します。  
開発者が一貫した見た目と操作感を保ち、保守しやすいコードを書くための基準となります。

---

## 2. CSSクラス命名規則  
- BEM（Block Element Modifier）方式を採用  
  - 例: `.modal-bg`, `.modal-content`, `.close-btn`  
- クラス名は役割や意味がわかる説明的な名称にする  
- 複数のクラスを組み合わせてスタイルを作成（例：`.btn.primary`）

---

## 3. モーダルコンポーネント

### 3.1 背景（`.modal-bg`）  
- 画面全体を覆う半透明の黒いオーバーレイ  
- 初期状態は非表示（`opacity: 0; visibility: hidden;`）  
- `.show` クラスで表示・フェードイン

### 3.2 コンテンツ（`.modal-content`）  
- 白背景、角丸（10px）、パディング（20px）  
- テキスト中央揃え  
- 表示時はスケール0.95から1へ拡大アニメーション

### 3.3 アニメーション  
- `.modal-bg.show` で透明度と可視性を切り替え  
- `.modal-bg.show .modal-content` でスケールを変化させる

---

## 4. ボタンコンポーネント

### 4.1 共通スタイル（`.btn`）  
- パディング、ボーダーなし、角丸5px  
- ホバー時に少し暗くなるエフェクト（`filter: brightness(90%)`）  
- フォントは太字で見やすく

### 4.2 ボタンのバリエーション  
- `.primary`: 主要アクション用（青系）  
- `.danger`: 警告・破壊的アクション用（赤系）  
- `.success`: 成功・肯定的アクション用（緑系）  
- `.warning`: 注意喚起用（黄色系）  
- `.info`: 情報提供用（水色系）  
- `.light`: 明るい背景、テキストは黒  
- `.dark`: 暗い背景、テキストは白  
- `.link`: 背景なし、下線テキストリンク風

### 4.3 特殊ボタン（`.magic`）  
- 横方向のグラデーション背景  
- ホバー時に色が変わるアニメーション効果を追加

---

###6. サンプルコード
```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BeastStyle - demo</title>
    <link rel="stylesheet" href="style.css">
    <script src="animation.js" defer></script>
</head>
<body>
    <button class="btn primary">Click Me!</button>
    <button class="btn danger">Click Me!</button>
    <button class="btn warning">Click Me!</button>
    <button class="btn success">Click Me!</button>
    <button class="btn info">Click Me!</button>
    <button class="btn light">Click Me!</button>
    <button class="btn dark">Click Me!</button>
    <button class="btn link">Click Me!</button>
    <button class="btn magic">Click Me!</button>
<hr>
<button class="btn magic open-modal" data-index="0">モーダル1を開く</button>
<button class="btn magic open-modal" data-index="1">モーダル2を開く</button>

<!-- モーダル1 -->
<div class="modal-bg">
    <div class="modal-content">
      <h2>モーダル1</h2>
      <button class="close-btn">閉じる</button>
    </div>
  </div>
  
  <!-- モーダル2 -->
  <div class="modal-bg">
    <div class="modal-content">
      <h2>モーダル2</h2>
      <button class="close-btn">閉じる</button>
    </div>
  </div>
</body>
</html>
```

## 5. 推奨デザインパターン・運用ルール  
- コンポーネント間のスペーシングは均一にし、画面のまとまりを保つ  
- インタラクティブ要素は見た目で区別でき、操作しやすいサイズにする  
- プロジェクト全体で統一されたカラーパレットを使う  
- 新しいコンポーネントやスタイルを追加するときは既存ルールに沿って命名・実装する  
- 複雑なスタイルは複数クラスの組み合わせで対応し、再利用性を高める

---

## 6. まとめ  
このガイドに沿うことで、BeastStyleのUIは統一感があり、メンテナンスしやすいものになります。  
全員がルールを理解し守ることで、チーム開発の効率化とユーザー体験の向上が期待できます。
