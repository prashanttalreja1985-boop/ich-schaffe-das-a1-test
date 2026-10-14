# Ich schaffe das — German A1 iPhone test app

A swipe-up course with grammar explanations, vocabulary practice, and quizzes. On an unfinished lesson card, swiping up marks it complete and advances. Quiz cards require a correct answer. There is no login and no AI is used while studying.

## Home screen and progress

Enter a profile name the first time, or tap a saved name to continue. YouTube and Games settings are in separate collapsible sections. The app saves preferences separately for each profile. A1 is the only available course at first, with 10 topic-based lessons, 1,406 activities, and 402 vocabulary entries. Lessons cover introductions and sounds; people, nouns and articles; verbs and routines; time and appointments; food, shopping and home; city and travel; work and plans; clothes, health and weather; past events and writing; and requests plus a full review. A1+ Revision is a separate continuation with 14 lessons, 145 activities, and 208 vocabulary entries. It stays greyed out until that profile completes A1; it does not duplicate the A1 lesson set.

## YouTube Reels

Enter comma-separated interests such as travel, football, or cooking. The toggle controls whether a session includes videos. With Reels enabled alone, up to three matching Shorts appear at the start; another appears after every four learning cards. When Games is enabled too, break cards mix Shorts and games. Only videos matching an entered interest are shown. An empty interest list or a keyword with no catalog match shows no videos. Videos play inside the card. They may repeat, and some creators prevent embedding. This is a small test catalog, not your YouTube feed or a live keyword search. No YouTube account or API key is needed.

## Games

The Games section contains two puzzles with 20 levels each: a wooden-plank escape puzzle and a color-territory puzzle. With Games enabled, each lesson includes at least two game-level breaks. The game uses saved profile progress to unlock levels in order; progress is stored locally and synced to the Deutsch project when anonymous Supabase access is available.

## A1+ Revision transcript coverage

The longer [A1+ video](https://www.youtube.com/watch?v=-KdGfbgL6sg) transcript supplied for this build contains 868 timestamp markers. The source archive maps every marker in order across 14 revision lessons. Lessons review and extend pronunciation and greetings; articles, gender, plurals, numbers and dates; present tense and sentence order; questions, negation and time; modal and separable verbs; past forms and Perfekt; accusative and possessives; dative and prepositions; comparisons and demonstratives; imperatives; and everyday themes including routines, cafés, housing, work, travel, shopping, clothing, weather and health.

The app lessons use original instructional wording and examples rather than copied transcript text. Timestamp mapping verifies chapter placement; it is not a word-for-word transcript audit. The supplied [A1 video](https://www.youtube.com/watch?v=0emzztSmKjA) also has a minute-by-minute coverage map. The course is not a reproduction of Netzwerk neu A1; checking exact textbook coverage still requires the materials. Listening and speaking assessment are still pending.

## Install the test IPA

Open the [IPA build](https://github.com/prashanttalreja1985-boop/ich-schaffe-das-a1-test/actions/workflows/build-ipa.yml), choose the newest successful run, and download the `ich-schaffe-das-a1-v11-unsigned-ipa` artifact. Unzip it, then select `Ich-schaffe-das-A1-v11-unsigned.ipa` in Sideloadly. Sideloadly signs this unsigned test IPA with your Apple ID for installation.

## Source and database

The [v11 source ZIP](ich-schaffe-das-a1-source-v11.zip) contains the Flutter app, 10-lesson A1 and separate A1+ Revision courses, Shorts catalog, games, coverage maps, lexicon, validation code, Supabase schema, and content importers. Course data uses `learning_books`, `learning_lessons`, and `learning_activities`; each activity has its own ID, lesson ID, `sequence_number`, `kind`, and JSON payload. The app selects its preset grammar, vocabulary, or quiz card by `kind`. Noun and verb meanings and forms are stored per book slug in `learning_lexicon`. A1 is published in the **Deutsch** Supabase project; the separate A1+ course remains a draft. Card completion and quiz attempts use `learner_activity_progress` and `learner_answers`. `learner_game_progress` keeps each profile's highest unlocked level for each puzzle. All learner tables use RLS by anonymous Supabase user ID. The IPA reads published lessons and the lexicon from Supabase, falls back to bundled course data offline, and has no account screen. Anonymous progress is tied to that app install; it does not transfer to another device.

## Card interactions

Cards show both the lesson number and the card's position within that lesson.
Long-press an amber noun or green verb to open its meaning in a dark green
popover near the word. Tapping a word in a quiz option still selects the option.
Vertical swipes over a Shorts video advance or return to the adjacent card.

## Content review flags

Every lesson card has a flag button. Flags are saved on the device for the
current profile and sent to `learning_content_flags` in Deutsch without requiring
a learner login. Supabase stores one open review item per course activity with
its flag time and an `open` or `fixed` status. If the network is unavailable,
the app keeps the local flag and reports that it could not sync.
