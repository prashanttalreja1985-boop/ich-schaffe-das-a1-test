# Ich schaffe das — German A1 iPhone test app

A swipe-up course with grammar explanations, vocabulary practice, and quizzes. On an unfinished lesson card, swiping up marks it complete and advances. Quiz cards require a correct answer. There is no login and no AI is used while studying.

## Home screen and progress

Enter a profile name to keep your place, or tap a saved name to continue. Choose A1 or A1+. Progress and answer attempts are saved separately by profile and course on this device. A1 contains 35 ordered lessons, 1,406 activities, and 402 vocabulary entries. A1+ contains that baseline plus 14 original transcript-aligned chapter lessons: 49 lessons, 1,551 activities, and 618 vocabulary entries.

Enter comma-separated Shorts interests such as German, travel, or football. These rank six bundled public YouTube Shorts. Each session begins with three Shorts; another appears after every four learning cards. Videos play inside the card. They may repeat, and some creators prevent embedding. This is a small test catalog, not your YouTube feed or a live keyword search. No YouTube account or API key is needed.

## A1+ transcript coverage

The longer [A1+ video](https://www.youtube.com/watch?v=-KdGfbgL6sg) transcript supplied for this build contains 868 timestamp markers. The source archive maps every marker in order across 14 chapter lessons. Lessons cover pronunciation and greetings; articles, gender, plurals, numbers and dates; present tense and sentence order; questions, negation and time; modal and separable verbs; past forms and Perfekt; accusative and possessives; dative and prepositions; comparisons and demonstratives; imperatives; and everyday themes including routines, cafés, housing, work, travel, shopping, clothing, weather and health.

The app lessons are written in original instructional wording and examples, not copied verbatim from the transcript. Timestamp mapping verifies chapter placement; it is not a word-for-word transcript audit. The supplied [A1 video](https://www.youtube.com/watch?v=0emzztSmKjA) also has a minute-by-minute coverage map. The course is not a reproduction of Netzwerk neu A1; checking exact textbook coverage still requires the materials. Listening and speaking assessment are still pending.

## Install the test IPA

Open the [v4 build](https://github.com/prashanttalreja1985-boop/ich-schaffe-das-a1-test/actions/workflows/build-ipa.yml), choose the newest successful run, and download the `ich-schaffe-das-a1-v4-unsigned-ipa` artifact. Unzip it, then select `Ich-schaffe-das-A1-v4-unsigned.ipa` in Sideloadly. Sideloadly signs this unsigned test IPA with your Apple ID for installation.

## Source and database

The [v4 source ZIP](ich-schaffe-das-a1-source-v4.zip) contains the Flutter app, bundled courses, Shorts catalog, coverage maps, validation code, optional Supabase schema, and book importer. This IPA reads bundled content and saves profiles and progress locally; it has no Supabase credentials. The A1+ database import is a draft and has not been deployed.
