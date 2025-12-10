
What is CI/CD?

CI/CD stands for Continuous Integration and Continuous Delivery/Deployment.
It’s a way to automate building, testing, and releasing software so teams can deliver updates faster and with fewer errors.

CI means:
Every time you or your team pushes code to GitHub, a robot checks your work automatically. Download the code, Check for errors, Build the app, Sends to testers, Alerts if something breaks

Step-by-Step:

1. Create a new React Native project:
    - Open your terminal and run npx @react-native-community/cli@ TestProject 
    - Navigate to the project directory: cd TestProject
  
    - Set up a GitHub repository:
    - Create a new GitHub repository with a readme.md file
    - Initialize Git and push to GitHub
        git init
        git add .
        git commit -m "Initial React Native TestProject"
        git remote add origin https://github.com/chimuanyavic7/TestProject.git
        git push -u origin main

    - Initialize a new Git repository in your project directory: git init
    - Add the GitHub repository as a remote: git remote add origin https://github.com//chimuanyavic7/TestProject.git
    - Commit your changes: git add . && git commit -m "Initial commit"
    - Push the changes to GitHub: git push -u origin main
  
    - Create a new GitHub Actions workflow file:
    - Create the GitHub Actions workflow (complete file)
    - Create .github/workflows/android-ci.yml in your repo with this content. This workflow:
    - Runs on push to main.
  
    **- This GitHub Actions workflow defines a CI/CD pipeline for a React Native Android project. Here's a breakdown of the pipeline and its stages:**

The pipeline is triggered on:
- Push events to the main branch
- Pull requests targeting the main branch

Job: build-android
The pipeline consists of a single job called build-android, which runs on an ubuntu-latest environment.

Stages:

1. Checkout code
    - Uses actions/checkout@v4 to checkout the repository code.
2. Set up Node.js
    - Uses actions/setup-node@v4 to set up Node.js 20.
    - Caches npm dependencies to speed up subsequent runs.
3. Install Java
    - Uses actions/setup-java@v4 to set up Java 17 (Temurin distribution).
4. Install Android SDK
    - Uses android-actions/setup-android@v3 to set up the Android SDK (API level 33, build tools 33.0.2).
5. Install dependencies
    - Runs npm ci to install project dependencies.
6. Make Gradle executable
    - Makes the Gradle wrapper script executable.
7. Clean Gradle
    - Runs gradlew clean to clean the Gradle build.
8. Build Android
    - Runs gradlew assembleDebug to build the Android app (debug variant).

  
  **** Deploying to Google Play Console Internal Testing:**

1. Create a Google Play Console account: Set up a new Google Play Console account.
2. Create an app: Create a new app in the Google Play Console.
3. Get the AAB file: Get the AAB file from your CI/CD pipeline 
4. Upload to Google Play: Use the Google Play Console API or UI to upload the AAB file.
5. Publish to Internal Testing: Set the app to Internal Testing and invite testers to download and install the app.

   **Key Theoretical Steps:**
1. Artifact Preparation: A signed Android App Bundle (.aab) is generated, with an incremented versionCode.
2. Authentication (API/CI/CD): For automation, a Google Play Developer API Service Account JSON key is used. This key must be granted release management permissions in the Play Console.
3. Deployment Method:
    - Manual: Upload the .aab file directly through the Google Play Console UI under the Internal Testing track.
    - Automated (CI/CD): Use a tool (like Fastlane or the official Google Play Publisher Library) to interact with the Developer API:
    - Open an edit session $\rightarrow$ Upload the AAB $\rightarrow$ Assign the AAB to the Internal Testing track $\rightarrow$ Commit the edit.
4.  Processing & Access: Google Play processes the AAB (which leverages Play App Signing). The app is made available almost immediately to the pre-configured Internal Testers (Google Accounts) via a private link on the Google Play Store.
5.  Focus: Formal entry into the Google Play ecosystem, utilizing the Play App Signing service, and testing the core store distribution process.



     
     

