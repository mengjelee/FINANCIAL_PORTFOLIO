### Calculate Price of European and American Option
| [程式碼][] |
### Calculation
#### 1. BS model
#### 2. Monte Carlo
#### 3. Binomial Tree
#### 4. Binomial Tree with One Column Vector
#### 5. Binomial Tree with Combinatorics Method
  [程式碼4]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Calculate%20Price%20of%20European%20and%20American%20Option/Calculate%20Price%20of%20European%20and%20American%20Option.ipynb    "程式碼"
#### 學習歷程
我使用BS model / Monte Carlo計算歐洲選擇權的價格；運用basckward induction的方式計算Binomial Tree，但此方法會消耗大量儲存空間，故採用One Column Vector Method，首先計算各種期末報酬並放置list中，再相同list中透過與機率、折現率的方式計算所有節點之現值並更新至相同list。
Combinatorics Method適合處理資訊量較大的資料，直接從期末報酬回推該情況之現值，最終累加所有潛在可能的現值。

#### Combinatorics Method運算過程
1.	輸入選擇權資料、模擬次數、重複次數、delta t。
2.  計算u、d、p及期末報酬並放置相同list中
3.  計算各期機率及發生次數(以np.math.factorial算階層)，兩者相乘放置pro_list
4.  計算機率 * 發生次數 * max(期末報酬,0)
5.  累加所有潛在機會之現值
