
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

*Joins* 

owners.groupby('area').agg({'owner':'count'}) -- this will aggregate counts of owners in each area 
                                    -- group by and sort also take lists as inputs .. 
lef_on and right_on let you join on different column names 
join using indexs (use left_index = True and right_index = True if you are joining on indexes on both sides )

*filtering joins*

semi join -- filter using isin 
anti join -- use indicator = True to get _merge column and use loc operator to filter _merge = "left_only" 






**MatplotLin Notes** 

.plot(kind = "bar", rot=45, alpha = 0.7, bins = 20) 
-- rot rotates axis labels 
-- alpha enables transparency 
-- bins for histograms 








