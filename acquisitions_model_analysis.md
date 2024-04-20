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

<img width="591" alt="Screenshot 2024-04-20 at 3 06 49 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/5eb450a5-0e9c-4577-8cec-bb0794031932">

To estimate the value of West Ridge North, we utilized the formula:

\[ \text{Property Value} = \frac{\text{Net Operating Income}}{\text{Cap Rate}} \]

In order to facilitate ease of reference and consistency in our financial model, we established a named range for Streit's target cap rate, set at 6.00%.

The purchase price of West Ridge North, calculated in cell F2, incorporates the AcquisitionCapRate named range along with the net operating income from our previous analysis. It's crucial to note that we use net operating income, not net income, in this calculation.

In our financial model, Year 0 denotes the acquisition phase, during which only acquisition costs are accounted for, with no additional income or expenses incurred.

Based on our calculations, the purchase price of West Ridge North, with a cap rate of 6.00%, amounts to approximately $7,288,683. Since this outlay represents an expense, it is formatted as a negative value.

<img width="91" alt="Screenshot 2024-04-20 at 3 17 13 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/02f771f7-4cf1-408b-86a8-b14fa436426d">

Despite the substantial initial investment of $7.3 million, the acquisition of West Ridge North aligns with Streit's objective of achieving a 6% capitalized return, thereby positioning it as a financially sound investment opportunity.

<img width="254" alt="Screenshot 2024-04-20 at 3 15 19 AM" src="https://github.com/ricardolarajacome/excel_projects/assets/128415592/99c60a1e-d564-4f2e-ac7e-6698f95f6114">

In conclusion, the acquisition of West Ridge North presents Streit with an opportunity to leverage its expertise and resources to revitalize the property and capitalize on the burgeoning real estate market in Downtown Detroit.

**3. Forecasting Rental Income**

Financial models are crucial for analyzing investments over time, relying on assumptions to estimate future revenue and expenses. Growth rates are often employed to project increases in revenue and expenses. Using the formula `[Previous Value] * (1 + [Rate])`, we can determine the future value of an item with a growth rate.

To enhance usability, we've formatted the worksheet for clarity. We've created a custom number formatting for the periods in cells D16:N16 to display "Year " before the numbers.

Streit plans to remodel all units in the first year and anticipates renting units starting in Year 2 at $2,300 per month. Rent is expected to increase annually according to the Rent Growth % assumption.

To forecast rental income for the next 10 years:
- Enter $2300 in cell F19 to specify rental income for Year 2.
- Use the formula in cell G19 to forecast rental income: `[Previous Value] * (1 + [Rent Growth %])`, ensuring to lock the cell reference to Rent Growth %.
- Drag this formula to N19 to complete the analysis up to Year 10.

Now, we calculate the net potential rent for each year, representing the total potential rent earned by the entire property annually. Net potential rent is obtained by multiplying the monthly rent (cell F19) by the Units named range and then by 12 to convert to an annual figure. This calculation is dragged across to N18 for analysis up to Year 10.

The estimated Net Potential Rent in Year 10 is $3,262,222, indicating significant growth over the 10-year period, thanks to the planned renovations and rent increases.

**4. Predicting Sales Price**

Real estate investors often aim to sell properties within 5-10 years to generate cash for further investments and portfolio diversification. To analyze the predicted sales price of West Ridge North during any year of our analysis, we'll use the cap rate formula: `[Property Value] = [Net Operating Income] / [Cap Rate]`.

By utilizing HLOOKUP() to dynamically lookup the net operating income for the specified holding period (Years), we determine that Year 10 yields the highest sales price due to substantial renovations and rent growth, making it an attractive asset for potential buyers.

**5. Scenario Analysis**

Streit's Chief Investment Officer seeks to explore various outcomes using the Scenario Manager tool in Excel. By comparing scenarios, we can assess the net operating income for Year 10 across different assumptions, providing valuable insights for decision-making.

Upon reviewing the scenarios, the difference between the Expected Rent and High Rent scenarios for Year 10 is $717,739.

**6. Goal Seek Analysis**

Goal Seek enables us to determine the Exit Cap Rate required for the Sell Price to reach $100M. After running Goal Seek, we find that an Exit Cap Rate of 5.00% is needed for the Sell Price to be $100M.

**7. Sensitivity Analysis**

A sensitivity analysis on Rent Growth % reveals the impact on net operating income. At a 5.00% rent growth rate, net operating income is $2,954,983, while at a 10.00% rate, it increases to $4,519,938.

**8. Return on Investment (ROI)**

We calculate the ROI for West Ridge North, finding it to be 857.61%. Although impressive, this ROI reflects a long-term investment over 10 years.

**9. Benchmark Analysis**

Using benchmarks such as future value and present value, we assess the investment's performance. West Ridge North exceeds the future value benchmark, indicating a successful investment. Additionally, the present value of the investment, based on a 20.00% benchmark rate, is $11,365,424, demonstrating the project's viability compared to alternative investment opportunities.

**10. Net Present Value Analysis**

The Chief Investment Officer has tasked us with determining the net present value (NPV) of the total net income earned over the lifetime of West Ridge North. NPV() function simplifies this calculation.

The NPV for West Ridge North is approximately $7.4M. Since this value is greater than 0, West Ridge North would be a preferable investment compared to another investment with a 20% return.

However, we encountered a limitation with NPV(), as it assumed cash flows started in Year 1 rather than Year 0. To address this issue, we utilized XNPV(), a more precise function that considers the timing of cash flows based on dates.

The XNPV of the Net Income cash flows is calculated to be $7,372,047, providing a more accurate representation of the project's profitability.

**11. Internal Rate of Return (IRR) Analysis**

The internal rate of return (IRR) is a crucial metric to assess the project's profitability, representing the discount rate that makes the net present value zero.

With the standard IRR calculation, we find the IRR to be 29.78%. However, since we have dates associated with each cash flow, XIRR() would provide a more precise result.

The IRR using XIRR() is 29.75%, indicating an annual rate of return of 29.75%. To further analyze the project's viability, we set the benchmark rate equal to the IRR.

Updating the benchmark rate in cell J5 to match the XIRR, we find that the value of XNPV in J10 is 0. This aligns with expectations, as the discount rate in NPV often represents the project's cost. If the project cost equals the return, there would be no real financial gain.


