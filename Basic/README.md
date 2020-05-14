# Financial_Engineering
#### 李孟哲；國企三；B06704028
*******
### HW4 - Calculate Price of European Put and Call Option
| [設計過程4][] || [流程圖4][] || [程式碼4][] |

  [設計過程4]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw4/HW4%E5%AD%B8%E7%BF%92%E6%AD%B7%E7%A8%8B.pdf  "設計過程4"
  [流程圖4]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw4/HW4%E6%B5%81%E7%A8%8B%E5%9C%96.pdf  "流程圖4"
  [程式碼4]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw4/hw4.ipynb    "程式碼4"
#### HW4 學習歷程
我使用兩種方式以BS model計算歐洲選擇權的價格，第一種是老師提供的計算方式，先將各期股利折現並從現值中扣除；第二種是不計算p head，而是在計算公式時以現價乘以(e^(-dividend_yield*t))代替，此方法參考john hull《Options, Futures, and Other Derivatives》，計算方式如下。
 ![BS model](https://github.com/mengjelee/Financial_Engineering/blob/master/hw4/2.png)
##### 參考網站 : https://goodcalculators.com/black-scholes-calculator/

#### 運算過程
1.	輸入 current price、 σ 、dividends、times dividend paid in a year、interest rate、strike price、maturity from now
2.	計算各期股利折現並從現值中扣除
3.	BS model
Normal distribution: scipy.stats.norm(0, 1).cdf()
4.	輸出Price of European Put and Call Option

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


### HW2-計算債券的 YTM、Spot Rate、Forward Rate 及Forward Rate 對照表
| [設計過程2][] || [流程圖2][] || [程式碼2][] |

  [設計過程2]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw2/hw2%E8%A8%AD%E8%A8%88%E6%96%87%E4%BB%B6.pdf  "設計過程2"
  [流程圖2]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw2/HW2%E6%B5%81%E7%A8%8B%E5%9C%96.pdf  "流程圖2"
  [程式碼2]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw2/hw2.ipynb    "程式碼2"
  
#### HW2學習歷程
本次作業我使用python運算各期攤還之本金、利息及累計，並使用matplotlib製作表格輸出。

###### 一、	計算ytm: 
運用規劃求解概念以python求出ytm
1.	允許負殖利率!!
2.	允許非整數年分
3.	允許以各式報價方式計算ytm
計算過程
1.	判斷正負殖利率:若Current Bond Price > Bond Par Value + Bond Par Value* Bond Coupon Rate (% p.a.)* Years to Maturity，則為負殖利率，反之為正
2.	若為正Ytm，從Ytm = 0開始以0.0001遞增尋找近似解 – 若下個ytm數值讓pv小於Current Bond Price則為最佳ytm
3.	若為負Ytm，從Ytm =0開始以-0.0001遞減尋找近似解 – 若下個ytm數值讓pv大於Current Bond Price則為最佳ytm

###### 二、	計算spot rate
計算邏輯:
1.	Spot rate 1 = ((current price / par value) ^ (-1/duration)) -1
2.	Spot rate 2 = ln(current price / par value)*(-1/duration)

###### 三、	計算遠期利率
計算邏輯:
1.	Forward rate 1 = ((current price / par value) ^ (1/Duration of forward rate)) -1
2.	Forward rate 2 = ln(current price / par value)*(1/Duration of forward rate) 

###### 四、製作遠期利率矩陣
由於運算過程與第三步雷同，這次作業花較多時間學習如何使用matplotlib製作出隨著不同資料量改變呈現方式的純表格展示法。

![試算結果](https://github.com/mengjelee/Financial_Engineering/blob/master/hw2/forward_rate_matrix.png)
=========
### HW1-本金平均攤還法試算利息
| [學習歷程][] || [流程圖][] || [程式碼][] |

  [學習歷程]:  https://drive.google.com/file/d/1PqDCQObODw5D3BfJtN054Y4N8pyFAitc/view?usp=sharing  "學習歷程"
  [流程圖]:  https://drive.google.com/file/d/18R_u8MKJx4o-csnH3Z_6m7w2qulkm4C4/view?usp=sharing  "流程圖"
  [程式碼]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw1/hw1.ipynb    "程式碼"
  
#### HW1學習歷程
本次作業我使用python運算各期攤還之本金、利息及累計，並使用matplotlib製作表格輸出。由於運算過程不複雜，這次作業花較多時間學習如何使用matplotlib製作出隨著不同資料量改變呈現方式的純表格展示法(見圖一)。
此外，我增加幾項[試算網站][]沒有的功能。
1. 期數(年)可為小數，若不滿一個月無條件捨去
2. 期數不可為零或是負數
3. 年利率(%)可為負
4. 運用matplotlib製作表格

![試算結果](https://github.com/mengjelee/Financial_Engineering/blob/master/hw1/hw1.png)

  [試算網站]:  https://ttc.scu.org.tw/memdca1.htm    "本金平均攤還法試算利息試算網站"
