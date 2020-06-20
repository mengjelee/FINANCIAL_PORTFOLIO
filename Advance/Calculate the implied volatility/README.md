## Calculate the implied volatility
### Calculate the implied volatility with Bisection method and Newton’s method.
### Use BS model and Binomial tree as option pricing model.
| [code][] | [document][] |
### 1	Algorithm

### 1.1	f(x) = c(sigma) - market price of the option
### 1.2	c() : BS Model, Binomial Tree

### 1.3	Inputs: S0, K, r, q, T, market price of the option, n, convergence criterion. Outputs: Implied volatility
### 1.4	Build def of BS model and Binomial tree
### 1.5	Bisection method
### 1.6	Newton’s method
### 1.6.1	Calculate VEGA as f’ of BS model
### 1.6.2	Calculate slope with interval of 0.00000001 as f’ of Binomial tree
  [code]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Calculate%20the%20implied%20volatility/Calculate%20the%20implied%20volatility.ipynb    "code"
  [document]:  https://github.com/mengjelee/FINANCIAL_PORTFOLIO/blob/master/Advance/Calculate%20the%20implied%20volatility/Calculate%20the%20implied%20volatility.pdf    "document"