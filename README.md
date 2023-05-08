Download Link: https://assignmentchef.com/product/solved-sdgb-7844-hw-2-townsend-material-deprivation-index
<br>
Submit two files through Blackboard: (a) .Rmd R Markdown file with answers and code and (b) Word document of knitted R Markdown file. Your file should be named as follows: “HW1-[Full Name]-[Class Time]” and include those details in the body of your file.

Please submit your solutions only once! Complete your work individually and comment your code for full credit. For an example of how to format your homework see the files related to the Lecture 1 Exercises and the RMarkdown examples on Blackboard.

Deprivation indices are used to measure levels of deprivation in populations which go beyond simply measuring income (as in poverty measures). Initially developed in the UK, the most common are the Townsend, Carstairs, Jarman, and the Index of Multiple Deprivation. These indices have been shown to be good proxies for indicating health-related problems in local communities<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>.

<u>Goal: </u>In this assignment, you will compute the Townsend Material Deprivation Index for census tracts in New York County (i.e., Manhattan) using American Community Survey (ACS) data (administered by the U.S. Census Bureau).

The Townsend index is constructed from four variables: % unemployment among people 16 and over (unemp), % of overcrowded households defined as homes with more than one person per room (oc), % of housing which is rented (rent), and % of households without a vehicle (car). A higher percentage of any of these variables indicates more deprivation in a geographic area (<u>Note: </u>you should <u>not </u>convert the percentage variables into decimal form). Let geographic region be denoted by the subscript <em>i </em>and variable by <em>j</em>. To compute the index, follow the four steps described next.

1

<ul>

 <li>transform the variables to reduce skewness (note: log is natural log):</li>

 <li>compute geographic region mean <em>t<sub>j </sub></em>and standard deviation <em>s<sub>j </sub></em>for each variable <em>j</em>.</li>

 <li>standardize variables for each region <em>i </em>and variable</li>

 <li>compute sum of standardized variables for each region</li>

</ul>

You will have one Townsend index value for each region <em>i</em>. These values are on a relative scale; that is, the actual number is meaningless, just the ranking is important. A negative score indicates a <u>less </u>deprived region; a score of 0 indicates roughly the average level of deprivation; a positive score indicates a <u>more </u>deprived region.

<ol>

 <li>What is a census tract? How many census tracts are in New York County? (Provide the citations for references used.)</li>

 <li>Describe one advantage and one disadvantage of computing estimates after combining 5-years of data.</li>

 <li>Download the ACS data for 5-year estimates spanning from 2011-2015. (This means 2015 5-year estimates, not a combination of 1-year estimates for 2011, 1-year estimates for 2012, etc.) for for all New York County census tracts for the following variables using American FactFinder <a href="http://factfinder.census.gov/faces/nav/jsf/pages/index.xhtml">(</a><a href="http://factfinder.census.gov/faces/nav/jsf/pages/index.xhtml">link</a><a href="http://factfinder.census.gov/faces/nav/jsf/pages/index.xhtml">;</a> further instructions can be found on Blackboard in the file “Downloading Map and ACS Data”). Table DP03 contains selected economic characteristics and Table DP04 includes selected housing characteristics. Each row in the table represents a single census tract in New York County.

  <ul>

   <li>unemployment: Table DP03, variable HC03 VC07</li>

   <li>housing tenure (whether house is rented or owned): Table DP04, variable HC03 VC66</li>

   <li>no vehicles: Table DP04, variable HC03 VC85</li>

   <li>low occupancy: Table DP04, variable HC03 VC113 (<strong>You will have to transform this variable to get % overcrowded to use in the index</strong>)</li>

  </ul></li>

</ol>

Clean the data and merge the tables into one data frame, each row representing a census tract, each column representing one of the Townsend variables (keep the geography columns).

Page 2 of 3

For each variable, construct a histogram and compute the following summary statistics: mean, median, standard deviation, maximum, and minimum. Describe the shape of each histogram.

<ol start="4">

 <li>How many observations are missing for each variable? What percentage of census tracts do not have complete data? Is this a problem for our analysis? Justify your answer. (Note: do not delete tracts with missing data.)</li>

 <li>Construct scatterplots of the four variables. Are they linearly related? Now, transform the variables as given in step (a), adding the transformed variables to your data frame. Make another scatter plot matrix with the transformed variables. Are they linearly related? Construct a correlation matrix of the transformed variables and describe your results.</li>

 <li>Compute the Townsend index value for each census tract. Add the index to your data frame. For how many census tracts are you able to compute the Townsend index? Why does this number not equal the total number of census tracts?</li>

 <li>Identify which census tract is the most deprived and which is the least deprived (give the census tract number and deprivation index level). Based on your results, would you like to live in the least deprived census tract? Justify your answer.</li>

 <li>The ACS data includes not only estimates but their margins of error which we ignored in our calculations. What are the implications?</li>

 <li>Construct a map color-coded by the deprivation index value quintile. Each quintile (i.e., 20%) should be assigned a different color from least to most deprived. Download the shape files for New York state census tracts for 2015 from the U.S. Census Bureau website <a href="https://www.census.gov/cgi-bin/geo/shapefiles2013/main">(</a><a href="https://www.census.gov/cgi-bin/geo/shapefiles2013/main">link</a><a href="https://www.census.gov/cgi-bin/geo/shapefiles2013/main">;</a> further instructions can be found on Blackboard in the file “Downloading Map and ACS Data”). Extract the tracts for New York County only. Include a legend and plot title. Describe the patterns you see, especially in relation to what you know about neighborhoods in New York City. What does the large rectangle in the middle of the map represent?</li>

 <li>In which census tract is 140 W. 62nd St. (where we have class)? What is the deprivation level rank (where a rank of 1 is the most deprived)? Mark it on the map (use the computer, not by hand) and add it to your legend. (Provides citations for references.)</li>

 <li>New York County is an urban county, however New York state has roughly 22 counties classified as rural (e.g., Allegany, Essex, Otsego, Sullivan). Would it make sense to compute the Townsend index values for all census tracts within New York state combined? Why or why not?</li>

</ol>

Page 3 of 3

<a href="#_ftnref1" name="_ftn1">[1]</a> For more information: (a) Townsend, P., Phillimore, and P., Beattie, A. (1988). <em>Health and deprivation: inequalities and the north. </em>Croom Helm, London. (b) Carstairs, V. and Morris, R. (1991). <em>Deprivation and health in Scotland</em>. Aberdeen University Press, Aberdeen. (c) Jarman, B. (1983). Identification of underprivileged areas. <em>BMJ </em><strong>286 </strong>1705-1709. (d) Jordon, H., Roderick, P., and Martin, D. (2004). The index of multiple deprivation 2000 and accessibility effects on health. <em>Journal of Epidemiology and Community Health</em>. <strong>58 </strong>250-257.