# 專案目的
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/I-Sheng/Traveling-Planner-With-LLM/blob/main/README.en.md)

此 GitHub repository 是國科會計畫「以 GPT 為核心的旅遊行程規劃系統」的專案。原計畫中預計使用 GPT（客製化的 ChatGPT）作為核心模型，但隨著科技技術的進步以及客製化需求的增加，現已改用 LangChain 進行實作。

## 專案架構圖
![專案架構圖](https://github.com/user-attachments/assets/0197dbd5-e37b-46db-8469-679150e3a7d2)

## 使用者流程
1. 使用者根據提示（Prompt）輸入喜好：
    ```
    # 提示範例
    # 我喜歡__的景點，計劃旅遊__天，請幫我推薦一些景點。
    # 例如：
    我喜歡古蹟類的景點，計劃旅遊2天，請幫我推薦一些景點。
    ```
2. 語言模型（LLM）推薦可能的景點。
3. 使用者選擇偏好的景點及住宿地點。
4. 語言模型（LLM）根據使用者的選擇返回詳細行程規劃。

## 專案實作細節
根據專案架構圖，本專案以嘉義旅遊為目的地，實作分為四個主要部分：

1. **資料收集**：收集嘉義旅遊相關資訊，包括景點、餐廳及飯店。
   → 目錄：`/webcrab`

2. **停留時間計算**：計算各景點建議的停留時間。
   → 目錄：`/waiting_time`

3. **資訊查詢**：在使用者決定景點後，取得各景點的詳細資訊。
   → 腳本：`/langchain/distance_matrix.py`

4. **行程規劃**：將取得的相關資訊放入演算法中，並生成景點行程規劃。
   （**注意：此步驟尚未完成**）

## 環境設定

1. **建立 `.env` 檔案**
   在專案根目錄下建立 `.env` 檔案，內容如下：
    ```env
    # 生成式 AI
    OPENAI_API_KEY='YOUR_OPENAI_API_KEY'
    ANTHROPIC_API_KEY='YOUR_ANTHROPIC_API_KEY'
    GOOGLE_API_KEY='YOUR_GOOGLE_API_KEY'

    # Google 地圖 API
    GOOGLE_MAP_API_KEY='YOUR_GOOGLE_MAP_API_KEY'

    # LangChain
    LANGCHAIN_HUB_API_KEY='YOUR_LANGCHAIN_HUB_API_KEY'
    LANGCHAIN_API_KEY='YOUR_LANGCHAIN_API_KEY'
    ```

