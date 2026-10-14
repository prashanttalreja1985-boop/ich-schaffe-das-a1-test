# Ich schaffe das — German A1 iPhone test app

A swipe-up course with original grammar explanations, vocabulary cards, and quizzes. On an unfinished lesson card, swiping up marks it complete and advances. Quizzes require a correct answer. The app has no login screen and uses no AI while you study.

## Version 3 home screen

Enter a profile name to keep your place, or tap a saved name to continue. Choose A1 or A1+. Progress and answer attempts are saved separately by profile and course on this device. A1 has 35 ordered lessons, 1,406 activities, and 402 vocabulary entries. A1+ is currently a separate draft copy of A1 with independent progress; it is **not** a completed new course.

Enter comma-separated Shorts interests such as German, travel, football. These rank six bundled public YouTube Shorts. Each session begins with three Shorts; another appears after every four learning cards. Videos play inside the card. They may repeat, and a creator can prevent embedding. This is a small test catalog, not your YouTube feed or a live keyword search. No YouTube account or API key is needed.

The A1 course practices der/die/das, noun cases, pronouns, word order, present and perfect forms, modal and separable verbs, questions, time, dates, travel, food, health, work, and other everyday topics. The supplied [55-minute A1 video](https://www.youtube.com/watch?v=0emzztSmKjA) has a minute-by-minute coverage map in the source ZIP. Listening and speaking assessment are still pending. This course is not a reproduction of Netzwerk neu A1; exact book coverage still needs checking against the materials when supplied.

The longer [A1+ video](https://www.youtube.com/watch?v=-KdGfbgL6sg) has no accessible transcript or captions. Its published chapter times are recorded in the source ZIP, but no complete concept coverage is claimed. A transcript or usable course notes are needed before expanding A1+ against that video.

## Install the test IPA

Open the [version 3 build](https://github.com/prashanttalreja1985-boop/ich-schaffe-das-a1-test/actions/workflows/build-ipa.yml), choose the newest successful run, and download the ich-schaffe-das-a1-v3-unsigned-ipa artifact. Unzip it, then select Ich-schaffe-das-A1-v3-unsigned.ipa in Sideloadly. Sideloadly signs this unsigned test IPA with your Apple ID for installation.

## Source and database

The [v3 source ZIP](ich-schaffe-das-a1-source-v3.zip) contains the Flutter app, bundled courses, Shorts catalog, coverage maps, tests, optional Supabase schema and book importer. This IPA reads bundled content and saves profiles and progress locally. It has no Supabase credentials. The A1+ database import is draft only and has not been deployed.
