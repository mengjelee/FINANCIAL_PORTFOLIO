
### HW3 –運用backward induction計算出各節點價格及hedge ratio
| [設計過程3][] || [流程圖3][] || [程式碼3][] |

  [設計過程3]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw3/HW3%E5%AD%B8%E7%BF%92%E6%AD%B7%E7%A8%8B.pdf  "設計過程3"
  [流程圖3]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw3/HW3%E6%B5%81%E7%A8%8B%E5%9C%96.pdf  "流程圖3"
  [程式碼3]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw3/hw3.ipynb    "程式碼3"

#### HW3 學習歷程
這次作業主要花時間在思考如何寫出有效率的backward induction模型，有效率的計算各期理論權利金價格以及對沖比率，同時針對選擇權類型的差異調整計算方式，最終以matplotlib輸出圖表。

#### 運算過程
1.	輸入值 : 選擇權種類(call / put)、current stock price、upward move、downward move、rate、stike price and period
2.	首先將輸入值轉換成走向的機率及折現值
R = e^r ； p = (R − d)/(u − d)
3.	 以上下幅度計算標的物價格，若為CALL最終期以標的物價格減執行價為正權利金，PUT則相反
4.	以backward induction計算出各節點選擇權價格及hedge ratio
hedge ratio = 權利金價值差異 / 當期價格差異
5.	最終輸出有list of possible stock prices 、 option prices and hedge ratio並將後兩者輸出成表格。

#### 各期權利金理論價格圖表
![各期權利金理論價格圖表](https://github.com/mengjelee/Financial_Engineering/blob/master/hw3/%E5%90%84%E6%9C%9F%E6%AC%8A%E5%88%A9%E9%87%91%E7%90%86%E8%AB%96%E5%83%B9%E6%A0%BC.png)
#### 各期hedge ratio
![各期hedge ratio](https://github.com/mengjelee/Financial_Engineering/blob/master/hw3/%E5%90%84%E6%9C%9Fhedge%20ratio.png)


