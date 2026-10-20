<h1>HTM TO APK CONVERTOR</h1>

This starter kit lets you build a real **debug APK** for a website URL using GitHub Actions. You can set it up from Chrome on an Android phone.

## What works in this starter kit
- A responsive converter website interface (`website/index.html`)
- A native Android WebView app
- A GitHub Actions workflow that accepts a website URL and app name, builds an APK, and uploads it as a downloadable artifact

## Important limitation
The website form is a front-end demo and does **not** directly trigger the build. For this first milestone, submit the same app name and HTTPS URL in GitHub Actions manually. Do not put a GitHub access token in browser JavaScript. Automatic website-to-build integration requires a secure backend.

## Set it up from your phone

1. Sign in to GitHub in Chrome and create a **new repository**. You can name it `my-first-app-html-to-apk`.
2. Upload the contents of this ZIP to the repository, keeping the folders and paths exactly as shown. (GitHub's website supports **Add file → Upload files**.)
3. Open the repository's **Actions** tab. If prompted, enable GitHub Actions.
4. Open the workflow named **Build Website APK**. Tap **Run workflow**.
5. Enter:
   - **Website URL:** a site you own or have permission to wrap, including `https://` (example: `https://example.com`)
   - **App name:** `My First App`
6. Start the workflow and wait for it to finish successfully.
7. Open the completed run and download the artifact named `my-first-app-apk`. GitHub downloads it as a ZIP. Extract it and install the `.apk` on your Android phone.
8. If Android asks, allow installation from that source. Only install APKs you built or trust.

## Files
- `website/index.html` — converter website interface
- `.github/workflows/build-apk.yml` — cloud build workflow
- `settings.gradle` and `build.gradle` — Gradle project
- `app/` — native Android WebView application

## What the APK does
It opens the URL you supplied in an Android WebView. Internet permission is included. The URL must use HTTPS. The APK is a debug-signed testing build, not a release-signed Play Store build.

## Troubleshooting
- If the Actions tab is missing, confirm the workflow file exists at `.github/workflows/build-apk.yml` on the repository's default branch.
- If the build fails, open the failed run and read the first red error in the logs.
- If a site blocks embedding, requires special browser features, or does not permit WebView use, it may not work correctly.
- This template does not bundle offline HTML/ZIP files yet; it converts a hosted URL only.
