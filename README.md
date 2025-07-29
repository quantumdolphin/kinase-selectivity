# Chat Summary: Kinase Inhibitor Selectivity Metrics

## Session Context

* Explored selectivity metrics for kinase inhibitors, focusing on the **Gini coefficient** and alternatives (Partition Index, Entropy, Window Score, Ranking Score).
* Used active recall, stepwise Socratic questioning, and live Python examples for practical understanding.

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
You can further explore code for random, moderate, or pan-inhibition scenarios, or experiment with other selectivity metrics on your own kinase screening data.

---

Let me know if you want to expand this or need code for other selectivity metrics!
