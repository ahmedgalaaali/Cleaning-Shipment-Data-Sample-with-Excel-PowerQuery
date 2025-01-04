# Dirty Shipment Data Sample Cleaning and Analysis
## Content
1. [Overview](#overview)
2. [Data Inspection](#data-inspection)
3. [Cleaning and Preparation](#cleaning-and-preparation)
4. [Data Analysis](#data-analysis)
## Overview
This projects was accomplished to showcase my abilities in cleaning and preparing data using Excel PowerQuery and analyzing using simple descriptive data analsysis features in Excel. The [Dirty Data Sample](https://www.kaggle.com/datasets/shivavashishtha/dirty-data-sample) was downloaded from Kaggle.com in the form of a `xlsx` file published by [Shiva Vashishtha](https://www.kaggle.com/shivavashishtha). The excel workbook composed of 2 sheets:
- `Dirty1`: The actual dirty data that I'm supposed to work on.
- `Clean1`: the shape of the data which the publisher seeks.
## Data Inspection
1. The data looked a little bit messy so I had to highlight some columns to better understand what I see. Here we see that the data takes the shape of a pivot table that shows:
    - `Order ID` column.
    - The first row which will later express the `Segment` column.
    - The second column which will later express the `Ship mode` column.
    - And finally, the values of the pivot table scattered all around, these are so useful and are considered the `Sales` column.
2. It seemed like each order ID had **only one value**, this value expresses the ship mode as it's in the same column of its name, and also the segment as the value exists in the same highlighted segment.
![alt text](image-1.png)
## Cleaning and Preparation
By inspecting and understanding the data, I loaded the range into Excel PowerQuery; where I will make the data look better and smoother.
1. **Removed the top row**: this ensures that the second row becomes the first for the next step.
2. **Make first row as column name**: in this step the ship mode names became the columns names, and also changed the data type into decimal.
3. **Rename the ID column**: as making the first row as the column name, the order ID column needs to be modified too.
4. **Merge ship mode columns**: now the key step here, is to merge the similar columns together, so I merged all of the segment columns together, all `first Class` together and so on with the others.
5. **Merge segment columns**: you might notice the existance of some columns like `Consumer Total`,`Corporate Total`,`Home office Total`, these are the key elements of getting the segment column, but wait, **we removed them earlier!** No worries! Just rename the columns that contain the values of each segment total.
    - `Consumer Total` to `Consumer`
    - `Corporate Total` to `Corporate`
    - `Home office Total` to `Home office`
6. **Unpivot columns**: this step will return the columns to the natural state as needed.
    - **Unpivot ship mode columns**: this will return 2 columns, a column that has all the segments per each order ID and another column with that has the value of sales relates to the ship mode of the order and blanc value of the ship mode not related; **_this column is the hero of the day_**
    - **Unpivot the segment column**: this will also return 2 columns same as the previous one, but this time I'm going to remove the value column and only retain the segment.
7. **Filter the values**: the value column which we called **_the hero of the day_** contains `blanc` cells, we'll filter to remove these blancs, this will result a clean visual of the data.
8. **Remove non-necessary value**: noticed the presence of grand total values that exist at the bottom of the table, removed them by _remove bottom 12 rows_.
9. **changed sales data type into currency and sorted by ascending ship mode**
10. **loaded the clean data into excel worksheet**
## Data Analysis
With the power of PivotTables, I created meany of them to see what the data sample would like to show us.
1. _Consumers are the top customers of the shipment service with total **444** orders shown in the sample.
![alt text](image-2.png)
2. On the other hand the average price paid by _consumers_ is the least, wich explains their interst in dealing with our service.
![alt text](image-4.png)
3. _Consumers_ is also the greatest segment in terms of sales with about half of the values of sales.
![alt text](image-5.png)
4. When it comes to the _ship mode_ it seems like the _standard class_ is the most selling service with more than half of the sales, it's also the most preferred to all segments.
![alt text](image-6.png)
![alt text](image-8.png)