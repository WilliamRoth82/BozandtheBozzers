

## Cleaning Code Snippets


*This code outlines how we were able to merge our two data sets using Pandas.*
```python
# Merge two data sets
merged_data = pd.merge(transposed_data, filtered_data, how='outer', left_index=True, right_index=True)
merged_data.rename(columns={'Year': 'Date'}, inplace=True)
merged_data.index = merged_data.index.rename('Date')

merged_data.to_csv('inputs/merged_data.csv')

print(merged_data.head())
filtered_merged_data = merged_data.loc['2010-01':'2021-06']

print(filtered_merged_data.head())

filtered_merged_data.to_csv('inputs/filtered_merged_data.csv')
```

*Below we have our code for adding information with regard to our zip codes and sea level data to the data set.*
```python
Coastal = [36532.0, 36605.0, 99501.0, 94015.0, 93950.0, 93109.0, 77505.0, 19968.0, 19963.0, 19901.0, 19720.0, 33137.0, 33129.0, 33131.0, 33308.0, 33062.0, 32226.0, 96778.0, 70124.0, 70122.0, 70126.0, 39501.0, 29412.0, 29577.0, 29582.0, 77058.0, 77015.0, 21403.0, 21122.0, 21220.0, 10305.0, 10314.0, 11214.0, 10069.0, 10010.0, 28468.0, 23518.0, 23661.0]
Inland = [36576.0, 36606.0, 99508.0, 94014.0, 93940.0, 93108.0, 77504.0, 19947.0, 19960.0, 19904.0, 19702.0, 33127.0, 33145.0, 33130.0, 33309.0, 33060.0, 32218.0, 96771.0, 70118.0, 70119.0, 70116.0, 39503.0, 29407.0, 29579.0, 29566.0, 77062.0, 77020.0, 21401.0, 21060.0, 21237.0, 10304.0, 10306.0, 11204.0, 10023.0, 10003.0, 28467.0, 23502.0, 23666.0]
Combined = [36532.0, 36576.0, 36605.0, 36606.0, 99501.0, 99508.0, 94015.0, 94014.0, 93950.0, 93940.0, 93109.0, 93108.0, 77505.0, 77504.0, 19968.0, 19947.0, 19963.0, 19960.0, 19901.0, 19904.0, 19720.0, 19702.0, 33137.0, 33127.0, 33129.0, 33145.0, 33131.0, 33130.0, 33308.0, 33309.0, 33062.0, 33060.0, 32226.0, 32218.0, 96778.0, 96771.0, 70124.0, 70118.0, 70122.0, 70119.0, 70126.0, 70116.0, 39501.0, 39503.0, 29412.0, 29407.0, 29577.0, 29579.0, 29582.0, 29566.0, 77058.0, 77062.0, 77015.0, 77020.0, 21403.0, 21401.0, 21122.0, 21060.0, 21220.0, 21237.0, 10305.0, 10304.0, 10314.0, 10306.0, 11214.0, 11204.0, 10069.0, 10023.0, 10010.0, 10003.0, 28468.0, 28467.0, 23518.0, 23502.0, 23661.0, 23666.0]

additional_columns = [
    "TotalWeightedObservations",
    "GMSL_noGIA",
    "StdDevGMSL_noGIA",
    "SmoothedGSML_noGIA",
    "GMSL_GIA",
    "StdDevGMSL_GIA",
    "SmoothedGSML_GIA",
    "SmoothedGSML_GIA_sigremoved",
]

selected_columns = Coastal + Inland + additional_columns

filtered_zip = filtered_merged_data.loc[:, selected_columns]
filtered_zip = filtered_zip.reset_index()
```

*Once we had all our data, it was then time to pair up our points for analysis.*
```python
# Add the "Coastal/Inland" and "Pair" columns
transposed_filtered_zip['Inland/Coastal'] = transposed_filtered_zip['Zip'].apply(lambda x: 1 if x in Coastal else 0)
transposed_filtered_zip['Pair'] = 0
pair_index = 1

for i in range(0, len(Combined), 2):
    inland_zip = Combined[i]
    coastal_zip = Combined[i+1]
    transposed_filtered_zip.loc[transposed_filtered_zip['Zip'] == inland_zip, 'Pair'] = pair_index
    transposed_filtered_zip.loc[transposed_filtered_zip['Zip'] == coastal_zip, 'Pair'] = pair_index
    pair_index += 1

# Sort the DataFrame by the "Pair" column
transposed_filtered_zip = transposed_filtered_zip.sort_values(by='Pair')
```

*Lastly, we rearranged our data utilizing the Pandas melt function to finalize our data for our analysis.* 
```python
# Melt dataset - Rearrange data
transposed_filtered_zip = transposed_filtered_zip.iloc[8:]
melted_df = transposed_filtered_zip.melt(id_vars=['Zip', 'Inland/Coastal', 'Pair'],
                    var_name='Date',
                    value_name='Price')
                    
# Prep sea level data for merge and filter for the second date range (2017-10 to 2021-06)
filtered_data_2 = filtered_data.loc['2017-10':'2021-06'].reset_index()
# Merge:
zip_sea_new = pd.merge(melted_df_2, filtered_data_2.rename(columns={'Year': 'Date'}),
         on='Date', how='outer', validate='many_to_one')

zip_sea_new.to_csv('inputs/zip_sea_new.csv', index=False)
(zip_sea, zip_sea_new)
```

