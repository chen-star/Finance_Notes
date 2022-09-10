# Forwards

### Basics
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


* Forward Interest Rates
    * A FIR is an interest rate that can be locked in now for some loan term starting in the future.
    * L(t, T1, T2): the simply compounded rate that can be locked in at time=t for a loan term from T1 to T2 from the prevailing spot LIBOR curve. 