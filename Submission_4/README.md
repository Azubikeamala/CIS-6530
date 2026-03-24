# Submission 4 – Malware Classification Using Opcode Analysis

## 📌 Overview

This project implements a machine learning approach to classify executable files as **malware** or **benign** using opcode sequence analysis. The system leverages instruction-level behavior rather than traditional signature-based detection.

---

## 📦 Project Structure

The full project is packaged as a compressed archive:

```id="zipstructure"
Iyagba_Azubike_Submission_4.zip
```

The ZIP file contains:

* Dataset (processed opcode files)
* `main.py` (model training and evaluation)
* `load_dataset.py` (data loading and preprocessing)

---

## ⚙️ Methodology Summary

### Opcode Processing

* Extracted from executables using reverse engineering tools
* Cleaned to retain only opcode mnemonics
* Converted into sequential text format

### Feature Engineering

* **1-gram**: Individual opcodes
* **2-gram**: Opcode pairs

### Vectorization

```python id="veczip"
CountVectorizer(ngram_range=(1,2))
```

### Models Used

* Support Vector Machine (SVM)
* K-Nearest Neighbors (KNN, k=3)
* Decision Tree

---

## 📊 Results Summary

| Model         | Accuracy | Precision | Recall | F1 Score |
| ------------- | -------- | --------- | ------ | -------- |
| SVM           | 0.92     | 0.846     | 0.92   | 0.882    |
| KNN (k=3)     | 0.92     | 0.846     | 0.92   | 0.882    |
| Decision Tree | 0.92     | 0.96      | 0.92   | 0.932    |

### Key Insight

All models achieved similar accuracy, but the **Decision Tree model provides more balanced classification performance**, especially for benign samples.

---

## ⚠️ Dataset Note

Full dataset excluded due to size limitations.
Available upon request.

---

## 🚀 How to Run

1. Extract the ZIP file
2. Navigate into the extracted folder
3. Install dependencies:

```bash id="runzip1"
pip install scikit-learn pandas numpy
```

4. Run:

```bash id="runzip2"
python main.py
```

---

## 📚 References

* MITRE ATT&CK Framework: https://attack.mitre.org/
* NIST Malware Guide: https://nvlpubs.nist.gov/
* Scikit-learn Documentation: https://scikit-learn.org/
* Ghidra: https://ghidra-sre.org/

---

## 👥 Authors

* Bereni Iyagba
* Amalachukwu Azubike

---

## 📌 Notes

This project was developed for
**CIS*6530 – Cyber Threat Intelligence and Adversarial Risk Analysis**

