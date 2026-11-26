# World Quiz Run

Host-led country quiz (Jordan, Morocco, Algeria, France, South Africa, Egypt, Turkey)
with a hidden Algeria reveal and a NAL CLUSTER flag finale.

The whole game is one file: `docs/index.html`. No build step, no server, no database.

## Option A — GitHub Pages (free)

1. Create a new repository on github.com (e.g. `world-quiz-run`). Public repos get Pages for free.
2. On the repo page click **Add file → Upload files**, drag in the `docs` folder and the other files, then **Commit changes**.
3. Go to **Settings → Pages**. Under **Build and deployment** choose **Deploy from a branch**, branch **main**, folder **/docs**, then **Save**.
4. Wait about 1 minute and refresh the Pages settings to see the link.
5. Your game is live at `https://<your-username>.github.io/world-quiz-run/`

To update: edit `docs/index.html` on GitHub (pencil icon) and commit — it redeploys by itself.

## Option B — Firebase Hosting (free Spark plan)

1. Go to console.firebase.google.com → **Add project** (Google Analytics not needed).
2. Copy the project ID and put it in `.firebaserc` instead of `your-firebase-project-id`.
3. Install Node.js (nodejs.org), then in a terminal inside this folder run:

   ```
   npm install -g firebase-tools
   firebase login
   firebase deploy --only hosting
   ```

4. Your game is live at `https://<project-id>.web.app`

To update: edit `docs/index.html` and run `firebase deploy --only hosting` again.

## Notes

- The Schneider Electric logo is uploaded from the setup screen and remembered only in that browser.
  To make it permanent, put the logo file in `docs/` (e.g. `docs/logo.png`) and ask for the page to load it.
- Works best on a laptop connected to a projector. Space/Enter = next step, keys 1–8 = mark teams correct.
