# ishark

A tiny site that keeps your iPad Pro screen awake while the page is visible.
Just an AI-generated logo and a small status indicator. No build step, external
libraries, analytics, or third-party requests.

## Usage

Open the page over HTTPS. It automatically requests a screen wake lock using the
[Screen Wake Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Wake_Lock_API).
When **Keeping your screen awake** appears, the wake lock is active.
If it fails or is released, tap the logo to retry (or use Enter / Space).

- Use a supported version of iPadOS / Safari and keep the page in the foreground.
- Switching tabs or apps releases the wake lock. Returning to the page automatically
  attempts to acquire it again.
- Power-saving settings or browser / OS decisions may prevent or release the lock.
- Manual screen locking still works. Close the page or switch to another tab or app
  to stop keeping the screen awake.

## GitHub Pages

1. Push this repository to GitHub with `main` as the default branch.
2. Under **Settings → Pages → Build and deployment**, choose **GitHub Actions**.
3. Run **Deploy to GitHub Pages** from the Actions tab for the initial deployment.

The workflow deploys only `public/`. Later changes to `public/` or the workflow
on `main` deploy automatically. No build step is needed.
The README, license, and local development files stay outside the published site
directory.

## Local preview

From the repository root, run:

```sh
python3 -m http.server 8000 --directory public
```

Open <http://localhost:8000>. Screen Wake Lock requires a secure context, such as
HTTPS or localhost.

## Files

```text
.github/workflows/pages.yml  # GitHub Pages deployment
public/
  index.html  # HTML, CSS, and JavaScript in one page
  logo.png    # AI-generated transparent logo
LICENSE       # MIT license
README.md
```

## Logo

Created with OpenAI's built-in image generation tool.
Prompt: a minimal logo for ishark, a tool that keeps an iPad screen awake.
A curved shark silhouette and the lowercase wordmark `ishark`, in pale icy blue
on a transparent background, readable on dark navy, with no ornamentation.

## License

[MIT](LICENSE)
