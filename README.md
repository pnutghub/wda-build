# Build WebDriverAgent without a Mac

GitHub's free macOS machine compiles appium/WebDriverAgent and gives you an unsigned `WDA.ipa`.
Sideloadly signs it with your Apple ID afterwards.

1. On github.com create a **new public repository** (e.g. `wda-build`). Public repos get free macOS minutes.
2. Add the workflow file: in the repo click **Add file > Upload files** and drag in the `.github` folder from here
   (the path must end up as `.github/workflows/build-wda.yml`). If the browser won't take a folder, use
   **Add file > Create new file**, type `.github/workflows/build-wda.yml` as the name, and paste the file's contents.
   Commit.
3. Open the **Actions** tab > **Build WebDriverAgent IPA** > **Run workflow** (leave the ref blank). If GitHub
   asks to enable workflows, enable them.
4. Wait about 5-15 minutes. Open the finished run, scroll to **Artifacts**, download **WDA-ipa**, unzip it to get `WDA.ipa`.
5. Drag `WDA.ipa` into Sideloadly. Done; continue with the main README.

If the build fails on the newest default branch, rerun with a release tag in the ref box (see appium/WebDriverAgent's
Releases page). If the app crashes on launch on your iOS version, try a newer tag or the default branch.

Not yet run: written from the standard xcodebuild recipe, never executed.
