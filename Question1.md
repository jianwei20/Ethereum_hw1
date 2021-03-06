## Homework description

### (20%) 1. Please compare hash function and cryptographic hash function and give an example.
## Answer
### hash function 是什麼？
一種從任何一種資料中建立小的數字「指紋」的方法。
**雜湊函式** 把訊息或資料 (key) 壓縮成摘要，使得資料量變小，將資料的格式固定下來。該函式將資料打亂 混合，重新建立一個叫做 **雜湊值（hash values，hash codes，hash sums，或hashes）** 的指紋。
這個雜湊值就當作是陣列的索引，資料就儲存在這個索引，資料就儲存在這個索引的位置中。
雜湊值通常用一個短的隨機字母和數字組成的字串來代表。

### hash function 性質
1. 運算速度快
2. **不可逆性**： 無法從雜湊值推回原本的資料是什麼
3. 如果兩個雜湊值是 **不相同** 的（根據同一函式），那麼這兩個雜湊值的原始輸入也是 **不相同** 的
4. 如果兩個雜湊值是 **相同** 的（根據同一函式），那麼這兩個雜湊值的原始輸入 **不一定** 是相同的

* **衝突 (collision)**
也就是 **第 2 種情況** 發生時就稱為「雜湊衝突」。好的雜湊函式在輸入域中很少出現雜湊衝突。在雜湊表和資料處理中，不抑制衝突來區別資料，會使得資料庫記錄更難找到。

### 範例 **hash table**

hash table是hash function的一個主要應用，使用hash table **能夠快速的按照關鍵字 (hash value) 尋找資料記錄**。

hash table 理想應用是把每個key對映到唯一的index上（也就是完全零碰撞），因為這樣能夠保證直接存取表中的每一個資料。

一個好的hash function應具有 **均勻** 的真正隨機輸出。同樣重要的是，隨機雜湊函式不太會出現非常高的衝突率。但是，少量的可以估計的衝突在實際狀況下是不可避免的。

可以用 **陣列** 、 **tree** 或者是 **linked list** 建表。使用 linked list 遇到碰撞時就接在同一個索引後面即可，如下圖。
![](https://i.imgur.com/D85eZMz.png)


### cryptographic hash function 是什麼？
密碼雜湊函式 **Cryptographic hash function**，又譯為加密雜湊函式、密碼雜湊函式、加密雜湊函式，是雜湊函式的一種。
它被認為是一種單向函式，也就是說極其難以由雜湊函式輸出的結果，回推輸入的資料是什麼。這樣的單向函式被稱為「現代密碼學的馱馬」。
這種雜湊函式的輸入資料，通常被稱為訊息（message），而它的輸出結果，經常被稱為訊息摘要（message digest）或摘要（digest）。
在資訊安全中，有許多重要的應用，都使用了密碼雜湊函式來實作，例如數位簽章，訊息鑑別碼。

### hash function 性質
1. 運算速度快
2. **不可逆性**： 無法從雜湊值推回原本的資料是什麼
3. 在不更動雜湊數值的前提下，修改訊息內容是不可行的。
4. 如果兩個雜湊值是 **不相同** 的（根據同一函式），那麼這兩個雜湊值的原始輸入也是 **不相同** 的
5. 如果兩個雜湊值是 **相同** 的（根據同一函式），那麼這兩個雜湊值的原始輸入 **不一定** 是相同的

### 範例 **Digital Signature**
是一種類似寫在紙上的普通的物理簽名，但是使用了公鑰加密領域的技術實現，用於鑑別數位信息的方法。一套數位簽章通常定義兩種互補的運算，一個用於簽名，另一個用於驗證，但法條中的電子簽章與數位簽章，代表之意義並不相同，電子簽章用以辨識及確認電子文件簽署人身分、資格及電子文件真偽者。而數位簽章則是以數學演算法或其他方式運算對其加密，才形成的電子簽章，意即並非所有的電子簽章都是數位簽章。


下圖 說明數位簽章的簽名及驗證過程
![](https://upload.wikimedia.org/wikipedia/commons/6/66/Digital_Signature_diagram_zh-CN.svg)


### Reference
- Hash function[Wiki](https://zh.wikipedia.org/wiki/散列函數) 

- Cryptographic hash function [WiKi](https://en.wikipedia.org/wiki/Cryptographic_hash_function)




