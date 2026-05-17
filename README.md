# LW4-Improving-CNN-Performance-Using-Regularization

## Google collab link: https://colab.research.google.com/drive/1ZAfPwuAf5XXvKMvQFVMD-yZx8TTcZXdv?usp=sharing



## Guide Questions

### A. Model Evaluation Analysis

**1. What were the weakest-performing classes based on the confusion matrix?**
According to the categorization report and confusion matrix, the weakest
AloeBlueboy (F1: 0.31), AloeBlueElf (F1: 0.46), and
and Aloe Maculata (F1: 0.48). The courses with the lowest F1-scores were
showing that the model had the most difficulty accurately classifying them.

**2. How did Precision, Recall, and F1-score vary across classes?**
Between classes, the measures differed considerably. High-achieving courses
such as Aloezkraohliana (F1: 0.88) and AloeKarasbergensis (F1: 0.77) had
constant recall and accuracy. AloeBlueboy and other weak courses demonstrated
low recall (0.24) and low accuracy (0.43), indicating the model
seldom accurately recognized them.

**3. What does a low recall indicate in your model?**
A poor recall indicates that many real occurrences of that are being missed by the model.
class. AloeBlueboy, for instance, had a recall of 0.24, or 76% of
Images of AloeBlueboy were mistakenly categorized as something else.

**4. How does AUC score reflect model performance compared to accuracy?**
The model's capacity to differentiate across classes is gauged by the AUC score.
regardless of the criterion, whereas accuracy solely accounts for accurate forecasts.
Although our baseline accuracy was 0.67, the model's AUC was 0.9228.
possesses a great capacity for discrimination even in situations when overall accuracy is just moderate.
For datasets that are unbalanced, AUC is more dependable.

### B. Model Improvement

**5. How did data augmentation affect validation accuracy?**
The model's ability to generalize was improved via data augmentation, which exposed it to
several iterations of the training pictures using random flips, rotations, magnification,
and shifts in contrast. As a result, overfitting decreased and the model's
the capacity to deal with unseen photos during validation.

**6. Why is Batch Normalization important in CNNs?**
Each layer's output is normalized using batch normalization, which stabilizes
and expedites training. Internal covariate shift is lessened, enabling the
model to employ faster learning rates and reduce the network's sensitivity
to initialize the weight.

**7. What role did Dropout play in improving your model?**
During training, dropout randomly deactivates neurons, causing the network to
to become familiar with redundant representations. Overfitting is avoided as a result. We employed
Dropout (0.5) following the convolutional layers and Dropout (0.4) following the
thick layer.

**8. How did Early Stopping prevent overfitting?**
Early Stopping tracked validity loss and halted training when it
ceased becoming better for five epochs in a row before returning to the best
weights. As a result, the model was unable to commit the training data to memory.

### C. Performance Comparison

**9. What improvements were observed after modifying the model?**
The validation accuracy of the enhanced model was 0.5759. While
marginally less than the baseline, as a result of the enhanced model being
developed from the ground up using a challenging 19-class dataset of visually comparable
Aloe plants. Even yet, the AUC value of 0.8708 shows strong discriminative
capacity.

**10. Which enhancement contributed the most to performance improvement?**
Because it stabilized training, batch normalization made the most contribution.
during all 30 epochs, enabling the model to continuously get better
By epoch 29, val_accuracy has increased from 0.05 in epoch 1 to 0.57.

**11. Did the gap between training and validation accuracy decrease?**
Indeed. The enhanced model had validation accuracy of 0.42 and training accuracy of
accuracy of 0.57 at epoch 30, indicating that validation truly surpassed
training precision. This suggests that the regularization methods were
The model was not overfitting and was operating efficiently.
### D. Explainability (Grad-CAM)

**12. How did Grad-CAM help in understanding model predictions?**
Grad-CAM produced a heatmap that indicated which areas of the picture most
affected the forecast made by the model. By superimposing the heatmap over the
original picture, we could see if the model was in focus.
on unnecessary backdrop areas or the structure of the plant.

**13. Did the improved model focus on more relevant regions?**
The AloePolyphylla image's Grad-CAM overlay displayed the heatmap.
focused on the plant's spiral leaf design, which is the
characteristic that sets that species apart. This validates the learnt model.
significant visual elements as opposed to background noise.

**14. Why is explainability important in real-world AI applications?**
Explainability increases confidence in AI systems by demonstrating how choices are
created. In practical uses such as plant disease or medical diagnostics
detection, users must comprehend the rationale behind a model's prediction to
Make sure it's accurate. Errors might go unnoticed in the absence of explainability.
can have detrimental effects.

