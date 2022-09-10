# SWAP

### Basics
* Swaps are derivatives with 2 counterparties in which the 2 counterparties agree to exchange cash flows with each other.


* Types:
    * Currency Swap:
        * An interest payment in one currency is exchanged for an interest rate in another currency.
    * Equity Swap:
        * A fixed payment is exchanged for the return on some stock or stock index.
    * Commodity Swap:
        * A fixed payment is exchanged for a payment related to a commodity price. 


---


### Interest Rate Swap
* Basics
  * A fixed interest payment, on some notional value, is exchanged for a floating interest payment on the same notional value.
  * A floating interest payment (e.g. LIBOR rate) is paid by one party to the other, who in turn pays the first party an interest rate fixed at contract origination.


  * 2 counterparties:
    * payer: paying the fixed rate
    * receiver: paying the floating rate
    

* Notions:
  * N: When an IR swap is originated, a notional value N is contracted, representing the principal that interest payments will be based on (even though no principal is ever exchanged between the counterparties)
  * ti: The contract specifies a series of payment dates ti, t0 denotes the contract origination date.
  * m: Let m be the # of payments per year.
  * S: The fix interest rate is contracted, denoted by S, also called swap rate.
  * Li: A particular market interest rate is chosen for the floating rate, denoted by Li for the value of floating rate set on date ti.
    * Eg. The LIBOR rate Li-1 is the rate set on date ti-1, charged to borrow money from ti-1 to ti. The interest charged on principal N is: `(ti - ti-1) * Li-1 * N` is paid on date ti.
      * on date ti:
        * payer pays: `S/m * N`
        * receiver pays: `Li-1/m * N`
       
   
* Pricing Swap:
  * For fixed rate side, V_fixed is the total cash to pay as of now:
    * V_fixed = d(t0) * (S/m * N) + d(t1) * (S/m * N) + .... + d(tJ) * (S/m * N)
    * => `V_fixed = (S/m * N) * sum(d(tj)) (1 <= j <= J)`
  * For floating side,
    * V_floating = N * sum(d(tj-1) - d(tj)) (1<= j <= J)
    * => `V_floating = N * (1 - d(tJ))`
  * Fair Swap Rate:
    * is the value of fixed rate S, that sets the swap contract value to 0 at contract origination
    * => V_fixed = V_floating
    * => S = (m * (1 - d(tJ))) / (sum(d(tj)))