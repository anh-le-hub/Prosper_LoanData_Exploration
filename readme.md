
# Explore past Loan Data from Prosper.com
## by Anh Le


## Dataset

> This analysis explore Prosper.com data of past Loan Listing. Prosper.com is an US company providing peer-to-peer lending service.

> The data consists attributes of 113937 past loan listings . The attributes included details such as the loan amount, the loan status, the loan rating, the estimated yield, the borrower rating, the borrower income, the borrower's historical performance, percentage of the listing funded, and the number of investors invested.
>> Loan Data from Prosper https://www.google.com/url?q=https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv&sa=D&ust=1554486256021000

>> Prosper Data Dictionary https://www.google.com/url?q=https://docs.google.com/spreadsheet/ccc?key%3D0AllIqIyvWZdadDd5NTlqZ1pBMHlsUjdrOTZHaVBuSlE%26usp%3Dsharing&sa=D&ust=1554486256024000

> Preliminary Data WranlingL
>- Changed the name of few attributes to remove spaces
>- Created new fico_creditscore attribute to organize the credit scores to ranges for easier illustration and communication
>- Converted few attributes such as LoanStatus, ProsperScore, ProsperRating_alpha and fico_creditscore to ordered Categorical variables
>- Subset the Data: a new dataframe subset_loan_df which includes only these 3 Loan Status to avoid the noise that may created by other Loan Status. These loans will be called as concluded Loans.
>- Created a new variable "is_badloan" to identify the status of the loan, with 0 refers to completed loan and 1 refers to bad loan.

## Summary of Findings

> Loans on Prosper.com are more of the consumer market with low Loan Amounts, ranging from \\1K$ to \\$25K. Most of the loans having the amount lower than \\$10K.  

> Prosper.com business model is effective:
>- Prosper Rating is effective in rating the risk of the loans. The success rate (rate of loans get completed) is high across all Prosper Rating, with the lowest is 61.8% for the highest risk Rating.
>-  Prosper.com is doing a good job in setting the Borrower APR. Borrower APR of the bad loans are higher than that of the Good Loans across most of the Prosper Ratings, except for those high risk loan listings with Prosper Rating of D, E and HR, they are about the same.
>- The median of the estimated principle loss of the bad loan is higher than that of the good loans. This suggests that Prosper.com estimation is good and helpful to investors.

> However, the % of bad loans including chargedoff and defaulted are relatively high, about 50% of the completed loans, and the Net principle loss is considerable. Hence, there are still rooms for improvement.
>- For high risk ratings - D, E, HR, the bad Loans have low Amounts, they are <= \\$15K; and the Net principle loss can  be the full principle or almost 0.
>- For the good risk rating - AA and A, the bad loans spread from low to  very high amount (\\$25K). The net principle loss are also high, most of them are close to the principle, only few loss are low
>- For the middle range of risk rating - B and C, the bad loans can be of high amount, but less number of bad loans having amount > \\$15K compared to those of the good ratings.  The principle loss of the large loans are close to the full principle.

>- If I was to invest in any loan on Prosper.com, I'd choose the middle Prosper risk rating B and C, as they have high success rate of 82% & 78% respectively, and come with good Interest rate ( Good interest rate is derived from the fact that the Borrower APR median for these 2 ratings is >= 17%).


## Key Insights for Presentation

> Loans on Prosper.com are more of the consumer market with low Loan Amounts, ranging from \\1K$ to \\$25K. Most of the loans having the amount lower than \\$10K.  

> Prosper.com is effective in rating risk of the loan, setting Borrower APR and estimation of principle loss

> However, there are still rooms for improvement as the % of chargedoff and defaulted loans are relatively high, about 50% of the completed loans, and the Net principle loss is considerable.

>- If I was to invest in any loan on Prosper.com, I'd choose the middle Prosper risk rating B and C, as they have high success rate of 82% & 78% respectively, and come with good Interest rate

### References
> fico_creditscore variable holds the credit score rank based on the scoring boundaries of ranges according to Experian website https://www.experian.com/blogs/ask-experian/credit-education/score-basics/what-is-a-good-credit-score/

### Feedback from others:
>- To include the success rate of the good loans (i..e completed loans) in the plot comparing good and bad loans across different ProsperRating - this makes the plot highlights the main point that I want to convey to readers
