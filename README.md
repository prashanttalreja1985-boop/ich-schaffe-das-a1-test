# Ich schaffe das — iPhone A1 test app

This Flutter app opens on a dark Google sign-in page. Google sign-in and sign-up use the same OAuth button. After authentication, a new account begins at A1 lesson 1; a returning account opens its first unfinished card. Completing A1 automatically opens the separate A1+ Revision course. There is no home screen, local profile picker, anonymous session, or AI call during study.

The learner's Supabase Auth UUID is the key for completed cards, quiz attempts, game levels, points, and device preferences. Supabase's `learner_activity_progress`, `learner_answers`, `learner_game_progress`, and `learner_score_events` tables hold progress. The legacy `learner_profiles` table has been removed. A one-time device migration clears old named-profile progress and settings. Existing anonymous accounts and their progress were deleted from Deutsch before this release.

Tap the initial at the top right of a card for settings, monthly leaders, personal points, YouTube interests, game settings, and sign-out. Four Shorts open each session when enabled. After every four learning cards a Short or game appears, with up to four game breaks per lesson. The wooden-plank and Lines puzzles each have 20 levels. Shorts are found through keyword search using the YouTube Data API key injected by the build; the key is not in this source archive. The Google OAuth secret stays in Deutsch Supabase.

In v32, unanswered quiz cards follow an upward drag and spring back with a brief amber hint. Correct answers wait half a second, pull down, then advance upward. Short swipes are captured across the video area. The monthly leaderboard shows Google display names to signed-in learners.

A1 contains 10 topic-based lessons with 1,406 activities. A1+ Revision contains 14 lessons with 145 activities, bundled in the IPA as a continuation. Book, lesson, and activity rows use IDs, sequence numbers, content kinds, and JSON payloads; each kind uses a preset card renderer. The app reads published content and the lexicon from Deutsch Supabase and uses bundled content offline. A1+ is currently a draft database book, so its bundled copy is used until publication.

Google OAuth is currently in test mode and only Google accounts listed as test users in its Cloud project can authenticate. The OAuth redirect is `de.ichschaffedas.a1://login-callback/`. This IPA is unsigned for Sideloadly to sign with the installer's Apple ID. To add Facebook or Apple later, enable their Supabase providers and expand the sign-in gate; the account-based progress schema is already suitable.

## Install this test build

Open the [GitHub Actions build](https://github.com/prashanttalreja1985-boop/ich-schaffe-das-a1-test/actions/workflows/build-ipa.yml), download the newest successful `ich-schaffe-das-a1-v32-unsigned-ipa` artifact, unzip it, and select `Ich-schaffe-das-A1-v32-unsigned.ipa` in Sideloadly. The [v32 source archive](ich-schaffe-das-a1-source-v32.zip) contains the app and database migrations.
