# 📄 PaperReady AI
## AI-Powered Conference Paper Pre-Submission Readiness Checker

<p align="center">
  <b>Analyze Before You Submit.</b><br>
  Check formatting, references, figures, AI-writing risk, conference requirements, and submission readiness in one workflow.
</p>

---

## 📌 Overview

**PaperReady AI** is an AI-assisted pre-submission analysis system designed to help researchers check the readiness of a conference paper before submission.

Preparing a conference paper often requires authors to manually verify multiple aspects of their manuscript, including document formatting, figures, tables, citations, references, paper structure, conference requirements, and submission deadlines. These checks may involve different tools and repeated manual review.

**PaperReady AI brings multiple pre-submission checks into a unified pipeline.**

The system takes:

- 🌐 An **official conference / author-guidelines / Call for Papers URL**
- 📄 A **conference paper in `.docx` format**

It then performs multiple analyses and presents detailed module-wise results together with an overall paper-readiness assessment.

> ⚠️ PaperReady AI is designed as a **decision-support and pre-submission checking system**. It does not replace conference organizers, peer reviewers, editors, or official submission requirements.

---

# 🎯 Problem Statement

Before submitting a research paper to a conference, an author may need to answer questions such as:

- Is my paper formatted correctly?
- What page size, margins, fonts, and columns are used?
- Are figures properly numbered and referenced?
- Are tables and figures cross-referenced correctly?
- Are citations and references consistent?
- Are there missing or unreferenced items?
- Is the paper structurally complete?
- Does the text show strong AI-writing patterns according to an AI detector?
- Are figures and embedded images properly identified?
- What are the official conference requirements?
- What is the submission deadline?
- Does the paper comply with the requirements that can actually be verified?

Checking all of these manually can be time-consuming and can result in overlooked errors.

### 💡 PaperReady AI addresses this problem by providing a unified pre-submission analysis workflow.

---

# 🚀 Key Features

PaperReady AI combines the following capabilities:

| Module | Capability |
|---|---|
| **Module 1** | DOCX formatting and document analysis |
| **Module 2** | Figure and table cross-reference checking |
| **Module 3** | Citation and reference verification |
| **Module 4** | Paper structure and completeness analysis |
| **Module 5** | Section-aware AI-writing risk analysis |
| **Module 6** | Figure and visual analysis |
| **Module 7** | Conference requirements and deadline analysis |
| **Module 8** | Final paper readiness assessment |

---

# 🧠 End-to-End Idea

```text
                    ┌──────────────────────────┐
                    │  Official Conference URL │
                    └────────────┬─────────────┘
                                 │
                                 ▼
                      ┌──────────────────────┐
                      │ Requirement & Date  │
                      │ Extraction          │
                      └──────────┬───────────┘
                                 │
                                 │
┌──────────────────────┐         │
│ Conference Paper     │         │
│ (.docx)              │─────────┤
└──────────┬───────────┘         │
           │                     ▼
           ▼          ┌─────────────────────────┐
┌──────────────────┐  │      PaperReady AI      │
│ Document Reader  │──│  Pre-Submission Engine  │
└────────┬─────────┘  └────────────┬────────────┘
         │                         │
         └────────────┬────────────┘
                      ▼
      ┌─────────────────────────────────────┐
      │       Multi-Module Analysis         │
      └─────────────────────────────────────┘
                      │
      ┌───────────────┼────────────────┐
      ▼               ▼                ▼
 Formatting      Figures/Tables     Citations
      │               │                │
      ▼               ▼                ▼
 Structure      AI-Writing Risk    Visual Analysis
      │               │                │
      └───────────────┼────────────────┘
                      ▼
          Conference Requirement Comparison
                      │
                      ▼
           Final Paper Readiness Assessment
```

---

# 🧩 Module 1 — Document Formatting Analysis

The formatting module analyzes the uploaded `.docx` paper and extracts important document properties.

### Checks include:

- 📐 Page dimensions
- 📄 Paper size
- 📏 Page margins
- 📰 Section information
- 🧱 Number of columns
- 🔤 Font information
- 🔠 Font-size information
- 📝 Word styles
- ↔️ Paragraph alignment
- 📊 Line-spacing information
- 🖼️ Number of embedded images
- 📋 Number of tables

The module also considers the difference between:

- **Direct formatting**
- **Inherited formatting from Word styles/themes**

This is important because many `.docx` documents do not explicitly define the font and size for every character.

### Example Output

```text
PAGE AND SECTION ANALYSIS

Section 1
Page size
Paper size
Margins
Columns

FONT ANALYSIS

WORD STYLE ANALYSIS

EFFECTIVE FONT DISTRIBUTION

DIRECT VS INHERITED FORMATTING

COLUMN DISTRIBUTION

LINE SPACING

PARAGRAPH ALIGNMENT

DOCUMENT OBJECTS
```

The results are stored for use by later stages of the pipeline.

---

# 🧩 Module 2 — Figure and Table Cross-Reference Checker

This module checks the consistency between figures, tables, captions, and references in the paper.

### The module searches for:

- Figure references
- Figure captions
- Table references
- Table captions
- Duplicate figure numbers
- Missing figure references
- Unreferenced figure captions
- Missing table references
- Numbering gaps

### Example Checks

```text
✓ Figure 1 is mentioned and has a matching caption
✓ Figure 2 is mentioned and has a matching caption
✓ No clearly missing figure references detected
✓ All detected figure captions have corresponding text references

! Duplicate figure number detected
? Table caption not detected
```

This helps identify common manuscript consistency problems before submission.

---

# 🧩 Module 3 — Citation and Reference Verification

This module analyzes citations and references in the research paper.

Depending on the available metadata and verification results, the module can analyze:

- In-text citations
- Reference entries
- Citation-reference consistency
- Missing references
- Uncited reference entries
- DOI or identifier information where available
- External verification evidence
- Verification links

### Important

PaperReady AI preserves citation verification information and evidence generated by the analysis rather than replacing the result with a simplified pass/fail output.

This allows the final pipeline to retain useful verification details.

> ⚠️ Automated citation verification should still be reviewed by the author before submission.

---

# 🧩 Module 4 — Paper Structure and Completeness Analysis

This module identifies major sections in the conference paper.

Typical sections may include:

- Abstract
- Introduction
- Related Work
- Literature Review
- Methodology
- Proposed Method
- Results
- Discussion
- Conclusion
- References

### The system can:

- Detect major sections
- Count section-level content
- Identify missing or unusual structure
- Support section-aware analysis in later modules

### Example

```text
Detected Sections:

Abstract
Introduction
Literature Review
Methodology
Results
Conclusion
References
```

Paper structure can vary depending on the conference and research domain, so section detection is used as an analysis aid rather than a strict universal template.

---

# 🧩 Module 5 — Section-Aware AI-Writing Risk Analysis

This module analyzes the main prose sections of the paper using a trained AI-text detection model.

The system performs:

1. Section detection
2. Reference-section exclusion
3. Text chunking
4. Model inference
5. Section-wise aggregation
6. Overall risk interpretation

### Sections that may be analyzed:

- Abstract
- Introduction
- Literature Review
- Methodology
- Results
- Conclusion

### Reference Handling

The reference list is excluded from normal AI-writing analysis because bibliographic entries should not be treated as ordinary academic prose.

### Example Output

```text
SECTION-WISE RESULTS

Abstract
  Status             : ANALYZED
  Raw model signal   : ...

Introduction
  Status             : ANALYZED
  Raw model signal   : ...

Literature Review
  Status             : ANALYZED
  Raw model signal   : ...

Methodology
  Status             : ANALYZED
  Raw model signal   : ...

Results
  Status             : ANALYZED
  Raw model signal   : ...

Conclusion
  Status             : ANALYZED
  Raw model signal   : ...

References
  Status             : EXCLUDED
```

## ⚠️ Important Interpretation

The AI-writing result is a **model-based classification signal and risk indicator**.

It is **not scientifically conclusive proof** that AI wrote the paper.

A high score:

- Does not prove AI authorship
- May be influenced by formal academic writing
- May be affected by the model's training data
- May be affected by domain mismatch
- May produce false positives

Therefore, PaperReady AI presents this output as:

> **AI-Writing Risk Analysis — Not Proof of AI Authorship**

---

# 🧩 Module 6 — Figure and Visual Analysis

This module extracts embedded images from the `.docx` paper and analyzes their relationship with detected figures.

### The module identifies:

- Number of embedded images
- Figure captions
- Figure numbers
- Figure references
- Image dimensions
- Caption-to-image associations
- Figure cross-reference consistency

### Example

```text
Images extracted: 4

Figure/Image 1
  Figure number
  Visual type
  Dimensions
  Caption
  AI-generated probability: N/A
  Risk: NOT AVAILABLE
```

## Visual AI Detection

Where a compatible and validated visual AI detector is available, the architecture can support AI-generated visual risk analysis.

However, if no compatible detector is available in the execution environment, PaperReady AI explicitly reports:

```text
AI-generated visual probability: N/A
Risk: NOT AVAILABLE
```

The system does **not fabricate a visual AI probability**.

> A missing visual detector does not prove that an image is human-created. It only means that a reliable probability could not be calculated by the available pipeline.

---

# 🧩 Module 7 — Conference Requirements and Submission Deadline Analysis

This module uses an **official conference, author-guidelines, or Call for Papers URL**.

The system attempts to extract and verify information directly from the supplied official source.

### Potentially extracted information includes:

- 📅 Paper submission deadline
- 📅 Extended submission deadline
- 📅 Acceptance notification date
- 📅 Camera-ready deadline
- 📄 Page limit
- 📝 Abstract requirements
- 🔑 Keyword requirements
- 🔤 Font requirements
- 🔠 Font size
- 📐 Paper size
- 📰 Column count
- 📏 Margins
- ↔️ Line spacing
- 📋 Template information

### Conference Compliance Comparison

The module compares verified requirements with the formatting information extracted from the uploaded paper.

For example:

```text
Paper Size
Required: ...
Actual: ...
Status: ...

Columns
Required: ...
Actual: ...
Status: ...

Font
Required: ...
Actual: ...
Status: ...
```

## Truthfulness Principle

If a requirement cannot be verified from the official source, PaperReady AI reports:

```text
UNKNOWN / NOT VERIFIED
```

It does not invent requirements.

### Fallback Guidance

Any general publisher or template guidance is clearly separated from:

> **Officially Verified Conference Requirements**

Fallback information is not treated as official conference compliance data.

---

# 🧩 Module 8 — Final Paper Readiness Assessment

The final stage combines results from the individual analysis modules.

The final assessment provides a clear overview of:

- 📐 Document formatting
- 🖼️ Figure and table consistency
- 🔗 Citation and reference verification
- 🧱 Paper structure
- 🤖 AI-writing risk
- 🖼️ Figure and visual analysis
- 🌐 Conference requirement verification
- 📅 Submission deadlines
- ⚠️ Issues requiring author review

## Final Pipeline Principle

PaperReady AI is designed to preserve meaningful information from the individual modules.

For example:

- Detailed citation verification evidence is retained
- Verification links are retained where available
- Unknown conference requirements remain marked as unknown
- Module-specific issues are not silently converted into fabricated pass results
- AI-writing output remains a risk indicator
- Unavailable visual detection remains `NOT AVAILABLE`

This makes the final pipeline more transparent and useful for presentation and review.

---

# 🔄 Complete Workflow

```text
STEP 1
Enter Official Conference / Author Guidelines URL
                    ↓
STEP 2
Upload Conference Paper (.docx)
                    ↓
STEP 3
Run Document Formatting Analysis
                    ↓
STEP 4
Run Figure and Table Cross-Reference Analysis
                    ↓
STEP 5
Run Citation and Reference Verification
                    ↓
STEP 6
Run Paper Structure Analysis
                    ↓
STEP 7
Run Section-Aware AI-Writing Risk Analysis
                    ↓
STEP 8
Run Figure and Visual Analysis
                    ↓
STEP 9
Extract Official Conference Requirements
                    ↓
STEP 10
Extract Submission Deadlines
                    ↓
STEP 11
Compare Paper with Verified Requirements
                    ↓
STEP 12
Generate Final Paper Readiness Assessment
```

---

# 🛠️ Technology Stack

PaperReady AI is developed using the following technologies and libraries:

### Programming Environment

- Python
- Google Colab
- Jupyter Notebook

### Document Processing

- `python-docx`
- ZIP/XML-based DOCX inspection
- Regular Expressions

### AI and Machine Learning

- PyTorch
- Hugging Face Transformers
- Trained AI-text detection model

### Web and Requirement Analysis

- Requests
- BeautifulSoup
- URL-based official source extraction

### Data Handling

- JSON
- Python standard libraries

---

# 📥 Inputs

## Input 1 — Official Conference URL

Provide an official:

- Conference website URL
- Call for Papers URL
- Author Guidelines URL
- Submission requirements URL

Example:

```text
https://example-conference.org/call-for-papers
```

> The URL should be an official conference source whenever possible.

---

## Input 2 — Conference Paper

Upload the conference paper in:

```text
.docx
```

format.

The current pipeline is designed primarily for Word-based conference papers.

---

# 📤 Outputs

PaperReady AI displays detailed results for each module directly in the notebook.

### Outputs include:

```text
✓ Formatting Analysis
✓ Section and Page Analysis
✓ Figure Analysis
✓ Table Analysis
✓ Cross-Reference Checks
✓ Citation and Reference Verification
✓ Paper Structure Analysis
✓ AI-Writing Risk Analysis
✓ Visual Analysis
✓ Conference Requirement Extraction
✓ Deadline Extraction
✓ Paper vs Conference Comparison
✓ Final Readiness Assessment
```

Module results can also be stored as JSON files for integration into the final pipeline.

---

# 📁 Project Structure

A typical repository structure is:

```text
PaperReady-AI/
│
├── PaperReady_AI.ipynb
├── README.md
├── .gitignore
├── LICENSE
│
└── outputs/
    └── JSON analysis results (generated during execution)
```

If the notebook currently has a different name, it may be renamed to:

```text
PaperReady_AI.ipynb
```

for a more professional repository structure.

---

# ▶️ Installation and Usage

## Option 1 — Google Colab

### Step 1: Open the Notebook

Upload or open the `.ipynb` notebook in Google Colab.

### Step 2: Run the Required Setup Cells

Run the dependency installation and model setup cells.

### Step 3: Run the Pipeline

Execute the modules in the required order.

### Step 4: Enter the Official Conference URL

When prompted, provide the official conference or guidelines URL.

### Step 5: Upload the Paper

Upload the `.docx` conference paper.

### Step 6: Review the Module Results

Each module displays its detailed analysis.

### Step 7: Review the Final Readiness Assessment

The final pipeline combines the module results into a pre-submission overview.

---

## Option 2 — Jupyter Notebook

Install the required dependencies and run:

```bash
jupyter notebook
```

Then open the PaperReady AI notebook and execute the cells in sequence.

---

# 📊 Example Analysis Summary

A typical final analysis may contain information similar to:

```text
============================================================
PAPERREADY AI — FINAL PAPER READINESS ASSESSMENT
============================================================

FORMATTING
Status: REVIEWED

FIGURES AND TABLES
Status: ISSUES / PASS / REVIEW REQUIRED

CITATIONS AND REFERENCES
Status: VERIFIED RESULTS AVAILABLE

PAPER STRUCTURE
Status: ANALYZED

AI-WRITING RISK
Status: RISK INDICATOR AVAILABLE

VISUAL ANALYSIS
Status: AVAILABLE / NOT AVAILABLE

CONFERENCE REQUIREMENTS
Status: VERIFIED / PARTIALLY VERIFIED

SUBMISSION DEADLINE
Status: DETECTED / NOT FOUND

FINAL ACTION
Review all detected issues before submitting the paper.
============================================================
```

The actual output depends on:

- The uploaded paper
- The available document metadata
- The official conference source
- The availability of compatible AI models
- The quality and structure of the `.docx` file

---

# 🔬 Research Foundation

PaperReady AI is inspired by research across multiple areas of scholarly document processing.

Its research foundation includes:

- AI-generated scientific text detection
- Scientific document analysis
- Document layout analysis
- Multimodal document understanding
- Figure and table understanding
- Claim-to-evidence relationships
- Citation and reference analysis

## ⭐ Main Base Papers

### 1. Chamezopoulos et al. — DAGPap24

**Savvas Chamezopoulos, Drahomira Herrmannova, Anita de Waard, Domenic Rosati, and Yury Kashnitsky (2024)**

**Overview of the DAGPap24 Shared Task on Detecting Automatically Generated Scientific Paper**

*Proceedings of the Fourth Workshop on Scholarly Document Processing (SDP 2024), ACL.*

### Relevance to PaperReady AI

Supports the research foundation for:

> **AI-generated scientific-text detection and Module 5 AI-writing risk analysis.**

---

### 2. Zhang et al. — VSR

**Peng Zhang, Can Li, Liang Qiao, Zhanzhan Cheng, Shiliang Pu, Yi Niu, and Fei Wu (2021)**

**VSR: A Unified Framework for Document Layout Analysis Combining Vision, Semantics and Relations**

*ICDAR 2021.*

### Relevance to PaperReady AI

Supports the research foundation for:

> **Document structure, formatting, layout, and semantic relationship analysis.**

---

### 3. Kumar & Wang — CLIP for Scientific Evidence Identification

**Anukriti Kumar and Lucy Wang (2024)**

**Harnessing CLIP for Evidence Identification in Scientific Literature: A Multimodal Approach to Context24 Shared Task**

*Proceedings of the Fourth Workshop on Scholarly Document Processing (SDP 2024), ACL.*

### Relevance to PaperReady AI

Supports the research foundation for:

> **Multimodal analysis and relationships between scientific claims, figures, and tables.**

---

# 🌟 Key Innovation

Many existing approaches focus on a single task, such as:

```text
AI Text Detection
OR
Document Formatting
OR
Citation Analysis
OR
Figure Analysis
OR
Conference Guidelines
```

PaperReady AI aims to integrate these areas into one workflow:

```text
Document Formatting
        +
Figure/Table Cross-Checking
        +
Citation & Reference Verification
        +
Paper Structure Analysis
        +
AI-Writing Risk Analysis
        +
Figure & Visual Analysis
        +
Conference Requirement Verification
        +
Submission Deadline Analysis
        +
Final Readiness Assessment
```

## 💡 Core Contribution

> **PaperReady AI focuses on integrating multiple scholarly document checks into a unified pre-submission conference-paper readiness pipeline.**

The purpose is not to replace human academic judgment, but to help authors identify potential issues before submitting their paper.

---

# ⚠️ Limitations

PaperReady AI has several important limitations.

## AI-Writing Detection

AI-writing scores:

- Are model-based signals
- Are not proof of AI authorship
- Can produce false positives
- Can be affected by academic writing style
- Can be affected by domain mismatch

## Conference Requirements

Some official conference websites may not explicitly publish:

- Font information
- Margin information
- Page limits
- Column counts
- Template specifications

In such cases, the system should report the requirement as:

```text
UNKNOWN / NOT VERIFIED
```

rather than inventing a value.

## Visual AI Detection

A visual AI-generated probability depends on the availability of a compatible and validated detector.

If no such detector is available, the system reports:

```text
NOT AVAILABLE
```

## Document Format

The current implementation primarily supports:

```text
.docx
```

Papers in other formats may require future extensions.

---

# 🚀 Future Scope

Future versions of PaperReady AI may include:

- 📕 PDF paper support
- 🧩 Direct comparison with official conference templates
- 🌐 Web application interface
- 📊 Interactive paper-readiness dashboard
- 🔍 Advanced citation metadata validation
- 🔗 DOI validation and metadata matching
- 🖼️ Improved visual AI analysis
- 🧠 Better calibrated AI-writing risk models
- 📄 Multi-template support
- 🛠️ Automated formatting correction suggestions
- ✍️ Issue-specific improvement recommendations
- 📤 Downloadable final readiness reports
- 🏆 Support for multiple conference publishers and templates

---

# 👩‍💻 Author

**Vyshali**

PaperReady AI was developed as an academic and hackathon-oriented project focused on improving the **research paper pre-submission workflow**.

---

# 🤝 Contributions

Contributions, suggestions, and improvements are welcome.

Potential contribution areas include:

- Better DOCX parsing
- PDF support
- Conference guideline extraction
- Citation verification
- AI model calibration
- Visual document analysis
- User interface development
- Additional conference template support

---

# 📜 License

This project is released under the **MIT License**.

---

# ⚠️ Disclaimer

PaperReady AI is an automated assistance system.

The results produced by the system should be used as **pre-submission guidance and decision support**.

The final responsibility for:

- Conference formatting compliance
- Reference correctness
- Citation accuracy
- Academic integrity
- AI usage disclosure
- Submission eligibility

remains with the author.

Conference organizers and official author guidelines remain the final authority on submission requirements.

---

<p align="center">

## ⭐ PaperReady AI

### **Analyze Before You Submit.**

**Check Your Paper. Review the Risks. Verify What You Can. Submit with Confidence.**

📄 + 🤖 + 🔍 + 🌐 = **PaperReady AI**

</p>
