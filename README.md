
# Formatting 

Bold: **text**
Italic: *text*
Heading: # Heading

# Python_Practice


# Data Science in Python:

**Pandas Data Manipulation**  

Indexing: you can use loc and iloc to filter data using indexes 
so, set_index method helps you directly filter using categorical vaiables 

*Creating Dataframes*

pd.DataFrame(dict_of_lists / list of ditionaries) - this creates a data frame from a dictionary 
pd.read_csv("file_name.csv") -- create a dataframe from csv file 
df.to_csv("file_name.csv")  -- writes df to a csv file 

*missing values*

df.isna() - gives a bollean value 
df.isna().any() - tells us if there is any missing values in each column 
df.isna().sum() - number of na values (you can also plot this using .plot(kind='bar') at the end )
df.dropna() - get rid of missing values 
df.fillna(0) - fill 0 in place of missing values  

*sorting*

sort_values("column_name". ascending = True)

*Indexing*

idxmax - returns the index of the maximum (use this to return the column variable to resue in code)

*pivot tables*

df.pivot_table(index='column1', columns='column2',  values='column3', aggfunc='mean', fill_value=0)
-- default aggfun is mean 
gdp_pivot = gdp_pop.pivot_table('gdp_per_capita', 'date', 'country')


*Joins* 

merge - pd.merge(df1,df2, on ="column", how = "inner")
-- left_on , right_on to join by different column names 

owners.groupby('area').agg({'owner':'count'}) -- this will aggregate counts of owners in each area 
                                    -- group by and sort also take lists as inputs .. 
lef_on and right_on let you join on different column names 
join using indexs (use left_index = True and right_index = True if you are joining on indexes on both sides )

*filtering joins*

semi join -- filter using isin 
anti join -- use indicator = True to get _merge column and use loc operator to filter _merge = "left_only" 

*concat*

pd.concat([df1,df2,df3], ignore_index = True
, keys = [k1,k2,k3]
, sort = True -- alphabetically sort based on column names 
, join = 'inner' -- this will only result matching column names , default is 'outer'
)

*verifying integrity in merge&concat*

.merge(validate = None ) -- 'one_to_one' etc 
-- if validation is successful, merge results in a table and doesn't throw error 

.concat(verfiy_integrity = False -- default value ) -- True will check if the indexes have overlapping values 

-- you can drop dupes after merging wihtout ahving these arguments 

*merge_ordered* 
-- this is used for time series data and to hande missing data 
-- default how is outer as opposed to inner in merge (this is why forward filling missing data can be useful)
-- pd.merge_ordered this is the only way merge_ordered can be called not df.merge_ordered 
-- this method also sorts data on the join column 
-- fill_method = 'ffill'

*merge_asof* 
--to fill data not 

*.query*

stocks.query('nike>60 and disney<90') 
-- its a where statement - nike and disney are columns 

*.melt* 
-- melt converts data from long to wide 
-- id_vars = identifier variables ~ these remain unchanged 
-- value_vars /var_name = columns to unpivot 
-- value_name = melted column name  
-- Use melt on ten_yr, unpivot everything besides the metric column
bond_perc = ten_yr.melt(id_vars='metric', var_name='date', value_name='close')



**MatplotLin Notes** 

.plot(kind = "bar", rot=45, alpha = 0.7, bins = 20) 
-- rot rotates axis labels 
-- alpha enables transparency 
-- bins for histograms 








