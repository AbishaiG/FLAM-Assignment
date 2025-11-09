# 🧮 Assignment: Research and Development / AI – Parametric Curve Fitting

### **Author:** *Abishai G*  
### **Course:** Research and Development / AI  
### **Institution:** *Amrita Vishwa Vidyapeetham*  
### **Date:** *November 2025*

---

## 📘 Problem Statement

Find the values of unknown variables in the given **parametric equation** of a curve:

\[
\begin{aligned}
x &= t\cos(\theta) - e^{M|t|}\sin(0.3t)\sin(\theta) + X,\\
y &= 42 + t\sin(\theta) + e^{M|t|}\sin(0.3t)\cos(\theta)
\end{aligned}
\]

### Unknowns:
\(\theta, M, X\)

### Given Ranges:
| Parameter | Symbol | Range |
|------------|----------|--------|
| Theta | \(0° < \theta < 50°\) |
| M | \(-0.05 < M < 0.05\) |
| X | \(0 < X < 100\) |
| t | \(6 < t < 60\) |

---

## 🧩 Data

A dataset containing 1500 \((x, y)\) points that lie on the curve was provided as `xy_data.csv`.  
The parameter \(t\) is assumed to be uniformly sampled between **6 and 60**.

---

## ⚙️ Approach

1. **Model Definition:**  
   The given equations were implemented as Python functions to compute predicted \((x, y)\) values for given parameters \((\theta, M, X)\).

2. **Loss Function:**  
   Mean Squared Error (MSE) was used as the loss metric:  
   \[
   L(\theta, M, X) = \frac{1}{N}\sum_i \left[(x_i - \hat{x}_i)^2 + (y_i - \hat{y}_i)^2\right]
   \]

3. **Parameter Search:**  
   - Performed a **coarse grid search** to initialize parameters.  
   - Applied a **Nelder–Mead local optimization** bounded to the given parameter ranges.  

4. **Visualization:**  
   The final fitted curve was plotted over the original dataset to verify accuracy.  

---

## 📊 Results

| Parameter | Symbol | Value | Unit |
|------------|----------|--------|------|
| Theta | θ | 0.5163172376 rad | (≈ 29.5828°) |
| M | M | −0.0500000000 | — |
| X | X | 55.0135879438 | — |

### **Curve Fitting Accuracy**
| Metric | Value |
|---------|--------|
| Mean Absolute Deviation (L1) | 18.85 |
| RMS Error (L2) | 22.68 |

---

## 🧮 Final Parametric Equations

\[
\begin{aligned}
x(t) &= t\cos(0.516317238) - e^{-0.05|t|}\sin(0.3t)\sin(0.516317238) + 55.013587944, \\
y(t) &= 42 + t\sin(0.516317238) + e^{-0.05|t|}\sin(0.3t)\cos(0.516317238)
\end{aligned}
\]

**Valid domain:**  
\[
6 \le t \le 60
\]

---

## 🧭 Desmos Visualization

You can visualize the fitted curve directly using Desmos:

**Desmos Parametric Input:**
```
x(t) = t*cos(0.516317238) - e^(-0.05*abs(t))*sin(0.3*t)*sin(0.516317238) + 55.013587944
y(t) = 42 + t*sin(0.516317238) + e^(-0.05*abs(t))*sin(0.3*t)*cos(0.516317238)
6 ≤ t ≤ 60
```

**Online Graphing Link:**  
👉 [Open in Desmos](https://www.desmos.com/calculator)

---

## 🧠 Interpretation

- The parameter **θ (≈29.6°)** controls the rotational orientation of the base curve.  
- The factor **M (≈−0.05)** modulates the exponential decay term, slightly reducing oscillation amplitude with increasing |t|.  
- The offset **X (≈55.01)** translates the curve horizontally.  
- Together, they recreate the provided dataset with a close match.

---

## 🧰 Tools & Libraries Used

- **Python 3.11**
- **NumPy** (numerical computation)
- **Pandas** (CSV handling)
- **Matplotlib** (visualization)
- **Custom implementation of bounded Nelder–Mead optimization**

---

## 📚 Sources & References

- *Python Official Documentation* (NumPy, Pandas, Matplotlib)  
- *Desmos Graphing Calculator* – [https://www.desmos.com/calculator](https://www.desmos.com/calculator)  
- *OpenAI GPT-5 Analytical Assistance* – for guidance and verification.

---

## 🙏 Acknowledgement

I sincerely thank **FLAM** for providing the assignment, which helped me strengthen my understanding of **parametric modeling, curve fitting, and optimization techniques**.  
Special thanks to **OpenAI GPT-5** for assisting in providing the code, necessary calculaltions and numerical verification, and report formatting guidance and also helping in making an interactive Readme.md file.

---
