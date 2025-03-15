INSIGHTS

Week-on-Week (WoW) is a type of business metric that measures changes in a specific variable 
over a period of one week compared to the previous week. It is a common way of tracking 
business performance over time and is particularly useful for analyzing trends and identifying 
areas where improvements can be made. 
Here are the metrics for which we found the WoW change% in this video: 
1. Revenue WoW change %: To get the revenue change percentage week over week. 
2. Occupancy WoW change %: To get the occupancy change percentage week over week. 
3. ADR WoW change %: To get the ADR (Average Daily rate) change percentage week over 
week. 
4. RevPAR WoW change %: To get the RevPAR (Revenue Per Available Room) change 
percentage week over week. 
5. Realisation WoW change %: To get the Realisation change percentage week over week. 
6. DSRN WoW change %: To get the DSRN (Daily Sellable Room Nights) change percentage 
week over week. 
Let’s understand WoW change% for Revenue metric as an example: 
Let’s break down this formula: 

Var selv = IF(HASONEFILTER(dim_date[wn]), SELECTEDVALUE(dim_date[wn]),MAX(dim_date[wn])) 
This line creates a variable named selv. It checks if there is only one filter applied to the 
dim_date[wn] column. If there is only one filter, it uses the selected value of that filter; 
otherwise, it uses the maximum value of the dim_date[wn] column.

var revcw = CALCULATE([Revenue],dim_date[wn]= selv) 
This line creates a variable named revcw. It calculates the revenue by applying a filter on the 
dim_date[wn] column, where the value matches the one stored in the selv variable. The 
[Revenue] measure is used for this calculation. 

Var revpw = CALCULATE([Revenue],FILTER(ALL(dim_date),dim_date[wn]= selv-1)) 
This line creates a variable named revpw. It calculates the revenue for the previous week by 
applying a filter on the dim_date[wn] column, where the value is one less than the one stored in 
the selv variable. The FILTER function combined with ALL(dim_date) ensures that the filter is 
applied to all the dates, regardless of other filters that might be active. The [Revenue] measure 
is used for this calculation. 

DIVIDE (revcw, revpw,0)-1 
This line calculates the percentage change in revenue WoW. It uses the DIVIDE function to divide 
the value of revcw (current week revenue) by the value of revpw (previous week revenue), with 
a specified default value of 0 in case the divisor is 0. The resulting quotient is then subtracted by 
1 to calculate the percentage change. 
The entire formula returns the week-over-week percentage change in revenue. This formula can 
be used as a calculated column or a measure in Power BI to display the WoW revenue change in 
a visual or table. 

DASHBOARDING TIPS

1. Color Selection
 Primary and/or secondary colors 
1. Choose from the corporate identity e.g., LOGO 
2. Choose from the industry. Example: For the metal industry choose grey and yellow 
for beauty products choose purple/ red/ pink, for fashion brands dark blue or black, etc.
 3) Choose colors based on the theme of the dashboard or report
 Theme colors 
Determine the colors for the various elements on the dashboard such as page 
background, container background, borders, primary texts, secondary texts, 
highlighting texts, etc. 
2. Font Selection
 Choose the fonts for the identity/industry/subject. 
Size 
Determining the size for the KPI values, title text, value texts, and paragraph texts (in 
case of storytelling reports) in realtion to their importance and intended visibiltiy.
/codebasics
 Key things to consider while designing your 
dashboard
 3. Aspect Ratio
 Never go out of aspect ratios, it will make your static elements/ visuals ugly. 
1. Try to keep canvas size 16:9 ratio (popular ratios 1024×576, 1280×720, 1600×900, 
1920×1080, 2560×1440). In case of custom size keep width either 1024, 1280, 1600, 
1920, or 2560 and keep Height/ Length as required to accommodate all visuals
 2. Strictly keep Images & LOGOs in their aspect ratio
 3. Try to keep other elements’ size in multiple of 8 or if needed in a few cases in 
multiples of 4.
 4.  Positioning
 1. Try to place the elements at the positions (Horizontal / Vertical) in a multiple 
of 8 and f need than a multiple of 4
 2. Maintain proper distances (in most cases equal) from left and right to each 
other - not too congested or not too open
