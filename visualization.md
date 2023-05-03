

## Visualization Code Snippet

*Below is an example of code for one of our graphs. The output of this code outlines the relationship between the average prices of coastal and inland homes within a given zip code compared to sea level. 
```python
#4
# Calculate mean price for each GMSL_noGIA value and group
mean_prices = zip_sea.groupby(['GMSL_noGIA', 'Inland/Coastal'])['Price'].mean().reset_index()

# Plot the scatterplot
plt.figure(figsize=(12, 6))
sns.scatterplot(x="GMSL_noGIA", y="Price", hue="Inland/Coastal", data=mean_prices)
plt.title("Mean Price vs GMSL_noGIA for Coastal and Inland Properties")

# Add linear regression lines for each group
coastal_data = mean_prices[mean_prices["Inland/Coastal"] == 1]
inland_data = mean_prices[mean_prices["Inland/Coastal"] == 0]

sns.regplot(x="GMSL_noGIA", y="Price", data=inland_data, scatter=False, label="Inland")
sns.regplot(x="GMSL_noGIA", y="Price", data=coastal_data, scatter=False, label="Coastal")

plt.legend()
plt.savefig("graphs/mean_price_vs_GMSL_noGIA.png")
plt.show()
```
