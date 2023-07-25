# AWS QuickSight: Essential of data visualization

## Objectives

-   Understand the purpose of the QuickSight.

-   Learn the basics of connecting to data sources within Amazon QuickSight.

-   Acquire skills in building various types of visuals (charts, graphs, etc.) using the connected data.

-   Create calculations within QuickSight to perform data transformations and derive meaningful insights.

-   Design interactive dashboards to facilitate data exploration and analysis.

## Lab Setup

<center>
  
  ----------------------------------------
  | Time of performing | Required services  |
  |--------------------|--------------------|
  | 15 minutes         | AWS S3, QuickSight|
  ----------------------------------------

</center>

## Steps

1.  Create your dataset

2.  Rename Analysis

3.  Visualize Sales by Month

4.  Add Forecast to Line Chart

5.  Visualize Sales Year over Year

6.  Add Suggested Insights

7.  Visualize Sales by Industry

8.  Add Drill Down from Industry to Customer

## Step 1 -- Create your dataset

1.  On the left of your screen, choose **Datasets**.

2.  In the upper right of your screen, click **New dataset** button.

3.  Choose the first option called **Upload a file**.

4.  Browse to the **SaaS-Sales.csv** file.

5.  Choose **Next**.

6.  Choose **Visualize**.

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-1-FileUpload.gif)

## Step 2 -- Rename Analysis

You are now in an Analysis view. This is where you can add visuals,
adjust the layout and then publish your dashboard. First, let\'s change
the name of this analysis.

1.  Click the default name on the top panel to enter edit mode.

2.  Change the name to SaaS-Sales analysis - Build your first dashboard

3.  Click outside the name box to exit name edit mode.

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-2-RenameAnalysis.gif)

## Step 3 -- Visualize Sales by Month

1.  Click the empty visual to ensure that it is selected (indicated by blue border).

2.  From the **Fields list**, select **Sales** and **Order Date**.

3.  Enlarge the visual if axis labels are not visible.

4.  Click the **arrow** next to the Order Date label on your **X-axis**
and choose t**he Aggregate-\>Month.\
**Alternatively, you can expand the **Field Wells** section
towards the top of the screen, use the **arrow** on the **Order
Date** field and change the aggregation to **Month** from there.

5.  Resize the visual to take about two third of the horizontal space.

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-3-Line.gif)

## Step 4 -- Add Forecast to Line Chart

Let\'s use the in-built forecasting feature to add a forecast to our line chart.

1.  From the visual menu in the upper right of the visual, click the
ellipsis icon, and choose Add forecast.

2.  Optional - when adding/editing the forecast, you can apply backward
forecast as well to see how close the forecast is to the actuals
for the previous months.\
Change Periods backward to 6, click Apply and check out the
backward forecast.\
Then, change Periods backward back to 0 and click Apply.

3.  Close the Forecast properties panel and reopen Visualize panel.

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-4-Forecast.gif)

## Step 5 -- Visualize Sales Year over Year

1.  From top left of your screen, click + Add and then Add visual.

2.  From Visual types panel, change the Visual Type to Key Performance
Indicator (KPI).

3.  From Fields list, select Sales and Order Date.

4.  In Field Wells panel, click the dropdown on the Order Date field and
change the aggregation to Year.

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-5-KPI.gif)

## Step 6 -- Add Suggested Insights

1.  With the KPI visual selected, open the Insights panel from left
rail.

2.  Click the + button on the MONTH OVER MONTH CHANGE suggested insight
to add it to the Analysis.

3.  Open the Insights panel again.

4.  Click the + button on the FORECAST suggested insight to add it to
the Analysis.

5.  Resize the insights to be smaller, and move them to the right, just
beneath your KPI visual.

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-6-Insights.gif)

## Step 7

### a -- Visualize Sales by Industry

  1.  Click + Add and then Add visual.
  
  2.  From Visual types panel, change the Visual Type to Donut chart.
  
  3.  From Fields list, select Industry and Sales.

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-7a-Donut.gif)

### b -- Add Drill Down from Industry to Customer

1.  From the Fields list, drag the Customer field just beneath the
Industry field in the Field wells (make sure Field wells panel is
expanded before you drag and drop). You need to drag it inside the
blue box of the Group/Color field well, but just beneath the other
field in there. You should see a message saying Add drill-down
layer.

2.  Now you can click on Industry slices and you will see an option to
Drill down to Customer, and it will show just customers from that
industry. (You can drill back up by clicking on a slice and
choosing the drill up option, or by using the Drill up arrow in
the visual menu)

![Guidelines](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-7b-DrillDown.gif)

## Step 8: Clean and free up all resources used so far

## References

[Visualizing data in AmazonQuickSight](https://docs.aws.amazon.com/quicksight/latest/user/working-with-visuals.html)

[Visual types in AmazonQuickSight](https://docs.aws.amazon.com/quicksight/latest/user/working-with-visual-types.html)

[Visualize Amazon S3 Analytics Data with AmazonQuickSight](https://aws.amazon.com/blogs/big-data/visualize-amazon-s3-analytics-data-with-amazon-quicksight/)
