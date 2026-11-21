# Hair AI — Android APK build pack (V2)

This pack contains the Flutter prototype plus an Android permission template and a GitHub Actions workflow to build a release APK in the cloud.

## Contents
- `lib/main.dart`: camera preview, face detection and prototype overlay
- `pubspec.yaml`: Flutter dependencies
- `android_templates/AndroidManifest.xml`: camera permission template
- `.github/workflows/build-apk.yml`: cloud APK build workflow

## Build locally
1. Install Flutter stable and Android Studio on a computer.
2. Extract the ZIP and open a terminal in this folder.
3. Run `flutter create . --platforms android` to generate platform files.
4. Replace `android/app/src/main/AndroidManifest.xml` with the template from `android_templates/`.
5. Run `flutter pub get`.
6. Connect an Android device with USB debugging enabled or use an emulator.
7. Run `flutter run`.
8. To build APK: `flutter build apk --release`.

## Build using GitHub Actions (computer needed for initial setup)
1. Create a GitHub repository and upload these project files.
2. Ensure the workflow file `.github/workflows/build-apk.yml` is in the repository.
3. Open the repository's Actions tab and select `Build Hair AI APK`.
4. Run workflow (or push to main). Wait for the job to finish.
5. Download `hair-ai-apk` from the workflow artifacts.

## Important
- This is a prototype, not yet a realistic hair simulation. The overlay is a stylized graphic anchored to a detected face bounding box.
- The recommendation dialog is a placeholder and does not yet perform reliable face-shape classification.
- Face detection uses ML Kit; no facial image upload is configured in this prototype.
- Generated Android platform files and APK require Flutter/Android build tooling; this pack does not include a precompiled APK.
