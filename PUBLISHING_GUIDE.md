# Publish the SleepGate legal site for free

The finished site contains:

- `privacy.html` — URL for Google Play Console and the in-app Privacy Policy link
- `terms.html` — in-app Terms of Use link
- `index.html` — simple public landing page linking both documents
- `styles.css` — shared mobile-friendly design

## A. Publish with GitHub Pages

1. Sign in at https://github.com.
2. Click the `+` button in the top-right, then **New repository**.
3. Name the repository `sleepgate-legal`.
4. Select **Public** and click **Create repository**.
5. Click **uploading an existing file**.
6. Upload `index.html`, `privacy.html`, `terms.html`, and `styles.css` from this folder. Upload the files themselves, not the enclosing folder.
7. Enter the commit message `Publish SleepGate legal pages`, then click **Commit changes**.
8. Open the repository's **Settings** tab.
9. In the left sidebar, select **Pages**.
10. Under **Build and deployment**, choose **Deploy from a branch**.
11. Select branch `main`, folder `/ (root)`, then click **Save**.
12. Wait a few minutes and refresh the Pages settings screen. GitHub will show the live site URL.

If your GitHub username is `USERNAME`, the expected URLs are:

- Home: `https://USERNAME.github.io/sleepgate-legal/`
- Privacy Policy: `https://USERNAME.github.io/sleepgate-legal/privacy.html`
- Terms: `https://USERNAME.github.io/sleepgate-legal/terms.html`

Open each URL in an incognito/private browser window before using it in Play Console. It must load without signing in.

## B. Put the links inside SleepGate

In **Settings > Legal**, add two normal tappable rows:

- Privacy Policy
- Terms of Use

Open the public HTTPS URL in the device browser or a reliable in-app browser. Do not bundle only a local copy: Google Play requires a public policy URL as well as access within the app.

## C. Google Play Console

1. Open your app in Play Console.
2. Go to **Policy and programs > App content**.
3. Open **Privacy policy** and paste the public `privacy.html` URL.
4. Open **Data safety** and complete the declaration.
5. Open the **AccessibilityService API declaration** and accurately explain the app-blocking feature.
6. Provide the required demonstration video showing:
   - SleepGate opening;
   - the in-app Accessibility disclosure;
   - the user affirmatively accepting it;
   - Android Accessibility settings being opened and SleepGate being enabled;
   - a selected protected app being opened and SleepGate blocking it.

Because SleepGate has no account creation, do not claim that it has user accounts, and an account-deletion webpage is not required for the current build.

## D. Suggested Data Safety answers

These answers are appropriate only after verifying the final release build contains no library or SDK that sends data off-device.

- Does your app collect or share any required user data types? **No**
- Is all user data encrypted in transit? **Not applicable if no user data is transmitted**
- Can users request data deletion? SleepGate stores data locally; users can delete it in-app, clear app storage, or uninstall. Answer Play Console's exact current question truthfully.
- Privacy policy URL: use the public `privacy.html` URL.

Google defines collection for this form as transmitting data off the user's device. On-device processing alone is not collection for the Data Safety form. However, inspect every dependency in the final app bundle before selecting **No**. Crash reporting, analytics, advertising, remote configuration, authentication and some SDKs can transmit data even when you do not maintain your own server.

## E. Required in-app Accessibility disclosure

Show this as a dedicated screen/dialog immediately before taking the user to Android Accessibility settings. Do not hide it only in the Privacy Policy.

**Title:** Allow app blocking

**Body:** SleepGate uses Android Accessibility access to detect when you open an app you chose to protect and to show the blocking screen during an active protection session. App activity is processed on your device and is not sent to Ronit Parikh or a SleepGate server. SleepGate does not use this access to read passwords, messages, typed text or screen contents.

Buttons:

- `Continue`
- `Not now`

Only open Android Accessibility settings after the user taps **Continue**. Do not enable access automatically or use an auto-dismissing disclosure.

## F. Final verification before release

- Developer name in the Play listing is `Ronit Parikh`, matching the policy.
- App name is `SleepGate`, matching the policy.
- Support email is `ronitparikh15@gmail.com` and is monitored.
- Privacy URL works globally over HTTPS without login.
- Privacy page is HTML, not a PDF or editable cloud document.
- Privacy link is visible inside the app.
- Accessibility disclosure appears before the Android settings screen.
- The app does not describe itself as an accessibility tool.
- The Play Console Accessibility declaration and video match the actual app.
- The Data Safety answers match every dependency in the final Android App Bundle.
- If analytics, crash reporting, ads, accounts, cloud sync, payments or another SDK is added later, update the app, policy and Data Safety form before release.

## Important accuracy note

These files are written for the data practices supplied on 31 July 2026: no login, no account, no analytics, no advertising, and SleepGate records stored locally. Before publishing, compare the statements with the final `AndroidManifest.xml`, Gradle dependencies and release App Bundle. Legal and platform-policy compliance depends on the app's real behavior, not only the text of this site.
