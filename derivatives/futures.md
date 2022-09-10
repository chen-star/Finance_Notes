# Futures

### Basics
* A future contract is a contract between a seller and buyer to sell a certain asset at a fixed time in the future at a price that is agreed to when the contract is written.

* Diff
~~~text
                Forward                     Future
Traded on  |      OTC               |      stock exchange
Settlement |      On maturity date  |      On daily basis (market to market)
Risk       |      High              |      Low
Liquidity  |      Low               |      High 
~~~


* Terminology:
    * KT(t):
        * future price, contracted price of a future contract.
        * the future price for a contract originated at time=t and expiring at time=T.
        * usually 1 unit of the underlying.


* Marking to Market Process
    * Process:
        * Assume, the days of a future contract's life are given by t1, t2, ..., tN=T
        * from t1 to t2, the futures price changes from KT(t1) to KT(t2)
            * for short position:
                * Assume, KT(t2) < KT(t1)
                * => Thus, at the end of t2, the exchange would make a cash payment to the short's account with amount=KT(t1) - KT(t2) > 0
                * Assume, KT(t2) > KT(t2)
                * => Thus, at the end of t2, the exchange will charge this amount to the short
    * Margin Account:
        * Margins: When a new future position is opened, the investor must post an initial margin in cash in a margin account with the exchange.
        * The balance in the margin account must be maintained above the maintenance margin requirement, which is a smaller than the initial margin requirement.
        * Whenever the balance goes below the maintenance margin requirement, the exchange notifies the investor with a margin call. The investor must then deposit funds in the margin account to bring the balance up to the initial margin level.


* Future Price & Spot Price:
    * As t approaches the expiration date, the futures and spot prices come together (convergence) (KT(T) == S(T))