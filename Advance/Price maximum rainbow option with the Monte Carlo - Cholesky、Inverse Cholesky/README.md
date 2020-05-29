# FINANCIAL_PORTFOLIO
# Price maximum rainbow option with the Monte Carlo - Cholesky、Inverse Cholesky

1. | [運算流程][] |
2. | [程式碼][] |

  [運算流程]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Price%20maximum%20rainbow%20option%20with%20the%20Monte%20Carlo%20-%20Cholesky%E3%80%81Inverse%20Cholesky/Price%20maximum%20rainbow%20option%20with%20the%20Monte%20Carlo%20-%20Cholesky%E3%80%81Inverse%20Cholesky.pdf  "運算流程"
  [程式碼]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Price%20maximum%20rainbow%20option%20with%20the%20Monte%20Carlo%20-%20Cholesky%E3%80%81Inverse%20Cholesky/Price%20a%20maximum%20rainbow%20option%20with%20the%20Monte%20Carlo%20-%20Cholesky%E3%80%81Inverse%20Cholesky.ipynb  "程式碼"

## Calculate price of maximum rainbow option with Monte Carlo with following method:
### 1.	Cholesky
### 2.	Combine the antithetic variate approach and moment matching
### 3.	Inverse Cholesky
============
## Implement the inverse Cholesky method
### Input : 
#### 1.	K, r, T, number of simulations, number of repetitions, n
#### 2.	list of current prices, sigma
#### 3.	matrix of correlation coefficient with list format (n*n)

### data process :
#### 1.	Create new random samples(mean = 0, std = 1) with antithetic variate approach and moment matching
#### 2.	Calculate variance-covariance matrix(c2) of new random samples
#### 3.	Transform Covariance array into array c2 with Cholesky Decomposition

###  Calculation :
#### 1.	np.dot(Array of random samples, np.dot(inverse matrix of c2, array A ) ) 
