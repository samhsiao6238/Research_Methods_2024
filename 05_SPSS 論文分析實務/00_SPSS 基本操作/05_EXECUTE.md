# EXECUTE

<br>

## 說明

1. 指令 `EXECUTE` 的作用是 _強制執行先前累積的所有數據操作指令_，也就是立即更新數據文件的狀態，然而部分指令在執行後會自動觸發數據文件的更新，因此不需要顯式執行 `EXECUTE` 指令。

<br>

2. 如執行 `DELETE VARIABLES` 指令後，變數的刪除是立即生效的，不需要額外的 `EXECUTE` 指令來應用更改，這些機制由 SPSS 規範，由於添加這個語句若是累贅並不會影響指令運作，若有疑慮時將其加入便是。

    ```bash
    EXECUTE.
    ```

<br>

## 需要 `EXECUTE` 的情境

_`EXECUTE` 指令在以下情況中是必須的_

<br>

1. 數據轉換指令：當使用如 `COMPUTE`、`IF`、`RECODE` 等指令時，這些指令的邏輯是累積的，直到遇到需要執行的指令如 `FREQUENCIES` 或 `CROSSTABS`，或顯式地使用 `EXECUTE` 指令。

    ```bash
    COMPUTE new_num = old_num * 2.
    EXECUTE.
    ```

<br>

2. 在批次處理腳本中，可能希望在腳本中某個點立即應用所有先前的數據操作，這時可以使用 `EXECUTE`。

<br>

3. 當希望立即查看 SPSS 資料視圖中的變更結果時，可以使用 `EXECUTE` 指令來刷新顯示。

<br>

4. 條件篩選 `SELECT IF` 指令需要 `EXECUTE` 來應用篩選條件，否則篩選條件不會立即生效。

    ```bash
    SELECT IF (age > 18).
    EXECUTE.
    ```

<br>

5. 複數數據轉換操作：如果有多個數據轉換操作，可以將它們累積起來，然後一次性應用。

    ```bash
    COMPUTE newvar1 = var1 * 2.
    COMPUTE newvar2 = var2 + 10.
    EXECUTE.
    ```

<br>

___

_END_