# Early-Marriages
Analysis of Early Marriage in Kakuma
This project examines data on early marriage in Kakuma refugee camp, focusing on access to counseling and support services for girls. The analysis is conducted using both Excel and R, providing flexibility for data manipulation, exploration, and visualization.

Files Included
EARLY_MARRIAGE_CLEAN_DATA.xlsx: The dataset containing survey responses, used for analysis in both Excel and R.
analysis_script.R: The R script for deeper statistical analysis and visualization.
README.md: This file, providing an overview of the project.
Tools and Software Needed
Excel
Microsoft Excel (2013 or later)
For manual exploration, filtering, and basic calculations.
Pivot tables and conditional formatting can be used to explore data patterns.
R
R (version 4.0 or higher)
RStudio (optional but recommended)
R libraries: readxl, dplyr, ggplot2
Workflow
Initial Data Exploration in Excel:

Open EARLY_MARRIAGE_CLEAN_DATA.xlsx in Excel.
Use pivot tables to calculate percentages (e.g., percentage of "Yes" and "No" responses).
Apply conditional formatting to identify trends or patterns visually.
Advanced Analysis in R:

Open analysis_script.R in RStudio.
Run the script to perform in-depth statistical analysis and create visualizations.
Steps in the script include importing the Excel file, summarizing key variables, exploring relationships, and plotting results.
Key R Analysis Steps
Load Dataset: Use the readxl package to import the Excel data into R.
Calculate Percentages: Summarize responses using the dplyr package.
Explore Relationships: Filter and analyze correlations between variables like counseling access and education challenges.
Visualization: Generate bar plots and other visuals using the ggplot2 package.
Example R Code
R
Copy code
# Load necessary libraries
library(readxl)
library(dplyr)
library(ggplot2)

# Load dataset from Excel
data <- read_excel("EARLY_MARRIAGE_CLEAN_DATA.xlsx", sheet = "Sheet1")

# Summarize counseling responses
counseling_summary <- data %>%
  count(`Do refugee girls in Kakuma have access to counseling or support services to prevent early marriage?`) %>%
  mutate(Percentage = n / sum(n) * 100)

# Plot counseling response percentages
ggplot(counseling_summary, aes(x = `Do refugee girls in Kakuma have access to counseling or support services to prevent early marriage?`, y = Percentage, fill = `Do refugee girls in Kakuma have access to counseling or support services to prevent early marriage?`)) +
  geom_bar(stat = "identity") +
  labs(title = "Access to Counseling Services in Kakuma", x = "Response", y = "Percentage") +
  theme_minimal()
Example Output
Excel: Summary tables with percentages and trends.
R: Detailed analysis of variables and bar plots showing response distributions.
Contact
For questions or assistance, please contact [Your Name or Email].
