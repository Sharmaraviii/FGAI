# ICT4403 Assignment 2 — Autoregressive Text Generation with PyTorch

## Student and submission details
- **Student name:** Ravi Sharma
- **Registration number:** 230953324
- **Course:** Foundations of Generative AI (ICT4403)
- **Assignment:** Assignment 2
- **System title:** Autoregressive Text Generation Using Simple RNN, Bidirectional RNN, LSTM and GRU
- **Dataset:** Tiny Shakespeare
- **Dataset source:** https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt
- **GitHub repository:** [ADD YOUR GITHUB REPOSITORY URL HERE]


## Objective
Compare Simple RNN, Bidirectional RNN, LSTM, and GRU for next-token prediction and autoregressive text generation.

## Dataset
- Tiny Shakespeare
- Source: https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt
- Word and punctuation tokens; chronological 80/10/10 train/validation/test split.
- This run used a 12,000-token cap, context length 12, embedding dimension 96, hidden dimension 128, batch size 128, Adam at learning rate 0.002, and 2 epochs for each model.

## Actual results from the submitted run

| Model | Test loss ↓ | Perplexity ↓ | Accuracy ↑ | Training time (s) |
|---|---:|---:|---:|---:|
| RNN | 6.0009 | 403.80 | 11.20% | 3.77 |\n| BIRNN | 6.0370 | 418.64 | 10.86% | 5.15 |\n| GRU | 6.0441 | 421.61 | 11.36% | 5.68 |\n| LSTM | 6.0476 | 423.08 | 11.87% | 6.95 |\n
- Lowest test loss and fastest: **RNN** (loss 6.0009; 3.77s).
- Highest next-token accuracy: **LSTM** (11.87%).
- Overall interpretation: Simple RNN is fastest and has the lowest loss; LSTM has the highest accuracy. Generated samples remain weak in grammatical coherence, so no model dominates every criterion.

## Temperature analysis
The notebook generated text from the same seeds at temperatures 0.5, 1.0, and 1.3. The diagnostics show that lower temperature tended to produce more repeated bigrams, while higher temperatures generally increased variety. See `outputs/generated_samples.csv` and `outputs/generation_diagnostics.csv`; qualitative coherence should be judged from the actual samples.

## Files
- `notebooks/ICT4403_Assignment2_Text_Generation.ipynb`: implementation
- `outputs/model_comparison.csv`: measured test metrics
- `outputs/*_history.csv`: training histories
- `outputs/generated_samples.csv`: generated examples
- `outputs/generation_diagnostics.csv`: lexical diversity and repetition diagnostics
- `outputs/*.png`: plots
- `outputs/*_best.pt`: trained checkpoints
- `FINAL_REPORT.md`: results-based report

## Run
Install dependencies using `pip install -r requirements.txt`, then open the notebook in Jupyter or Google Colab and run all cells. The reported values correspond to the results currently in `outputs/`; if you rerun with different settings, replace the results and update the report accordingly.

## Submission reminder
Before submission, upload this folder to GitHub and replace the repository URL placeholder in `FINAL_REPORT.md`. The separate student-information cover document also requires your real name, registration number, and repository URL.
