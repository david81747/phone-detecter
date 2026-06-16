# 🖥️ FocusMind 本地 AI 視覺檢測系統

歡迎使用 FocusMind 專注力檢測系統！本系統採用 **本地端邊緣運算（Edge Computing）**，將吃重的 AI 影像辨識交由本地電腦執行，保障隱私且運作流暢，並將判定結果即時同步至雲端網頁。

要開始使用本系統的網頁功能，請先依照以下步驟在您的電腦上安裝並運行本地檢測程式。

---

## 🛠️ 第一步：安裝 Anaconda 
本系統需要透過 Anaconda 來建立乾淨的 Python 虛擬環境，避免與您電腦中其他的程式發生衝突。

1. 請前往 [Anaconda 官方網站](https://www.anaconda.com/download) 下載安裝程式。
2. 依照預設步驟完成安裝（一直點擊 Next 即可）。

---

## 📥 第二步：下載核心檔案
請從本 GitHub 專案中，下載以下兩個核心檔案，並將它們放在您電腦中指定的資料夾（例如：`C:\race\airace\yolo\vest3`）：

* `yolo_detect.py`（核心檢測程式）
* `my_model.pt`（AI 訓練模型權重檔）

*(您可以點擊檔案後，選擇右上角的 "Download raw file" 按鈕進行下載，或直接下載整個專案的 ZIP 檔並解壓縮)*

---

## 🚀 第三步：啟動檢測系統
環境準備好後，我們就可以喚醒 AI 監視器了！

1. 在 Windows 系統中，打開開始選單，搜尋並開啟 **「Anaconda Prompt」**（請注意，不是一般的 cmd 終端機）。
2. 依序複製並貼上以下指令（每貼上一行請按 Enter 執行）：

```bash
# 1. 建立專屬的虛擬環境 (只需執行一次)
conda create --name yolo-env1 python=3.12 -y

# 2. 啟動虛擬環境
conda activate yolo-env1

# 3. 進入您存放檔案的資料夾 (請依您實際存放的路徑修改)
cd C:\race\airace\yolo\vest3

# 4. 安裝 YOLO 核心套件 (只需執行一次)
pip install ultralytics

# 5. 啟動 AI 檢測程式！
python yolo_detect.py --model my_model.pt --source usb0 --resolution 1920x1080
