# Ich schaffe das — German A1 iPhone test app

A swipe-up course with grammar explanations, vocabulary practice, and quizzes. On an unfinished lesson card, swiping up marks it complete and advances. Quiz cards require a correct answer. There is no login and no AI is used while studying.

## Home screen and progress

Enter a profile name the first time, or tap a saved name to continue. The app saves course progress and preferences separately for each profile on this device. A1 is the only available course at first, with 35 lessons, 1,406 activities, and 402 vocabulary entries. A1+ Revision is a separate continuation with 14 lessons, 145 activities, and 208 vocabulary entries. It stays greyed out until that profile completes A1; it does not duplicate the A1 lesson set.

## YouTube Reels

Enter comma-separated interests such as German, travel, or football. The toggle controls whether a session includes videos. With Reels enabled, sessions begin with three bundled public YouTube Shorts; another appears after every four learning cards. Videos play inside the card. They may repeat, and some creators prevent embedding. This is a small test catalog, not your YouTube feed or a live keyword search. No YouTube account or API key is needed.

## A1+ Revision transcript coverage

The longer [A1+ video](https://www.youtube.com/watch?v=-KdGfbgL6sg) transcript supplied for this build contains 868 timestamp markers. The source archive maps every marker in order across 14 revision lessons. Lessons review and extend pronunciation and greetings; articles, gender, plurals, numbers and dates; present tense and sentence order; questions, negation and time; modal and separable verbs; past forms and Perfekt; accusative and possessives; dative and prepositions; comparisons and demonstratives; imperatives; and everyday themes including routines, cafés, housing, work, travel, shopping, clothing, weather and health.

The app lessons use original instructional wording and examples rather than copied transcript text. Timestamp mapping verifies chapter placement; it is not a word-for-word transcript audit. The supplied [A1 video](https://www.youtube.com/watch?v=0emzztSmKjA) also has a minute-by-minute coverage map. The course is not a reproduction of Netzwerk neu A1; checking exact textbook coverage still requires the materials. Listening and speaking assessment are still pending.

## Install the test IPA

Open the [v5 build](https://github.com/prashanttalreja1985-boop/ich-schaffe-das-a1-test/actions/workflows/build-ipa.yml), choose the newest successful run, and download the `ich-schaffe-das-a1-v5-unsigned-ipa` artifact. Unzip it, then select `Ich-schaffe-das-A1-v5-unsigned.ipa` in Sideloadly. Sideloadly signs this unsigned test IPA with your Apple ID for installation.

## Source and database

The [v5 source ZIP](ich-schaffe-das-a1-source-v5.zip) contains the Flutter app, separately bundled A1 and A1+ Revision courses, Shorts catalog, coverage maps, validation code, optional Supabase schema, and book importer. The A1+ import uses the separate `ich-schaffe-das-a1-plus` book slug in the normalized Supabase course tables. It remains a draft and has not been deployed. The IPA reads bundled content and saves profiles and progress locally; it has no Supabase credentials.