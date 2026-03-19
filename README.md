# Curriculum-Aware and Grounded Multimodal RAG for SSC-Level Bangla and Code-Mixed Educational Assistance

This repository contains the paper, figures, datasets, benchmark resources, and supporting materials for the study:

**Curriculum-Aware and Grounded Multimodal RAG for SSC-Level Bangla and Code-Mixed Educational Assistance**

The project introduces a curriculum-aware multimodal retrieval-augmented generation (RAG) framework for SSC-level educational assistance from textbook PDFs in Bangladesh. The system is designed to support grounded question answering, concept explanation, figure and table understanding, and assessment-oriented generation such as MCQs, CQs, and quizzes from multimodal textbook content.

---

## Overview

SSC-level students in Bangladesh mainly study from prescribed textbooks, notes, and exam-oriented PDFs. These materials contain not only text, but also figures, diagrams, tables, page-level layout cues, and scanned visual content. Traditional text-only retrieval and generation systems often fail to preserve this structure, which can reduce grounding quality and pedagogical usefulness.

To address this, this repository accompanies a multimodal educational RAG pipeline that:

- parses heterogeneous educational PDFs,
- cleans and structures multimodal content,
- applies curriculum-aware chunking,
- builds multimodal searchable representations,
- performs subject-aware hybrid retrieval and reranking,
- supports grounded generation for multiple student tasks,
- validates outputs for grounding, citation consistency, and task-specific quality.

---

## Main Contributions

The work presented in this repository focuses on the following contributions:

1. **Curriculum-aware multimodal RAG framework** for SSC textbook PDFs that jointly represents text, tables, figures, and page-level structure.
2. **Support for multiple student-facing tasks**, including factual QA, concept explanation, figure understanding, table understanding, MCQ generation, CQ generation, and quiz generation.
3. **Grounded generation and validation layer** for improving reliability, citation consistency, and educational quality.
4. **SSC-oriented benchmark and evaluation pipeline** covering retrieval, answer quality, multimodal understanding, ablation analysis, and human evaluation.

---

## Repository Structure

A recommended repository structure is shown below:

```text
.
├── README.md
├── LICENSE
├── requirements.txt
├── paper
│   ├── manuscript.pdf
│   ├── supplementary.pdf
│   ├── figures
│   │   ├── figure1_workflow.png
│   │   ├── figure2_retrieval_results.png
│   │   ├── figure3_qa_results.png
│   │   ├── figure4_figure_table_results.png
│   │   └── ...
│   ├── tables
│   │   ├── table1_retrieval.csv
│   │   ├── table2_qa_results.csv
│   │   ├── table3_figure_table_results.csv
│   │   └── ...
│   └── resources
│       ├── appendix_notes.md
│       ├── prompt_templates.md
│       └── evaluation_rubric.md
├── dataset
│   ├── raw_pdfs
│   │   ├── biology
│   │   ├── physics
│   │   ├── chemistry
│   │   └── general_science
│   ├── parsed_documents
│   ├── cleaned_chunks
│   ├── linked_objects
│   ├── benchmark
│   │   ├── benchmark_queries.json
│   │   ├── gold_answers.json
│   │   ├── gold_pages.json
│   │   └── gold_keywords.json
│   └── metadata
│       └── corpus_index.csv
├── figures
│   ├── main_paper
│   ├── supplementary
│   └── qualitative_examples
├── src
│   ├── parsing
│   ├── cleaning
│   ├── chunking
│   ├── indexing
│   ├── retrieval
│   ├── generation
│   ├── validation
│   └── evaluation
├── notebooks
│   ├── exploratory_analysis.ipynb
│   ├── benchmark_analysis.ipynb
│   └── qualitative_examples.ipynb
└── outputs
    ├── retrieval_results
    ├── generation_outputs
    ├── human_eval
    └── ablation_results


---

## Dataset Description

The experimental corpus used in this work contains **20 SSC-related PDFs**, with **5 PDFs per subject** across:

- Biology
- Physics
- Chemistry
- General Science

For each subject, the collected materials include:

- Book PDF
- Note PDF
- MCQ PDF
- CQ PDF
- Quiz PDF

These documents typically span **80–150 pages** and contain multimodal educational content such as:

- running text
- diagrams
- figures
- tables
- page-level layout structure
- scanned pages and noisy artifacts

The dataset also includes both **digitally generated** and **scanned PDFs**, which makes parsing and evidence extraction more realistic and more challenging.

---

## Benchmark

This repository includes an **SSC-oriented benchmark** designed to evaluate both retrieval and grounded educational generation.

### Supported query types

- factual question answering
- concept explanation
- figure interpretation
- table interpretation
- MCQ generation
- CQ generation
- quiz generation

### Query language settings

The benchmark includes student-style queries in:

- Bangla
- English
- code-mixed Bangla-English

### Annotation fields

Each benchmark item may contain:

- `query`
- `subject`
- `query_type`
- `gold_answer`
- `gold_pages`
- `gold_keywords`

---

## Methodology Summary

The overall framework follows these major stages:

1. PDF ingestion  
2. Parsing and document structuring  
3. Noise-aware cleaning  
4. Curriculum-aware chunking  
5. Multi-representation construction  
6. Indexing and multimodal retrieval  
7. Reranking and evidence-pack assembly  
8. Grounded generation  
9. Validation and quality control  
10. Benchmark evaluation and human assessment  

The system is designed to preserve multimodal structure instead of flattening all documents into plain text at the beginning of the pipeline.

---

## Retrieval and Generation Components

### Retrieval

The framework supports:

- text raw index
- text summary index
- table index
- visual/page index

It uses:

- curriculum-aware chunking
- subject-aware routing
- hybrid retrieval
- multimodal evidence linking
- reranking for improved evidence consistency

### Generation

The framework supports three generation backends:

- template-based grounded generator
- open text generator
- open multimodal generator

These are used to produce:

- grounded answers
- explanations
- figure/table interpretations
- MCQs
- CQs
- quizzes

### Validation

A lightweight validation layer is used to improve reliability through:

- grounding checks
- citation/page consistency checks
- modality-use verification
- task-specific structural checks

---

## Paper Resources

The `paper/` directory contains the core academic materials used in this project.

### Included materials

- main manuscript PDF
- supplementary document
- paper figures
- result tables
- appendix resources
- evaluation rubric
- prompt or template descriptions
- other paper-related supporting files

### Figures

All main-paper and supplementary-paper figures can be stored in:

- `paper/figures/`
- `figures/main_paper/`
- `figures/supplementary/`

### Tables and result files

Tables used in the manuscript can be stored in:

- `paper/tables/`

### Other paper resources

Any additional paper material such as notes, appendix text, benchmark descriptions, or evaluation resources can be stored in:

- `paper/resources/`

---

## Results Summary

The paper reports improvements across multiple evaluation dimensions, including:

- retrieval quality
- factual QA quality
- concept explanation quality
- figure and table understanding
- educational generation quality
- grounding
- citation correctness
- human evaluation
- ablation analysis

The full system consistently outperforms simplified text-only baselines and partial multimodal baselines, especially on tasks that require figure context, page continuity, or chapter-aware evidence.

---

## Human Evaluation

Human evaluation considers:

- correctness
- grounding
- clarity
- pedagogical usefulness
- curriculum alignment
- Bangla fluency and naturalness

This makes the evaluation more realistic for actual educational use.

---

## Paper Citation

**Paper citation details will be added soon.**

A full BibTeX entry and formal citation format will be included after the paper is finalized or published.

---

## Textbook Source

The SSC textbook materials used in this project are based on publicly available resources from **NCTB Bangladesh**.

**NCTB textbook source:**  
[https://nctb.gov.bd/pages/static-pages/6922dd8a933eb65569e15641](https://nctb.gov.bd/pages/static-pages/6922dd8a933eb65569e15641)

Please refer to the official NCTB source for textbook access, publication details, and distribution information.

---
