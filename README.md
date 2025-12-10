<<<<<<< HEAD
This is a new [**React Native**](https://reactnative.dev) project, bootstrapped using [`@react-native-community/cli`](https://github.com/react-native-community/cli).

# Getting Started

> **Note**: Make sure you have completed the [Set Up Your Environment](https://reactnative.dev/docs/set-up-your-environment) guide before proceeding.

## Step 1: Start Metro

First, you will need to run **Metro**, the JavaScript build tool for React Native.

To start the Metro dev server, run the following command from the root of your React Native project:

```sh
# Using npm
npm start

# OR using Yarn
yarn start
```

## Step 2: Build and run your app

With Metro running, open a new terminal window/pane from the root of your React Native project, and use one of the following commands to build and run your Android or iOS app:

### Android

```sh
# Using npm
npm run android

# OR using Yarn
yarn android
```

### iOS

For iOS, remember to install CocoaPods dependencies (this only needs to be run on first clone or after updating native deps).

The first time you create a new project, run the Ruby bundler to install CocoaPods itself:

```sh
bundle install
```

Then, and every time you update your native dependencies, run:

```sh
bundle exec pod install
```

For more information, please visit [CocoaPods Getting Started guide](https://guides.cocoapods.org/using/getting-started.html).

```sh
# Using npm
npm run ios

# OR using Yarn
yarn ios
```

If everything is set up correctly, you should see your new app running in the Android Emulator, iOS Simulator, or your connected device.

This is one way to run your app — you can also build it directly from Android Studio or Xcode.

## Step 3: Modify your app

Now that you have successfully run the app, let's make changes!

Open `App.tsx` in your text editor of choice and make some changes. When you save, your app will automatically update and reflect these changes — this is powered by [Fast Refresh](https://reactnative.dev/docs/fast-refresh).

When you want to forcefully reload, for example to reset the state of your app, you can perform a full reload:

- **Android**: Press the <kbd>R</kbd> key twice or select **"Reload"** from the **Dev Menu**, accessed via <kbd>Ctrl</kbd> + <kbd>M</kbd> (Windows/Linux) or <kbd>Cmd ⌘</kbd> + <kbd>M</kbd> (macOS).
- **iOS**: Press <kbd>R</kbd> in iOS Simulator.

## Congratulations! :tada:

You've successfully run and modified your React Native App. :partying_face:

### Now what?

- If you want to add this new React Native code to an existing application, check out the [Integration guide](https://reactnative.dev/docs/integration-with-existing-apps).
- If you're curious to learn more about React Native, check out the [docs](https://reactnative.dev/docs/getting-started).

# Troubleshooting

If you're having issues getting the above steps to work, see the [Troubleshooting](https://reactnative.dev/docs/troubleshooting) page.

# Learn More

To learn more about React Native, take a look at the following resources:

- [React Native Website](https://reactnative.dev) - learn more about React Native.
- [Getting Started](https://reactnative.dev/docs/environment-setup) - an **overview** of React Native and how setup your environment.
- [Learn the Basics](https://reactnative.dev/docs/getting-started) - a **guided tour** of the React Native **basics**.
- [Blog](https://reactnative.dev/blog) - read the latest official React Native **Blog** posts.
- [`@facebook/react-native`](https://github.com/facebook/react-native) - the Open Source; GitHub **repository** for React Native.
=======
# testprojectcicd
>>>>>>> 806bf21444ab7d2501cf59be3358565f591c05be



1. Create a new React Native project:
    - Open your terminal and run npx react-native init TestProject (replace TestProject with your desired project name)
    - Navigate to the project directory: cd TestProject
2. Set




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
    - Add the GitHub repository as a remote: git remote add origin https://github.com/your-username/TestProject.git
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


     
     

