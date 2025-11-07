# Security Notes

## ✅ Access Control
- `onlyOwner` used correctly in `PriceOracle` and `CollateralToken`
- LendingPool functions are public but rely on msg.sender/account checks

## ✅ Reentrancy
- No external calls after state changes
- No use of `call` or `delegatecall`
- `SafeERC20` used for token transfers

## ✅ Oracle Manipulation
- TWAP integrated into `PriceOracle` and used in `LendingPool`
- `getTWAP(token, interval)` smooths out short-term price spikes
- All collateral and borrow valuations now use TWAP (30-minute default)

## ✅ Liquidation Logic
- Uses TWAP-based collateral and borrow valuation
- Liquidation threshold and close factor enforced post-accrual
- Liquidation incentive (5%) applied to seized collateral

## ✅ Upgradeability
- Not upgradeable; no proxy pattern used

## ✅ Math Safety
- Uses `uint256` and WAD math
- No unchecked blocks or inline assembly

## ⚠️ Observations
- Oracle is still admin-controlled; decentralization recommended for production
- No circuit breaker or pause mechanism
- No rate limiting or borrow caps