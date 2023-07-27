# AWS QuickSight: Utilities for Business Intelligence

## Objectives

-   Enhance data presentation with a formatted Pivot Table.
-   Enable interactive data exploration with Filter Control and Action.
-   Improve dashboard usability with Dashboard Title and renamed Visual Titles.
-   Streamline reporting through Email Reports and easy access.

## Lab Setup

<center>
<div style="text-align: center;">
  
  | Time of performing | Required AWS services |
  |--------------------|--------------------|
  | 15 minutes         | S3, QuickSight|
</div>
</center>

## Steps

1.  
    a - Create a Pivot Table  
    b - Format the Pivot Table
2. Add a Filter Control
3. Add a Filter Action
4. Add a Dashboard Title
5. Rename Visual Titles
6. Publish a Dashboard
7.  
    a - Send an Email Report
    b - Open the Email Report

## Step 1
### a - Create a Pivot Table
1.  Click + Add and then Add visual.
2.  From Visual types panel, change the Visual Type to Pivot table.
3.  From the Fields list, select Region, Sales and Subregion.
4.  From the Fields list, drag Order Date to the Columns field well.
5.  Change the Aggregate setting of the Order Date to Year.
6.  Click the Region header and choose Collapse. Notice how you can use this to collapse an entire column. You can also expand/collapse individual grouping in the visual.

![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-7a-Donut.gif)

### b - Format the Pivot Table
1.  On the Pivot Table, click the Format visual pencil icon in the visual menu to open Format Visual panel.
2.  Expand the Pivot options section.
3.  Check the Hide single metric box. This will remove the repetitive Sales headers on each column.
4.  Expand the Subtotal section.
5.  Check the Show subtotals box under Rows.
6.  Click the Background icon and pick a color to use for subtotal rows.
7.  Scroll down and check the Apply styling to cells box to have the color applied to entire row.
8.  Close the Format visual panel.

![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-8b-Formatting.gif)

## Step 2 - Add a Filter Control
1.  With  **Pivot chart**  selected, open the  **Filter**  panel from  **left rail**.
2.  Click  **ADD FILTER**  button.
3.  Search for and select the  **Segment**  field.
4.  Click on the newly added  **Segment**  filter to expand it.
5.  Click  **Applied to**  dropdown, change the filter scope from  **Only this visual**  to  **All applicable visuals**.
6.  Click the  **ellipsis**  icon to open the filter menu and choose  **Add to sheet**.
7.  Move the  **filter control**  from the bottom of your analysis to the top right corner and adjust the width.
8.  Resize the other visuals so they fit nicely.
9.  Try changing the selection in filter control and see all visuals react accordingly. Then, set it back to  **Select all**  mode.

![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-9-Filter.gif)

## Step 3- Add a Filter Action

1.  With  **Donut chart**  selected, open  **Actions**  panel from  **left rail**.
2.  Click the  **Filter same-sheet visuals**  button. This is a shortcut to create a Filter Action which will filter all other visuals on the dashboard using all the dimensions used in this visual.
3.  Select a  **slice**  in the  **Donut chart**  and see how all other charts on the dashboard filter just to that Industry.  
    To deselect you can click the same slice again, or click in the empty space just inside or outside of the donut.
4.  Note the drill down we built before is now accessible via a right-click rather than a left-click.

![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-10-FilterAction.gif)

## Step 4 - Add a Dashboard Title

1.  Click  **+ Add**  and then  **Add title**.
2.  Click in the title box and type / paste  `Sales Overview Dashboard`. Click outside title box or use enter/return key to exit title edit mode.

![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-11-Title.gif)

## Step 5 - Rename Visual Titles

1.  Open  **Line chart**'s  **Format visual**  panel (hint - pencil icon) and click  **Edit title**  button. Type / paste in  `Monthly Trend and Forecast` and click  **Save**  button.
1.  Double click on the  **title**  of the  **KPI**  to open title editor, type / paste in  `YoY Sales` and  **Save**  it.
1.  Rename the  **Donut chart**  to  `Sales by Industry`. Then click the  **Edit subtitle**  button in  **Format Visual**  panel, type / paste in  `Click to filter dashboard, right-click to drill down to Customer` and  **Save**  it.
1.  Rename the  **Pivot Table**  to  `Regional Details`.
1.  Close  **Format Visual**  panel. Note that the  **pencil**  icon in  **visual menu**  can be clicked again to close the panel.

![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-12-VisualTitles.gif)

## Step 6 - Publish a Dashboard

1.  From top right of your screen, click  **Share**  and then  **Publish dashboard**.
2.  Name it  `Sales Overview`.
3.  Click  **Publish dashboard**. This will publish your dashboard and launch it in your current browser window.
4.  You have created your first dashboard! Notice the interactivity we added using the filter control, filter action, and drill down are all available on the dashboard and can be used by anyone you share this with.

![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-13-Publish.gif)

## Step 7 
### a - Send an Email Report

1.  While still on the dashboard, click  **Scheduling**  (Clock) from  **top rail**  and then  **Schedules**.
2.  Click  **ADD SCHEDULE**  button in  **Schedules**  panel.
3.  Enter the  **Schedule name**  as  `Test Schedule`
    or one of your choice.  
     - Note - In the  **Content**  section, note that sheet1 has been pre-selected — all the visible content from this sheet will be available in the PDF.  
    
    The  **Dates / Send On**  section let's you set a schedule frequency.
4.  In the  **Email**  section, select the  **File attachment**  option.
5.  Click  **SEND TEST**  button. This will trigger a one time test report mail out.  
    - Note - *It is okay if you clicked the Save button. You can delete it by clicking the ellipsis against it and then the Delete option.  
    If you are using a temp account provided by AWS, ensure that you don't leave a saved schedule in here to avoid getting scheduled emails while the account is in queue for recycling.*

  ![enter image description here](https://static.us-east-1.prod.workshops.aws/public/8215b450-c9d4-46ed-9185-f4975a8ad884/static/Author%20Workshop/1.Build%20Your%20First%20Dashboard/Exercises/NL-14a-Email.gif)

### b - Open the Email Report

1.  It may take a few minutes to receive the email, but open it once it arrives and you will see a screenshot of the dashboard in the email body, along with a PDF attachment of the dashboard.
2.  Click  **View dashboard**  to open it directly in your web browser.

## Step 8 - Clean and free up all resources used so far

## References

[Visualizing data in AmazonQuickSight](https://docs.aws.amazon.com/quicksight/latest/user/working-with-visuals.html)

[Visual types in AmazonQuickSight](https://docs.aws.amazon.com/quicksight/latest/user/working-with-visual-types.html)

[Visualize Amazon S3 Analytics Data with AmazonQuickSight](https://aws.amazon.com/blogs/big-data/visualize-amazon-s3-analytics-data-with-amazon-quicksight/)
