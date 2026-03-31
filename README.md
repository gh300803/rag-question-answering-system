# RAG Question Answering System for South Asian Cuisine

This repository contains a Retrieval-Augmented Generation (RAG) question answering system developed as part of a team coursework project.

It combines retrieval and generation to produce grounded answers, with evaluation carried out using multiple automatic metrics.

## Project Structure

- `01_corpus_and_benchmark.ipynb` — loads and inspects the background corpus and benchmark dataset
- `02_rag_pipeline.ipynb` — implements the retrieval and generation pipeline
- `03_evaluation.ipynb` — evaluates generated answers against benchmark answers
- `benchmark_dataset.json` — benchmark question-answer dataset
- `evaluation_results.json` — saved evaluation outputs
- `background_corpus.json` — custom document corpus used for retrieval
- `requirements.txt` — project dependencies

## Overview

The project focuses on a question answering setting where retrieved context is used to support answer generation.

The pipeline works in three stages:

1. Preparing and inspecting the corpus and benchmark dataset
2. Retrieving relevant context and generating answers
3. Evaluating generated outputs against reference answers

## Retrieval and Generation Pipeline

The RAG pipeline combines:

- dense retrieval using SentenceTransformers embeddings
- lexical retrieval using BM25
- top-k context selection
- prompt construction using retrieved passages
- answer generation using a Hugging Face language model

This hybrid approach improves retrieval performance by capturing both semantic similarity and keyword overlap.

## Evaluation

Generated answers are evaluated against benchmark answers using:

- ROUGE-1
- ROUGE-2
- ROUGE-L
- BLEU
- BERTScore
- Faithfulness

Evaluation outputs are saved in `evaluation_results.json`.

## Running the Project

Install dependencies:

pip install -r requirements.txt

Run the notebooks in the following order:

1. `01_corpus_and_benchmark.ipynb`
2. `02_rag_pipeline.ipynb`
3. `03_evaluation.ipynb`

## Notes

- This repository is adapted from a team project, so the implementation reflects collaborative coursework development
- Models may need to be downloaded from Hugging Face on first run
- The repository is intended to demonstrate the system pipeline, retrieval strategy, and evaluation workflow
