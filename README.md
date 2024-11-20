
*Global Gear's "Quick Inventory Search" tool is designed to enhance and streamline the process of locating products within the company's extensive inventory.*

# **Use Case: Streamlining Inventory Search with Global Gear's Quick Inventory Search Tool**
---

**Objective**
---
To develop a Python-based tool that enables quick and efficient search through Global Gear's extensive inventory. The tool aims to enhance productivity by providing instant access to inventory data, improving stock management, and enhancing customer service.


**Preconditions**
---
User has access to the Global Gear inventory system.
The inventory system is updated with accurate and current product information.

**Basic Flow:**
1. **Create the inventory class**

```python
class Inventory:
    def __init__(self, df):
        self.data = df
        
    def get_order_from_id(self, order_id):
        """
        Returns a dictionary representing the order with the specified ID,
        or None if no match is found.
        """
        # Filter the DataFrame based on the order ID
        filtered_df = self.data[self.data['order_number'] == order_id]

        # Check if a match was found
        if not filtered_df.empty:
            return filtered_df.iloc[0].to_dict()  # Return the first matching row as a dictionary
        else:
            return None
```

2. **Search Initiation**

User accesses the Quick Inventory Search tool. User inputs a search query, which can include the order id and the sales done.

```python
# Create an Inventory object using the DataFrame
inventory = Inventory(df)

order = inventory.get_order_from_id(10300)  
if order:
    print(f"Found order with ID {order['order_number']}: {order}")
else:
    print("No order found with the given ID.")
```

The tool processes the search query and quickly retrieves matching products from the inventory database.

**Results Display:**
---
The tool displays a list of matching products, including:

![Result dispay](<Images/Screenshot (311).png>)

No Match Found:
If no matching products are found, the tool displays a message indicating the search was unsuccessful. User can refine the search query or contact IT support for assistance.

**Postconditions:**

User is able to quickly and accurately locate the desired product. Inventory accuracy is maintained. Warehouse operations are streamlined. By effectively utilizing the Global Gear Quick Inventory Search tool, users can significantly streamline their inventory processes and improve overall operational efficiency.

