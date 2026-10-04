# Firebase 10.24.0 compatibility package

Tag `10.24.0-thecut.1` is based on upstream Firebase `10.24.0` (commit `42eae77a0af79e9c3f41df04a23c76f05cfdda77`). The only SDK change is a manifest range widening for `interop-ios-for-google-sdks`, from `100.0.0..<101.0.0` to `100.0.0..<102.0.0`.

This permits reCAPTCHA Enterprise 18.9.1, which requires Interop 101.0.0. CocoaPods previously resolved that Interop version independently. Upstream Firebase's Interop constraint comes from Firebase Auth, which theCut does not link.

The intended product set is FirebaseAnalytics, FirebaseCrashlytics, FirebaseDynamicLinks, and FirebasePerformance. Their target dependency closure does not include FirebaseAuth or RecaptchaInterop. SDK runtime sources, binary URLs, and checksums are unchanged. This compatibility package does not certify Firebase Auth against Interop 101.

Use an exact package tag and the workspace Package.resolved. Remove the fork when the application's Firebase upgrade permits the upstream reCAPTCHA dependency range.
