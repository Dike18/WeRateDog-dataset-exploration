# WeRateDog-dataset-dexploration

# Gathering Data

The first thing was to import the necessary libraries for the project and these included

1. Pandas
2. Numpy
3. Matplotlib
4. Json
5. Seaborn 
 
Next, the files to be used for the project which included The twitter_archive_enhanced.csv, The tweet_json.txt, and The image_predictions.tsv files were available at hand and were gathered using the pandas library to read the .csv, .tsv, and .txtfiles into a dataframe

# Assessing Data
This was done in two ways.

## Visual assessment:

The dataframe of each of the three files were loaded and assessed by scrolling horizontally and vertically

## Programmatical assessment:

Some codes where used to further reveal what can not be assessed visually. Some of the codes included 
 `.head() `
 `.query()` 
 `.info() `
` .sum() `
` .duplicated() `
` .describe() `
 `.value_counts() `etc

In addition, some visuallizations where used to further assess and demonstrated some of these assessments. At the end of the assessment of the datasets, 12 issues were identified in accordance with the project’s instructions. These issues were broadly classified into two groups; Quality issues and Tidiness issues. The quality issues were further grouped in completeness, validity, consistent, and accuracy issues. A summary of the kinds of issues assessed are listed below:

Over 2000 null values per column identified in two columns
Date type data appearing as strings
Presence of outliers in data most of which violate the rule of what data is supposed to be entered
Indefinite and undesirable data forms e.g. datapoints with html tags
Use of short forms for certain data points.
Inconsistence in column names etc.

# Cleaning

In this section, all identified issues were cleaned programmatically using line codes, user-defined-functions, iterations etc. The first step was to create a copy of all dataframes used for the assessment section using the pandas `.copy()` function. Some cleaning process are described below.

For issues 1 and 2, the columns containing the null datapoints were drops using the ` .drop() `  function.
The created_atand Datestamp columns which were originally in the object type datatype were changed to datetime datatype using the `pd.to_datetime.` This helped addressed incorrect data type that the columns had
The language column was changed from initially lang to language using  `.rename()`  function. In addition to this, short forms of the languages in the dataset under the language columns were changed to their full meaning using the `.replace()` function to replace short forms with their full meaning.
The tweet_id column which were inappropriately named where renamed using the ` .rename()` function. This further enabled merging of the three datasets together.
At the end of every cleaning a Code-Based-Test was used test for the effected changes of the cleaning process.

# Merging and storing.

The three datasets gathered, assessed, and cleaned where then merged on the tweet_id column and stored using the` pd.to_csv function.`
