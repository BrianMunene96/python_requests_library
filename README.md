# python_requests_library

## Overview
 
This assignment covers two practical workflows for retrieving JSON data using Python and converting it into structured CSV files: pulling data from a GitHub and consuming live API endpoints from DummyJSON.
 
 
## Part 2: JSON Data from GitHub
 
A synthetic dataset was created using Mockaroo, themed around **Kenyan election results**. The dataset contains 1,000 records with the following fields: `candidate_name`, `votes_received`, `party_affiliation` (ODM, UDA, Wiper, Jubilee, ANC), `constituency` (Nairobi, Mombasa, Kisumu, Nakuru, Eldoret), and `winning_status`.
 
The JSON file was uploaded to a public GitHub repository and accessed via its raw URL using the `requests` library. After confirming a successful `200` response, the data was parsed into a Python list and loaded into a pandas DataFrame, then exported as `elections.csv`.
 
**Source:** `https://raw.githubusercontent.com/BrianMunene96/Data_Repository/refs/heads/main/election_results_mock_data.json`
 
**Output:** `elections.csv`
 
 
## Part 3: DummyJSON API Endpoints
 
Data was extracted from two endpoints of the [DummyJSON](https://dummyjson.com) API.
 
### Products (`/products`)
A GET request was sent to `https://dummyjson.com/products`. The JSON response was a dictionary, and the relevant list was extracted using the `"products"` key. This was loaded into a DataFrame with 22 columns covering product details such as title, price, category, stock, rating, and more.
 
**Output:** `products.csv`
 
### Carts (`/carts`)
A GET request was sent to `https://dummyjson.com/carts`. The response was similarly parsed, extracting the `"carts"` key into a DataFrame of 30 rows with columns including `id`, `products`, `total`, `discountedTotal`, `userId`, `totalProducts`, and `totalQuantity`.
 
**Output:** `carts.csv`
 
 
## Libraries Used
 
- `requests` - HTTP requests to GitHub and DummyJSON
- `pandas` - DataFrame construction and CSV export
 
## Output Files
 
| File | Description |
|---|---|
| `elections.csv` | 1,000-row synthetic Kenyan election results dataset |
| `products.csv` | Product catalogue from DummyJSON |
| `carts.csv` | Shopping cart data from DummyJSON |
