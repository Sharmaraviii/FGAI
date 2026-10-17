# ICT4403 Assignment 2 — Results Report Template

## 1. Objective
State the goal of comparing Simple RNN, Bidirectional RNN, LSTM, and GRU for autoregressive next-token generation.

## 2. Dataset and preprocessing
- Dataset: Tiny Shakespeare
- Source: https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt
- Tokenization: words and punctuation as separate tokens
- Split: 80% train / 10% validation / 10% test (chronological)
- Vocabulary size: [copy from notebook]
- Number of tokens used: [copy from notebook]
- Context length: [copy from notebook]

## 3. Model and training configuration
Describe the common embedding/hidden dimensions, optimizer, learning rate, batch size, epoch count, and hardware used. Explain that all models used the same splits and comparable training settings.

## 4. Quantitative evaluation
Insert the actual `outputs/model_comparison.csv` table. Discuss loss, perplexity, next-token accuracy, and training time. Do not insert estimated or invented values.

## 5. Learning curves
Insert `outputs/learning_curves.png`. Comment on convergence, overfitting, and stability based on the observed curves.

## 6. Generated text and temperature analysis
Use examples from `outputs/generated_samples.csv` for temperatures 0.5, 1.0, and 1.3 using identical seeds. Discuss:
- Coherence
- Diversity
- Contextual consistency
- Repetition
Use `outputs/generation_diagnostics.csv` only as supporting evidence, not as a substitute for human review.

## 7. Comparison and best model
Identify the best overall model based on the actual metrics, training cost, and generated samples. Explain trade-offs. Do not claim a model is best simply because it is a more complex architecture.

## 8. Conclusion
Summarize findings and limitations. Note that results depend on dataset size, vocabulary, compute, and hyperparameters.

## 9. GitHub repository
Repository URL: [paste your public repository URL]
