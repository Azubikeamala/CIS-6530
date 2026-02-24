Overview

This submission contains a curated collection of malicious payloads associated with documented Advanced Persistent Threat (APT) groups.

Artifacts are organized into two categories:

Executable Malware

Other Payloads

Where direct binary downloads were not publicly accessible, verified SHA256 hashes attributed to the respective APT groups were documented instead.

⚠️ Safety Notice – Do Not Execute

The files included in this dataset represent real malicious artifacts or cryptographic identifiers of such artifacts.

These files must not be executed on a host system.

Any analysis should only be performed:

Within an isolated virtual machine (VM)

With networking disabled unless specifically required

Using appropriate malware analysis tools

In a controlled laboratory environment

The repository maintainer assumes no responsibility for misuse of the included artifacts.

Academic Use Disclaimer

This dataset is curated strictly for academic research and defensive cybersecurity education.

Artifacts were obtained from publicly accessible malware intelligence platforms used by the security research community. No attempt has been made to operationalize, weaponize, or distribute malware for malicious purposes.

Dataset Structure
Submission_2/
│
├── Executable_Malware/
└── Other_Payloads/


Each artifact is labeled according to its associated APT group.
Hash-only artifacts include SHA256 identifiers traceable to VirusTotal intelligence records.

Sources

MITRE ATT&CK – APT Group Attribution

MalwareBazaar – Public Malware Repository

VirusTotal – Hash Intelligence and Detection Metadata
