# CoinFlip Overlay 🪙

A modern Android application that provides a seamless coin-flip experience using a transparent system overlay. Unlike traditional apps, this coin flip appears directly on top of your current activity, whether you're on the home screen or using another app.

## ✨ Features

*   **True Overlay Experience**: The animation plays as a `SYSTEM_ALERT_WINDOW`, meaning it doesn't interrupt your current tasks.
*   **Fully Transparent**: Only the coin and the result are visible; your background apps remain fully visible and interactive.
*   **Beautiful Animations**: Powered by [Lottie](https://airbnb.io/lottie/) for smooth, high-quality coin flip sequences.
*   **Fair 50/50 Logic**: Uses Kotlin's `Random.nextBoolean()` to ensure a statistically fair result every time.
*   **Automatic Cleanup**: The overlay automatically vanishes 1.5 seconds after the result is shown, keeping your screen clutter-free.

## 🛠 Tech Stack

*   **Language**: Kotlin
*   **Architecture**: Foreground Service + WindowManager API
*   **Animation**: Lottie Android
*   **UI Components**: FrameLayout, ImageView

## 📸 How it Works

1.  **Launch**: Tap the app icon.
2.  **Permission**: On first launch, the app will request the **"Display over other apps"** permission.
3.  **Animation**: A Foreground Service starts and adds a transparent view to the `WindowManager`.
4.  **Result**: Once the animation ends, the 50/50 logic determines if it's Heads or Tails and updates the image.
5.  **Finish**: The service stops itself and removes the view from the screen.

## 🚀 Installation & Setup

### Prerequisites
*   Android 8.0 (Oreo) or higher (API 26+).
*   "Display over other apps" permission must be granted.

### Build from Source
1.  Clone the repository:
    ```bash
    git clone https://github.com/YOUR_USERNAME/CoinFlip.git
    ```
2.  Open the project in **Android Studio**.
3.  Sync Gradle and click **Run**.

## 🔒 Permissions

This app requires the following permissions to function as an overlay:
*   `SYSTEM_ALERT_WINDOW`: To draw the coin over other apps.
*   `FOREGROUND_SERVICE`: To maintain the animation state while the main activity is closed.
*   `POST_NOTIFICATIONS`: (Android 13+) To show the required service notification.

## 📜 License

This project is open source. Feel free to use and modify it as you wish!
