# MiniMoneyMarket Overview

MiniMoneyMarket is a simplified lending and borrowing protocol built in Solidity. It supports:
- Depositing collateral (ERC20)
- Borrowing stablecoins (USDC)
- Repaying loans
- Withdrawing collateral
- Liquidation logic based on price oracle and LTV
- TWAP (Time-Weighted Average Price) support added to oracle and integrated into lending logic to prevent flash loan manipulation.

Key contracts:
- `LendingPool.sol`: core lending logic
- `CollateralToken.sol`: ERC20 collateral with minting
- `MockUSDC.sol`: borrowable stablecoin
- `PriceOracle.sol`: admin-controlled price feed with TWAP support
- `InterestRateModel.sol`: dynamic interest rate curve

Security tooling used:
- Foundry tests
- Slither static analysis
- Manual audit notes