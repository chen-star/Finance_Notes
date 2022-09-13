# Finance 101

[[book]](https://marcelodelfino.net/files/Brealey__Myers_y_Allen_2009_Principles_of_corporate_finance.pdf) 
[[course]](https://ocw.mit.edu/courses/15-401-finance-theory-i-fall-2008/)


### Basics
* 2 fundamental challenges of finance
  * **Valuation** of assets(real/financial, tangible/intangible)
    * How *are* financial assets be valued?
    * How *should* financial assets be values?
    * How do financial markets determine asset values?
    * How well do financial markets work?
  * **Management** of assets(acquiring/selling)
    * How much should I save/spend?
    * What/When should I buy/sell?
    * How should I finance the transaction?


* 2 factors that make finance challenging
  * **Time**
    * $1 now is different from $1 later
  * **Risk**
    * uncertainty
  * How to address these 2 issues?
    * use historical data
    * use math(probability & stats)


* 2 frameworks of financial analysis
  * **Accounting**
  * **Balance Sheet & Income Statement**
    * Balance Sheet: snapshot of financial status quo
    * Income Statement: rate of change of the status quo
    ![](../img/finance_101_0.png)

---

### Present Value relations
* Assets & Cash flows
  * From a business perspective, an asset is a sequence of cash flows. (current & future)
    * Assets = {CF_t, CF_t+1, CF_t+2, ...}
  * Valuing an asset requires valuing a seq of cash flows.
    * Value of asset_t = V_t(CF_t, CF_t+1, CF_t+2, ...)
    * Net Present value of asset_0 = V_0(CF_0, CF_1, CF_2, ...)
      * if there's an init investment, then CF_0 < 0
      * assume:
        * cash flows are known
        * discount factors are known
        * no frictions in conversion (no txn fees)
    * in terms of interest rate(opportunity cost of capital /  growth rate) r:
      * FV -> PV: 1/(1 + r)^T in year 0 = $1 in year T
      * PV -> FV: $1 in year 0 = 1*(1 + r)^T
      * => V_0 = CF_0 + CF_1 / (1 + r) + CF_2 / (1 + r)^2 + ...