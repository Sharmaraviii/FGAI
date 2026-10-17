# ICT4403 — Foundations of Generative AI
## Assignment 2: Autoregressive Text Generation Using RNN, Bidirectional RNN, LSTM and GRU

## 1. Objective
This assignment implements and compares four recurrent neural network architectures for next-token prediction and autoregressive text generation: Simple RNN, Bidirectional RNN, Long Short-Term Memory (LSTM), and Gated Recurrent Unit (GRU). The models are evaluated using test loss, perplexity, next-token accuracy, training time, and qualitative generation behaviour at multiple sampling temperatures.

## 2. Dataset and preprocessing
- **Dataset:** Tiny Shakespeare
- **Source:** https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt
- **Preprocessing:** lower-case normalization; word and punctuation tokenization; vocabulary constructed from the training partition; out-of-vocabulary tokens mapped to `<unk>`.
- **Split:** chronological 80% training, 10% validation, 10% test.
- **Context window:** 12 tokens.
- **Training configuration:** embedding dimension 96, hidden dimension 128, batch size 128, Adam optimizer, learning rate 0.002, 2 epochs, and a 12,000-token corpus cap for this run.
- All models used the same dataset splits and comparable training settings.

## 3. Quantitative results

| Model | Test loss (lower better) | Perplexity (lower better) | Next-token accuracy (higher better) | Training time (s) |
|---|---:|---:|---:|---:|
| RNN | 6.0009 | 403.80 | 11.20% | 3.77 |\n| BIRNN | 6.0370 | 418.64 | 10.86% | 5.15 |\n| GRU | 6.0441 | 421.61 | 11.36% | 5.68 |\n| LSTM | 6.0476 | 423.08 | 11.87% | 6.95 |\n
### Interpretation
- **Lowest test loss:** RNN (6.0009).
- **Highest next-token accuracy:** LSTM (11.87%).
- **Fastest training:** RNN (3.77 seconds).
- Test perplexities are high and accuracies are modest, which indicates that this short, deliberately lightweight training run has limited predictive quality. These numbers should be interpreted in light of the 12,000-token cap and two training epochs.

## 4. Learning curves
The training histories and `learning_curves.png` show that training losses decreased across the two epochs for all four models. Validation loss improved for the Simple RNN and LSTM; the Bidirectional RNN and GRU showed little change between epochs. With only two epochs, this is not enough to make a strong claim about final convergence.

## 5. Temperature analysis
The same two seed sequences were used at temperatures 0.5, 1.0, and 1.3. Temperature 0.5 generally made outputs more repetitive; higher temperatures generally increased lexical variety and reduced repeated bigrams in this run, though individual samples vary.

Average diagnostics across models and seeds:

| Temperature | Mean unique-token ratio | Mean repeated-bigram ratio |
|---:|---:|---:|
| 0.5 | 0.461 | 0.275 |\n| 1.0 | 0.584 | 0.067 |\n| 1.3 | 0.566 | 0.043 |\n
These automated measures are only rough indicators. Manual inspection of the saved samples suggests that the generated text often has Shakespeare-like names and punctuation but does not consistently preserve grammatical coherence or contextual meaning. The higher temperature outputs tend to be less repetitive, but not necessarily more coherent.

## 6. Overall comparison and conclusion
For this specific run, the **Simple RNN is the strongest practical choice if prioritizing test loss and speed**, while the **LSTM has the highest next-token accuracy**. No single model dominates every metric. Generated samples remain weak across all architectures, so this should be presented as a lightweight comparative experiment rather than a high-quality text-generation system.

A more conclusive comparison would require training for more epochs, using more of the corpus, and possibly tuning the context length and model dimensions consistently across architectures. The final model choice should balance test metrics, runtime, and the human review of generated samples.

## 7. Reproducibility and output files
The `outputs/` folder contains the actual CSV metrics, per-epoch histories, generated samples, diagnostics, plots, and saved checkpoints from this run. The values reported above were read from `outputs/model_comparison.csv` and `outputs/generation_diagnostics.csv`.

## 8. GitHub repository
Student name: **Ravi Sharma**  
Registration number: **230953324**  
GitHub repository URL: **[ADD YOUR GITHUB REPOSITORY URL HERE]**
