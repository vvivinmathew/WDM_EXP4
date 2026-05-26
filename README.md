### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 26.06.2026
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
# Visitor segmentation based on characteristics
# read the data
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("/content/clustervisitor.csv")
df.head(10)

# Perform segmentation based on characteristics (e.g., age groups)
cluster = {
    "Young" : df['Age'] <= 30,
    "Middle" : ((df['Age'] > 30) & (df['Age'] <= 50)),
    "Old" : df['Age'] > 50
}

```
### Output:
<img width="342" height="766" alt="image" src="https://github.com/user-attachments/assets/2bfeb389-c15c-4432-ad2e-657483b031e5" />

### Visualization:
```python
# Create a list to store counts of visitors in each age group
visitor_counts = []

# Count visitors in each age group
for g, age in cluster.items():
    visitor = df[age]
    print(f"the visitors in {g} age are\n", visitor)
    print(f"Visitor Count : {len(visitor)}")
    visitor_counts.append(len(visitor))
    print("\n")
    
# Define age group labels and plot a bar chart
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
<img width="721" height="560" alt="image" src="https://github.com/user-attachments/assets/28bf5e95-abde-40a1-b69a-29cd1281ecc1" />


### Result:
Thus, visitor segmentation based on age groups was successfully done using Python.
