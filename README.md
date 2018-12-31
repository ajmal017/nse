# Programs to scan and manage NSE

## 01_nse_scan

* Extract symbols and margins from (5paisa)[https://www.5paisa.com/5pit/spma.asp]
* Prepares to *pickle* options with underlying symbols. 
   * Underlying symbol with: 
      * volatility, hi52, lo52, meanPrice
      * integrated with lots and margins
   * Option chains with:
      * option chain tickers (with expiries and strikes that fall in 2 SD from underlying)
      * option greeks
      * expected price (adjusted for premiums / penalties and base decimals)
      * return-on-margin (rom)
* Adjusts days-to-expire for last day option expiries
   
## 02_nse_manage

* Reads the account summary
* Harvests open option positions from a linest curve
* Prepares to Sow
   * Checks available funds
   * Makes a *blacklist* (existing positions which have run over position limit)
   * Focuses on Puts
      * with Strikes above the mean
   * Filters based on expected rom
   * Checks consumption of funds
 * Places Harvests (closing trades) and Sows (Opening Trades)
 * Records
   