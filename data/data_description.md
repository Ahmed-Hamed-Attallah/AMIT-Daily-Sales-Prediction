## Dataset Description: Sales Dataset

This dataset contains **9,800 sales transaction records** representing customer orders across different regions, product categories, and time periods.

Each row corresponds to a **single product line item within an order**.

### Dataset Size

* **Rows:** 9,800
* **Columns:** 18

---

## Column Descriptions

### Order Information

* **Row ID** *(Integer)*
  Unique identifier for each row in the dataset.

* **Order ID** *(Categorical)*
  Unique identifier for each customer order. Multiple rows can share the same Order ID.

* **Order Date** *(Date)*
  The date on which the order was placed.

* **Ship Date** *(Date)*
  The date on which the order was shipped.

* **Ship Mode** *(Categorical)*
  Shipping method used (e.g., Standard Class, Second Class).

---

### Customer Information

* **Customer ID** *(Categorical)*
  Unique identifier for each customer.

* **Customer Name** *(Text)*
  Name of the customer.

* **Segment** *(Categorical)*
  Customer segment (Consumer, Corporate, Home Office).

---

### Geographic Information

* **Country** *(Categorical)*
  Country where the order was placed.

* **City** *(Categorical)*
  City of the customer.

* **State** *(Categorical)*
  State of the customer.

* **Postal Code** *(Numeric / Categorical)*
  Postal code of the customer location (contains some missing values).

* **Region** *(Categorical)*
  Sales region (e.g., South, West, East, Central).

---

### Product Information

* **Product ID** *(Categorical)*
  Unique identifier for each product.

* **Category** *(Categorical)*
  Main product category (Furniture, Office Supplies, Technology).

* **Sub-Category** *(Categorical)*
  Product sub-category (e.g., Chairs, Tables, Storage).

* **Product Name** *(Text)*
  Name and description of the product.

---

### Target Variable

* **Sales** *(Continuous – Numeric)*
  Sales value for the product line item.
  This is the **target variable** for forecasting.

---
