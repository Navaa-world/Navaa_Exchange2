# NAVAA Exchange UI (GitHub Pages starter)

## What this is
A static HTML front end for the deployed Polygon exchange and NAVAA token addresses. It includes:
- Buy/sell amount calculators based on on-chain `quoteBuy` / `quoteSell`
- Polygon wallet connection and chain switching
- Automatic 0.2% fee display
- Automatic deadline and minimum-output calculations with user-selected slippage
- NAVAA approval flow before selling
- POL/NAVAA reserve checks and indicative POL/INR reference
- Owner dashboard for rates, fee wallet, POL deposit/withdrawal, NAVAA withdrawal, pause/unpause

## Deploy on GitHub Pages
1. Create a new GitHub repository, e.g. `navaa-exchange-ui`.
2. Upload `index.html` and this `README.md` to the repository root.
3. Open repository **Settings → Pages**.
4. Under Build and deployment, choose **Deploy from a branch**.
5. Choose branch `main` and folder `/ (root)`, then Save.
6. Wait for GitHub Pages to publish the site. Open the Pages URL in a wallet-enabled browser.

## Important
- Polygon Mainnet chain ID is 137.
- Contract addresses are hardcoded in `index.html`:
  - Exchange: `0xf31f82837b89f4d9a37b8e700cb175893766dd8f`
  - NAVAA token: `0x82dba663278ADF0c398c1795a31760c7a76CA932`
- This starter assumes the deployed exchange ABI matches the Solidity source supplied by the user.
- Before real public use, test on a separate test deployment / testnet, inspect actual verified ABI and deployed bytecode, and have the contract independently reviewed. This UI cannot fix a contract bug or guarantee a trade.
- Only the owner wallet sees the owner dashboard. The contract itself enforces owner-only permissions.
- `approve` gives the exchange permission to transfer the approved NAVAA amount from the connected wallet.
- POL/INR reference uses CoinGecko's public endpoint and may be unavailable/rate-limited.
- Do not enter a seed phrase or private key on the site. Wallet connection should happen only through your wallet.


RPC note: The frontend uses the Polygon Mainnet RPC endpoint `https://polygon.drpc.org` for read-only contract data. Polygon Mainnet chain ID remains 137.
