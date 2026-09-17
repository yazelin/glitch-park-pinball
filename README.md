# 格莉奇遊樂園・霓虹鋼珠台

一款可獨立遊玩的格莉奇鋼珠台。鋼珠具有重力、牆面反彈、角色碰撞柱與左右擋板碰撞；每局三顆球，分數和最高分保存在瀏覽器裡。撞擊角色時會出現火花、球尾、霓虹脈衝、機台震動與分層音效，並有低機率短暫改變球的大小或觸發最多兩球的 MULTIBALL。

## 操作

- 手機：左、右擋板按鈕分別位於機台兩側；按住右下角發球器會自己蓄力（約 1.2 秒滿），放開後發射；往下拉可以更快蓄滿。
- 桌機：滑鼠按住右下角發球器同樣蓄力（拖曳也可以）；方向鍵左右或 `A`、`D` 控制擋板。空白鍵按住時蓄力，放開後發射。
- 右上角聲音開關會同時控制主題曲與遊戲音效。

## 本機執行

```bash
python3 -m http.server 4173
```

瀏覽 `http://127.0.0.1:4173/`。角色碰撞柱共用單一頭像 Atlas（24 KB，跟頁面同站載），不載入七張獨立圖片；只有主題曲走 CDN（見下）。

日後嵌入 Larch 時，頁面會顯示「離開」按鈕，並把遊樂園主題曲交由外層統一播放。

主題曲改從 jsDelivr 載（五款共用同一個網址，瀏覽器快取共用）：`https://cdn.jsdelivr.net/gh/yazelin/glitch-park-claw@main/assets/audio/glitch-park-theme.mp3`。
Pages 直連 700 KB 要 11 秒、jsDelivr 1 秒。改檔要 purge：`https://purge.jsdelivr.net/gh/yazelin/glitch-park-claw@main/assets/audio/glitch-park-theme.mp3`。
