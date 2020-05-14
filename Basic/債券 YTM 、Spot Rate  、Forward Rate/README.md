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
  
