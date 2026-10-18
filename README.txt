MATH LEVELS — Web App (PWA)
===========================

This folder IS the app. Files:
  index.html      - the whole app (screens, styling, logic)
  manifest.json   - app name / icon / colours (makes it installable)
  sw.js           - service worker (makes it work offline)
  icon-192.png    - home-screen icon
  icon-512.png    - home-screen icon (large)

TRY IT ON YOUR PC
  1. Double-click index.html. It opens in your browser.
  2. Play a level to check it works.
  (Opening the file directly is fine for testing. Installing to your
   iPhone home screen needs the app hosted online - see below.)

PUT IT ON YOUR iPHONE (free, no Mac needed)
  1. Make a free account at github.com
  2. New repository -> name it "math-levels" -> Public -> Create.
  3. Add file -> Upload files -> drag in ALL FIVE files above -> Commit.
  4. Settings -> Pages -> Source: "Deploy from a branch",
     Branch: main, Folder: / (root) -> Save.
  5. Wait ~1 minute. Your app is live at:
        https://<your-username>.github.io/math-levels/
  6. On your iPhone, open that link in SAFARI.
  7. Share button -> "Add to Home Screen" -> Add.

It now runs full-screen from your home screen and works offline.

MAKE IT YOURS
  - Colours: edit the :root values at the top of index.html
  - Levels/questions: edit the LEVELS list in the <script> tag
  - Pass mark / number of questions: QUESTIONS_PER_LEVEL, PASS_RATIO

TROUBLESHOOTING
  - "Add to Home Screen" makes a bookmark: the app must be on an
    https:// address (GitHub Pages provides one), and all 5 files must
    be in the repository root.
  - Phone shows an old version after an edit: open sw.js and change
    "mathlevels-v1" to "mathlevels-v2", re-upload, reopen the app.
