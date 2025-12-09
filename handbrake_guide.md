# HandBrake Application Installation Guide (Windows OS)

> **Quick Access**  
> 🎥 **HandBrake Application Installation Tutorial:**  
> [Watch Video](https://youtu.be/A0UV0uY4gkk)

---

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Downloading HandBrake](#downloading-handBrake)
- [Installing HandBrake](#Installing-HandBrake)
- [Verify the Installation](#Verify-the-Installation)
- [Advanced: Installing HandBrake CLI](#Advanced-Installing-HandBrake-CLI)
- [Troubleshooting](#Troubleshooting)
- [Version History](#Version-History)
- [Downloads](#downloads)

---

## Overview
HandBrake is an open-source video transcoder that converts videos from nearly any format to modern, widely supported codecs.

This guide details the procedures to download, install, and launch HandBrake on a computer running Windows 10 or Windows 11. It covers both the standard Graphical User Interface (GUI) and the Command Line Interface (CLI) for advanced automation.

---

## Prerequisites
Before installing HandBrake, ensure your system meets the following requirements:

- **Operating System:** Windows 10 or Windows 11 (64-bit) 
- **Software Dependency:** Microsoft .NET Desktop Runtime 6.0.x or later.
  - **Note:** If the .NET Runtime is not installed, the HandBrake installer will prompt you to download and install it before proceeding.

---

## Downloading HandBrake
1. Open your browser and go to
[HandBrake website](https://handbrake.fr/)
`(https://handbrake.fr/)`.
2. On the home page, select the red **Download HandBrake** button.  
2. Save the installer file (e.g., `HandBrake-1.8.2-x86_64-Win_GUI.exe`) to your Downloads folder. 

---

## Installing HandBrake
1. Locate the downloaded executable file in your **Downloads** folder.

1. Double-click the file to start the installation wizard.

   > **Note:** If the **User Account Control** dialog box appears, asking if you want to allow this app to make changes to your device, select **Yes**.

1. On the **Welcome to HandBrake Setup** screen, select **Next** to continue.

    <img width="499" height="388" alt="HandBrake Setup Welcome Screen" src="https://github.com/user-attachments/assets/178ac8e2-b263-463d-b26c-ce57ac6a5d02" />

1. Review the License Agreement. If you agree to the terms, select **Next**.

1. On the **Choose Install Location** screen, accept the default destination folder or select **Browse** to specify a different location.

1. Select **Install**.
  
    <img width="499" height="388" alt="image" src="https://github.com/user-attachments/assets/e15d5c1a-839e-499f-8344-888ec356e112" />

1. Once the installation is complete, the **Completing the HandBrake Setup Wizard** screen appears.

1. Select the **Create Desktop Shortcut** check box if you want a shortcut on your desktop.

1. Select **Finish** to close the wizard.

---


## Verify the Installation  
To ensure HandBrake is installed and functioning correctly:
1. Select the **Start** button or select the **Windows logo key**.  

2. Type **HandBrake** and select the application from the search results.

    <img width="499" height="388" alt="image" src="https://github.com/user-attachments/assets/6a45ce05-b83d-4ac9-aa00-c1a21942c0fa" />

3. Verify that the application window opens and displays the **Source Selection** pane.

---
## Advanced: Installing HandBrake CLI
For users requiring batch processing or automation capabilities, the HandBrake Command Line Interface (CLI) is recommended.

### 1. Downloading the CLI
1. Navigate to the [HandBrake CLI Downloads](https://handbrake.fr/downloads2.php) page.
2. Download the Windows CLI `HandBrakeCLI-X.X.X-win-x86_64.zip` file.
3. Extract the contents to a dedicated directory (e.g., `C:\Program Files\HandBrakeCLI`).

### 2. Verifying the CLI Installation
To confirm the tool is recognized by the system:

1. Press the **Windows logo key** + **R**, type `cmd`, and press **Enter**.
2. Navigate to the directory where you extracted the binary:
   ```cmd
   cd "C:\Program Files\HandBrakeCLI"
3. Run the version command:
   ```cmd
   "HandBrakeCLI.exe --version"

* **Expected Output:** `HandBrake X.X.X (version)`

    <img width="1113" height="561" alt="image" src="https://github.com/user-attachments/assets/fd0f0ab9-d227-400a-ad65-5548fada7f8f" />


### 3. Basic CLI Usage Example
To transcode a video file using the default "Fast 1080p30" preset, run the following command:
    
    "HandBrakeCLI.exe -i "C:\Source\video.mov" -o "C:\Output\movie.mp4" --preset "Fast 1080p30"

| Flag | Description |
| :--- | :--- |
| `-i` | **Input:** The path to the source video file. |
| `-o` | **Output:** The destination path for the converted file. |
| `--preset` | **Profile:** The specific transcoding profile to apply (must be enclosed in quotes). |
 
 >**Tip:** To view a full list of available presets, run `HandBrakeCLI.exe --preset-list`.

---

## Troubleshooting
If the application fails to launch, refer to the table below for common solutions.

| Issue | Resolution |
| :--- | :--- |
| The application displays a ".NET Runtime" error. | Download and install the **.NET Desktop Runtime 6.0** from the official Microsoft website. |
| The application opens but closes immediately. | Ensure your graphics drivers are up to date and restart the computer. |

---

## Version History

| Version | Date     | Author      | Description           |
|--------|----------|-------------|------------------------|
| 1.0    | Sep 2025 | Vinoj John  | Initial draft created |

---

## Downloads

🎥 **HandBrake Application Installation Tutorial:**  
[Watch Video](https://youtu.be/A0UV0uY4gkk)

---


