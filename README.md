# Ich schaffe das — German A1 iPhone test app

A swipe-up course with original grammar explanations, vocabulary cards, and quizzes. Swipe up on an unfinished card to complete it and advance. A quiz advances after a correct answer. The app has no login screen and uses no AI while you study.

## A1 course

Version 2 bundles 35 ordered lessons, 1,406 activities, and 402 vocabulary entries. It practices der/die/das, noun cases, pronouns, sentence order, present and perfect verb forms, modal and separable verbs, questions, time, dates, travel, food, health, work, and other everyday topics. Progress from version 1 carries forward on the same device because its first eight activity IDs were retained.

The supplied [55-minute A1 video](https://www.youtube.com/watch?v=0emzztSmKjA) was reviewed minute by minute. The coverage map is in learning_app/tool/video_coverage_0emzztSmKjA.json inside the [v2 source ZIP](ich-schaffe-das-a1-source-v2.zip). The automatic captions mishear some German words, so this course uses corrected original explanations and exercises. The app currently teaches with text; listening and speaking assessment still need a later version.

This is not a copy of Netzwerk neu A1. Its exact lesson order and full vocabulary coverage still need checking against the book materials when supplied.

## Install the test IPA

Open [GitHub Actions](https://github.com/prashanttalreja1985-boop/ich-schaffe-das-a1-test/actions/workflows/build-ipa.yml), choose the newest successful run, and download the ich-schaffe-das-a1-v2-unsigned-ipa artifact. Unzip it, then select Ich-schaffe-das-A1-v2-unsigned.ipa in Sideloadly. Sideloadly signs the unsigned IPA with your Apple ID for installation.

## Build and content

The [workflow](.github/workflows/build-ipa.yml) unpacks the v2 source ZIP, validates the course and video coverage, runs Flutter tests, builds for iOS, and packages an unsigned IPA on a macOS runner. The app currently loads bundled JSON and saves progress and answer attempts locally. Optional Supabase tables, row-level policies, and an offline book importer are included in the source for a later database-backed release. No Supabase credentials are embedded in this test IPA.
