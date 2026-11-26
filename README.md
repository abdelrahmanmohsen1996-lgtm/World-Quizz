# World Quiz Run

Country quiz (Jordan, Morocco, Algeria, France, South Africa, Egypt, Turkey)
with phone play for teams, a hidden Algeria reveal and a NAL CLUSTER flag finale.

- `docs/index.html` — host screen (laptop + projector)
- `docs/play.html` — player screen (phones), opened at `/play`

## One-time Firebase setup

1. console.firebase.google.com → open project **world-quizz-9c9be**.
2. Left menu → **Build → Realtime Database → Create Database**.
   Pick a location (Belgium/europe-west1 is closest to Egypt) → **Start in locked mode** → Enable.
   (The included `database.rules.json` opens just the game data when you deploy.)
3. Project Overview → click the **</>** (Web) icon → name it `quiz` → **Register app**
   (no need to copy the code; Firebase Hosting fills it in automatically).

## Deploy (Mac Terminal)

```
cd <drag the world-quiz-run folder here>
npx firebase-tools login
npx firebase-tools deploy --only hosting,database
```

- Host screen: https://world-quizz-9c9be.web.app
- Players:     https://world-quizz-9c9be.web.app/play (also shown as a QR code)

## Running the game

1. Open the host link on the projector laptop, enter team names, press **Board the flight**.
2. Players scan the QR and pick their team. The lobby shows how many phones joined each team.
3. Press **Start the game**. The big screen shows NAL CLUSTER with each team's name on its flag spots.
4. Each team answers its own questions on their phones, at their own pace. Wrong answer → try again
   (100 pts first try, 70 second, 40 third, 20 after). Right answer → the flag replaces the team name on the big screen.
5. When every flag is revealed, press **Final results** → leaderboard → Algeria reveal → finished cluster.
   **End game now** (tap twice) stops early.

Question split: with N teams, team 1 gets questions 1, 1+N, 1+2N…, team 2 gets 2, 2+N… (see the answer key).

Host keys: Space/Enter next step · 1–8 toggle team · N show/hide NAL CLUSTER · T edit teams.

Without the database (e.g. opened as a plain file) the host screen still works on its own, scored by tapping teams.

Note: the database rules let anyone with the link read/write the game data — fine for an event,
and refreshing the host screen starts a fresh game.
