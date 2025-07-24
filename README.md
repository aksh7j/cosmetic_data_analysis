Here's a complete **README.md** file that describes the steps and purpose of your cosmetics ingredient analysis project using t-SNE for dimensionality reduction and visualization:

---

# 🧴 Cosmetics Ingredient Visualization using t-SNE

This project performs exploratory analysis and visualization on a cosmetics dataset using **Pandas**, **NumPy**, **scikit-learn**, and **Bokeh**. The primary focus is to understand patterns in the ingredients of **moisturizers for dry skin**, and visualize their similarity using **t-SNE (t-distributed Stochastic Neighbor Embedding)**.

---

## 📁 Dataset

The dataset used is `datasets/cosmetics.csv`, which includes:

* Product **Name**
* **Brand**
* **Price**
* Product **Label** (e.g., Moisturizer, Cleanser, etc.)
* Skin concern indicators (e.g., `Dry`, `Oily`, etc.)
* Ingredient list

---

## 🧪 Tasks Overview

### ✅ Task 1: Import and Inspect Data

* Imported `pandas`, `numpy`, and `TSNE` from `sklearn.manifold`.
* Loaded the dataset using `pd.read_csv()`.
* Displayed a random sample of 5 rows.
* Counted the number of products by type (Label column).

### ✅ Task 2: Filter for Moisturizers and Dry Skin

* Filtered `Label == "Moisturizer"` and `Dry == 1`.
* Reset the index to clean up row numbers.

### ✅ Task 3: Tokenize Ingredients

* Converted ingredients to lowercase.
* Split ingredient strings by `', '` into lists.
* Created a **corpus** (list of ingredient lists).
* Built an `ingredient_idx` dictionary mapping each unique ingredient to a unique index.

### ✅ Task 4: Initialize Document-Term Matrix

* Defined `M` = number of products and `N` = number of unique ingredients.
* Created a binary matrix `A` of shape `MxN`, initialized with zeros.

### ✅ Task 5: Create One-Hot Encoder Function

* Defined `oh_encoder(tokens)` to:

  * Create a binary vector of size `N`.
  * Set indices of present ingredients to 1 based on `ingredient_idx`.

### ✅ Task 6: Apply One-Hot Encoding

* Used `oh_encoder()` to convert each product's ingredient list into a binary vector.
* Filled matrix `A` with one-hot encoded ingredient presence per product.

### ✅ Task 7: Apply t-SNE for Dimensionality Reduction

* Reduced matrix `A` to 2D using `TSNE(n_components=2, learning_rate=200, random_state=42)`.
* Saved new coordinates to `moisturizers_dry['X']` and `moisturizers_dry['Y']`.

### ✅ Task 8: Visualize with Bokeh

* Created a Bokeh `ColumnDataSource`.
* Plotted each product as a point using `plot.circle()`.

### ✅ Task 9: Add Hover Tool

* Added tooltips to show:

  * Product Name
  * Brand
  * Price
  * Rank

### ✅ Task 10: Display the Plot

* Used `show()` to render the interactive visualization.

### ✅ Task 11: Compare Ingredients of Two Similar Products

* Printed and compared ingredient lists for:

  * `Color Control Cushion Compact Broad Spectrum SPF 50+`
  * `BB Cushion Hydra Radiance SPF 50`

---

## 🔧 Technologies Used

* Python
* pandas, numpy
* scikit-learn (TSNE)
* Bokeh (interactive plotting)

---

## 💡 Purpose

This project demonstrates:

* Ingredient-based similarity analysis in skincare products.
* Using text tokenization and one-hot encoding to build document-term matrices.
* Dimensionality reduction with **t-SNE** for ingredient visualization.
* Interactive product comparison using Bokeh.

---

## 📊 Output Example

An interactive 2D scatter plot of moisturizers for dry skin, where:

* Each point = 1 product.
* Proximity = similarity in ingredients.
* Hovering reveals name, brand, price, and rank.

---

## 📌 Note

This approach can be extended to:

* Compare products across other skin concerns (e.g., oily, sensitive).
* Perform clustering or recommendation systems based on ingredients.

---
