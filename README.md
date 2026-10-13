# Ich schaffe das — A1 test app

A swipe-up German lesson app for iPhone. It has no login screen and does not call
an AI service while a learner uses it. Grammar cards come first, then vocabulary,
then quizzes. A card unlocks the next one when completed; quizzes require a correct
answer. The app reopens at the first unfinished card.

## Current content status

`assets/starter_content.json` contains **original sample content only**: two short
A1 lessons and eight activities. It is not a reproduction of *Netzwerk neu A1* and
does not yet cover the complete book or A1 syllabus. After the book's edition,
table of contents, and usable source material are supplied, build a coverage map
for every lesson, grammar point, vocabulary set, and exercise goal. Review that map
against the source before marking the book `published`. Use original explanations
and questions unless you have the rights to reproduce the book's text and layout.

## Content and progress

- Without Supabase configuration, the app loads the bundled starter JSON and saves
  completed cards on the device with SharedPreferences.
- With Supabase configuration, it reads a published book, ordered lessons, and
  ordered activities from database tables. It silently creates a Supabase anonymous
  user so progress and answer attempts are private to that installation. There is
  no account UI. Removing the app or its data can make anonymous progress
  unrecoverable; cross-device recovery needs a later account-linking feature.
- `supabase/schema.sql` creates the tables and row-level policies. Run it in a
  **separate Supabase project** for this app. Enable Anonymous Sign-Ins in Auth.
  Never put a service-role key in the app.
- A book import happens outside the app. Validate a reviewed JSON file and emit SQL:

  ```sh
  python tool/import_book.py assets/starter_content.json tool/starter_import.sql --publish
  ```

  Review and run the emitted SQL in the Supabase SQL editor. Omit `--publish`
  while the coverage audit is incomplete. The importer is idempotent for known
  books, lessons, and activities, but deletion of removed content is a separate
  editorial step. Existing learner progress uses stable activity slugs.

## Build an IPA for Sideloadly

iOS builds require Xcode on macOS. The repository's
`.github/workflows/ich-schaffe-das-ipa.yml` runs the iOS build on a GitHub macOS
runner and uploads `Ich-schaffe-das-A1-unsigned.ipa`. Sideloadly can sign the IPA
with your Apple ID when installing it. Trigger the workflow manually from GitHub
Actions, or push changes under `learning_app/`.

For the bundled starter course, leave the workflow variables unset. For a published
Supabase course, set repository variables `LEARNING_SUPABASE_URL` and
`LEARNING_SUPABASE_PUBLISHABLE_KEY`, and publish the course under slug
`netzwerk-neu-a1`. Then run the workflow and download its artifact. The build
embeds only the public project URL and publishable key.

Locally on a Mac:

```sh
flutter pub get
flutter analyze
flutter test
flutter build ios --release --no-codesign
mkdir -p build/ipa/Payload
cp -R build/ios/iphoneos/Runner.app build/ipa/Payload/
(cd build/ipa && zip -qr Ich-schaffe-das-A1-unsigned.ipa Payload)
```

This is a testing package, not an App Store signed distribution. The iOS bundle ID
is `de.ichschaffedas.a1` and the display name is **Ich schaffe das**.
