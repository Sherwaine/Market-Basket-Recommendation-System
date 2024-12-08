# Market Basket Recommendation System

This project implements a **Market Basket Recommendation System** using the **Apriori algorithm** to identify frequently bought products and generate association rules. It allows for the recommendation of products based on the frequency of co-occurrence in transactions.

## Table of Contents

- [Description](#description)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)
- [License](#license)

## Description

This system processes transaction data from an online retail store (`Online Retail.xlsx`) to identify associations between products. Using the **Apriori algorithm** and **Association Rules**, it generates product recommendations based on the frequency of products purchased together. The project does not include graph visualizations in its final version, focusing solely on recommending products based on the association rules.

### Key Features:
- **Data Preprocessing**: Filters out products bought more than 20 times for better relevance.
- **Apriori Algorithm**: Identifies frequent itemsets based on the transaction data.
- **Association Rules**: Generates rules based on metrics like **lift** to identify relationships between products.
- **Recommendation Engine**: Recommends top `n` products for a given product description.

## Technologies Used

- **Python**: The core programming language.
- **Pandas**: For data manipulation and analysis.
- **MLxtend**: For implementing the Apriori algorithm and generating association rules.
- **Openpyxl**: For reading Excel files.

## Installation

Follow these steps to set up the environment:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/Sherwaine/market-basket-recommendation.git
    cd market-basket-recommendation
    ```

2. **Create a virtual environment** (optional but recommended):
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install the required dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Download the dataset**: Place the `Online Retail.xlsx` file (or your dataset file) in the project directory.

## Usage

### Example Usage

Once the dataset is loaded, you can call the `recommend_products` function to get product recommendations based on an input product description. The system will recommend products that are frequently bought together with the given product, using association rules generated by the Apriori algorithm.

```python
# Example usage:
product_description = 'WHITE HANGING HEART T-LIGHT HOLDER'  # Input product
recommended_products = recommend_products(product_description, rules, top_n=5)

# Display the recommended products
print(f"Recommendations for '{product_description}':")
for product in recommended_products:
    print(f"- {product}")