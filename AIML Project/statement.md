# AI Purchase Recommendation System

This project is a simple console-based AI recommendation system that generates sample purchase data, trains a basic recommendation engine, and lets a user query recommendations and customer insights.

## Components

- `Main.py`: Entry point that:
  - Initializes `DataLoader` and `SimpleRecommendationEngine`.
  - Generates sample purchase data for a number of customers.
  - Trains the recommendation engine.
  - Provides a text menu to:
    - Get product recommendations for a customer.
    - View customer purchase insights.
    - Show sample data and available products.[attached_file:1]

- `DATALOADER.PY`:
  - Defines `DataLoader` with:
    - A catalog of products and categories.
    - `generate_sample_data(...)` to create random purchase records (customer, product, quantity, date).
    - `get_customer_purchases(customer_id, purchase_data)` to filter purchases for a given customer.[attached_file:2]

- `recommendation_enginge.py`:
  - Defines `SimpleRecommendationEngine` which:
    - Builds a customer–product matrix from purchase data.
    - Computes product–product and customer–customer similarity using cosine similarity.
    - Finds frequently bought-together item pairs.
    - `fit(purchase_data)` trains internal structures.
    - `recommend_products(customer_id, top_n=5)` produces recommendations using:
      - Similar products to those already bought.
      - Purchases of similar customers.
      - Frequent co-purchase patterns.
    - `get_customer_insights(customer_id, purchase_data)` returns summary stats for a customer (totals, unique products, favorite category, average quantity, and purchase frequency).[attached_file:3]

## Dependencies

- Python 3.x.[web:9]
- Libraries:
  - `pandas` for tabular data handling.[attached_file:1][attached_file:2][attached_file:3]
  - `numpy` for numerical operations.[attached_file:2][attached_file:3]
  - `scikit-learn` (`sklearn.metrics.pairwise`, `sklearn.feature_extraction.text`) for similarity computations and feature extraction.[attached_file:3]
  - `collections` (`defaultdict`) for counting frequent patterns.[attached_file:3]

## Usage

1. Install dependencies.
2. Run `Main.py`.
3. Use the console menu to:
   - Enter a customer ID to get product recommendations.
   - View insights for a specific customer.
   - Inspect sample purchase data and available products.[attached_file:1]
