# QnA-Generator
This repository contains a Question-and-Answer (QnA) Generator system built using Large Language Models (LLMs). The system takes a context as input and generates relevant questions along with concise answers. It also includes additional features such as question selection, similarity checking, and saving results. The application can be accessed via a Gradio interface for ease of use.

## Features
1. Question Generation
   - Uses an LLM to generate up to 5 relevant questions based on the given context.
   - Designed to focus only on information presented within the provided context.
2. Answer Generation
   - Each generated question is answered concisely (maximum 2 sentences).
   - Answers strictly adhere to the provided context, avoiding irrelevant details.
3. Question Selection
   - Users can review and select which generated QnA pairs they wish to keep.
4. Similarity Check
   - The system uses FAISS and sentence embeddings to ensure the uniqueness of the selected QnA pairs by comparing them against a stored dataset.
5. Save QnA Pairs
   - Selected QnA pairs are saved into a CSV file, ensuring they are added to a cumulative dataset.
6. Gradio Interface
   - The system provides an intuitive Gradio web interface to interact with the QnA generator and manage QnA pairs.

## System Workflow
- Step 1: Input Context

  The user inputs a context, e.g., a paragraph about Borobudur Temple.
- Step 2: Generate Questions

  The system generates a set of concise and contextually relevant questions.
- Step 3: Generate Answers

  Each question is automatically answered using the same context.
- Step 4: Question Selection

  Users can review the generated QnA pairs and select which ones to keep.
- Step 5: Similarity Check

  The system checks the selected QnA pairs for similarity against a stored dataset to ensure uniqueness.
- Step 6: Save QnA Pairs

  Selected and unique QnA pairs are appended to a CSV file for further use.

## Example Context and Output
- Input Example

Candi Borobudur dibangun oleh Dinasti Sailendra. Candi Borobudur merupakan peninggalan Buddha terbesar di dunia yang dibangun antara tahun 780-840 Masehi. ...
- Generated Question
  1. Siapa yang membangun Candi Borobudur?
  2. Pada tahun berapa Candi Borobudur dibangun?
  3. ...
- Generated Answer
  1. Candi Borobudur dibangun oleh Dinasti Sailendra
  2. Candi Borobudur didirikan antara tahun 780-840 Masehi
  3. ...

# Model Evaluation Using RQUGE
This repository utilizes models, such as Lucas-Hyun-Lee/gemma-2b-it, nvidia/Llama3-ChatQA-1.5-8B, and afrizalha/Kancil-V1-llama3-4bit for question generation and answering. The RQUGE metric is employed to evaluate the quality of generated questions and answers with respect to a given context.

## About RQUGE
RQUGE evaluates the quality of generated questions and answers by comparing them to the given context. The score reflects how well the generated QA pairs align with the context, providing a quantitative measure of model performance

## Key Features
- Question generation based on contextual input.
- Automated answer generation using pre-trained language models.
- Similarity check to avoid redundant questions.
- RQUGE scoring for QA evaluation.
- Visual comparison of model performance using bar plots.

## Visualization

The pipeline provides visual insights into model performance through bar charts. These plots highlight:
- Individual model performance per context.
- Overall mean RQUGE scores.
