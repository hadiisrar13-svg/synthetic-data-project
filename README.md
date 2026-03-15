import pandas as pd
import numpy as np
from faker import Faker

fake = Faker()

records = 200

data = {
    "Customer_ID": range(1001, 1001 + records),
    "Name": [fake.name() for _ in range(records)],
    "Age": np.random.randint(18, 60, records),
    "Gender": np.random.choice(["Male", "Female"], records),
    "City": np.random.choice(["Lahore", "Karachi", "Islamabad", "Rawalpindi"], records),
    "Product": np.random.choice(["Shoes", "Bag", "Watch", "Clothes"], records),
    "Purchase_Amount": np.random.randint(2000, 10000, records)
}

synthetic_data = pd.DataFrame(data)

print(synthetic_data.head())

synthetic_data.to_csv("synthetic_customer_data.csv", index=False)
