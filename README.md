# DFOR 740 Final Project - Process Anomaly Detector

## Description
The Process Anomaly Detector is a Windows defensive deception tool that attempts to learn the normal behavior of running processes (executable paths, parent processes, and user accounts) and then alerts on any deviation. It is designed to catch **process masquerading** – for example, an attacker renaming `cmd.exe` to `svchost.exe` and running it from a temporary folder.

## Features
- Detects process masquerading and unusual execution contexts.
- Logs alerts to console and Windows Event Log.
- Baseline persists in Windows Registry.

## Compilation

### Using Visual Studio (IDE)
1. Create a new **Console Application** project.
2. Replace the content of the main `.cpp` file with the provided source code.
3. In **Project Properties → Linker → Input → Additional Dependencies**, add `advapi32.lib` (if not already present).
4. Build the solution (F7). The executable will be created in the `Debug` or `Release` folder.

### Running the Code Using Command Line (Developer Command Prompt)
1. Open a **Developer Command Prompt for Visual Studio** (as Administrator if you want to test immediately). or an Administrator Command Prompt.
2. Navigate to the folder containing the executable file (e.g., `DFOR 740.exe`).
3. If you run the tool without any arguments, or with `help` or `?`, a help screen is displayed.
4. Run the code initially to establish the baseline for normal processes and how they are run. Afterwards, you can run the tool as often as you would like to see any alerts for suspicious processes.
5. Go to Windows Registry location HKEY_CURRENT_USER\Software\DFOR740Detector to view information from the tool's scans.

## Options
1. Press X to stop the tool's scanning
2. -- min (Number) to establish how many times a process must appear to become part of the baseline

## License
This tool is provided for educational purposes only. Use responsibly.
