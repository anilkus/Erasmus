# Erasmus+ Rotam

An interactive quiz and route finder built for Erasmus+ info sessions at Yozgat Bozok University, Boğazlıyan Vocational School (MYO).

Students join from their phones by scanning a QR code, compete in a short Erasmus+ quiz, and see their names climb a live leaderboard. As a reward, they get a personalised Erasmus+ route: the countries that fit their program and interests, what they can do there, career opportunities, and real institutions where they could do an internship or study.

**Live site:** https://anilkus.github.io/Erasmus/
**Projector view:** https://anilkus.github.io/Erasmus/?ekran

## Features

- **Quiz game:** 10 random questions from a pool of 20, 15 seconds each. Correct answers earn 500 points plus a speed bonus of up to 500.
- **Live leaderboard:** shown on the home page, on the results screen and on a full-screen projector view with a podium for the top three.
- **Route finder:** matches students to Erasmus+ countries based on their program and interests (technology, nature, sea, budget and more).
- **Institution suggestions:** pulls companies, clinics, labs, workshops, universities and colleges from OpenStreetMap for the selected city.
- **What you can do / career paths:** short, program-specific guidance for each department.
- **Apply button:** links to the Boğazlıyan MYO Exchange Programmes Office page.

## Programs covered

Bilgisayar Programcılığı, Büyük Veri Analistliği, Elektronik Teknolojisi, Gıda Teknolojisi, Laborant ve Veteriner Sağlık, Ormancılık ve Orman Ürünleri, Mimari Restorasyon.

## How to run an event

1. Open the projector view (`?ekran`) on the classroom screen.
2. Students scan the QR code and play on their phones.
3. Scores appear live as soon as each student finishes.

To start a fresh leaderboard for a new event, add a session name to both links, for example `?oturum=aralik` for students and `?ekran&oturum=aralik` for the projector.

## Setup

The whole app is a single `index.html` file with no build step. It is hosted on GitHub Pages (Settings → Pages → Deploy from branch `main`).

Scores are stored in a Firebase Realtime Database through its REST API. To use your own database, set `DB_URL` near the top of the script. If `DB_URL` is empty, the app runs in test mode and keeps scores only on the current device.

Other settings you may want to edit, all at the top of the script:

| Setting | What it does |
| --- | --- |
| `APPLY_URL` | Target of the Apply buttons |
| `QUESTIONS` | Quiz question pool (the first option is the correct one) |
| `PROGRAMS` | Departments, matching countries, tasks, careers and OpenStreetMap tags |
| `COUNTRIES` | Erasmus+ countries, interest tags and cities |
| `Q_TIME`, `Q_COUNT` | Seconds per question and number of questions |

## Free APIs used

- [OpenStreetMap Overpass API](https://overpass-api.de) for institutions
- [REST Countries](https://restcountries.com) for country facts
- [flagcdn](https://flagcdn.com) for flags
- [QR Server](https://goqr.me/api/) for QR codes
- [Firebase Realtime Database](https://firebase.google.com/products/realtime-database) for the leaderboard

## Note

Institutions are listed for inspiration only and are not necessarily Erasmus+ partners. Students should contact the unit Erasmus coordinator before applying.

## Contact

Öğr. Gör. Anıl Kuş, Erasmus+ Unit Representative, Boğazlıyan MYO
anil.kus@yobu.edu.tr

Map and institution data © OpenStreetMap contributors.
