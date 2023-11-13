# pandas-challenge

# Written Report: School Performance Analysis

Summary of Analysis:

The analysis was conducted on school performance based on various factors such as spending per student, school size, and school type. The dataset utilized includes information on average math and reading scores, as well as the percentage of students passing math, reading, and both subjects.

# Findings:

Impact of Spending per Student:

The analysis categorized schools based on their per-student spending into four ranges: <$585, $585-630, $630-645, and $645-680. The results indicate that schools with a lower per-student budget tend to perform better in terms of overall passing rates. Specifically, schools in the <$585 spending range exhibited higher overall passing rates compared to schools in higher spending ranges. This suggests that allocating more resources per student does not necessarily correlate with improved academic performance.

Effect of School Size:

The schools were categorized by size into three groups: small (<1000 students), medium (1000-2000 students), and large (2000-5000 students). The analysis reveals that smaller and medium-sized schools tend to outperform larger ones in terms of overall passing rates. This could be attributed to the potential for more personalized attention and focused resources in smaller school environments.

# Conclusions:

Spending Impact:

Contrary to common assumptions, a higher per-student spending does not guarantee better academic outcomes. Schools with lower budgets can achieve comparable or even superior performance by efficiently utilizing available resources.

School Size Matters:

Smaller and medium-sized schools demonstrate a consistent trend of better academic performance than larger schools. This implies that factors such as more personalized learning experiences and closer teacher-student relationships could contribute to higher success rates.

In conclusion, the analysis provides valuable insights into the relationships between school performance and spending, as well as the size of educational institutions. Policymakers and educators can use these findings to make informed decisions and allocate resources more effectively for improved academic outcomes.

# Note-Got an error while calculating the - school_spending_df 

Error -ValueError: Unable to parse string "$628.00" at position 0

Issue-the "Per Student Budget" column still contains string values with a dollar sign and possibly other non-numeric characters.
To overcome this problem - we need to remove these non-numeric characters and convert the column to a numeric type.
This solution works-school_spending_df["Per Student Budget"] = (
    school_spending_df["Per Student Budget"]
    .replace('[\$,]', '', regex=True)
    .astype(float)
)