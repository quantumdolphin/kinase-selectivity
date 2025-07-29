# Kinase Inhibitor Selectivity Metrics

## Background

* Explored selectivity metrics for kinase inhibitors, focusing on the **Gini coefficient** and alternatives (Partition Index, Entropy, Window Score, Ranking Score).
  
---

## Key Concepts Discussed

### 1. Gini Coefficient

* Measures how unequally a drug inhibits targets (e.g., kinases) in a panel.
* **High Gini (\~1):** Very selective (strong effect on few kinases).
* **Low Gini (\~0):** Non-selective (affects all kinases similarly).
* **Calculation:**

  * Order inhibition values (e.g., % inhibition or –log(IC₅₀)).
  * Compute cumulative fractions for kinases (X) and inhibition (Y).
  * Plot Lorenz curve; Gini is area between this curve and the diagonal.

### 2. Lorenz Curve

* Not specific to biology; used in economics for income/wealth distribution.
* **In SBDD:**

  * X-axis: cumulative fraction of kinases.
  * Y-axis: cumulative fraction of inhibition.
* **Interpretation:**

  * Curve near the diagonal: non-selective.
  * Curve hugs axes and jumps up: highly selective.

### 3. Panel Size Effects

* **Gini is only reliable for large panels** (e.g., >50 kinases).
* For small panels (e.g., 10 kinases), the Lorenz curve is blocky and the Gini coefficient can be unstable or misleading.

### 4. Alternative Metrics

* **Standard Selectivity Score:** Simple threshold, but arbitrary.
* **Window Score (WS):** Fraction of targets within a window of the best affinity.
* **Ranking Score (RS):** Affinity difference between the best and nth best target.
* **Partition Index & Entropy Score:** Thermodynamic/statistical measures of selectivity.

### 5. Practical Python Examples

* Created sample datasets (selective and non-selective scenarios).
* Generated Lorenz curves and calculated Gini coefficients for small (10) and large (500) kinase panels.
* Demonstrated the smoothness/blockiness of the Lorenz curve and the behavior of Gini as panel size changes.

---

## Key Takeaways

* **Use Gini for large kinase panels**; avoid for small panels.
* **Lorenz curve** is a powerful, general visualization of distribution/inequality.
* Always consider panel size and metric limitations when interpreting selectivity.
* Alternative metrics (WS, RS, Partition Index, Entropy) are often more reliable for small panels or when comparing across datasets.

---

**Next steps:**
## 🔬 Key References: Selectivity Metrics for Kinase Inhibitors

### 1. Graczyk, P. P. (2007).  
**“Gini Coefficient: A New Way To Express Selectivity of Kinase Inhibitors against a Family of Kinases.”**  
*Journal of Medicinal Chemistry*, 50(25), 5773–5779.  
Introduced the Gini coefficient for kinase selectivity, with calculations using inhibition data (e.g., percent inhibition at a single concentration). Demonstrated behavior across ~85 kinases and ~40 inhibitors, showing that **a Gini > ~0.75 reflects strong selectivity**. Noted limitations with small panels (~<50 kinases) but robustness with larger panels :contentReference[oaicite:1]{index=1}.

---

### 2. Cheng, A. C., Eksterowicz, J., Geuns‑Meyer, S., & Sun, Y. (2010).  
**“Analysis of Kinase Inhibitor Selectivity using a Thermodynamics‑Based Partition Index.”**  
*Journal of Medicinal Chemistry*, 53(11), 4502–4510.  
Presents the **Partition Index**, a thermodynamics-derived selectivity metric based on association/dissociation constants (Kₐ, Kᵢ, K_d). Compares the binding strength to a reference (on‑target) versus off‑targets—in contrast to distribution-based metrics like Gini :contentReference[oaicite:2]{index=2}.

---

### 3. Bosc, N., et al. (2017).  
**“The use of novel selectivity metrics in kinase research.”**  
*BMC Bioinformatics*, 18, Article number: 1413.  
Compares established selectivity metrics (standard score, Gini, entropy, partition index) with **new metrics Window Score (WS)** and **Ranking Score (RS)** on large kinase profiling datasets (~300–440 kinases). Provides guidance on strengths, limitations, and when to choose each method :contentReference[oaicite:3]{index=3}.

---

### 📊 Comparison Table of Metrics

| Metric                | Core Idea                                          | Ideal for Panel Size         |
|-----------------------|-----------------------------------------------------|------------------------------|
| **Gini Coefficient**  | Measures inequality in inhibition distribution     | Large panels (>50 kinases)  |
| Partition Index       | Thermodynamic ratio of binding to a reference target| Any size—but requires IC₅₀/K_d data |
| Entropy Score         | Statistical disorder across affinities              | Medium-to-large panels       |
| Window Score (WS)     | Fraction within top-affinity window                 | Small to large panels, flexible |
| Ranking Score (RS)    | Difference between top and nth best target affinity | Similar to WS                |

---


