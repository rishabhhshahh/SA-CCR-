# **SA-CCR Risk Assessment for Interest Rate Derivatives**

#### **Objective**
This project implements the **Standardized Approach for Counterparty Credit Risk (SA-CCR)** to assess and quantify the risk exposure of a $5.41 billion portfolio of interest rate derivatives. Using regulatory formulas, the project calculates **Exposure at Default (EAD)** through components like Adjusted Notional, Potential Future Exposure (PFE), and Replacement Cost (RC), providing insights into counterparty risk and optimizing capital requirements.

---

#### **Methodology**

1. **Portfolio Segmentation**:
   - **Margined Trades**: $4.23 billion secured under margin agreements.
   - **Unmargined Trades**: $1.18 billion without margin coverage.

2. **Risk Quantification**:
   - **Adjusted Notional**: 
     \[
     \text{Adjusted Notional (}d_i\text{)} = \text{Notional} \times \text{Supervisory Duration (SD)}
     \]
     where:
     \[
     SD = \max\left( e^{-0.05 \cdot S} - e^{-0.05 \cdot E}, 0.05 \right), \text{S = Start Date, E = End Date.}
     \]
     
   - **Replacement Cost (RC)**:
     For margined and unmargined netting sets:
     \[
     RC = \max\left(0, V - C + \text{MTA} + \text{TH} - \text{NICA}\right)
     \]
     where:
     - \(V\): Market Value
     - \(C\): Collateral Value
     - \(\text{MTA}\): Minimum Transfer Amount
     - \(\text{TH}\): Threshold Amount
     - \(\text{NICA}\): Net Independent Collateral Amount

   - **Potential Future Exposure (PFE)**:
     \[
     PFE = \text{Multiplier} \times \text{AddOn}_{\text{Aggregate}}
     \]
     \[
     \text{Multiplier} = \min\left(1, 0.05 + 0.95 \cdot \exp\left(-\frac{V - C}{1.9 \cdot \text{AddOn}_{\text{Aggregate}}}\right)\right)
     \]

3. **Exposure at Default (EAD)**:
   The total EAD is computed as:
   \[
   EAD = \alpha \times (RC + PFE)
   \]
   where:
   - \(\alpha = 1.4\), a regulatory multiplier to capture wrong-way risk and model uncertainty.

4. **Validation and Analysis**:
   - Calculations were validated in **Excel**, ensuring accurate implementation of RC, PFE, and EAD formulas.
   - The impact of collateral and margining agreements was analyzed to optimize capital requirements.

5. **Portfolio Impact Analysis**:
   - Stress testing and scenario analysis were conducted to evaluate exposure under adverse market conditions.

---

#### **Key Results**

- **Counterparty Risk Reduction**:
  - Counterparty exposure was reduced by **44%**, primarily due to margin agreements and collateralization.
  - The portfolio's total Mark-to-Market (MTM) value was **$2.85 million**.

- **Improved Risk Metrics**:
  - Margined trades exhibited significantly lower EAD compared to unmargined trades.
  - PFE calculations effectively captured supervisory adjustments for risk sensitivity.

- **Capital Optimization**:
  - Netting and collateralization effects resulted in lower regulatory capital requirements.

---

#### **Conclusion**
This project demonstrates the successful application of SA-CCR for interest rate derivatives risk assessment. By implementing regulatory formulas for RC, PFE, and EAD, the framework provides a robust method to quantify counterparty risk, improve capital efficiency, and ensure compliance with Basel III.
