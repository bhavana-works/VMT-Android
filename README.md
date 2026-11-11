# VMT — Vinay's Money Tracker

VMT (Vinay's Money Tracker) is a mobile-first personal finance management application designed to help users manage their income, expenses, budgets, transactions, savings, and financial insights in one place.

The project is built as a web application and packaged as an Android application using **Capacitor**. It is designed primarily for **single-user, phone-based usage** with local data storage.

---

## 📱 About the Project

VMT provides a simple and user-friendly financial dashboard where users can record and monitor their daily financial activities.

The application focuses on:

- Tracking income and expenses
- Monitoring monthly financial performance
- Managing budgets
- Viewing transaction history
- Tracking savings and wallet balance
- Understanding spending patterns
- Exporting and backing up financial data
- Providing a mobile-friendly experience

The project uses the existing VMT application logic and local storage structure so that previously created data can remain compatible with the updated Android-ready version.

---

## ✨ Key Features

### 🔐 Passcode Protection

- First-time 4–8 digit passcode setup
- Lock and unlock the application
- Change passcode
- Lock the application immediately
- Passcode screen displays the VMT branding

> Note: The passcode system acts as an application lock and should not be considered equivalent to full database encryption.

---

### 📊 Dashboard

The dashboard provides an overview of the user's financial activity, including:

- Current/net balance
- Monthly income
- Monthly expenses
- Savings rate
- Budget status
- Spending category breakdown
- Recent transactions
- Financial summary

This allows users to understand their overall financial position quickly.

---

### 💰 Income Management

Users can add, edit, and delete income transactions.

Income records can include:

- Amount
- Date
- Note
- Income source
- Income type

Existing income sources and fields from the original VMT prototype are retained.

---

### 💸 Expense Management

Users can record and manage their expenses with details such as:

- Amount
- Date
- Note
- Expense category
- Expense subcategory
- Payment method
- Card/account information

Existing categories such as **Travel, Petrol, UNI, AXIS**, and other predefined fields are retained.

---

### 📅 Calendar

The calendar section allows users to:

- Navigate between months
- Select a particular date
- View transactions recorded on that date
- Review daily financial activity

This makes it easier to identify when specific transactions occurred.

---

### 🎯 Budget Management

VMT includes budgeting functionality for better expense control.

Users can:

- Create overall budgets
- Create category-based budgets
- Edit budgets
- Delete budgets
- Monitor budget progress
- Identify overspending

Budget indicators help users compare actual spending against planned spending.

---

### 👛 Wallet & Savings

The application provides a wallet/net-balance section to monitor available savings.

Users can:

- View current wallet/net balance
- Set a savings target
- Monitor savings progress

---

### 📈 Financial Insights

The Insights section helps users understand their financial habits through information such as:

- Income vs. expenses
- Spending by category
- Average transaction amount
- Highest spending category
- Highest individual expense
- Monthly financial trends
- Savings performance

Visual charts and summaries make financial information easier to understand.

---

### 📤 Data Export & Backup

VMT supports data portability and backup through:

- CSV export
- Multi-sheet XLSX export when the required library is available
- JSON backup
- JSON restore
- Legacy JSON data import

Users should create regular backups to avoid losing locally stored financial records.

---

## 🗃️ Data Storage

VMT is designed as a **local single-user application**.

Financial data is stored locally using the application's WebView storage.

The project does **not require Firebase or cloud synchronization** for its intended phone-only usage.

The existing local storage key:

`artha.v1.data`

is retained to help prevent previously created data from becoming inaccessible when moving to the Android-ready version.

### ⚠️ Important

Uninstalling the application or clearing the application's data may remove locally stored financial records.

Always create a **JSON backup** before:

- Uninstalling the application
- Clearing app data
- Moving to another device
- Performing major updates

---

## 🛠️ Technologies Used

### Frontend

- HTML5
- CSS3
- JavaScript

### Mobile / Android

- Capacitor
- Android SDK
- Android Studio
- Gradle

### Development Tools

- Visual Studio Code
- Node.js
- npm
- Git
- GitHub

### Data & Storage

- Browser/WebView local storage
- JSON backup and restore
- CSV export
- XLSX export

---

## 📂 Project Structure

```text
VMT-Android-Ready/
│
├── android/                  # Android/Capacitor project
│   ├── app/
│   ├── gradle/
│   ├── build.gradle
│   ├── gradle.properties
│   ├── settings.gradle
│   └── gradlew.bat
│
├── www/                      # Web application files
│   ├── index.html
│   ├── service-worker.js
│   ├── manifest.webmanifest
│   └── EXPORT-OLD-DATA.txt
│
├── capacitor.config.ts       # Capacitor configuration
├── package.json              # Node/npm configuration
├── package-lock.json
├── tsconfig.json
├── .gitignore
└── README.md
```

---

## 💻 Run the Web Version

To test the web version locally:

1. Open the project folder in **Visual Studio Code**.
2. Open `www/index.html`.
3. Use **Live Server** if installed.
4. Test the application using sample data before importing real financial records.

---

## 📱 Build the Android Application

### Requirements

Install the following:

- Node.js LTS
- Android Studio
- Android SDK
- Required Android SDK build tools
- Java/JDK compatible with the installed Android/Gradle setup

### Install dependencies

Open the VS Code terminal inside the project folder:

```powershell
npm install
```

### Synchronize Capacitor

Since the Android folder already exists, do **not** run `npx cap add android` again.

Run:

```powershell
npx cap sync android
```

### Open Android Studio

Run:

```powershell
npx cap open android
```

Android Studio will open the Android project.

---

## ▶️ Run on an Android Phone

1. Enable **Developer Options** on your Android phone.
2. Enable **USB Debugging**.
3. Connect the phone to the computer using a USB cable.
4. Allow the computer when the USB debugging permission appears.
5. Wait for Android Studio to detect the device.
6. Select the phone from the device selector.
7. Click **Run ▶**.

Android Studio will build and install the application on the connected phone.

---

## 📦 Generate an APK

In Android Studio:

**Build → Build Bundle(s) / APK(s) → Build APK(s)**

After the build completes, Android Studio will display the location of the generated APK.

The APK can then be installed on a compatible Android device.

---

## 🔄 Updating the Application

When changes are made to the web application:

```powershell
npm install
npx cap sync android
npx cap open android
```

Then rebuild the application from Android Studio.

For future source-code changes, use Git to track modifications:

```powershell
git status
git add .
git commit -m "Update VMT application"
git push
```

---

## 🌐 GitHub Repository

This project is maintained using Git and GitHub for version control.

Repository:

**VMT-Android**

GitHub helps maintain the source code, track changes, and preserve previous versions of the project.

---

## 🔒 Privacy & Security

VMT is designed as a local single-user finance application.

Because financial information can be sensitive:

- Do not share your backup files publicly.
- Do not upload personal financial records to public repositories.
- Keep exported CSV/XLSX/JSON files secure.
- Do not commit personal transaction data to GitHub.
- Use the passcode lock on your personal device.

The application passcode is intended as an app-level lock and is **not a replacement for full encryption or enterprise-grade security**.

---

## ⚠️ Important Limitations

- VMT is currently designed for local, single-user usage.
- It does not require Firebase/cloud synchronization.
- Clearing application data can remove locally stored records.
- XLSX export may depend on the availability of its required library.
- Some features should be tested on the actual Android device before regular use.
- The project is an Android-ready source project; the APK must be built separately.

---

## 🧪 Recommended Testing Before Real Use

Before entering important financial records, test:

- Passcode setup
- Unlock/lock functionality
- Adding income
- Adding expenses
- Editing transactions
- Deleting transactions
- Calendar transactions
- Budget creation
- Budget progress
- Wallet balance
- Financial insights
- CSV export
- XLSX export
- JSON backup
- JSON restore
- Legacy data import

Always create a backup before importing or modifying important records.

---

## 🚀 Future Improvements

Possible future improvements include:

- Improved data encryption
- Biometric authentication
- Automated backup
- Cloud synchronization as an optional feature
- Advanced financial analytics
- Recurring income and expenses
- Bill and subscription reminders
- More detailed charts
- Custom categories
- Multiple currency support
- Dark/light theme customization
- Improved accessibility
- Automated financial reports

---

## 👩‍💻 Project Purpose

VMT was developed as a practical personal finance management project combining **web development, JavaScript-based application logic, local data storage, and Android app development using Capacitor**.

The project demonstrates how a web application can be converted into a mobile Android application while maintaining its existing functionality and local data structure.

---

## 📄 License

No open-source license has been added to this repository yet.

Until a license is added, the source code should not be assumed to be freely reusable or redistributable.

---

### VMT — Vinay's Money Tracker

**Track. Plan. Save. Manage.**