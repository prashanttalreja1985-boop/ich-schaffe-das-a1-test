# Ich schaffe das — A1 test IPA

This iPhone test app uses Google sign-in and opens the learner's first unfinished A1 card. Completing A1 opens the separate A1+ revision course. Lesson text, vocabulary, questions, answers, points, flags, and progress are unchanged. The feed now contains learning cards only; YouTube Shorts and games have been removed.

All 1,406 A1 cards and 145 A1+ revision cards have animated visual scenes: a background, a character with four poses, a prop, and a short line from the card. The scene assignments live in the Deutsch Supabase `learning_visual_scenes` table and are bundled for offline fallback. The 220 selected images come from ClipStudio's packaged cutout library, which is included in this public test-app source archive. ClipStudio's generated asset cache is on its RunPod volume, not in Supabase. The original lesson payloads have not been edited.

The IPA is unsigned. Download the newest successful `ich-schaffe-das-a1-v33-unsigned-ipa` artifact from [GitHub Actions](https://github.com/prashanttalreja1985-boop/ich-schaffe-das-a1-test/actions/workflows/build-ipa.yml), unzip it, and open `Ich-schaffe-das-A1-v33-unsigned.ipa` in Sideloadly. Google OAuth remains in test mode, so the Google account must be on the Cloud project's test-user list.

The [v33 source archive](ich-schaffe-das-a1-source-v33.zip) contains the Flutter app, packaged cutouts, scene assignments, migration, and tests. The scene-generation script requires the ClipStudio pack as a sibling directory in the local monorepo; it is not run by the public IPA workflow.
