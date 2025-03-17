# 🔍 Memory Forensics and Active Cyber Defense

Welcome to the Memory Forensics and Active Cyber Defense repository! This project involves detailed memory forensic analyses using the Volatility Framework to investigate suspicious activities, malicious processes, and network connections within memory dumps.

## 🎯 Objectives
- Identify malicious activities and compromised processes using memory analysis.
- Investigate suspicious network connections and determine associated processes.
- Detect and analyze process injection and API hooking using forensic techniques.

## 🛠️ Tools & Technologies
- **Volatility Framework** (Memory Analysis)
- **Kali Linux (Windows Subsystem for Linux - WSL)**
- **Notepad++ (Data Analysis)**

## 📚 Project Files
- [`Volatility`](https://github.com/DDMetoyer/Memory-Forensics-and-Defense/blob/main/Volatility.pdf)
- [`API`](https://github.com/DDMetoyer/Memory-Forensics-and-Defense/blob/main/API.pdf)

## ⚙️ Methodology

### 🔬 [`API`](https://github.com/DDMetoyer/Memory-Forensics-and-Defense/blob/main/API.pdf)
- Investigated API hooking events, distinguishing user-mode versus kernel-mode.
- Identified hooking techniques (Inline/Trampoline) targeting `wsmprovhost.exe` process.
- Determined hook operation in user-mode, disproving the kernel-mode hooking claim.

### 🌐 [`Volatility`](https://github.com/DDMetoyer/Memory-Forensics-and-Defense/blob/main/Volatility.pdf): Network and Process Injection Investigation
- **Network Connection Analysis:**
  - Command:
    ```bash
    volatility -f TORNBERG.dmp --profile=Win8SP1x64 netscan -v > torn_netscan.txt
    ```
  - Identified active network connections, highlighting suspicious established connections (port 4444).

- **Process Injection Detection:**
  - Used `malfind`, `apihooks`, and `ldrmodules` plugins to uncover process injection into `powershell.exe` (PID: 1748).
  - Identified malicious DLL injection conducted by process PID 5012.

- **Remote Desktop Protocol (RDP) Investigation:**
  - Confirmed host system (`10.252.9.131`) receiving RDP connections on port 3389.
  - Attributed management of RDP connection to `svchost.exe`.

## 🚩 Key Findings
- [`API`](https://github.com/DDMetoyer/Memory-Forensics-and-Defense/blob/main/API.pdf) Confirmed API hooks occurred strictly in user-mode, debunking kernel-mode hooking suspicion.
- [`Volatility`](https://github.com/DDMetoyer/Memory-Forensics-and-Defense/blob/main/Volatility.pdf)
  - Identified process injection targeting `powershell.exe`.
  - Confirmed process PID 5012 responsible for malicious code injection.
  - Detected active RDP sessions handled by `svchost.exe`.

## 📌 Conclusion
These memory forensic investigations effectively demonstrate how memory analysis techniques can reveal critical details of cyber intrusions, enhancing capabilities for active cyber defense and incident response.

## ⚠️ Disclaimer
The tools and analyses presented in this repository are strictly for educational and ethical research purposes. Misuse of the provided information is strictly prohibited.
