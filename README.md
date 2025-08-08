# 🌐 MSW造型防盜拆解工具 Web | MSW Skin Fragmenter Web

一款開源、易用的圖像分割防盜工具，可將含透明區的 PNG 主圖依指定規則自動切割為多片碎片，顯著提升圖片二次拼合與逆向還原的難度。  
An open-source and easy-to-use anti-theft image fragmenter that automatically splits a PNG image with transparency into multiple fragments based on specified rules, significantly increasing the difficulty of reconstruction and reverse engineering.

支援遮罩分割、自訂碎片數量、尺寸與隨機度、原圖干擾像素等多項進階防護機制，並提供即時預覽與一鍵打包下載功能。  
Supports mask-based splitting, customizable fragment count, size and randomness, original image interference pixels, and more advanced protection mechanisms, with real-time preview and one-click ZIP export.

---

## 🔹 基主要功能 | Main Features

- 支援 PNG 主圖，完整保留透明度資訊  
  Supports PNG main image with full alpha transparency
- 可選擇遮罩圖，自訂分割區域  
  Optional mask image to define custom split areas
- 分割張數、方塊尺寸、隨機度皆可調整，分割效果更不規則  
  Adjustable fragment count, block size, and randomness for irregular results
- 支援啟用「干擾像素」，有效混淆後續碎片  
  Interference pixels option to confuse reconstruction attempts
- 即時預覽分割結果，可獨立檢視任一碎片  
  Real-time split preview with individual fragment viewing
- 所有碎片可批次打包為 ZIP 下載  
  Batch ZIP export of all fragments
- 全功能於本地瀏覽器執行，安全無檔案上傳  
  Fully runs in the local browser with no file uploads

---

## 🖼 遮罩分割邏輯說明 | Mask Splitting Logic

- **遮罩僅用於決定分割區域，不再對每個碎片進行 alpha>0 的二次裁切**  
  Mask is only used to define the split area, without additional alpha>0 trimming on each fragment
- 每個碎片皆可完整覆蓋遮罩有效範圍，避免反覆裁切產生零碎邊緣  
  Each fragment can fully cover the valid mask area to avoid fragmented edges from repeated cropping
- 分割流程更直觀、效能更高，碎片分布自然，降低異常小塊或過度破碎情況  
  More intuitive and efficient splitting process with natural fragment distribution
- 遮罩只需設計分割範圍，無須擔心碎片被多次裁切  
  Mask only needs to define the split region without worrying about over-trimming

---

## 📖 基本操作說明 | Basic Usage

1. **上傳主圖 / Upload Main Image**  
   僅支援 PNG，且需包含透明區。  
   PNG format required, must include transparency.

2. **（可選）上傳遮罩圖 / (Optional) Upload Mask**  
   只有完全不透明的遮罩區域會被納入分割，可用於限制分割範圍。  
   Only fully opaque mask areas will be included for splitting.

3. **設定參數 / Configure Parameters**  
   - 拆分張數 / Fragment count: 1~10  
   - 方塊尺寸與尺寸隨機度 / Block size & randomness  
   - 可啟用原圖裁切干擾像素（僅限兩片以上時）  
     Enable interference pixels (only when more than 2 fragments)

4. **執行拆解 / Run Splitting**  
   即時預覽及管理所有碎片，可逐一命名、瀏覽、下載  
   Real-time preview, naming, browsing, and download for all fragments

5. **一鍵打包 ZIP 下載所有碎片 / One-Click ZIP Download**  

6. **手動放入MSW提供的原始PSD檔 / Manually insert into the provided PSD template**

---

## ⚠ 注意事項 | Notes

**中文**  
干擾像素與重疊像素功能非常重要，請盡可能優先使用。  
不要為了拆更多層碎片而犧牲這些功能的效果。  
如果缺乏干擾像素，現代的圖像偵測 AI 可以輕鬆還原碎片，降低防盜效果。  

**English**  
The functions of interference pixels and overlapping pixels are very important and should be prioritized whenever possible.  
Do not sacrifice these features just to split the image into more fragments.  
Without interference pixels, modern image detection AI can easily restore the fragments, reducing anti-theft effectiveness.  

**한국어**  
간섭 픽셀과 중첩 픽셀 기능은 매우 중요하므로 가능한 한 우선적으로 사용해야 합니다.  
더 많은 조각으로 나누기 위해 이 기능들을 희생하지 마세요.  
간섭 픽셀이 부족하면 최신 이미지 감지 AI가 쉽게 조각을 복원하여 방지 효과가 떨어질 수 있습니다.  

---

- 本工具**僅於本地瀏覽器執行**，不會將圖片檔案上傳至網路  
  This tool runs entirely in the local browser and does not upload any files online
- 防盜分割無法絕對保證圖片「不可還原」，安全性取決於主圖內容及參數配置  
  Anti-theft splitting cannot fully guarantee irreversibility; effectiveness depends on content and settings
- 參考密碼學 Kerckhoffs's Principle：「安全性應建立於輸入的不確定性，而非演算法本身」  
  Based on Kerckhoffs's Principle: "Security should depend on the uncertainty of the input, not the secrecy of the algorithm"

---

## 📜 授權 | License

**中文說明**  
本專案採用 **MIT License**，使用者需自負風險，作者不承擔任何法律責任。  

MIT 授權條款

著作權所有 (c) 2025 DuoDuo

特此免費授權，允許任何取得本軟體與相關文件檔案（以下稱「軟體」）的人員，不受限制地處理本軟體，包括但不限於使用、複製、修改、合併、出版、發行、再授權及/或銷售本軟體副本，並允許本軟體提供者在符合以下條件的情況下也可這樣做：

上述著作權聲明與本授權聲明應包含於本軟體的所有副本或主要部分中。

本軟體是「按現狀」提供，不包含任何明示或暗示的保證，包括但不限於對適銷性、特定用途適用性及非侵權的保證。在任何情況下，作者或版權持有人不對因本軟體或本軟體的使用或其他交易而引起的任何索賠、損害或其他責任承擔責任，無論是在合約訴訟、侵權行為或其他方面。


---

**English**  
This project is licensed under the **MIT License**. Use at your own risk; the author assumes no legal responsibility.  

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

作者：**DuoDuo**  
發布：**2025**
