# Analysis of Model Confidence and Image Interpretability

This document analyzes the relationship between ViT model confidence scores and the visual interpretability of student-generated scientific models. The data is categorized into **Beginning**, **Developing**, and **Proficient** proficiency levels based on specific rubric criteria.

## 1. High Confidence: Visual Clarity and Simple Patterns
High-confidence predictions ($Conf \approx 1.00$) typically occur when images present very clear, non-ambiguous visual evidence.

* **Beginning Level (e.g., `1_40890.jpg`)**: 
    * **Data**: $100\%$ confidence.
    * **Observation**: These images are often extremely simple sketches that clearly fail to identify particles or motion as required by the rubrics. Their "Beginning" status is easy for the model to confirm because they lack the complex elements (like keys and specific labels) found in higher proficiency levels.
* **Proficient Level (e.g., `3_42577.jpg`, `3_42652.jpg`)**:
    * **Data**: Confidence $> 99.8\%$.
    * **Observation**: These samples feature professional-grade or highly structured digital diagrams. In Task 48, for example, water molecules and their kinetic energy must be clearly modeled. In these high-confidence images, particles are represented by distinct, non-overlapping shapes, and motion vectors (arrows) are clear and correctly directed.

## 2. Low Confidence: Clutter, Overlap, and Ambiguity
Low-confidence predictions ($Conf < 0.55$) and incorrect predictions are strongly associated with "noisy" visual data where the model cannot clearly distinguish key rubric features.

* **Clustered and Overlapping (e.g., `2_46605.jpg`)**: 
    * **Data**: $42.43\%$ confidence; incorrectly predicted as "Developing".
    * **Observation**: In tasks like Task 44 (Jane's inflated ball), the model must identify that air particles move faster at higher temperatures. When an image contains too many overlapping arrows and circles, the model's ability to count or judge the "faster/slower" motion criteria is compromised.
* **Abstract or Disorganized (e.g., `2_50156.jpg`, `0_50865.jpg`)**:
    * **Data**: $39.08\%$ and $51.44\%$ confidence respectively.
    * **Observation**: These images feature messy handwriting or abstract symbols that overlap with the diagram. For instance, in Task 45 (Melting Butter), a proficient response must show particles moving faster after heating. If the "signs of movement" (hashes or lines) are disorganized or visually merged with the "butter particles," the model loses certainty.

## Conclusion
The model's confidence is directly tied to the visual "cleanliness" of the student's work. High confidence is achieved when the drawing is either extremely simple (Beginning) or professionally structured (Proficient). Conversely, cluttered drawings with overlapping elements consistently result in low confidence and misclassification, typically toward the "Developing" middle-ground.
