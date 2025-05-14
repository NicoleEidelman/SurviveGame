## Step-by-Step Work

### 1. APK Analysis & Setup
  * I downloaded the APK file provided.
  * Renamed it to `.rar` and extracted the contents to access source code and resources.
  * Copied the relevant Java files (`Activity_Menu.java`, `Activity_Game.java`) and assets into a new Android Studio project.
  * Repaired the `AndroidManifest.xml`, layout XMLs, and vector image resources.
  * Removed broken or unnecessary files and rebuilt a clean working project.

### 2. First Bug Encountered – Corrupt URL
   * The code in `strings.xml` contained this line:  
    ![Screenshot 2025-05-11 202701](https://github.com/user-attachments/assets/96230ca9-adf2-434d-8ef1-7ff06e4de3f9)
   * There were invisible Unicode characters inside the string, as taught in class.
   * Fixing this resolved the crash, and the app launched successfully.


### 3. Second Bug Encountered – OutOfBoundsException

### 4. Game Logic and Code Walkthrough

  * The app fetches a list of U.S. states from a Pastebin URL.
  * The 8th digit of the ID (index 7) is used to choose the index of the state:
  * Example: ID = `209361641` → 8th digit = `'4'` → `states[4] = Illinois`
  * The state is passed via Intent to `Activity_Game.java`, which runs the game logic.

#### Game Mechanics
  * Each digit of the ID is converted to a direction using modulo 4:

| Digit | Digit % 4 | Direction |
|-------|------------|-----------|
| 0     | 0          | Left      |
| 1     | 1          | Right     |
| 2     | 2          | Up        |
| 3     | 3          | Down      |

  * The player must press arrow buttons in the exact sequence to survive.
    * If all moves are correct → Toast: **Survived in [State]**
    * If any move is wrong → Toast: **You Failed**

### 5. Final Test
* ID entered: `209361641`
* Result: **Survived in Illinois**


   ![Screenshot 2025-05-14 023646](https://github.com/user-attachments/assets/494af995-d0f1-411e-ae7c-2cb5e4e55f82)




