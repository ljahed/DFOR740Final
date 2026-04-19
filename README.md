# DFOR 740 Final Project - Process Anomaly Detector

## Description
The Process Anomaly Detector is a Windows defensive deception tool that learns the normal behavior of running processes (executable paths, parent processes, and user accounts) and then alerts on any deviation. It is designed to catch **process masquerading** – for example, an attacker renaming `cmd.exe` to `svchost.exe` and running it from a temporary folder.

## Features
- Detects process masquerading and unusual execution contexts.
- Logs alerts to console and Windows Event Log.
- Optionally terminates suspicious processes (`--terminate`).
- Baseline persists in Windows Registry.

## Compilation

### Using Visual Studio (IDE)
1. Create a new **Console Application** project.
2. Replace the content of the main `.cpp` file with the provided source code.
3. In **Project Properties → Linker → Input → Additional Dependencies**, add `advapi32.lib` (if not already present).
4. Build the solution (F7). The executable will be created in the `Debug` or `Release` folder.

### Running the Code Using Command Line (Developer Command Prompt)
1. Open a **Developer Command Prompt for Visual Studio** (as Administrator if you want to test immediately).
2. Navigate to the folder containing the executable file (e.g., `DFOR 740.exe`).
3. If you run the tool without any arguments, or with `help` or `?`, a help screen is displayed.

## Options
--terminate	Kill processes that trigger an anomaly alert (requires Admin).

## License
This tool is provided for educational purposes only. Use responsibly.
