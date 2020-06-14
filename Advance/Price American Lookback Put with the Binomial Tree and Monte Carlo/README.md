# FINANCIAL_PORTFOLIO
# Price American Lookback Put with the Binomial Tree and Monte Carlo 

1. | [運算流程][] |
2. | [程式碼][] |

  [運算流程]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Price%20American%20Lookback%20Put%20with%20the%20Binomial%20Tree%20and%20Monte%20Carlo/Price%20American%20Lookback%20Put%20with%20the%20Binomial%20Tree%20and%20Monte%20Carlo.pdf  "運算流程"
  [程式碼]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Price%20American%20Lookback%20Put%20with%20the%20Binomial%20Tree%20and%20Monte%20Carlo/Price%20American%20Lookback%20Put%20with%20the%20Binomial%20Tree%20and%20Monte%20Carlo.ipynb  "程式碼"


## 1. requirement:
### The payoff function of the lookback put is as follows.
### Payofft = max(Smax,t − St , 0), where Smax,t = max Su, for u = 0, ∆t, 2∆t, ..., t.

## Implement the binomial tree model to price both European and American lookback puts. 

## 2. Binomial Tree Algorithm :
### 1	Build the binomial tree
### 2	Record possible max price(Smax) for each node. 
### 2.1	Insert max price for monotonic upward and downward prices.
### 2.2	The forward-tracking method – For a node with the stock price St ,inherit Smax’s from parents :

### 1. If Smax from parents ≥ St ⇒ Insert this Smax into its Smax-list
### 2. If Smax from parents < St ⇒ Ignore Smax and insert St into its Smax-list

### 3	Two Backward inductions (a/e) – Calculate early exercise at the same time for American put
### Backward inductions : Try to find Smax(t) in list of Smax(t+1). If found, use the option price of the same Smax. If not, insert option values of the upward price, which will be the maximum.
### Notice : for monotonic upward price, use the option price of the next upward node if there is no same Smax.

## 3. Monte Carlo Algorithm :
### 1. Break a price path into 100/300 prices. Use the new price to calculate next mean.
### 2. Record the maximum price 
### 3. Create 10000 paths and their value with 20 repetitions. 
