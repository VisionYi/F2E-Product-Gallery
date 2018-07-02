# The F2E Challenge - Product Gallery

- [挑戰說明](https://www.facebook.com/groups/173311386703334/permalink/190069861694153/)
- [線上設計稿](http://bit.ly/2lxMFQC)

## 筆記
### Parcel
- 當多個 HTML 頁面時，需要在各自的 HTML 裡直接引入 css/scss/less, js/jsx 檔案
- 由於 dist 和 .cache 在建置後或開啟 server 時，不會把原先的檔案刪除，需要事先手動刪除
  - 在執行命令前可以先下 `rm -rf dist && rm -rf .cache` 清除原先的檔案
- 當不同的檔案在同個時間下，加載到同一個需要被編譯的檔案時，就會出現 bug
  - 例如: 本專案在觀看 product.html 時，更改 scss 檔案儲存就會 Error

### CSS grid
- 教學指南參考: [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/#prop-grid-area)
- 當父元素為 grid，子元素指定放置的範圍時，使用以下撰寫:
  - `grid-column: x / span n格數;` `grid-row: y / span n格數;`
  - `grid-area: x / y / span n格數 / span n格數;`
  - 單獨使靠齊上下左右的 CSS 屬性為: `align-self` & `justify-self`
  - 當 `grid-template-columns` 指定欄位實際數值的寬度後，不代表全部加總後就是實際 `width`
    - 由於 `width` 沒有真的數值，所以使用 margin 左右等於 auto 時也是會沒效果的
