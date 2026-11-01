# GameGuard (Android starter project)

GameGuard uses Android's Accessibility Service to notice app-window changes. If the foreground
package is marked with `ApplicationInfo.CATEGORY_GAME`, it sends the user to the Home screen.

## Important limitations
- This only detects apps whose developers correctly set Android's game category.
- Some games are not categorized as games; some non-game apps may be categorized as games.
- Android/OEM battery management can stop background services. Check battery settings if it
  stops working.
- Accessibility access is powerful. This service does not read screen text or collect data;
  it only checks the package name and app category, then returns Home.
- This is a starter project, not a guaranteed or tamper-proof parental-control solution.
- The app does not silently enable Accessibility. The user must enable it in Android Settings.

## Build
Open this project in AndroidIDE (recommended on-device) or Android Studio, allow Gradle sync,
then Build > Build APK(s).

If building in Termux, you need a working Android SDK and compatible Gradle/Android Gradle Plugin
installation. Termux alone does not include the Android SDK.

## Enable
1. Install the generated APK.
2. Open GameGuard.
3. Tap Enable GameGuard.
4. In Android Accessibility settings, open GameGuard app blocker and enable it.
5. Confirm Android's warning dialog.

## Test
Install a known game, enable the service, and open the game. If Android reports its category as
GAME, GameGuard should return to the Home screen. Use "Show detected games" to inspect what
Android categorizes as games.
