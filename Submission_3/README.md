README – Submission 3
Malware Opcode Extraction and Static Analysis using IDA
Course

CIS-6530 – Cyber Threat Intelligence
University of Guelph
Winter 2026

Authors

Iyagba – Azubike

Overview

This submission contains the results of a static malware analysis project focused on extracting operational codes (opcodes) from malware samples using IDA Free.

The goal of the analysis was to examine malware samples associated with several Advanced Persistent Threat (APT) groups, determine their binary characteristics, and extract opcode sequences that can later be used for malware classification, pattern analysis, or machine learning research.

The analysis workflow involved:

Collecting malware samples associated with known APT groups.

Loading each sample into IDA Free.

Determining the binary type, architecture, and execution characteristics.

Extracting opcode sequences when possible.

Documenting the analysis results for each sample.

Some samples could be fully analyzed, while others were limited by architecture compatibility or binary format constraints.

Contents of the Submission

The ZIP file in this folder contains the following components:

Submission_3/
│
├── Iyagba_Azubike.zip
│
├── README.md

The ZIP archive includes:

Iyagba_Azubike/
│
├── malware_samples/
│
├── opcode_outputs/
│
├── screenshots/
│
└── analysis_documentation.pdf
Malware Samples

The dataset includes samples associated with multiple APT groups, including:

APT3

APT12

APT17

APT19

APT28

APT29

APT30

APT33

APT39

APT41

Axiom

Chimera

Evilnum

Gamaredon

MenuPass

Patchwork

SideWinder

Turla

FIN7

These samples were extracted from a threat intelligence malware dataset used in the course lab.

Analysis Tool

All static analysis in this project was performed using:

IDA Free

IDA Free was used to:

identify executable architecture

inspect disassembly

extract readable strings

identify entry points

examine PE structure

export opcode sequences

However, several limitations were encountered due to the capabilities of the free version.

Analysis Workflow

The general workflow used for each malware sample was:

Open the executable in IDA Free.

Allow IDA to perform initial auto-analysis.

Identify key properties such as:

binary format

architecture

entry point

imported APIs

readable strings

Determine whether the sample was:

native executable

raw binary payload

.NET managed assembly

document container

compressed or packed artifact

If possible, export opcode sequences for use in the dataset.

Important Observations from the Analysis

Several patterns were observed across the analyzed samples.

1. Raw Binary Payloads

Some samples did not contain valid PE headers and were loaded by IDA as raw binary data.

Examples include:

APT3

APT12

APT19

APT30

These samples likely represent:

packed malware payloads

shellcode fragments

extracted artifacts from larger malware archives.

The absence of PE structure prevented full disassembly.

2. Native Windows Executables

Several samples were valid Windows PE files compiled for x86 architecture and could be fully analyzed.

Examples include:

APT17

APT39

Gamaredon

Turla

These binaries allowed:

identification of entry points

disassembly of program logic

extraction of opcode sequences.

For example, the Gamaredon sample was successfully disassembled and produced a 61751-line opcode output file. 

Iyagba_Azubike_Malware_Analysis…

3. 64-bit Malware Samples

Some executables were compiled for AMD64 architecture.

Examples include:

APT28

APT29

APT33

APT41

Because the analysis environment used IDA Free, which does not support AMD64 binaries, full reverse engineering could not be performed. 

Iyagba_Azubike_Malware_Analysis…

4. .NET Malware

Several samples were identified as .NET managed assemblies, including:

Chimera

Evilnum

Patchwork

These executables rely on the Common Language Runtime (CLR) and contain the entry point:

_CorExeMain

IDA Free cannot analyze CLI bytecode, so full managed code reconstruction was not possible. 

Iyagba_Azubike_Malware_Analysis…

5. Document-Based Malware Delivery

The MenuPass sample was identified as a Microsoft Word OpenXML document rather than an executable.

The internal structure contained:

[Content_Types].xml
word/document.xml
word/media/image1.jpeg

This confirms that the file acts as a malicious delivery document used in spear-phishing campaigns, rather than the final malware payload. 

Iyagba_Azubike_Malware_Analysis…

Opcode Extraction

Opcode extraction was performed for executable samples where disassembly was possible.

Opcode files were generated in the following format:

sample_name.opcode

These files contain the extracted instruction sequences used for later malware analysis tasks such as:

behavioral comparison

opcode frequency analysis

machine learning classification.

Automation Script

To improve efficiency when analyzing multiple malware families, a Windows batch automation script was developed.

The script:

Allows the analyst to specify the malware family folder.

Searches for executable files within that directory.

Checks for existing analysis results such as:

.opcode
.idb
.i64

Opens the correct file in IDA depending on whether prior analysis exists.

This prevents accidental overwriting of previous analysis results and allows consistent workflow across multiple malware families. 

Iyagba_Azubike_Malware_Analysis…

Security and Ethical Notice

This repository contains malware samples and reverse engineering artifacts used strictly for academic cybersecurity research and coursework.

These materials are intended for:

malware analysis education

reverse engineering practice

threat intelligence training

All malware analysis must be performed in isolated environments such as virtual machines or dedicated analysis labs.

Running malware on production systems is strictly prohibited.

Repository Structure

Within this GitHub repository the project is organized as:

CIS-6530
│
├── Submission_2
│
├── Submission_3
│   ├── Iyagba_Azubike.zip
│   └── README.md
│
└── README.md
