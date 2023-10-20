
# Setting Up React Native

### System requirements: 
*Before you begin, make sure your development system meets the following specifications:*
- **CPU**: *A multi-core processor*
- **RAM**: *At least 8GB of RAM*
- **OS**: *React Native development can be done on Windows, macOS, or Linux. Specific requirements may vary depending on your chosen platform. Ensure your system meets the requirements for the platform you're using.*

---

### Installation instructions
1. *Install Chocolatey by opening up powershell and running the following command:* <br/>
    `Get-ExecutionPolicy`
    - *If it returns Restricted, then run Set-ExecutionPolicy AllSigned or Set-ExecutionPolicy Bypass -Scope Process.*
    - *next run the following command:* <br/>
    `Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))`
2. *Install NODE.js and Java SE Development Kit (JDK) using the following command:* <br/>
    `choco install -y nodejs-lts microsoft-openjdk11`
3. *Install Android Studio*
    - *While on Android Studio installation wizard check the following items*
        - *Android SDK*
        - *Android SDK Platform*
        - *Android Virtual Device*
4. *Install Android SDK*
    - *open Android Studio, click on "More Actions" button and select "SDK Manager".*
    - *Select the "SDK Platforms" tab from within the SDK Manager, then check the box next to "Show Package Details" in the bottom right corner.*
    - *Look for "Android 13 (Tiramisu) and make sure the following items are checked:"*
        - *Android SDK Platform 33*
        - *Intel x86 Atom_64 System Image or Google APIs Intel x86 Atom System Image*
5. *Install SDK tools*
    - *in the same page as installing Android SDK select the "SDK Tools" tab and check the box next to "Show Package Details" here as well.*
    - *Expand Android SDK Build-Tools and select 33.0.0*

---

### Configuration steps
1. *Set up Environment variables*
    - *press the windows key, search and press "edit the systems environment variables"*
    - *Navigate to environment variables...*
    - *Click on New... and create a new variable with the following:* <br/>
    `Variable name: ANDROID_HOME`
    - *The Variable value: can be found in Android Studio "Settings" dialog, under Languages & Frameworks → Android SDK. and should look like the following:* <br/>
    `C:\Users\Tyler\AppData\Local\Android\Sdk`
    - *you can also find the default location of the SDK install at the following location:* <br/>
    `%LOCALAPPDATA%\Android\Sdk`
    - *To make sure you correctly set up your environment variables do the following*
        1. *Open powershell*
        2. *Copy and paste the following into powershell:* <br/>
            `Get-ChildItem -Path Env:\`
        3. *Verify ANDROID_HOME has been added*
2. *Add platform-tools to Path*
    - *In the same window you added your environment variables Select the Path variable.*
    - *Click edit*
    - *Click new and add same file path you added as the variable value but with \platform-tools at the end. it should look like the following:* <br/>
        `C:\Users\Tyler\AppData\Local\Android\Sdk\platform-tools`
3. *Open up Virtual Device Manager and Create New Device*
    - *pick which ever phone size you'd like and click next.*
    - *Select "Tiramisu" with an API Level of "33" then click next and finish*
    - *Launch the emulator and let it run.*


### Project creation
1. *Find a place you'd like to create your app. navigate to that folder using CD in the Command line, then type the following* <br/>
`npx react-native@latest init projectName`
    - *Feel free to change the "projectName" to whatever you'd like*
    - *Once your project is installed type the following in the CLI:* <br/>
    `npx react-native run-android`
    - *If everything has worked correctly your project will be shown on the emulated android*

### Troubleshooting
1. *If you had the app say "error Failed to install the app." and had it prompt you with the following:* <br/>
`Failed to install the following SDK components:`  <br/>
`tools Android SDK Tools` <br/>
`build-tools;30.0.3 Android SDK Build-Tools 30.0.3` <br/>
    - *Follow these steps to fix the issue*
        1. *Open Android Studio and navigate to SDK manager.*
        2. *select the "SDK Tools" tab and check the box next to "Show Package Details" if you haven't done so already*
        3. *Uncheck the build-tool that had the error*
            - *in my case I unchecked 30.0.3*
        4. *Run the following in the CLI if your project again and let it re-download the files needed* <br/>
            `npx react-native run-android`

### Resources
1. *You can use the following links for a more in-depth guide to installing React-Native:* <br/>
    `https://reactnative.dev/docs/environment-setup?guide=native&package-manager=npm`
    - *If you'd rather watch a in-depth tutorial video on how to install React-Native:* <br/>
    `https://www.youtube.com/watch?v=CJie9gNRJd4`
