# 添加 UID

<br>

## 面板操作

1. 開啟 `轉換 -> 計算變數`。

    ![](images/img_18.png)

<br>

2. 輸入名稱 `UID`， 函數群組選擇 `全部`，下方第一個預設的計算公式為 `$CASENUM`，點擊。

    ![](images/img_19.png)

<br>

3. 點擊兩下就會自動將函數添加到 `數值表示式` 的對話中，然後點擊 `貼上` 可查看語法，點擊 `確認` 就會添加 UID。

    ![](images/img_21.png)

<br>

## 語法操作

1. 開啟指定的資料集。

    ```bash
    *========================================.
    DATASET ACTIVATE 資料集1.
    *========================================.
    ```

<br>

2. 添加 UID。

    ```bash
    *========================================.
    *添加 UID.
    COMPUTE UID = $CASENUM.
    EXECUTE.
    *========================================.
    ```

<br>

3. 標籤、值標籤、小數位數、變數類型。

    ```bash
    *========================================.
    *標籤名稱.
    VARIABLE LABELS UID '唯一識別碼'.

    *小數的位數為「0」，F 為 Format 的意思.
    FORMATS UID (F4.0).

    *變數類型為序數.
    VARIABLE LEVEL UID (ORDINAL).

    *靠左 置中 靠右 LEFT CENTER RIGHT.
    VARIABLE ALIGN UID (CENTER).

    *執行.
    EXECUTE.
    *========================================.
    ```

<br>

## 排序變數

1. 接下來要把 UID 移動到最前面。

    ![](images/img_20.png)

<br>

2. 重新完整排序；可手動進行編輯，斷行與縮排無強規定。

    ```bash
    *========================================.
    *排序變數.
    MATCH FILES FILE = *
    /KEEP = UID sex age isKnowHideFunction useYears useFrequency useTime
    Ｑan01 Ｑan02 Ｑan03 Ｑan04 Ｑan05 Ｑan06 Ｑan07 Ｑan08 
    Ｑan09 Ｑan10 Ｑan11 Ｑan12 Ｑan13 Ｑan14 Ｑan15 Ｑan16 
    Ｑan17 Ｑan18 Ｑan19
    Hide01 Hide02 Hide03 Hide04 Hide05 Hide06 Hide07
    Hide08 Hide09 Hide10 Hide11 Hide12 Hide13 Hide14 
    Hide15 Hide16 Hide17 Hide18
    Show01 Show02 Show03 Show04 Show05 Show06 Show07
    Show08 Show09 Show10 Show11 Show12 Show13 Show14
    Show15 Show16 Show17 Show18.
    EXECUTE.
    *========================================.
    ```

<br>

___

_END_
