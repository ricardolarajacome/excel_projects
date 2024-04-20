# Acquisitions Model Analysis for West Ridge North

Streit, a Real Estate Investment Trust (REIT), is considering the acquisition of West Ridge North, a run-down apartment complex located in Downtown Detroit. Streit sees the potential to revitalize the property and transform it into a premier residential destination in the area. Before proceeding with the purchase, Streit must conduct a thorough financial analysis to assess the investment's viability.

### 1. Financial Review:

The seller, Shady Tree Management, has provided an income statement for the last year. As part of the acquisitions model, we need to calculate the subtotals and net income in the Last Year column using the SUM() function.

- **Rental Income:** This represents the total potential rent collected from tenants. In real estate, it's common to present the total potential rent of the property and subtract any uncollected rent due to non-payments or vacancies.

- **Net Operating Income (NOI):** NOI is the income remaining after covering all expenses associated with the day-to-day operations of the business.

<img width="638" alt="Screenshot 2024-04-20 at 2 52 27 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/1e9beb4d-851c-4142-aad1-15e9f319e0a0">


Based on the provided information, the net income of West Ridge North for the last year amounts to $416,139.

### 2. Property Valuation:

Real estate investors often employ the capitalization rate (cap rate) as a key metric to gauge the profitability of their investments. The cap rate is calculated by dividing the Net Operating Income (NOI) by the Property Value. Streit has set a target cap rate of 6.00% for its investments.

To estimate the value of West Ridge North, we utilized the formula:

\[ \text{Property Value} = \frac{\text{Net Operating Income}}{\text{Cap Rate}} \]

In order to facilitate ease of reference and consistency in our financial model, we established a named range for Streit's target cap rate, set at 6.00%.

The purchase price of West Ridge North, calculated in cell F2, incorporates the AcquisitionCapRate named range along with the net operating income from our previous analysis. It's crucial to note that we use net operating income, not net income, in this calculation.

In our financial model, Year 0 denotes the acquisition phase, during which only acquisition costs are accounted for, with no additional income or expenses incurred.

<img width="919" alt="Screenshot 2024-04-20 at 3 11 47 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/ef39e383-14a4-4e4d-b10a-025a072bbe48">


Based on our calculations, the purchase price of West Ridge North, with a cap rate of 6.00%, amounts to approximately $7,288,683. Since this outlay represents an expense, it is formatted as a negative value.

Despite the substantial initial investment of $7.3 million, the acquisition of West Ridge North aligns with Streit's objective of achieving a 6% capitalized return, thereby positioning it as a financially sound investment opportunity.

<img width="254" alt="Screenshot 2024-04-20 at 3 15 19 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/99c60a1e-d564-4f2e-ac7e-6698f95f6114">

In conclusion, it seems the acquisition of West Ridge North presents Streit with an opportunity to leverage its expertise and resources to revitalize the property and capitalize on the burgeoning real estate market in Downtown Detroit. Although we can continue improving the analysis by adding some key metrics such as Net Present Value and Internal Rate of Return.

**3. Forecasting Rental Income**

Financial models are crucial for analyzing investments over time, relying on assumptions to estimate future revenue and expenses. Growth rates are often employed to project increases in revenue and expenses. Using the formula `[Previous Value] * (1 + [Rate])`, we can determine the future value of an item with a growth rate.

To enhance usability, we've formatted the worksheet for clarity. I've created a custom number formatting for the periods in cells D16:N16 to display "Year " before the numbers.

Streit plans to remodel all units in the first year and anticipates renting units starting in Year 2 at $2,300 per month. Rent is expected to increase annually according to the Rent Growth % assumption.

To forecast rental income for the next 10 years I have entered $2300 in cell F19 to specify rental income for Year 2. Then I have used the formula in cell G19 to forecast rental income: `[Previous Value] * (1 + [Rent Growth %])`, ensuring to lock the cell reference to Rent Growth %. And finally I have dragged this formula to N19 to complete the analysis up to Year 10.

Now, I calculate the net potential rent for each year, representing the total potential rent earned by the entire property annually. Net potential rent is obtained by multiplying the monthly rent (cell F19) by the Units named range and then by 12 to convert to an annual figure. This calculation is dragged across to N18 for analysis up to Year 10.

<img width="1183" alt="Screenshot 2024-04-20 at 3 27 11 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/01b84478-f69a-471c-b56e-ec75c30c033f">

The estimated Net Potential Rent in Year 10 is $3,262,222, indicating significant growth over the 10-year period, thanks to the planned renovations and rent increases.

**4. Predicting Sales Price**

Real estate investors often aim to sell properties within 5-10 years to generate cash for further investments and portfolio diversification. To analyze the predicted sales price of West Ridge North during any year of our analysis, I've used the cap rate formula: `[Property Value] = [Net Operating Income] / [Cap Rate]`.

By utilizing HLOOKUP() to dynamically lookup the net operating income for the specified holding period (Years), we determine that Year 10 yields the highest sales price due to substantial renovations and rent growth, making it an attractive asset for potential buyers.

<img width="745" alt="Screenshot 2024-04-20 at 3 29 34 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/7c94fc15-88bb-4fa0-88b0-ab0571bf7d57">

**5. Scenario Analysis**

In case Streit's seeks to explore various outcomes I have used the Scenario Manager tool in Excel. By comparing scenarios, I can assess the net operating income for Year 10 across different assumptions, providing valuable insights for decision-making.

<img width="894" alt="Screenshot 2024-04-19 at 10 23 46 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/d64254ff-1ed7-444e-901b-2319e2bfb356">

Upon reviewing the scenarios, the difference between the Expected Rent and High Rent scenarios for Year 10 is $717,739.

**6. Goal Seek Analysis**

Goal Seek enables us to determine the Exit Cap Rate required for the Sell Price to reach $100M. After running Goal Seek, we find that an Exit Cap Rate of 5.00% is needed for the Sell Price to be $100M.

<img width="239" alt="Screenshot 2024-04-20 at 3 35 32 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/46439cef-71a6-42a3-8848-5e63b07bfaa0">


**7. Sensitivity Analysis**

A sensitivity analysis on Rent Growth % reveals the impact on net operating income. At a 5.00% rent growth rate, net operating income is $2,954,983, while at a 10.00% rate, it increases to $4,519,938.

<img width="563" alt="Screenshot 2024-04-20 at 3 37 26 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/236e05c4-c62c-4a74-ac00-1f161a26660c">

**8. Return on Investment (ROI)**

We calculate the ROI for West Ridge North, finding it to be 857.61%. 

<img width="455" alt="Screenshot 2024-04-20 at 3 39 16 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/729461d0-48c2-4557-affa-594eac452275">

Although impressive, this ROI reflects a long-term investment over 10 years.

**9. Benchmark Analysis**

Using benchmarks such as future value and present value, we assess the investment's performance. West Ridge North exceeds the future value benchmark, indicating a successful investment. Additionally, the present value of the investment, based on a 20.00% benchmark rate, is $11,365,424, demonstrating the project's viability compared to alternative investment opportunities.

<img width="458" alt="Screenshot 2024-04-20 at 3 40 26 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/7df7a695-c963-4373-83d6-1dd498f3555f">


**10. Net Present Value Analysis**

In order to determine the net present value (NPV) of the total net income earned over the lifetime of West Ridge North. NPV() function simplifies this calculation. On a separate sheet we can proceed with our calculations:

<img width="1436" alt="Screenshot 2024-04-20 at 2 42 57 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/2557f88e-1b91-42a9-ab52-ce7a55f9ad40">
 
Finally using the formula: =NPV(J5,E53:N53)+D53 We can see that the NPV for West Ridge North is approximately $7.4M. Since this value is greater than 0, West Ridge North would be a preferable investment compared to another investment with a 20% return.

<img width="1311" alt="Screenshot 2024-04-20 at 3 44 06 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/b23301ce-5ff0-4a34-8a17-af2618cca02b">

However, we encountered a limitation with NPV(), as it assumed cash flows started in Year 1 rather than Year 0. To address this issue, we utilized XNPV() in the formula =XNPV(J5,D53:N53,D15:N15). This is a more precise function that considers the timing of cash flows based on dates.

<img width="554" alt="Screenshot 2024-04-20 at 3 45 51 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/9381abbd-4d98-4a4e-a9d8-fbe897bf2f1b">

The XNPV of the Net Income cash flows is calculated to be $7,372,047, providing a more accurate representation of the project's profitability.

**11. Internal Rate of Return (IRR) Analysis**

The internal rate of return (IRR) is a crucial metric to assess the project's profitability, representing the discount rate that makes the net present value zero.

With the standard IRR calculation, we find the IRR to be 29.78%. However, since we have dates associated with each cash flow, XIRR() would provide a more precise result.

<img width="1240" alt="Screenshot 2024-04-20 at 2 00 34 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/c2ed8c1b-0a5f-4fda-ae75-bea46b4571bf">

The IRR using XIRR() is 29.75%, indicating an annual rate of return of 29.75%. To further analyze the project's viability, we set the benchmark rate equal to the IRR.

<img width="578" alt="Screenshot 2024-04-20 at 3 48 03 PM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/c5b00ac7-9984-465b-910b-cdf0e2d96775">

Updating the benchmark rate in cell J5 to match the XIRR, we find that the value of XNPV in J10 is 0. This aligns with expectations, as the discount rate in NPV often represents the project's cost. If the project cost equals the return, there would be no real financial gain. In conclusion, while the investment initially appeared promising, the analysis reveals it to be a project devoid of significant financial gain

<img width="848" alt="Screenshot 2024-04-20 at 2 05 37 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/01c79db0-0398-4045-92ab-f6aad7b0c96b">



