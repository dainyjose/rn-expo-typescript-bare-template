# rn-expo-typescript-bare-template



## Table of Contents

- [Purpose](#purpose)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Scripts](#scripts)
- [Linting & Formatting](#linting--formatting)
- [Testing](#testing)
- [Environment Variables](#environment-variables)
- [Author](#author)

---

## Purpose
This repository is a bare workflow template for building React Native apps with Expo and TypeScript. It provides a well-structured foundation with:

- Type safety (TypeScript)
- Linting & formatting (ESLint + Prettier)
- Testing (Jest + React Native Testing Library)
- Simple project structure for scalability
- Support for Bun as a fast package manager

It’s designed to help you quickly bootstrap production-ready apps without repeating setup steps.

---

## Tech Stack

- React Native (Bare Workflow)
- Expo SDK
- TypeScript
- Bun
- ESLint & Prettier
- Jest & @testing-library/react-native
- (Optional) Redux Toolkit & React Navigation
  
---

### Prerequisites

- **Node.js** (only for installing Expo CLI globally)
- **Bun** (v1.0+)
- **Expo CLI** (for initializing and running projects)
- Xcode / Android Studio for iOS & Android builds

### Install Expo CLI

```bash
npm install -g expo-cli
```

### Clone the Repo

```bash
git clone https://github.com/dainyjose/rn-expo-typescript-bare-template.git
cd rn-expo-typescript-bare-template
```

**Renaming a project during cloning**

```bash
git clone https://github.com/dainyjose/rn-expo-typescript-bare-template.git new-repo-name
cd new-repo-name
```

### Install Dependencies

```bash
bun install
```

### Run the App

```bash
bun expo run:android   # For Android
bun expo run:ios       # For iOS
bun expo start         # Metro bundler
```
### Android Setup

If you see this error when building the Android app:
SDK location not found. Define a valid SDK location with an ANDROID_HOME environment variable or by setting the sdk.dir path in your project's local properties file.


follow these steps:

1. **Open Android Folder in Android Studio**
   - Open **Android Studio**
   - Go to **File > Open**
   - Select the `android/` folder inside the project root

2. **Configure SDK Location**
   - Go to **Android Studio > Preferences > Appearance & Behavior > System Settings > Android SDK**
   - Copy the SDK path (e.g. `/Users/<your-username>/Library/Android/sdk`)

3. **Update `local.properties`**
   Inside the `android/` folder, create or update the `local.properties` file:

   ```properties
   sdk.dir=/Users/<your-username>/Library/Android/sdk

---

## Project Structure

```
src/
├── __tests__/         # Test component
├── api/               # API calls
├── components/        # Reusable components
├── constants/         # App-wide constants
├── context/           # Global contexts
├── enums/             # TypeScript enums
├── hooks/             # Custom hooks
├── navigation/        # Navigation config
├── redux/             # Redux store and slices
├── screens/           # Screen components
├── theme/             # Theming and styles
├── types/             # Global types
├── utils/             # Utility functions
App.tsx                # Entry point

```

---

## Scripts

```bash
bun run dev            # Start Metro bundler
bun run android        # Run on Android
bun run ios            # Run on iOS
bun run lint           # Run ESLint on src/
bun run format         # Format code with Prettier
bun run test           # Run unit tests
```

---

## Linting & Formatting

**Run ESLint:**

```bash
bun run lint
```

**Run Prettier:**

```bash
bun run format
```

Configured to ignore `node_modules`, `android/`, `ios/`, `build/`, etc.

---

## Testing

**Unit Testing Setup:**

- Framework: `jest`
- Render tests: `@testing-library/react-native`

```bash
bun run test
```

---

## Environment Variables

Create a `.env` file at the root:

```env
API_URL=https://your-api.com
APP_ENV=development
```

In `env.d.ts`:

```ts
declare module '@env' {
  export const API_URL: string;
  export const APP_ENV: string;
}
```

---

## 📖 Documentation

For full setup instructions and details, check out the [Getting Started Guide](./GETTING_STARTED.md).

## 🧑‍💻 Author

**Dainy Jose**  
[GitHub](https://github.com/dainyjose) | [LinkedIn](https://linkedin.com/in/dainyjose)

---

## License

[MIT](./LICENSE)
