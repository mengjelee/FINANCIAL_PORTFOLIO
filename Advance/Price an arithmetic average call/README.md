## Price an arithmetic average call using the binomial tree model.
### Payoff(t) = max(Save(t) - K; 0)
### where Save(t) is the arithmetic average of stock prices from the issue date until the current time point t.
| [code][] | [document][] |
### Price an arithmetic average call


## 1.	Method
### (i) binomial tree model : European and American arithmetic average calls
### (ii) Monte Carlo simulation : European arithmetic average calls

## 2.	Algorithm
### Inputs: St, K, r, q, sd, T - t, M, n, Save(t), passing time, number of simulations, number of repetitions. 
### 1. build tree and calculate average of max and min price series. 
### 2. Generate M times of average prices for each node between average of max and min price series.
### 3.  For each terminal node(n, j), decide the payoff for each representative average price A(n, j, k).  
### 4. Backward Induction : Find corresponding average prices and its option price from terminal
### 5. Apply Interpolation method to get appropriate average price for A(I,J,K)
### 6. backward induction for both euro and American calls
  [code]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Price%20an%20arithmetic%20average%20call/Price%20an%20arithmetic%20average%20call.ipynb    "code"
  [document]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Price%20an%20arithmetic%20average%20call/Price%20an%20arithmetic%20average%20call.pdf    "document"