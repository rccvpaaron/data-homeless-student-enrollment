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
1. After failing to successfully add all .txt files to Google Sheets on account of their size, I added all the .txt files into individual sheets of an Excel book.
2. I filtered each sheet by the following columns to limit the data to Schools in Riverside Unified School District:
- District Name = Riverside Unified
- Aggregate Level = S
3. After failing to successfully use a VSTACK formula for the first time, I copied the filtered data from each sheet and stacked them in a new sheet manually and named it "Riverside Unified".
4. I saved this new file locally as "RUSD HSE data 19-25.xlsx"
5. I uploaded ["RUSD HSE data 19-25.xlsx"](https://docs.google.com/spreadsheets/d/16R-V5unq1OjSRNofp31RPYhJdsBTVHfs/edit?usp=sharing&ouid=103174665380155667131&rtpof=true&sd=true) to Google Sheets.
6. I converted ["RUSD HSE data 19-25.xlsx"](https://docs.google.com/spreadsheets/d/16R-V5unq1OjSRNofp31RPYhJdsBTVHfs/edit?usp=sharing&ouid=103174665380155667131&rtpof=true&sd=true) to a [Google Sheet](https://docs.google.com/spreadsheets/d/1rBlyNReUlVHquiVsW_emQ6S33g8Do95JwqubdK91Aco/edit?usp=sharing).

## 03. Analyzing the Data
1. I created a pivot chart named "SUM of HSE" with the following steps:
- Added Row: "Academic Year"
  * All selected
  * "Show totals" box checked
- Added Values: Homeless Student Enrollment
  * Summarize by: SUM
  * Show as: Default
- Added Filter: "Charter School" and selected "No"

## 04. Creating the Datawrapper Charts
