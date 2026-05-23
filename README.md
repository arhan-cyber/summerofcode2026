# Week 1 — MNIST Classification

**Mentee:** Arhan Khade
**SoC Track:** Diffusion Models from Scratch — SoC 2026

## Final results
- **Test accuracy:** 0.9760
- **Best validation accuracy:** 0.9762 at epoch [10]
- **Final train loss:** [0.1124]

## Design choices
- **Architecture:** 2-layer MLP for MNIST classification: Flatten (28×28 → 784) → Linear(784 → 256) → ReLU → Dropout(0.5) → Linear(256 → 256) → ReLU → Dropout(0.5) → Linear(256 → 10)
- **Optimizer:** Adam (learning rate = 1e-3)
- **Batch size:** 64
- **Epochs trained:** 10
- **Validation split:** 10% of training data (seed=42)

## What I learned
A relatively simple fully connected MLP can achieve strong performance on MNIST when paired with good regularization like dropout. I also saw how sensitive training is to the optimizer and learning rate, with Adam providing stable convergence without much tuning. Monitoring validation accuracy each epoch was important to ensure the model didn’t overfit as training progressed.
## What I'd do differently
I would try a CNN instead of an MLP since spatial structure is lost in flattening. I’d also experiment with a learning rate schedule or slightly longer training to see if performance can be pushed beyond ~97.6%
## How to reproduce
1. Open `week1_mnist.ipynb` in Colab with a T4 GPU runtime.
2. Run all cells top to bottom.
3. Checkpoint will be saved to `best_model.pt`.
```

---
