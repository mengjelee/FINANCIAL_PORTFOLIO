### HW5 - Calculate Option Price with Changing Interest Rate
| [設計過程5][] || [流程圖5][] || [程式碼5][] |

  [設計過程5]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw4/HW4%E5%AD%B8%E7%BF%92%E6%AD%B7%E7%A8%8B.pdf  "設計過程5"
  [流程圖5]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw4/HW4%E6%B5%81%E7%A8%8B%E5%9C%96.pdf  "流程圖5"
  [程式碼5]:  https://github.com/mengjelee/Financial_Engineering/blob/master/hw4/hw4.ipynb    "程式碼5"
#### HW5 學習歷程
#### 我使用QL套件的Hull-White Process產出一段時間內的利率集，再用蒙地卡羅模擬法計算未來的可能資產價格，最終根據執行價集折現率計算call和put的價格。

#### 運算過程
### Step1 :  Create List of Interest Rate by Hull-White Process
#### 1.	輸入Sigma of Interest rate, a, timestep, length (in years), forward rate, number of paths
#### 2.	用QL套件計算Hull-White Process
#### 3.	產出一段時間內的利率集及走勢圖
### Step2 : Calculate Option Price by Monte Carlo with Changing Interest Rate
#### 1.	輸入strike price, risk-free interest rate, delta T, Sigma of stock, stock price
#### 2.	以蒙地卡羅計算未來資產價格
#### 3.	產出call和put的價格及走勢圖

