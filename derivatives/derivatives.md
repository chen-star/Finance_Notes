# Derivatives

## Basics
* **Financial product**: 
  * financial products are assets suitable for investments.
  * 2 categories:
    * **Cash Product**
      * e.g. `stocks, bonds, currencies, commodities`
      
      * Bond:
        ~~~text
        Bond Holder                       Bond Issuer
        (Loaner)                          (Borrower)
                    --------> Bond Price
                    <-------- Interest
                    <-------- Interest
                    <-------- Interest
                           ...
                    <-------- Par Value
        ~~~
        * A bond is an asset, often regarded as a 'debt instrument'. One may think of 'owning' a bond as the same thing as 'owning' debt.
        * The principal of a loan in bond is called 'par value' or 'face value'.
        * The bond price paid by the bond holders to the bond issuers represents a loan or debt. In essence, the bond buyer is lending the bond price to the bond issuer.

      * Stock:
        ~~~text
        Shareholder                         Company
                    --------> Share Price
                    <-------- Dividend
                    <-------- Dividend
                            ...
        ~~~
        
      * Currencies:
        * Assume, we have K allocation (unit) of a foreign currency, interest rate of this currency is rf, S(t) is the exchange rate of domestic to foreign currency at time t.
        * The FV of domestic currency we have is: K * (e ^ (rf * t)) * S(t)

      * **Derivatives**
        * A derivative is an asset linked to (or derived from) another asset, called the underlying asset, or just underlying.
        * The structure and value of the derivative asset is defined by its relationship to the underlying.
        * The linkage of the derivative to the underlying is usually through the payoffs of the derivative. The payoffs are the revenues paid to holders of the derivative product.
        * e.g. `forwards, futures, swaps, options`
          * forwards and futures: are contracts that lock in the price 2 parties will buy and sell an asset for at some future date. The traded asset is the underlying.
          * options: similar to forwards, but one party has the right not to participate at the time the contract expires.
          * swaps: linked to interest rates, allowing a floating interest rate to be switched to a fixed rate. In this case, the underlying asset is an interest rate.


---


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

---


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
    * Continuous Compounding
      * It's the limit of periodic compounding as the frequency m to infinity
      * The future value of P0 is: `P(t) = e ^ (r(t)*t) * P0`
    * Simple Interest
      * for short term interest rates
      * only applied on the original principal. no compounding. 
      * If we loan a principal F at a simple interest r for a duration T years, the total interest paid will be `rTF`
  * LIBOR, SONIA, SOFR, Fed Funds Rate
    * LIBOR: interest rates reflect the borrowing costs banks pay for unsecured borrowing from other banks for loan terms ranging from overnight to 1 year.
    * SONIA: overnight rate only based on actual txns, insensitive to credit risk. 
    * SOFR: overnight rate only based on actual txns, 

---


* **Time Value of Money (TVM)**:
  * TVM is a concept that a sum of money is worth more now than the same sum will be at a future date due to its earnings potential.
  * `present value (PV)`: PV of X, is the amount that should be invested today at prevailing interest rates, so that at time t the investment will be worth exactly X.
    * `(1 + r(t) / m) ^ (mt) * PV = X` => `PV = X / (1 + r(t) / m) ^ (mt)`
    * PV is also called discounted value
  * `discount factor`: the value today of receiving $1 at time t. Discount factors reflect the time value of money.
    * `PV = d(t) * X`, where `d(t) = (1 + r(t) / m)  ^ (mt)`

---


* Investment Return Measures
  * Gross Return
    * `V(t + x) / V(t)`, V(t) is the value of some investment or asset at time t. 
  * Net Return
    * `(V(t + x) - V(t)) / V(t)`
  * Discounted Cash Flow Analysis
    * Suppose a holder own an asset, another party pays a seq of payments c1, c2, ..., cN, at the corresponding times t1, t2, ..., tN.
    * The payments ci are called cash flows. 
    * To value our asset (i.e. to value a stream of cash flows), we must know what the PV of a stream of cash flow is. 
    * PV of a stream of cash flow = `d(t1)c1 + d(t2)c2 + ... + d(tN)cN`
  * Yield
    * A yield for a bond, or other securities, is a measure of the return of the investment.
    * Current yield = `Annual Interest (coupon value) / Price`
    * Yield to maturity: most common yield measure in bond.
      * `P = sum(ci / (1 + y) ^ Ti)`, P is the market price of the bond, ci is the coupons(interests) are paid at time Ti
      * y is the interest rate such that the market price of the bond would be recovered if all payments were discounted by it

---


* **Yield Curves & Discount Curves**
  * Yield Curves
    * A yield curve quantifies the relationship between return of a fixed income security and term or maturity, the term structure of interest rates.
  * Discount Curves
    * A primary application of yield curves in finance is to produce discount curves.
    * Discount Curve is a function d(T) which for any T is a discount factor corresponding to discounting back from time T.
    * Spot Rate Curve:
      * A special kind of discount curve, where y(T) is a (continuously compounded) spot rate curve.
      * `d(T) = e ^ (-y(T) * T)` => `y(t) = - log(d(T)) / T`
  * Bootstrapping Spot Rate Curve from Bonds
    * Bootstrapping is the main technique for building a yield curve from real market data.
    * Steps:
      1. Assume we have a collection of N bonds with maturities T1 < T2 < ... < TN, and market prices P1, P2, ... , PN
      2. We first choose d(T) for T <= T1 to discount the coupons of bond 1 and recover P1.
      3. for T1 < T <= T2, get d(T) from bond 2.
      4. repeat
    * Eg.:
      * Suppose we have 3 bonds:
        * Bond 1: 0 coupon bond, a $1k face value, maturing in 6 months, trading price P1 = $985
        * Bond 2: 5% coupon, with semiannual payments, a $10k face value, maturing in 1 years, trading price p2 = $10,124
        * Bond 3: 7 % coupon, with annual payments, a $10k face value, maturing in 2 years, trading price p3 = $10,507
      * Calc d(t) & y(t):
        * Bond 1:
          * `P1 = d(0.5) * 1k` => `d(0.5) = 985 / 1k = 0.985` => `y(0.5) = - (log(0.985)) / 0.5 = 3%`
        * Bond 2:
          * `P2 = d(0.5) * 250 + d(1) * 10,250` => `d(1) = 0.9637` => `y(t) = 3.7%`
        * Bond 3:
          * `P3 = d(1) * 700 + d(2) * 10,700` => `d(2) = 0.91891` => `y(t) = 4.2%`

---

* **Long / Short position**
  * Long position:
    * We say that we have a long position on a particular asset if the value of our portfolio goes up when the value of the asset goes up.
    * The simplest way to take a long position is to buy it. 
  * Short position:
    * We say that we have a short position on a particular asset if the value of our portfolio goes down when the value of the asset goes up.


---
---
---

## Arbitrage

* **Definition**
  * Arbitrage is the simultaneous purchase and sale of the same asset in different markets in order to profit from differences in the assets' listed price. 
  * Usually arbitrages will be realized in the following way: a portfolio will be presented that can be entered without cost, that yields a certain and positive profit at some time t > 0.


* **The Law of One Price**
  * Definition
    * Assume, A & B are assets with prices PA(t) & PB(t) at time t (t > 0). Prob(PA(t) == PB(t)) = 1. 
    * Then, either (1) PA(0) == PB(0) or (2) there's an arbitrage.
  * Prove
    * Assume, PA(0) > PB(0) => we need to prove there's an arbitrage.
    * => to construct an arbitrage
      * => at time=0 (current), take a short position on A, long on B
        * => borrowed A and sold A, purchased B (no cash spent on this portfolio)
          * => cash flow: PA(0) - PB(0) > 0 (positive cash flow)
          * => portfolio: 
            * -A
            * B
            * cash: PA(0) - PB(0)
      * => at time=t (future)
        * => sold B, purchased B and returned A
        * => portfolio:
          * cash: (PA(0) - PB(0)) * (e ^ (rt)) -> risk-less profit


---
---
---

## Derivatives

* **Basics**
  * spot price / cash price
    * The price of the underlying asset is referred to as the cash price or the spot price.

---

* **Forwards**
  * A forward contract is an agreement between a seller and a buyer in which they agree that the seller will sell an asset to the buyer at a certain time in the future at a price agreed upon at the time of entering the contact.
  * Forward contracts are privately negotiated between counterparties, on OTC markets and can be highly customized to suit the 2 counterparties. 
  * Terminology:
    * long position: the position of the buyer
    * short position: the position of the seller
    * expiration date or expiry: the agreed trade date
    * forward price: the contracted price
  * Forward Payoffs:
    * S(t): the price of underlying asset at time=t
    * K(t): the forward price for expiry=t
    * T: expiration date
    * r: risk free rate
    * V(t): value of long position at time=t (long forward payoff)
    * ~~~text
      At T
      Long          Short
          ----> K(T)
          <---- S(T)
      
      For long:
        V(T) = S(T) - K(T)
      For short:
        -V(T) = K(T) - S(T)
      ~~~
    * fair K(T):
      * K(T) = e ^ rT * S(0)
  * Forwards on an underlying with a known income
    * fair K(T): K(T) = e ^ rT * (S(0) - I) (I is the present value of income)
  * FX Forwards
    * FX: foreign exchange
    * locks in a particular exchange for the expiration date of the contract.
    * 