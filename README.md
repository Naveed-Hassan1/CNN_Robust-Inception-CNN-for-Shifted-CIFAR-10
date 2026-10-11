# CNN_Robust-Inception-CNN-for-Shifted-CIFAR-10
This project trains an Inception-style CNN from scratch on only 500 CIFAR-10 images and tests it on a shifted set with rotation, brightness/contrast changes, occlusion and grayscale. On-the-fly augmentation, regularization, an ablation study, error analysis and test-time augmentation improve robustness under distribution shift.



-------------------------------------------------------------------------------------------------------------------------------------
Robust CIFAR-10 Classification from 500 Images

I trained a CNN on only 500 CIFAR-10 images and tested it on changed images (rotated, darker/brighter, covered with a box, sometimes grayscale). I used augmentation and regularization to make it work better on them.

Student ID: 23F-0599 Notebook: dlp-ass-2.ipynb

What I did
Data: 50 images per class (500 total), split into 400 train and 100 validation.
Shifted test: the 10,000 test images with random rotation, brightness/contrast change, a black box and random grayscale.
Model: conv layers + 2 Inception blocks, about 0.2M parameters, trained from scratch.
Part A: baseline with no augmentation. It overfits and fails on the shifted test.
Part B: augmentation (flip, rotation, shift, brightness, contrast, grayscale, cutout) done while training.
Part C: BatchNorm, dropout, weight decay, label smoothing, learning rate decay, early stopping.
Part D: ablation table, adding one augmentation at a time.
Part E: per-class accuracy, confusion matrix, wrong predictions, grayscale test.
Part F: test-time augmentation (bonus).

All results use 3 seeds (42, 43, 44) and 60 epochs.

How to run
Open a Kaggle notebook and upload dlp-ass-2.ipynb.
Turn on Internet (needed once to download CIFAR-10).
Run all cells from top to bottom.
