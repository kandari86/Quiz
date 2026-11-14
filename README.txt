MATH LEVELS — Web App (PWA)
===========================

This folder IS the app. Files:
  index.html      - the whole app (screens, styling, logic)
  manifest.json   - app name / icon / colours (makes it installable)
  sw.js           - service worker (makes it work offline)
  icon-192.png    - home-screen icon
  icon-512.png    - home-screen icon (large)

16 LEVELS, TWO TIERS
  Levels 1-12  - arithmetic drills (10 questions each). Type the answer
                 on the keypad; fractions use tap-to-choose.
  Levels 13-16 - ADVANCED tier (20 questions each), all multiple choice:
                 13 Number Sense   - comparing fractions, mental maths, LCM/HCF
                 14 Real-World     - percentages, ratios, averages, discount+tax
                 15 Algebra        - solving for x, patterns, word equations
                 16 Aptitude       - speed/distance/time, work, trains, pipes

  Pass mark is 80% (8/10 or 16/20). 10/10 (or 20/20) = 3 stars.

TIMER
  Each question has a countdown, and the time grows as the levels get
  harder (about 12s at Level 1, rising to about 75s at Level 16), plus a
  small bonus on longer questions for reading time. The bar turns amber
  then red as time runs out. If it reaches zero, the question is marked
  wrong and the correct answer + worked solution are shown, just like a
  wrong answer. You can switch the timer off on the home screen.

ANSWER + EXPLANATION
  Get a question wrong (or run out of time) and the app shows the correct
  answer AND a short worked solution ("how to solve it"), then waits for
  you to tap Next. Correct answers move on quickly by themselves.

TRY IT ON YOUR PC
  1. Double-click index.html. It opens in your browser.
  2. Play a level to check it works.
  (Installing to your iPhone home screen needs the app hosted online.)

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

UPDATING AN ALREADY-INSTALLED APP
  Re-upload the changed files (Add file -> Upload files -> Commit). If the
  phone still shows the old version, open sw.js and bump the cache name
  (for example, "mathlevels-v6" -> "mathlevels-v7"), re-upload, and reopen the app.

MAKE IT YOURS
  - Colours: edit the :root values at the top of index.html
  - Levels/questions: edit the LEVELS list in the <script> tag. Each level
    has a gen() function returning { prompt, answer, choices, explain }.
    `choices: null` = number keypad; an array = multiple choice.
  - Timer lengths: edit the TIME_PER_LEVEL table in index.html.
  - Pass mark / questions: PASS_RATIO, and each level's `count`.

TROUBLESHOOTING
  - "Add to Home Screen" makes a bookmark: the app must be on an
    https:// address (GitHub Pages provides one), and all 5 files must
    be in the repository root.
  - Phone shows an old version after an edit: bump the cache name in sw.js.
