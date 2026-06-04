# 🚀 Ultimate Windows & NVIDIA Optimization Guide

Welcome to the comprehensive, step-by-step optimization guide for Windows, gaming performance, and NVIDIA drivers. This guide compiles several advanced optimization techniques into a unified, sequential walkthrough designed to minimize latency, debloat your system, and maximize performance.

---

## 📋 Table of Contents
1. [Prerequisites & Tools](#-prerequisites--tools)
2. [Step 1: Debloat Windows Apps (Geek Uninstaller)](#step-1-debloat-windows-apps-geek-uninstaller)
3. [Step 2: Windows System Tweaks (CTT Toolbox & O&O ShutUp10++)](#step-2-windows-system-tweaks-ctt-toolbox--oo-shutup10)
4. [Step 3: Power Plan Optimization](#step-3-power-plan-optimization)
5. [Step 4: Clean Driver Removal (DDU)](#step-4-clean-driver-removal-ddu)
6. [Step 5: Clean Driver Installation (NVCleanstall)](#step-5-clean-driver-installation-nvcleanstall)
7. [Step 6: Profile Optimization (NVIDIA Profile Inspector)](#step-6-profile-optimization-nvidia-profile-inspector)
8. [🔄 Post-Optimization Notes](#-post-optimization-notes)

---

## 🛠 Prerequisites & Tools

Before you begin, download the original official tools listed below. *(Note: Keeping drivers up to date is usually recommended, but specific versions are chosen here to prevent performance loss).*

* **Display Driver Uninstaller (DDU):** [Guru3D Download](https://www.guru3d.com/download/display-driver-uninstaller-download/)
* **NVCleanstall:** [TechPowerUp Download](https://www.techpowerup.com/download/techpowerup-nvcleanstall/)
* **Windows Update Blocker (WUB):** [Sordum.org](https://www.sordum.org/9470/windows-update-blocker-v1-8/)
* **NVIDIA Profile Inspector:** [GitHub Releases](https://github.com/Orbmu2k/nvidiaProfileInspector/releases)
* **MSI Tool Background Information:** [Guru3D Forums](https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/)

---

## Step 1: Debloat Windows Apps (Geek Uninstaller)

Clean out integrated bloatware before modifying system structures.

1. Open `geek.exe`.
2. Navigate to **Options** > **Microsoft Store apps**.
3. Uninstall unwanted Microsoft Bloatware (apps you do not usually use).
   * *Recommendation:* It is safe to keep essentials like **Photos**, **Movies & TV**, and **Windows Security**.

---

## Step 2: Windows System Tweaks (CTT Toolbox & O&O ShutUp10++)

Use the Chris Titus Tech (CTT) Toolbox—an All-in-One Windows Tweaker—and O&O ShutUp10++ to disable telemetry and background overhead.

### Part A: CTT Toolbox Configuration
1. Open **ChrisTitusTool**.
2. Click the **Tweaks** button.
3. Select the **Standard** button for an easier initial baseline.
4. Check/tick the following additional options:
   * **Hibernation** 
 `Disable`
   * **Microsoft Store Recommended Search Results** 
 `Disable`
   * **Start Menu Previous Layout** 
 `Enable`
   * **Widgets** 
 `Remove (!!!)`
5. Navigate to **Advanced Tweaks** and configure:
   * **Background Apps** 
 `Disable`
   * **Brave Browser** 
 `Debloat` *(if you use the Brave browser)*
   * **File Explorer Home and Gallery** 
 `Disable`
   * **Fullscreen Optimizations** 
 `Disable`
   * **Microsoft Edge** 
 `Debloat`
   * **Microsoft OneDrive** 
 `Remove`
   * **Razer Software Auto-Install** 
 `Disable`
   * **Right-Click Menu Previous Layout** 
 `Enable`
   * **Storage Sense** 
 `Disable`
   * **Teredo** 
 `Disable`
   * **Visual Effects** 
 `Set to best Performance`
   * **Windows AI** 
 `Disable`
   * **Xbox and Gaming Components** 
 `Remove`

### Part B: O&O ShutUp10++ Privacy Configuration
6. Directly after configuring CTT, find and click: **O&O ShutUp10++ - Run**.
7. Once the app opens, click **Actions** and select **Recommended and somewhat recommended settings**.
8. Navigate to **App Privacy** and explicitly **untick** (leave enabled) the following to ensure hardware compatibility:
   * `Disable app access to microphone`
   * `Disable app access to use voice activation`
   * `Disable app access to use Camera`
9. Exit the application safely, choose **Restart Windows**, and boot back into your desktop.

---

## Step 3: Power Plan Optimization

Maximize CPU responsiveness by deploying a custom optimized power schedule.

1. Right-click `enable_power_plan.bat` and select **Run as administrator**. Once the import command finishes, close the Command Prompt (CMD).
2. Open Windows Search, type **Edit Power Plan**, and open it.
3. Go to **Power Options** and click **Show additional plans**.
4. Select/tick the **"trnd2026"** power plan.
5. Restart your computer.

---

## Step 4: Clean Driver Removal (DDU)

Ensure no corrupted, legacy, or conflicting driver files interfere with your clean installation.

1. Open **Display Driver Uninstaller (DDU)**, go to **Options**, and tick:
   * `Prevent downloads of drivers from Windows Update when Windows search for a driver for a device.`
   * `Remove AMD Audio Bus`
   * `Remove "C:\AMD" driver folders.`
   * `Remove the driver/filter AMDKMPFD` *(Note: A backup is recommended for AMD chipsets).*
   * `Remove Intel NPU`
2. **Boot to Safe Mode:** DDU is most effective when run inside Windows Safe Mode.
   * *Tip:* Hold the `Shift` key while clicking **Restart** in your Windows Power Menu. Navigate to **Troubleshoot** > **Advanced options** > **Startup Settings** > **Restart**, then press `4` or `F4`.
3. **Run the Clean:**
   * Select device type: `GPU`
   * Select device manufacturer: `NVIDIA` *(or your respective AMD/Intel card if troubleshooting)*
   * Click **Clean and restart** (highly recommended).

---

## Step 5: Clean Driver Installation (NVCleanstall)

Install a highly customized, stripped-down graphics driver without unnecessary NVIDIA background components.

1. Launch **NVCleanstall**.
2. Select **"Install best driver for my hardware"** or **"Select driver version manually"** and click **Next**.
3. Check **"Periodically check for driver updates in background"**, then press **Next**.
4. Select the explicit components to install: Check **"Display Driver"** and **"Legacy Control Panel"**, then press **Next**.
5. On the tweaks screen, check/tick the following:
   * `Disable Installer Telemetry & Advertising`
   * `Perform a Clean Installation`
   * `Disable Multiplane Overlay (MPO)`
   * `Disable Ansel`
   * `Show Expert Tweaks`
   * `Disable Driver Telemetry`
   * `Disable NVIDIA HD Audio device sleep timer`
   * `Enable Message Signaled Interrupts`
       * *Interrupt Policy:* `Default`
       * *Interrupt Priority:* `High`
   * `Disable HDCP`
   * `Use method compatible with Easy-Anti-Cheat (EAC)`
   * `Automatically accept the "driver unsigned" warning`
6. Click **Next** and choose **Custom** inside the launching native NVIDIA Installer prompt to finalize the configuration.

---

## Step 6: Profile Optimization (NVIDIA Profile Inspector)

Fine-tune driver values directly inside the hardware profiles.

1. Open `nvidiaProfileInspector.exe`.
2. Click the **Import user defined profiles** button (represented by an icon of a hard drive with a down arrow).
3. Select the profile file named `999fps.nip`.
4. Click **Apply changes** in the upper right corner and safely close the application.

---

## 🔄 Post-Optimization Notes

* **Windows Updates:** If you need Windows Update services back online after finalizing your system modifications, you can safely re-enable updates using **WUB (Windows Update Blocker)**.
* **Driver Update Policies:** While keeping drivers updated is generally best practice under normal conditions, the stripped, telemetry-free deployment built here prevents structural overhead and mitigates performance drops.
* If u have problems, contact me on `Discord`: **n05y**
