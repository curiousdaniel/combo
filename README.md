
# AuctionMethod Bidder Sandbox

Single-file demo for SIMU-OR and MISU (OR/XOR) with real-time WL/DL and exact winners.
Preloads the first 48 West Auctions lots from your CSV. Styled with AuctionMethod colors.

## Run locally
Open `index.html` in Chrome/Edge/Safari. No build step required.

## Deploy to GitHub Pages
1. Create a new **public** repo, e.g. `auctionmethod-sandbox`.
2. Upload two files from this zip: `index.html` and `README.md` (drag-and-drop on GitHub works).
3. Go to **Settings → Pages**.
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` (or `master`) - `/root`
   - Save.
4. Wait ~30 seconds. Your site will be live at:  
   `https://<your-username>.github.io/<repo-name>/`

### Optional: custom domain
- Add your domain under **Settings → Pages → Custom domain**.
- Create a `CNAME` DNS record pointing to `<your-username>.github.io`.
- You can also commit a `CNAME` file (contents: your domain) at the repo root for persistence.

## Notes
- All logic is browser-side. No keys, no backend.
- WL/DL math per research:
  - SIMU-OR: WL_k(x) = REV_k(N) − REV_k(N−x); DL_k(x) = min_{i∈[x..N]} REV_k(i) − REV_k(i−x)
  - MISU-OR/XOR: exact winners; WL(S) = REV(U) − REV(U\S{; banned bidder in XOR}); DL(S) = REV(S) or REV_XOR(S; banned bidder)
- If images in the preload don't resolve, it's because the source CSV didn't have public image URLs. The sandbox still works; you can paste your own image URLs into the editor box.
