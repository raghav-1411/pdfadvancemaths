# Learning Probability Density Functions using 102303580-Parameterized Non-Linear Model

A Python implementation for learning probability density function parameters from transformed air quality data using Maximum Likelihood Estimation (MLE).

---

## 📌 Overview

This project implements a roll-number-parameterized non-linear transformation model to learn probability density functions. The analysis uses **NO₂ (Nitrogen Dioxide)** data from the India Air Quality Dataset to demonstrate parameter estimation techniques.

---

## 🎯 Objectives

1. **Transform Data**: Apply a roll-number-parameterized non-linear transformation to NO₂ measurements  
2. **Parameter Learning**: Estimate parameters (λ, μ, c) of a Gaussian-like probability density function  
3. **Statistical Analysis**: Use Maximum Likelihood Estimation (MLE) to fit the distribution  

---

## 📂 Dataset

- **Source**: India Air Quality Dataset (Kaggle)
- **Source**: [India Air Quality Data](https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data)
- **Feature Used**: NO₂ (Nitrogen Dioxide) concentration levels  

---

**Feature Used**: NO2 (Nitrogen Dioxide) concentration levels

##  Methodology

### Step 1: Non-Linear Transformation

Transform each NO2 value (x) into z using:
```
z = Tr(x) = x + ar·sin(br·x)
```

Where:
- `ar = 0.05 × (r mod 7)`
- `br = 0.3 × (r mod 5 + 1)`
- `r` = University Roll Number (102317200 in this implementation)

**Calculated Parameters**:
- ar = 0.30
- br = 0.30

### Step 2: Probability Density Function

Learn parameters of the following PDF:
```
p̂(z) = c × e^(-λ(z-μ)²)
```

Where:
- **λ** (lambda): Controls the spread/variance of the distribution
- **μ** (mu): Mean of the transformed variable
- **c**: Normalization constant

**Estimated Parameters**:
- μ = 32.89 (mean of transformed data)
- σ = 20.58 (standard deviation)
- λ = 0.00118 (precision parameter = 1/(2σ²))
- c = 0.01940 (normalization constant = 1/(σ√(2π)))

### Step 3: Visualization

The notebook includes:
- Histogram of transformed data distribution
- Overlaid fitted probability density function
- Visual comparison of empirical vs. theoretical distributions

##  Technologies Used

- **Python 3.12.12**
- **NumPy**: Numerical computations and array operations
- **Pandas**: Data manipulation and analysis
- **Matplotlib**: Data visualization
- **Kaggle Environment**: Cloud-based notebook execution

## Results

The analysis demonstrates:

1. **Successful Transformation**: NO2 data is transformed using the parameterized non-linear model
2. **Parameter Estimation**: Statistical parameters are derived using sample statistics
3. **Distribution Fitting**: The fitted Gaussian-like distribution approximates the transformed data distribution
4. **Visual Validation**: Histogram comparison shows reasonable fit between empirical and theoretical distributions

## Mathematical Details

The probability density function used is a Gaussian (normal) distribution:
```
p̂(z) = (1/(σ√(2π))) × e^(-(z-μ)²/(2σ²))
```

Reparameterized as:
```
p̂(z) = c × e^(-λ(z-μ)²)
```

Where:
- λ = 1/(2σ²)
- c = 1/(σ√(2π))

##  Key Findings

- The transformed NO2 data approximately follows a normal distribution
- Mean of transformed data: **32.89 μg/m³**
- Standard deviation: **20.58 μg/m³**
- The non-linear transformation slightly skews the original distribution

## 🎓 Educational Value

This project demonstrates:
- Working with real-world environmental data
- Applying statistical transformations
- Maximum likelihood parameter estimation
- Probability density function fitting
- Data visualization techniques

---

## 👨‍🎓 Roll Number

**102303580**
