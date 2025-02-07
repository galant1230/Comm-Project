# 🎵 THE VOICE - Instrument Recognition using Deep Learning

## 📌 Description
本專案致力於 **音訊分析與樂器識別**，透過 **MFCC 特徵提取** 與 **深度學習模型** 來分類音訊的樂器種類。  
我們使用 **Google Magenta 計畫** 提供的開源數據庫進行訓練，該數據庫包含約 **30 萬筆音訊樣本**，能夠提供豐富的訓練資料。  
此外，我們搭建了一個 **API 網頁介面**，讓使用者可以上傳音樂檔案並即時獲取分析結果。

---

## 📥 Methodology
### 🔹 1. MFCC 特徵提取 (Mel-Frequency Cepstral Coefficients)
- 透過 **短時距傅立葉轉換 (STFT)**，將音訊信號轉換為頻譜資訊。
- 使用 **梅爾倒頻譜濾波器**，模擬人耳對不同頻率的響應特性，提取出關鍵特徵。
- 採用 **標準化 (Standardization)**、**倒譜均值方差歸一化 (CMVN)** 及 **正規化 (Normalization)** 三種方式進行測試。

### 🔹 2. 深度學習模型訓練
- 透過 **TensorFlow** 與 **CNN 模型** 訓練音訊數據，識別樂器種類。
- 使用 **Google Magenta** 提供的數據庫，涵蓋各種樂器音訊樣本。
- 探討不同 **MFCC 處理方式** 如何影響模型準確度。

### 🔹 3. API 介面開發
- 架設 **Flask 伺服器**，允許使用者上傳音訊檔案，並透過 **深度學習模型** 進行分析。
- 預測結果會即時回傳到 **網頁前端**，提供即時分析體驗。

---

## 📊 Results & Analysis
### 🎯 準確率比較（不同 MFCC 處理方式）
![image](https://github.com/user-attachments/assets/7df2912b-ae1f-4297-ac28-5a859ab284ff)


如上圖所示，不同 **MFCC 特徵處理方式** 對於樂器識別準確度的影響如下：
- **未處理 (Raw MFCC)**：62.65%
- **標準化 (對特徵)**：67.9%
- **標準化 (對時間)**：56.17%
- **正規化 (Normalization)**：**91.32%**
- **倒譜均值方差歸一化 (CMVN)**：71.09%

#### 📌 分析：
- **正規化 (Normalization) 獲得最高準確率 91.32%**，顯示該方法能夠更有效去除噪音並增強關鍵特徵。
- **標準化 (對時間) 的表現最差 (56.17%)**，推測是因為時間尺度的變異影響了特徵學習的穩定性。
- **CMVN（71.09%）表現良好**，但仍低於正規化方法。

---

## 📎 References
- **Google Magenta 計畫**：[官方網站](https://magenta.tensorflow.org/)
- **TensorFlow 深度學習框架**：[TensorFlow 官網](https://www.tensorflow.org/)
- **Flask 網頁框架**：[Flask 官網](https://flask.palletsprojects.com/)


