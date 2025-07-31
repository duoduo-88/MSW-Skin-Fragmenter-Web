# MSW造型防盜拆解工具 Web v1.0.1

**MSW Skin Fragmenter Web**  
一款開源、易用的圖像分割防盜工具，可將含透明區的 PNG 主圖依指定規則自動切割為多片碎片，有效提升圖片二次拼合與逆向還原的難度。  
支援遮罩分割、自訂碎片數量、尺寸與隨機度、原圖干擾像素等多項進階防護機制，並可即時預覽與一鍵打包下載。

---

## 功能特色

- 支援 PNG 主圖，保留透明度資訊
- 可選擇遮罩圖，自訂分割區域
- 可設定分割張數、方塊尺寸、隨機度，讓分割更不規則
- 支援啟用「干擾像素」混淆後續碎片
- 即時預覽分割效果、可獨立預覽任一碎片
- 所有碎片可批次打包下載
- 全部功能於瀏覽器本地執行，安全無上傳

---

## 遮罩分割邏輯優化說明

- **遮罩現在僅用來決定分割區域，而不會再於每張碎片做 alpha>0 的二次裁切**
- 每個碎片會完整覆蓋遮罩有效範圍，不再因反覆裁切產生過多零碎細塊或破碎邊緣
- 分割流程更直觀、效能提升，碎片分佈更自然，避免異常小塊或過度破碎
- 遮罩只需設計限制範圍，不需擔心碎片被重複多次切割

---

## 操作說明

1. **上傳主圖**  
   - 僅支援 PNG，需含透明區。
2. **（可選）上傳遮罩圖**  
   - 僅完全不透明的遮罩區域會參與分割；可用於限定可分割區域。
3. **設定參數**
   - 拆分張數：可1~10
   - 方塊尺寸、尺寸隨機度：調整碎片形狀及混淆效果
   - 可啟用原圖裁切干擾像素（需兩張以上碎片）
4. **執行拆解**  
   - 預覽與管理所有碎片，可逐一命名、瀏覽、下載
5. **一鍵打包 ZIP 下載所有碎片**

---

## 注意事項

- 本工具**僅於本地瀏覽器執行**，不會將圖檔上傳網路
- 防盜分割無法絕對保證圖片「不可還原」，安全性取決於主圖內容與參數配置  
  參考加密學 Kerckhoffs's Principle：「安全性應建立於輸入的不確定性，而非演算法本身」

---

## 開源授權 (MIT License)

MIT License

Copyright (c) 2025 DuoDuo

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## 聯絡方式

作者：DuoDuo  
Email：duoduobaobao88@gmail.com  

---
