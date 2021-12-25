# Project-14---Use-Data-Analytics-to-Analyze-Inventory
import codecademylib3
import pandas as pd
#1
inventory = pd.read_csv('inventory.csv')
#2
print(inventory.head(10))
#3
staten_island = inventory.head(10)
#4
product_request = staten_island.product_description
#5
seed_request = inventory[(inventory.location == 'Brooklyn') & (inventory.product_type == 'seeds')]
#6
inventory["in_stock"] = inventory.apply(lambda row: True if row.quantity > 0 else False, axis = 1)
print(inventory.head(10))
#7
inventory['total_value'] = inventory.apply(lambda row: row.price * row.quantity, axis = 1)
print(inventory.head(10))
#8
combine_lambda = lambda row: \
    '{} - {}'.format(row.product_type,
                     row.product_description)
print(inventory.head(10))
#9
inventory['Full Description'] = inventory.apply(combine_lambda, axis = 1)
print(inventory.head(10))
