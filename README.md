# VMT — Android-ready project

This project is based on the VMT mobile-first finance prototype. It keeps the existing app logic and local storage key (`artha.v1.data`) to avoid orphaning data created in the previous prototype. The visible app name and exported filenames are changed to VMT.

## Current features in the web app
- First-use 4–8 digit passcode setup and lock/unlock; change passcode and lock immediately.
- Dashboard with net balance, monthly income/expenses, savings rate, budgets, category breakdown and recent transactions.
- Add/edit/delete income and expense transactions, date, note, income source/type, expense category/subcategory, payment method and card/account name.
- Calendar with month navigation and daily transaction list.
- Overall and category budgets, edit/delete budgets, progress/overspend indicators.
- Wallet/net balance, savings target, CSV export, multi-sheet XLSX export when the XLSX library is available, JSON backup/restore, legacy JSON import.
- UNI/AXIS and other existing categories/fields present in the starter are retained.
- Phone-first responsive layout and bottom navigation.

## Open in VS Code first
1. Extract this ZIP.
2. Open the `VMT-Android-Ready` folder in VS Code.
3. To preview the web version, install Live Server if needed, then right-click `www/index.html` → Open with Live Server.
4. Test using sample data before importing real records.

## Build as an Android app (Windows)
Install:
- Node.js LTS from https://nodejs.org/
- Android Studio from https://developer.android.com/studio
- Android SDK components offered by Android Studio

Then open VS Code Terminal in this project folder and run:

```powershell
npm install
npx cap add android
npx cap sync android
npx cap open android
```

If `android` already exists, do not run `npx cap add android` again; run `npx cap sync android` and `npx cap open android`.

In Android Studio:
1. Wait for Gradle sync to finish.
2. Connect your Android phone using USB and enable Developer options → USB debugging, or use an emulator.
3. Select your phone and press Run ▶ to install/test the app.
4. To create an APK: Build → Build Bundle(s) / APK(s) → Build APK(s). Android Studio shows the generated APK location.
5. Keep the APK private; install only on your own phone.

## Important limitations and safety
- This package is an Android-ready source project, not a compiled APK.
- Data is stored locally in the app's WebView storage. Uninstalling/clearing app data can remove it. Export a JSON backup regularly and test restore.
- The passcode gate is not full database encryption. It is suitable as a prototype lock screen, not a security guarantee for highly sensitive records.
- XLSX export uses a library loaded from a CDN, so it needs internet when that library has not been cached. CSV and JSON backup are simpler fallbacks.
- This is a local single-user app; no Firebase/cloud sync is required for your stated phone-only use.
- Before real use, test passcode, backup/restore, categories, transaction totals, and export on the actual phone. Import old data only after creating a separate backup.
