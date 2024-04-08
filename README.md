import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the dataset
df = pd.read_csv("adidas_products.csv")

# Display basic information about the dataset
print("Dataset Information:")
print(df.info())

# Display the first few rows of the dataset
print("\nFirst few rows of the dataset:")
print(df.head())

# Summary statistics
print("\nSummary statistics:")
print(df.describe())

# Check for missing values
print("\nMissing values:")
print(df.isnull().sum())

# Visualize the distribution of product categories
plt.figure(figsize=(10, 6))
sns.countplot(data=df, x='Category')
plt.title('Distribution of Product Categories')
plt.xlabel('Category')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()

# Visualize the distribution of average ratings
plt.figure(figsize=(10, 6))
sns.histplot(data=df, x='Average rating', bins=20, kde=True)
plt.title('Distribution of Average Ratings')
plt.xlabel('Average Rating')
plt.ylabel('Count')
plt.show()

# Visualize the relationship between price and average rating
plt.figure(figsize=(10, 6))
sns.scatterplot(data=df, x='Price (selling)', y='Average rating')
plt.title('Price vs. Average Rating')
plt.xlabel('Price (selling)')
plt.ylabel('Average Rating')
plt.show()

# Visualize the relationship between price and reviews count
plt.figure(figsize=(10, 6))
sns.scatterplot(data=df, x='Price (selling)', y='Reviews count')
plt.title('Price vs. Reviews Count')
plt.xlabel('Price (selling)')
plt.ylabel('Reviews Count')
plt.show()

# Visualize the distribution of colors
plt.figure(figsize=(10, 6))
sns.countplot(data=df, x='Color')
plt.title('Distribution of Colors')
plt.xlabel('Color')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()

# Visualize the relationship between availability and average rating
plt.figure(figsize=(10, 6))
sns.boxplot(data=df, x='Availability', y='Average rating')
plt.title('Availability vs. Average Rating')
plt.xlabel('Availability')
plt.ylabel('Average Rating')
plt.show()

