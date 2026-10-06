# Publish the release repository

Create a new **public** GitHub repository named `offerloop-assist-releases`, then push this folder as its own repository. Do not push it as a subfolder of the private application repository.

## Repository preparation

```powershell
cd offerloop-assist-releases
git init
git add README.md INSTALL.md SUPPORT.md PRIVACY.md PUBLISH.md CHANGELOG.md .gitignore release-assets screenshots
git commit -m "docs: prepare OfferLoop Assist release repository"
git branch -M main
git remote add origin https://github.com/chitranjanit/offerloop-assist-releases.git
git push -u origin main
```

## Create release `v1.0.0`

Use the GitHub Releases page to create tag `v1.0.0`. Copy the notes from `CHANGELOG.md` and attach:

- `OfferLoop-Assist-Setup-1.0.0-x64.exe`
- `OfferLoop-Assist-Portable-1.0.0-x64.exe`
- `SHA256SUMS.txt`

Do not commit installer binaries into the Git repository. GitHub Release assets are the distribution channel.

## Website configuration

Set this during the website build:

```env
NEXT_PUBLIC_ASSIST_DOWNLOAD_URL=https://github.com/chitranjanit/offerloop-assist-releases/releases/latest/download/OfferLoop-Assist-Setup-1.0.0-x64.exe
```

After publishing, verify the URL in a private browser window and on a clean Windows computer.

## Release gate

- Verify both SHA-256 checksums.
- Confirm no `.env`, logs, source maps, private profiles, API keys, or provider credentials are packaged.
- Test install, uninstall, portable startup, login pairing, audio, screenshot, recharge, and device revocation.
- Sign production installers before unrestricted public distribution.

