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

