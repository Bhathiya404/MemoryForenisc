# MemoryForenisc
This notebook presents an automated workflow for analyzing Windows memory images as part of a memory forensics investigation. The workflow begins by specifying the path to a Windows memory image that will be analyzed. A memory image represents a snapshot of the system’s volatile memory (RAM) captured at a specific point in time.

Once the memory image path is provided, the framework initiates an automated forensic analysis process using the Volatility memory forensics framework. The workflow extracts and analyzes key forensic artifacts to assist investigators in identifying suspicious or malicious activity within the system.

Memory images can contain valuable forensic evidence, including information about running processes, network connections, loaded drivers, injected code segments, and other system artifacts. Analyzing these artifacts enables investigators to detect indicators of compromise and better understand the behavior of potential malware or unauthorized activities present in the system.

Following Open Source projects are used in this workflow

https://github.com/microsoft/msticpy

Author:
Bhathiya Madanayaka
bathiyapulasthi@gmail.com

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Pre-requisites

### Software Requirements
- Python 3.8 or above  
- Jupyter Notebook  
- Volatility 3
- API keys are required to support MSTICPY with its enrichments. GreyNoise and OTX

### Python Libraries
```bash
pip install msticpy[azure] seaborn jellyfish pandas argparse colorama selenium pillow matplotlib networkx

```

### The framework implements the following detection rules:

- Rule 1: Detection of multiple instances of single-instance processes
- Rule 2: Suspicious parent-child process lineage detection
- Rule 3: Process masquerading using name similarity (Damerau-Levenshtein distance)
- Rule 4: svchost.exe / rundll32.exe without command-line arguments
- Rule 5: Executables running from suspicious directories
- Rule 6: Process network relationship visualization
- Rule 7: Process-to-network communication mapping
- Rule 8: Process execution time anomaly detection
- Rule 9: Suspicious command-line argument detection
- Rule 10: IoC extraction from command lines
- Rule 11: Suspicious rundll32.exe parent detection
- Rule 12: External communication frequency analysis
- Rule 13: Threat intelligence correlation of external IPs/domains
- Rule 14: Suspicious non-browser web connections
- Rule 15: IP address detection in command-line arguments
- Rule 16: Kernel callback anomaly detection
- Rule 17: SSDT hooking detection
- Rule 18: Wiped driver base address detection
- Rule 19: Suspicious Windows service name detection
- Rule 20: DLL/SYS loaded from unusual locations
- Rule 21: Detection of unusually long DLL/SYS names
- Rule 22: Malfind-based MZ header detection (injected code)
- Rule 23: Malfind-based assembly/code injection detection

### Usage

1. git clone https://github.com/Bhathiya404/MemoryForenisc.git
2. Update msticpyconfig.yaml and include the API keys described in the pre-requisites
3. Open the workflow.ipynb within Jupyter and follow instructions within the notebook
4. Follow the instraction given withing the workflow notbook.


### Sample Outputs
<img width="1570" height="1122" alt="image" src="https://github.com/user-attachments/assets/eac643ee-a904-4a85-b256-4ac4c68b1ec2" />

<img width="1984" height="1984" alt="image" src="https://github.com/user-attachments/assets/5e3953e1-0114-4548-95c4-ebfda79f7475" />

<img width="559" height="529" alt="image" src="https://github.com/user-attachments/assets/b28b8cb4-a67b-42b6-b416-46123079c8d3" />



