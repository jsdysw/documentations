# pandas_documentation

### Series - column
````
Series(data=[1,2,3], index=['a','b','c'])
````


````
dict_data = {"a":1, "b": 2}
example_obj = Series(dict_data, dtype=np.float32, name="ex_series")
example_obj["a"]
````

````
example_obj.values  # value list, array([1, 2])
example_obj.index  # indices list, array(['a', 'b'])
````

### Dataframe - table of columns
````
dict_data = {"col1":[1,2], "col2": [3,4]}
df = pd.DataFrame(dict_data, columns=['COL1','COL2'])
df.COL1
df["COL1"]
````

````
df.index = list(range(0,15))
df.loc[1]  # row which name of the index is "1"
df.loc[:2]
df.iloc[1]  # row at index 1 position
df.iloc[:2]
````

````
df['age'] > 40  # [True, False, True, ...]
df.T
df.values   # [[row1], [row2], ...]
df.to_csv()
````

````
del df['dept']  # delete column
````


### Selection & drop, indexing is almost same with numpy's
````
df[['age'], ['name']].head(3)
df['age'][:3]
df['age'][df['age'] > 30]
````

````
df.loc[1]  # row which name of the index is "1"
df.loc[:2]
df.iloc[1]  # row at index 1 position
df.iloc[:2]
````

````
df['age'] > 40  # [True, False, True, ...]
df.T
df.values   # [[row1], [row2], ...]
df.to_csv()
````

````
del df['dept']  # delete column
df.drop([1,2])  # drop row of index name 1 and 2
df.drop("age", axis=1)  # drop age column
````

````
df_people[df_people['gender'] == 'male']
````



### operation
````
series_1 + series_2  # elementwise sum, if there's no row pair the summation result becomes NaN
series_1.add(series_2) # elementwise sum, if there's no row pair the summation result becomes NaN
````

````
df_1 + df_2  # elementwise sum, if there's no row pair, the summation result becomes NaN
df_1.add(df_2) # elementwise sum, if there's no row pair, the summation result becomes NaN
df_1.add(df_2, fill_value=0) # elementwise sum, if there's no row pair, the do summation with 0
````

### map - modify each column
````
series_1.map(lambda x: x**2).head(5)  // square every row
````
````
z = {'male':0, 'female':1}
series_2.map(z)  // replace value
df['gender'].map(z)
df['gender'].replace(z)
df['gender'].replace(['male', 'female'], [0,1], inplace=True)
````


### apply - modify several columns
````
df[['age', 'dept']].apply(lambda x: x.max() - x.min()) 
````

### built in functions
````
df.describe()    // summary
df.head()
df['gender'].unique()
````
````
value = list(map(int, np.array(list(enumerate(df['gender'].unique())))[:0].tolist()))
key = np.array(list(enumerate(df['gender'].unique())))[:1].tolist()
# value => [0, 1], key => ['male', 'female']
df['gender'].replace(to_replace=key, value=value, inplace=True)
````

````
df.sum(axis=0)
df.sum(axis=1)
````

````
df.isnull()
#  [[false, True],
#  [false, True]]
````

````
df.isnull().sum()
# age  0
# address 10
# name 1
````

````
df.sort_values(['age', 'earn'], ascending=True)
````

### Group by : split -> apply -> combine
````
df.groupby("Team")["Points"].sum()
# TeamA  100
# TeamB  20

df.groupby(["Team", "Year"])["Points"].sum()
# TeamA  2020 100
# TeamA  2021 100
# TeamB  2001 20
````

````
df.groupby('Team').unstack()   // grouped df -> matrix
grouped_df.get_group("TeamDevils")
````

````
grouped_df['Points'].agg(sum)
grouped_df['Points'].agg([np.sum, np.mean, np.std])
````
````
score = lambda x: (x - x.mean()) / x.std()
grouped.transform(score)  // transform based on each group
````

````
df.groupby('Team').filter(lambda x: len(x) >= 3)
````

````
df.groupby(['month', 'item'])['date'].count()
df_phone.groupby(['month', 'item']).agg({'duration':[min, max, sum], 'network_type':"count", 'date': [min, 'first', 'nunique']})
````

<img width="940" alt="Screenshot 2023-11-07 at 10 05 17 PM" src="https://github.com/jsdysw/documentations/assets/76895949/a9df2685-e775-40c1-852d-1ffe93ac0179">

### merge & concat
````
pd.merge(df_a, df_b, on='subject_id', how='right')   // outer, inner, right, left join
````
````
df = pd.concat([df_a, df_b], axis=0)
df.reset_index()
df_a.append(df_b)
````
