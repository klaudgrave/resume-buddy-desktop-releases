# Resume Buddy Desktop Releases

# Installation Guide

Download Resume Buddy Desktop for your operating system and follow the platform-specific instructions below.

## Download

Get the latest version from the [Releases page](https://github.com/klaudgrave/resume-buddy-desktop-releases/releases/latest).

### Choose Your Platform

- **macOS**: Download `Resume-Buddy-Desktop-{version}.dmg` or `Resume-Buddy-Desktop-{version}-arm64.dmg`
  - Use `arm64` for Apple Silicon (M1/M2/M3/M4)
  - Use regular version for Intel Macs
- **Windows**: Download `Resume-Buddy-{version}-portable.exe`

---

## macOS Installation

### Standard Installation

1. Download the appropriate `.dmg` file for your Mac
2. Open the downloaded `.dmg` file
3. Drag Resume Buddy to your Applications folder
4. Launch Resume Buddy from Applications

### Handling "Unidentified Developer" Warnings

macOS may block the app with a warning like "Resume Buddy cannot be opened because it is from an unidentified developer."

**Method 1: Right-Click to Open**
1. Locate Resume Buddy in your Applications folder
2. Right-click (or Control+click) on the app
3. Select "Open" from the menu
4. Click "Open" in the confirmation dialog
5. The app will now launch (you only need to do this once)

**Method 2: Remove Quarantine Attribute**
1. Open Terminal
2. Run the following command:
   ```bash
   xattr -cr /Applications/Resume\ Buddy\ Desktop.app
   ```
3. Launch the app normally

**Method 3: System Settings**
1. Open System Settings → Privacy & Security
2. Scroll to "Security" section
3. Click "Open Anyway" next to the Resume Buddy message
4. Confirm by clicking "Open"

### Troubleshooting macOS

**"App is damaged and can't be opened"**
```bash
# Remove quarantine attribute
xattr -cr /Applications/Resume\ Buddy\ Desktop.app
```

**App won't open or crashes immediately**
```bash
# Check if the app is properly signed
codesign --verify --verbose /Applications/Resume\ Buddy\ Desktop.app

# If unsigned, remove quarantine and try again
xattr -cr /Applications/Resume\ Buddy\ Desktop.app
```

---

## Windows Installation

### Standard Installation

1. Download `Resume-Buddy-{version}-portable.exe`
2. **Important**: This is a portable app - no installation needed
3. Move the `.exe` file to your preferred location (e.g., `C:\Program Files\Resume Buddy\`)
4. Double-click the `.exe` file to launch

### Handling SmartScreen Warnings

Windows may show "Windows protected your PC" with a SmartScreen warning.

**Method 1: Click "More info" → "Run anyway"**
1. Click "More info" on the SmartScreen dialog
2. Click "Run anyway"
3. The app will launch

**Method 2: Unblock the File**
1. Right-click the `.exe` file
2. Select "Properties"
3. Check "Unblock" at the bottom of the General tab
4. Click "Apply" then "OK"
5. Double-click to run

### Running as Administrator (If Needed)

If the app fails to start or has permission issues:
1. Right-click the `.exe` file
2. Select "Run as administrator"
3. Click "Yes" in the User Account Control dialog

### Troubleshooting Windows

**"The app can't run on your PC"**
- Ensure you downloaded the correct version (64-bit)
- Try running as administrator

**Anti-virus blocks the app**
- Add an exception for Resume Buddy in your anti-virus software
- The app is safe but may be flagged due to lack of code signing certificate

**App won't start or crashes**
```powershell
# Check if required dependencies are installed
# Resume Buddy requires Visual C++ Redistributable
# Download from: https://aka.ms/vs/17/release/vc_redist.x64.exe
```

---

## First Launch

1. Launch Resume Buddy Desktop
2. The app will create a local database for your data
3. All data is stored locally on your machine
4. Optional: Configure AI features with your own API keys in Settings

---

## Updating

### Manual Update
1. Download the latest version from the [Releases page](https://github.com/klaudgrave/resume-buddy-desktop-releases/releases/latest)
2. Follow the installation instructions for your platform
3. Your data will be preserved during updates

---

## Uninstalling

### macOS
1. Drag Resume Buddy from Applications to Trash
2. (Optional) Remove user data:
   ```bash
   rm -rf ~/Library/Application\ Support/resume-buddy-desktop
   ```

### Windows
1. Delete the portable `.exe` file
2. (Optional) Remove user data:
   ```powershell
   C:\Users\{username}\AppData\Roaming\resume-buddy-desktop
   ```

---

## Getting Help

If you encounter issues not covered in this guide:

1. Check the [Issues page](https://github.com/klaudgrave/resume-buddy-desktop-releases/issues)
2. Search for similar problems or create a new issue
3. Include your OS version, app version, and error messages

---

## Privacy & Security

- Resume Buddy runs entirely on your local machine
- No data is sent to external servers (except when using optional AI features with your own API keys)
- All resume data is stored in a local database on your computer
