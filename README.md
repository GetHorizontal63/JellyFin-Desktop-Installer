# JellyFin-Desktop-Installer
Create a browser-based desktop application that connects to your JellyFin media server. This script detects installed browsers, creates shortcuts, and uses the official Jellyfin icon. Simply specify your server's IP address and port for a seamless full-screen Jellyfin experience.


## Overview
The Jellyfin Desktop App Installer creates a lightweight desktop application for accessing your Jellyfin media server on Windows. Unlike a regular browser bookmark, this solution launches in a standalone window without address bars, tabs, or other browser elements, providing a clean, dedicated interface for your Jellyfin experience.

## Features
- **Browser-Based Experience**: Uses Chrome or Edge in app mode (or IE as fallback)
- **Full-Screen Mode**: Launches Jellyfin in a distraction-free, full-screen interface
- **Official Integration**: Uses the official Jellyfin icon from the Jellyfin GitHub repository
- **Custom Server Support**: Connect to any Jellyfin server by specifying IP address and port
- **Automatic Browser Detection**: Finds installed browsers on your system
- **Easy Installation**: Simple setup with clear prompts and sensible defaults
- **Desktop & Start Menu Integration**: Creates convenient shortcuts

## Why Use This?
- **Better than a Browser Tab**: No browser UI elements or accidental navigation away from Jellyfin
- **Cleaner than a Browser Bookmark**: Appears as a standalone app in taskbar and Alt+Tab
- **Lighter than Electron Apps**: Uses your existing browser rather than bundling a complete Chromium instance
- **More Native Feel**: Integrates with Windows desktop, taskbar, and Start Menu
- **Flexible Configuration**: Works with any Jellyfin server, not just localhost

## Requirements
- Windows Operating System
- Administrator privileges (for installation only)
- Google Chrome or Microsoft Edge (recommended, will fall back to IE if neither is available)
- A running Jellyfin media server (local or remote)

## Installation
1. Save the script as `jellyfin-installer.bat`
2. Right-click and select "Run as administrator"
3. Follow the on-screen prompts:
   - Installation directory (defaults to `Program Files\Jellyfin`)
   - Jellyfin server IP address (defaults to `localhost`)
   - Jellyfin server port (defaults to `8096`) 
   - Whether to create a Start Menu shortcut

## How It Works
The installer:
1. Requests administrator privileges for proper installation
2. Searches for Chrome and Edge browsers on your system
3. Creates a program directory to store the launcher and icon
4. Downloads the official Jellyfin icon from GitHub
5. Creates a launcher script that:
   - Tries to use Chrome in app mode, if installed
   - Falls back to Edge in app mode, if Chrome isn't available
   - Falls back to Internet Explorer in kiosk mode as a last resort
6. Creates shortcuts on your Desktop and optionally in the Start Menu
7. Configures those shortcuts to connect to your specified Jellyfin server

## Technical Details
The installer uses:
- Windows batch scripting for the main logic
- VBScript for creating shortcuts and the IE fallback launcher
- PowerShell for downloading the Jellyfin icon
- Browser command-line arguments `--app` and `--start-fullscreen` to create the app-like experience

## Troubleshooting
- **Permission Issues**: Make sure to run the script as Administrator
- **Browser Not Found**: Install Chrome or Edge for best results
- **Can't Connect to Server**: Check that your Jellyfin server IP and port are correct
- **Missing Icon**: Ensure your machine can access GitHub URLs
- **Installation Path Problems**: Avoid paths with special characters or spaces

## Customization
You can modify the script to:
- Change the default port
- Adjust the window style (fullscreen vs. normal)
- Add additional browsers
- Modify the URL path if your Jellyfin instance is not at the root

## Uninstallation
To uninstall:
1. Delete the shortcuts from Desktop and Start Menu
2. Delete the installation directory (default: `Program Files\Jellyfin`)

## JellyFin Icon
- Uses official Jellyfin icon from the [Jellyfin GitHub repository](https://github.com/jellyfin/jellyfin-server-windows/)

## License
This script is provided as-is under the Apache 2.0 License. Feel free to modify and distribute as needed.

---

*Note: This installer is not officially affiliated with the Jellyfin project. It's a community tool to enhance the Jellyfin user experience.*
