# Lab 07 — t-tests and ANOVA

EAES 480: Modern Statistics in Earth & Environmental Science  
University of Illinois Chicago  
Instructor: Dr. Gavin McNicol

---

# Dataset & Study Context

This lab continues using the simplified **AmeriFlux-style dataset** from the **US-AMS site at Argonne National Laboratory (near Chicago, IL)** covering **2022–2023 at 30-minute resolution**.

## What is AmeriFlux?

AmeriFlux is a network of ecosystem observation sites (primarily **eddy covariance towers**) that measure exchanges of:

- carbon dioxide (CO₂),
- water vapor,
- energy,

between ecosystems and the atmosphere, along with supporting meteorological variables.

AmeriFlux overview:  
https://ameriflux.lbl.gov/about/about-ameriflux/

AmeriFlux variable documentation:  
https://ameriflux.lbl.gov/data/aboutdata/data-variables/

---

# Why This Dataset is Ideal for Comparing Means

The US-AMS time series contains:

- strong seasonality,
- a clear day–night cycle,
- structured variability across months and years,
- and substantial short-term fluctuations.

These properties make it ideal for exploring:

- differences **between groups of observations**,
- how variability influences **comparisons of means**, and
- how we evaluate whether **groups differ in a statistically meaningful way**.

---

# Overview

This lab extends hypothesis testing from **single-parameter claims** to **comparisons between groups**.

Rather than asking:

> Is this mean equal to a claimed value?

we now ask:

> Are two (or more) groups meaningfully different?

This assignment introduces:

- **one-sample t-tests**
- **two-sample t-tests**
- **paired t-tests**
- **analysis of variance (ANOVA)**

You will continue working in a structured **R Markdown (`.Rmd`) document** with:

- guided code chunks with fill-in sections,
- sections where you write code from scratch,
- and short written interpretation responses.

---

# Learning Goals

By the end of this lab, you should be able to:

- Compute and interpret a **one-sample t-test**
- Distinguish between **two-sample and paired t-tests**
- Compute and interpret **t-statistics and p-values**
- Understand the role of **degrees of freedom**
- Explain how **uncertainty in variance affects inference**
- Compare manual calculations to `t.test()` results
- Understand ANOVA as a comparison of **multiple group means**
- Interpret **F-statistics and ANOVA p-values**
- Produce a fully reproducible **R Markdown analysis**

---

# What You’ll Do

In the provided R Markdown template, you will:

- Select a **numeric variable** from the dataset
- Perform a **one-sample t-test** on a selected day
- Compare two days using a **two-sample t-test**
- Compare the same day across years using a **paired t-test**
- Compute test statistics manually and using `t.test()`
- Interpret **p-values and confidence intervals**
- Visualize group differences using plots
- Construct categorical groupings (e.g., seasons)
- Perform and interpret an **ANOVA**
- Compare manual ANOVA calculations to `aov()`
- Write clear explanations of your results

This lab emphasizes:

> understanding how statistical tests compare **signal (differences)** to **noise (variability)**

---

# Repository Contents

Contents

* `lab-07-t-tests-and-anova.Rmd`  
→ The lab template you will complete and submit

* `README.md`  
→ This file

* `data/us-ams-simple.csv`  
→ Simplified AmeriFlux-style dataset (US-AMS, 2022–2023)

---

# Instructions

1. Fork or clone this repository to your own GitHub account  
2. Open `lab-07-t-tests-and-anova.Rmd` in **RStudio**  
3. Work through the document **from top to bottom**  
4. Complete all code chunks (some fill-in, some from scratch)  
5. Answer interpretation prompts in complete sentences  
6. Knit regularly to catch errors early  

⚠️ Code that runs in the Console but not in the `.Rmd` does not count.

---

# Reproducibility Requirements

Your submission must:

- Knit without errors  
- Run top-to-bottom in a clean R session  
- Include all required libraries in the setup chunk  
- Avoid hard-coded local file paths  
- Use `na.rm = TRUE` where appropriate  
- Clearly define any chosen variables (e.g., `target_var`, `day1`, `day2`)  
- Ensure paired data are correctly aligned when required  

These are not stylistic preferences—they are **scientific standards**.

---

# Submission

You should:

- Commit and push your completed `.Rmd` file to your GitHub repository
- Submit the **GitHub repository link** on Canvas

You do **not** need to submit the knitted HTML unless instructed.

Your work will be evaluated on:

- correctness of statistical calculations,
- clarity of interpretation,
- understanding of differences between tests,
- and reproducibility.

---

# Collaboration Policy

Please consider:

- You may discuss statistical concepts and testing strategies with classmates
- You may not copy code verbatim from others
- Code you submit must be written and understood by you

---

# Why This Matters

In Earth & Environmental Science:

- we often compare **conditions across space, time, or treatments**,
- variability is inherent in environmental data,
- and detecting meaningful differences is essential for inference.

t-tests and ANOVA provide a framework to determine whether:

> observed differences reflect **real environmental signals** or **random variation**

This lab builds directly on hypothesis testing and prepares you for:

> **model-based inference and predictive analysis** in your final projects.