# SA-CCR Risk Assessment for Interest Rate Derivatives

## **Objective**
This project implements the **Standardized Approach for Counterparty Credit Risk (SA-CCR)** to assess and quantify the risk exposure of a $5.41 billion portfolio of interest rate derivatives. Using regulatory formulas, the project calculates **Exposure at Default (EAD)** through components like Adjusted Notional, Potential Future Exposure (PFE), and Replacement Cost (RC), providing insights into counterparty risk and optimizing capital requirements.

---

## **Methodology**

### **1. Portfolio Segmentation**
- **Margined Trades**: $4.23 billion secured under margin agreements.
- **Unmargined Trades**: $1.18 billion without margin coverage.

### **2. Risk Quantification**

#### Adjusted Notional
Adjusted Notional (d_i) = Notional × Supervisory Duration (SD)

Supervisory Duration (SD) = max(e^(-0.05 × S) - e^(-0.05 × E), 0.05) where:

S = Start Date
E = End Date
#### Replacement Cost (RC)
For margined and unmargined netting sets:
RC = max(0, V - C + MTA + TH - NICA)

where:

V: Market Value
C: Collateral Value
MTA: Minimum Transfer Amount
TH: Threshold Amount
NICA: Net Independent Collateral Amount
#### Potential Future Exposure (PFE)
PFE = Multiplier × AddOn_Aggregate

Multiplier = min(1, 0.05 + 0.95 × exp(-(V - C) / (1.9 × AddOn_Aggregate)))

#### Exposure at Default (EAD)
EAD = α × (RC + PFE)

where:

α = 1.4 (Regulatory multiplier to capture wrong-way risk and uncertainty)

### **3. Validation and Analysis**
- Calculations were validated in **Excel**, ensuring accurate implementation of RC, PFE, and EAD formulas.
- The impact of collateral and margining agreements was analyzed to optimize capital requirements.

### **4. Portfolio Impact Analysis**
- Stress testing and scenario analysis were conducted to evaluate exposure under adverse market conditions.

---

## **Key Results**

- **Counterparty Risk Reduction**:  
  - Counterparty exposure was reduced by **44%**, primarily due to margin agreements and collateralization.  
  - The portfolio's total Mark-to-Market (MTM) value was **$2.85 million**.  

- **Improved Risk Metrics**:  
  - Margined trades exhibited significantly lower EAD compared to unmargined trades.  
  - PFE calculations effectively captured supervisory adjustments for risk sensitivity.

- **Capital Optimization**:  
  - Netting and collateralization effects resulted in lower regulatory capital requirements.

---

## **Conclusion**
This project demonstrates the successful application of SA-CCR for interest rate derivatives risk assessment. By implementing regulatory formulas for RC, PFE, and EAD, the framework provides a robust method to quantify counterparty risk, improve capital efficiency, and ensure compliance with Basel III.

---

## **Installation and Usage**

### **Prerequisites**
- Excel or equivalent spreadsheet software for validation.

### **Usage Instructions**
1. Load the derivative portfolio data into the provided SA-CCR framework.
2. Apply the formulas for Adjusted Notional, PFE, RC, and EAD.
3. Validate the outputs against provided regulatory guidelines.
4. Perform scenario and stress testing for additional insights.

---

## **References**
- Basel III Endgame Proposal
