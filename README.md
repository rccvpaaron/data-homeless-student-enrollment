# Homeless Student Enrollment
I collected data on students experiencing homelessness in Riverside Unified School District in Riverside County, California.

## 01. Getting the Data
  - California Department of Education has an open data portal at https://www.cde.ca.gov/ds/.
  - The open data portal has a list of downloadable data files at https://www.cde.ca.gov/ds/ad/downloadabledata.asp.
  - Looking through the list, I found the Homeless Children and Youth heading, leading to the Homeless Student Enrollment (HSE) page.
  - I downloaded the text files on the HSE page at https://www.cde.ca.gov/ds/ad/fileshse.asp for the following school years:
    * 2019-2020 [hse1920.txt](hse1920.txt)
    * 2020-2021 [hse2021.txt](hse2021.txt)
    * 2021-2022 [hse2122.txt](hse2122.txt)
    * 2022-2023 [hse2223.txt](hse2223.txt)
    * 2023-2024 [hse2324.txt](hse2324.txt)
    * 2024-2025 [hse2425.txt](hse2425.txt)
  - The files can be found in the [Data](https://github.com/rccvpaaron/data-homeless-student-enrollment/tree/main/Data) folder.

## 02. Cleaning the Data
1. After failing to successfully add all .txt files to Google Sheets on account of their size, I added all the .txt files into individual sheets of an Excel book saved locally as "Homeless Enrollment Data.xlsx".
- "Homeless Enrollment Data.xlsx" is over the 25MB limit for Github upload.
3. I filtered each sheet by the following columns to limit the data to Schools in Riverside Unified School District:
- District Name = Riverside Unified
- Aggregate Level = S
3. Row 186, Column H in the 2021-2022 data set had a typo. Changed "REACH Leadership STEM Academy" to "REACH Leadership STEAM Academy".
4. After failing to successfully use a VSTACK formula for the first time, I copied the filtered data from each sheet and stacked them in a new sheet manually and named it "Riverside Unified".
5. I saved this new file locally as "RUSD HSE data 19-25.xlsx"
6. I uploaded ["RUSD HSE data 19-25.xlsx"](https://docs.google.com/spreadsheets/d/16R-V5unq1OjSRNofp31RPYhJdsBTVHfs/edit?usp=sharing&ouid=&rtpof=true&sd=true) to Google Sheets.
7. I converted ["RUSD HSE data 19-25.xlsx"](https://docs.google.com/spreadsheets/d/16R-V5unq1OjSRNofp31RPYhJdsBTVHfs/edit?usp=sharing&ouid=103174665380155667131&rtpof=true&sd=true) to a [Google Sheet](https://docs.google.com/spreadsheets/d/1rBlyNReUlVHquiVsW_emQ6S33g8Do95JwqubdK91Aco/edit?usp=sharing).

## 03. Analyzing the Data
1. I created a pivot chart from "Riverside Unified" named "SUM of HSE" with the following steps:
- Added Row: "Academic Year"
  * All selected
  * "Show totals" box checked
- Added Values: Homeless Student Enrollment
  * Summarize by: SUM
  * Show as: Default
- Added Filter: "Charter School" and selected "No"
2. I added the following columns to "Riverside Unified":
- "School Category" -- in new column (I) with the purpose of aggregating data by category of school
  * C = Continuation School
  * E = Elementary School
  * H = High School
  * M = Middle School
  * A = Alternative School
- "Share HSE" -- in new column (O) with the purpose of calculating the share of Homeless Enrollment (Column N)  in Cumulative Enrollment (Column M)
  * Formula: =N2/M2
  * Format: as percent
    + Decreased decimal point to tenths

## 04. Creating the Datawrapper Charts
### Number of K-12 students experiencing homelessness in RUSD, 2019-2025
1. Upload Data
- Copied the data table from SUM of HSE pivot chart
- Pasted the data table from SUM of HSE pivot chart
2. Check & Describe
- No changes
- "First row as label" box selected
3. Visualize
- Chart Type: Lines
- Refine:
  * Horizontal axis
    + Select column: Academic Year
    + Grid: off
  * Vertical axis
    + Scale type: Linear
    + Custom range: min - 3000
    + Number format: (automatic)
    + Grid: Lines
    + Labels: Auto, Left
  * Customize Line
    + Color: #18a1cd
    + Interpolation: Linear
    + Width: 2 pixels
    + Dash: Solid
    + Label: None
    + Show Line Symbols: Circle, first & last, Filled, Size=3.5, Opacity=1
  * Tooltips
    + Show tooltips on hover
    + Values format: Same as vertical axis
  * Appearance
    + Plot height: Fixed
    + 300px
- Annotate:
  * Title: Number of K-12 students experiencing homelessness in RUSD, 2019-2025
  * Description: Homelessness is described as living Temporarily Doubled Up, Temporarily Unsheltered, in&nbsp;<br>Temporary Shelters, Hotels/Motels and Unknown.
  * Notes: Data includes all Riverside Unified School District non-charter schools.
  * Data Source: California Department of Education
  * Link to data source: https://www.cde.ca.gov/ds/ad/fileshse.asp
  * Byline: Aaron Friesen
  * Alternative description for screen readers: A line chart showing the number of K-12 students experiencing homelessness in RUSD, 2019-2025. It rose from 1,144 students in 2019-2020 to 2,486 students in 2024-2025.
- Layout:
  *  Output locale: English (en-US)
  *  Layout
    + Theme: Datawrapper
  * Footer
    + Data download: on
    + Image download options: off
    + Embed link: off
    + Datawrapper attribution: on
  * Share buttons
    + Social media share buttons: off
    
### Percent of K-12 students experiencing homelessness by school in RUSD, 2019-2025
#### Version 1
1. Upload Data
- Copied the data table from SHARE of HSE pivot chart
- Pasted the data table from SHARE of HSE pivot chart
2. Check & Describe
- Transposed rows and columns
- "First row as label" box selected
3. Visualize
- Chart Type: Lines
- Refine:
  * Horizontal axis
    + Select column: School Name
    + Grid: off
  * Vertical axis
    + Scale type: Linear
    + Custom range: min - 18
    + Number format: 0.0%
    + Grid: Off
    + Labels: Off
  * Lines
    + Base color: #18a1cd
    + Interpolation: Linear
    + Show value labels: same as vertical axis; line ends=first, last; labels per line=0; use line color=yes; show line symbols=no
  * Customize Line: Longfellow Elementary
    + Color: #18a1cd
    + Interpolation: Linear
    + Width: 2 pixels
    + Dash: Solid
    + Label: As legend
    + Show value labels: same as vertical axis; line ends=first, last
    + Show Line Symbols: no
  * Customize Line: Mark Twain Elementary
    + Color: #09bb9f
    + Interpolation: Linear
    + Width: 2 pixels
    + Dash: Solid
    + Label: As legend
    + Show value labels: same as vertical axis; line ends=first, last
    + Show Line Symbols: no
  * Customize Line: REACH Leadership STEAM Academy
    + Width: Hidden
    + Note: This is a charter school I missed in data cleaning.
  * Customize Line: Remainder of Schools
    + Color: #e0e0e0
    + Interpolation: Linear
    + Width: 2 pixels
    + Dash: Dotted
    + Label: no
    + Show value labels: no
    + Show Line Symbols: no
  * Tooltips
    + Show tooltips on hover
    + Values format: Same as vertical axis
  * Appearance
    + Plot height: Fixed
    + 300px
    + Label margin: 0px
- Annotate:
  * Title: Number of K-12 students experiencing homelessness in RUSD, 2019-2025
  * Description: Homelessness is described as living Temporarily Doubled Up, Temporarily Unsheltered, in&nbsp;<br>Temporary Shelters, Hotels/Motels and Unknown.
  * Notes: Data includes all Riverside Unified School District non-charter schools.
  * Data Source: California Department of Education
  * Link to data source: https://www.cde.ca.gov/ds/ad/fileshse.asp
  * Byline: Aaron Friesen
  * Alternative description for screen readers: 
- Layout:
  *  Output locale: English (en-US)
  *  Layout
    + Theme: Datawrapper
  * Footer
    + Data download: on
    + Image download options: off
    + Embed link: off
    + Datawrapper attribution: on
  * Share buttons
    + Social media share buttons: off    
#### Version 2
- Added Description 
#### Version 3
- Removed line highlight formatting from Mark Twain Elementary 
- Added line base formatting to Mark Twain Elementary
- Added line highlight formatting to Lake Matthews Elementary
