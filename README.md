# DCPMetaForge Pro (v1.0.0)

> **SMPTE ST 429 Digital Cinema Package (DCP) Studio, ISDCF Naming Assistant & Theatrical Package Validator CLI**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](http://LICENSE) [![SMPTE](https://img.shields.io/badge/Standard-SMPTE%20ST%20429--7%20%2F%20429--8-red.svg)](https://www.smpte.org) [![ISDCF](https://img.shields.io/badge/Naming-ISDCF%20v9.5-gold.svg)](https://isdcf.com) [![Python](https://img.shields.io/badge/Python-3.8%2B-brightgreen.svg)](https://www.python.org/) ![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20CLI%20%7C%20Docker-purple.svg)

---

## 📽 Overview

**DCPMetaForge Pro** is an autonomous engineering workstation designed for independent filmmakers, theatrical finishing houses, film festival projectionists, and digital cinema mastering engineers. Operating within the **SMPTE ST 429 Digital Cinema Package (DCP)** ecosystem, it bridges the gap between complex theatrical standards and independent post-production by delivering:

1. **SMPTE ST 429 Package Manifest Synthesis**: Generates compliant, production-ready XML documents:  
   - **CPL.xml (ST 429-7)**: Composition Playlist specifying theatrical reel order, aspect ratios, and durations.  
   - **PKL.xml (ST 429-8)**: Packing List declaring cryptographic SHA-1 hashes and file sizes for MXF essences.  
   - **ASSETMAP.xml (ST 429-9)**: Filesystem asset mapping detailing chunk lengths and volume indices.  
2. **ISDCF Digital Cinema Naming Assistant (v9.5)**: Interactive token builder that constructs bulletproof, projection-booth-compliant `ContentTitleText` strings communicating aspect ratios, audio routing, and subtitle languages to automated Theater Management Systems (TMS).  
3. **10-Point Normative Theatrical Auditor**: Automated verification engine checking RFC 4122 UUID compliance, picture and audio reel duration synchronization, rational edit rates (`24 1`, `25 1`), DCI aspect ratios (Flat 1.85:1 vs Scope 2.39:1), and manifest hash integrity.  
4. **Standalone Python CLI (`dcp-cli.py`)**: Zero-dependency command-line utility for automated theatrical ingest pipelines.

---

## 🚀 Key Features

- **Standard DCI Resolutions & Containers**: Pre-configured support for 2K Flat (1998x1080), 2K Scope (2048x858), 4K Flat (3996x2160), 4K Scope (4096x1716), and Full Container (1.90:1).  
- **Audio Configuration Presets**: Supports 5.1 Surround, 7.1 Surround, Dolby Atmos bitstreams, and 2.0 Stereo.  
- **ISDCF Token Decomposition**: Live visual chips highlighting Title, Content Kind (FTR, TLR, TSR), Aspect Ratio, Language, Rating, and Package Type (OV/VF).  
- **Reel Synchronization Guard**: Verifies that picture and sound tracks within each reel share identical frame lengths to prevent theatrical sync drift.  
- **Zero Heavy Runtime Dependencies**: Pure standard library Python 3 CLI and modern HTML5/ES6 web studio.

---

## 🛠 Quick Start

### 1\. Interactive Web Studio

Open `source-code/index.html` directly in any modern web browser:

- Enter your Movie Title and choose Content Kind and Format.  
- Adjust Audio configuration, language pair, territory, and rating.  
- Click **"Synthesize Package Manifests"** to generate all three core SMPTE XML files.  
- Inspect the **ISDCF Naming Assistant** tab.  
- Copy or download **CPL.xml**, **PKL.xml**, and **ASSETMAP.xml**.  
- Run the **10-Point Normative Theatrical Auditor**.

### 2\. Standalone Python CLI

\# Display CLI help

python3 build/dcp-cli.py \--help

\# Generate full SMPTE DCP package manifests

python3 build/dcp-cli.py create \--out-dir ./dcp\_package/ \--title "HORIZON" \--kind FTR \--format 2K\_FLAT \--fps 24

\# Audit an existing CPL file

python3 build/dcp-cli.py audit ./dcp\_package/CPL.xml

\# Generate ISDCF Title text

python3 build/dcp-cli.py isdcf \--title "INTERSTELLAR" \--kind FTR \--format 4K\_SCOPE

### 3\. Run Automated Test Suite

python3 test\_dcp.py

---

## 📁 Repository Structure

product\_278/

├── README.md                          \# Main project overview & user manual

├── test\_dcp.py                        \# 10-point automated unit test suite

├── source-code/

│   ├── index.html                     \# Interactive multi-tab Studio UI

│   ├── dcp.css                        \# Theatrical dark theme stylesheet

│   ├── dcp-engine.js                  \# DCI / SMPTE ST 429 manifest engine

│   ├── dcp-auditor.js                 \# 10-point normative compliance rules

│   └── app.js                         \# Application event controller & UI glue

├── build/

│   ├── dcp-cli.py                     \# Standalone executable CLI utility

│   └── dcpmetaforge-pro-v1.0.0.zip    \# Complete production release package

├── documentation/

│   ├── ARCHITECTURE.md                \# SMPTE ST 429 specification deep-dive

│   ├── USER\_GUIDE.md                  \# Comprehensive operational manual

│   └── MONETIZATION\_AND\_MARKETING\_PLAYBOOK.md \# Commercial strategy & pricing tiers

└── screenshots/

    └── dcp-studio-preview.svg         \# High-resolution vector preview of GUI

---

## 📄 License

Released under the MIT License. Copyright © 2026 Autonomous Digital Product Factory.