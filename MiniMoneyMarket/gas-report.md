# Gas Report

## InterestRateModel Tests
- `testBaseRate()`: 11,048 gas
- `testFullUtilizationRate()`: 11,904 gas
- `testHalfUtilizationRate()`: 12,065 gas

## LendingPool Tests
- `testDeposit()`: 151,522 gas
- `testWithdraw()`: 175,309 gas
- `testBorrowAndRepay()`: 256,056 gas

## Liquidation Test
- `testLiquidation()`: 183,050 gas

### Observations
- Borrow/repay is the most expensive operation
- Deposit/withdraw are reasonably optimized
- Liquidation logic is gas-heavy due to oracle and account data checks