# Minitab

<br>

## 說明

_這裡是說明假如要使用 Minitab 進行數據轉換以及常態檢定的步驟，先跳過。_

<br>

1. 在 SPSS 中複製差分項。

    ![](images/img_01.png)

<br>

2. 開啟一個 EXCEL 檔案並貼上。

    ![](images/img_02.png)

<br>

3. 變數名稱不會複製，所以插入一行（row）給變數命名。

    ![](images/img_03.png)

<br>

4. 自訂一個名稱。

    ![](images/img_04.png)

<br>

5. 然後選取這個列（欄位），可全選後複製。

    ![](images/img_05.png)

<br>

6. 開啟「Minitab」後，在下方的表單中貼上。

    ![](images/img_06.png)

<br>

7. 會包含變數名稱都貼上。

    ![](images/img_07.png)

<br>

## 開啟 `Minitab`

1. 可先進行一次常態檢定：`統計 -> 基本統計 -> 常態檢定`。

    ![](images/img_08.png)

<br>

2. 設定。

    ![](images/img_09.png)

<br>

3. 報表會顯示是否符合。

    ![](images/img_10.png)

<br>

## 進行 `Box-Cox`

1. `統計 -> 控制圖表 -> BOX-COX`。

    ![](images/img_11.png)

<br>

2. 選取變數後先進行設定

    ![](images/img_12.png)

<br>

3. 先選擇最佳化 lambda 值，並設定輸出欄位 -> OK

    ![](images/img_13.png)

<br>

4. 然後再 OK 一次

    ![](images/img_14.png)

<br>

5. 下方會在指定欄位「C2」顯示 BOX-COX 報表，可自訂名稱（選）。

    ![](images/img_15.png)

<br>

## 分析

1. 當範圍包含「0」，會自動計算出最佳解；若不包含「0」，需手動在選項中輸入。

    ![](images/img_16.png)

<br>

2. 對於 `lambda = -1`。

    ```bash
    *========================================.
    * 對於 lambda = -1.
    COMPUTE BC_m1 = (diffHideShow ** -1 - 1) / -1.
    EXECUTE.
    *========================================.
    ```

<br>

3. 對於 `lambda = 1`。

    ```bash
    *========================================.
    * 對於 lambda = 1.
    COMPUTE BC_1 = (diffHideShow ** 1 - 1) / 1.
    EXECUTE.
    *========================================.
    ```

<br>

___

_END_
