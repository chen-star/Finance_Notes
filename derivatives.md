# Derivatives

## Basics
* **Financial product**: 
  * financial products are assets suitable for investments.
  * 2 categories:
    * **Cash Product**
      * e.g. `stocks, bonds, currencies, commodities`
      * Bond: 
        * A bond is an asset, often regarded as a 'debt instrument'. One may think of 'owning' a bond as the same thing as 'owning' debt.
        * The principal of a loan in bond is called 'par value' or 'face value'.
        * The bond price paid by the bond holders to the bond issuers represents a loan or debt. In essence, the bond buyer is lending the bond price to the bond issuer. 
        ~~~
        Bond Holder                       Bond Issuer
                    --------> Bond Price
                    <-------- Interest
                    <-------- Interest
                    <-------- Interest
                        ...
                    <-------- Par Value
        ~~~

    * **Derivatives**
      * A derivative is an asset linked to (or derived from) another asset, called the underlying asset, or just underlying.
      * The structure and value of the derivative asset is defined by its relationship to the underlying.
      * e.g. `forwards, futures, swaps, options`
        * forwards and futures: are contracts that lock in the price 2 parties will buy and sell an asset for at some future date. The traded asset is the underlying.
        * options: similar to forwards, but one party has the right not to participate at the time the contract expires.
        * swaps: linked to interest rates, allowing a floating interest rate to be switched to a fixed rate. In this case, the underlying asset is an interest rate.


* **Value**:
  * 2 notions of financial value:
    * Price
      * determined on markets
    * Fair value
      * 'correct value'
      * it's connected to concepts like:
        * time value of money
        * discounted cash flow analysis
        * arbitrage
          * is a relative valuation method, and is the ideal tool for determining the relationship between the value of a derivative asset and the value of its underlying.


* **Interest Rate**:
  * Interest rates are measures of the price charged in the economy to borrow money.
  * Terminology:
    * `principal`: the amount of money borrowed in a loan.
    * `interest rate`: the fraction of the principal of a loan that will be charged as interest per unit time.
    * `risk free rate`: the interest rate if there's no risk
      * E.g. In real-world interest rate, very close to being an actual risk free interest rate: the Secured Overnight Financing Rate (SOFR)
    * `future value`:
      * r(t) is the annual and annually compounded interest rate for a loan term of t years, P0 is the principal, the future value of P0 at time t is: `P(t) = (1 + r(t)) ^ t * P0`
  * Interest rates are determined by market activity. Teh market of borrowers and lenders is a diverse collection of markets which are usually viewed as divided into 2 classes:
    * Money Market: short term loans (<= 1 year)
    * Bond Market (> 1 year)
  * Compounding convention
    * Assume: r(t) is the annual interest rate, in each (m times per year) compounding period, the earned interest is (r(t) / m) * P0
    * The future value of P0 is: `P(t) = (1 + r(t) / m) ^ (mt) * P0`


* **Time Value of Money (TVM)**:
  * TVM is a concept that a sum of money is worth more now than the same sum will be at a future date due to its earnings potential.
  * `present value (PV)`: PV of X, is the amount that should be invested today at prevailing interest rates, so that at time t the investment will be worth exactly X.
    * `(1 + r(t) / m) ^ (mt) * PV = X` => `PV = X / (1 + r(t) / m) ^ (mt)`
    * PV also called discounted value
  * `discount factor`: the value today of receiving $1 at time t. Discount factors reflect the time value of money.
    * `PV = d(t) * X`, where `d(t) = (1 + r(t) / m)  ^ (mt)`