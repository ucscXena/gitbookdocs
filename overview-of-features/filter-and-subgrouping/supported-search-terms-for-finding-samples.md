# Supported search terms for finding samples

## Supported search terms

### Categorical features  <a id="searchingcategoricalfeatures"></a>

Our search is 'contains' search, meaning the term you enter can be at the beginning, end or in the middle of a matched term. Our search is case-independent. An example is

> IIA

will match 'Stage IIIA' and 'Stage IIA'. To specify a specific string, use quotes

> "Stage IIA"

### Numerical and Continuous features  <a id="searchingcontinuousfeatures"></a>

You can specify a certain column and mathematical expression such as

> A:&gt;2

which will highlight all values greater than 2 in the first column. We support the following operators

* = \(equal\)
* &gt;= \(less than or equal\)
* &gt;= \(greater than or equal\)
* &lt; \(less than\)
* &gt; \(greater than\)
* != \(not equal\)

### Mutation data

You can search any annotation on a mutation, such as the functional impact, protein position, or gene name itself

To find all samples with mutations with the protein change, enter:

> V600E

To find all samples where the functional impact has 'frame' or 'nonsense'

> D:frame OR nonsense

To find all samples that have a mutation, search the gene annotation:

> TP53

To find all samples that do not have a mutation, use the negation of the gene annotation:

> !=TP53

### No data

To find all samples that do not have data in one or more columns, use:

> null

and choose 'Remove samples'. To find all samples that do not have data for just one column, use:

> B:null

### Sample IDs  <a id="searchingsampleids"></a>

Whether the sample ID column is in view or not, it is always possible to enter a sample ID to find that one sample of interest. An example:

> TCGA-DB-A4XH

Try using 'alt-click' to freeze the tooltip for copying a sample ID. Paste into highlight feature to keep track of where that sample lies as you move columns around, changing the sort order.

### Searching a specific column  <a id="searchingaspecificcolumn"></a>

To make it easy to search a specific column, we use shorthand to annotate the first column as 'A:', the second as 'B:', etc. An example is

> A:YES

This will search ONLY the first column for the word 'YES'. Note that we will retain your original search if you move the columns around.

### Boolean operators: OR, AND, and !=  <a id="usingbooleanoperatorsandgrouping"></a>

You can enter multiple search terms and we will match all of them with an implicit 'AND'. We also support 'OR'.

Use parentheses to group search terms. For example:

> "Stage II" \(B:Negative OR C:Negative\)

will search for samples that match 'Stage II' in any column and are 'Negative' for either the second or third column.

You can also use '!=' to negate a term such as:

> !=null

which will match all samples that have data across all columns.

