# Shapiro Model Implementation - Prompt Sequence

This is the set of prompts I provided to generate the example Monte Carlo simulation. However,
there is some randomness in the process and you will need to adapt to what Q does.
Caveat emptor!


##  Basics

list scripts

/context add /Users/skrainka/workplace/q/src/AmazonBuilderGenAIPowerUsersQContext/scripts/pdd.script.md

run pdd

## Step 1: Create Project Structure

/editor

```
You are a Principal Economist and need to use the data generating process (DGP) in the paper on TV advertising by 
Shapiro, Hitsch, and Tuchman.  You can find this paper in the PDF: ShapiroTV.pdf. 
Create a Monte Carlo simulation that uses the DGP in the paper to evaluate the design of a long-term RCT to measure
the returns on brand marketing. Make sure you complete the following requirements:

*   Generate 18 months of data
*   Generate 210 DMAs, which are the observational unit
*   For half of the DMAs, supress the level of advertising by 50% after one year until the end of the experiment
*   Use Python to implement this
*   Use Python library functions from statsmodels or PanelOLS or equivalent to analyze results. Do not reimplement standard estimators on your own.
```

## Step 2: Initial Process Planning

1.


## Step 3: Requirements Clarification

### Question 1: Data Generating Process Specification

Read the paper in the PDf ../ShapiroTV.pdf. This will define the DGP. We want to simulate OPS as the outcome.

### Question 2: Paper Content and Model Specification

Figure out how to read the PDF. Extract the text if necessary and read that.

### Question 3: Outcome Variable Clarification

Use option B. Replace Online Purchase Share with OPS. Retain the rest of the model.

### Question 4: Parameter Values and Ranges

Use reasonable parameter values from the paper. If there is a distribution or multiple values, use the mean, median, variance, etc. as appropriate.

### Question 5: Experimental Design Details

Only model response for one brand (Amazon). OPS will have a skewed distribution.

### Question 6: OPS Distribution and Range

You should end up with a log-log regression for analysis. To start, assume OPS is log-normally distributed.

### Question 7: Data Structure and Stores

Only simulate aggregate OPS per DMA. Use realistic variation in the size of each DMA market.

### Question 8: Analysis Requirements

A. Include fixed effects, robust SE. Then run enough replications to estiamte the power of the design and analysis method.

### Question 9: Completion Check

This looks good. Let's do it!


## Step 4: Research Relevant Information

The Shapiro paper should provide sufficient Economic information. Please make sure you don't hard code any magic numbers and put configuration parameters in a YAML file.


## Research Summary


Please create the design.

Please implement.


##  Wrap up

Now you need to verify the code via both manual inspection, running the code, and
reviewing the results make sense. You will probably find some simple mistakes, such
as in specification of the DGP and model. Also, the estimation procedure may use the
wrong functions, such as OLS instead of a panel data regression.

You are responsible for making sure that
what Q produces is correct because you are the owner.


- - -

# Shapiro Model Implementation - Prompt Sequence Reconstructed by Q CLI

Based on the Shapiro, Hitsch, and Tuchman (2021) econometric model for TV advertising effectiveness, here's the sequence of prompts needed to create the complete solution as a standalone project:

## **Prompt Sequence for Shapiro Model Implementation**

### **Prompt 1: Project Setup and Requirements**
"Create a Python project to implement the Shapiro, Hitsch, and Tuchman (2021) econometric model for TV advertising effectiveness. Set up the directory structure, configuration file with model parameters (210 DMAs, 78 weeks, δ=0.9 carryover, -50% treatment effect), and requirements.txt with pandas, numpy, statsmodels, linearmodels, matplotlib, and seaborn."

### **Prompt 2: Data Generating Process**
"Implement the core data generating process for the Shapiro model: log(Q_dt) = β*log(1 + Ad_dt) + α*log(p_dt) + γ_d + γ_S(t) + γ_T(t) + ε_dt. Create functions to generate DMA fixed effects, seasonal patterns, time trends, baseline advertising levels, and prices. Include realistic parameter values: advertising elasticity 0.014, price elasticity -1.5, error variance 0.25."

### **Prompt 3: Advertising Stock and Carryover Effects**
"Implement the advertising stock calculation with carryover effects: Ad_dt = Σ(τ=t-L to t) δ^(t-τ) * ad_dτ where δ=0.9 and L=52 weeks. Create functions to calculate advertising stock from flow data and handle the dynamic carryover structure efficiently for panel data."

### **Prompt 4: Experimental Treatment Implementation**
"Create functions to apply experimental treatment (50% marketing reduction) to randomly assigned DMAs starting at week 53. Implement randomization of 105 out of 210 DMAs to treatment, apply the reduction only during the treatment period (weeks 53-78), and recalculate advertising stock after treatment application."

### **Prompt 5: Panel Data Generation**
"Build a complete panel data generator that combines all components: creates 210 DMAs × 78 weeks dataset (16,380 observations), applies treatment assignment and timing, generates the outcome variable using the Shapiro model equation, and returns a clean DataFrame with all necessary variables for analysis."

### **Prompt 6: Panel Regression Estimation**
"Implement panel regression analysis using linearmodels.PanelOLS with entity and time fixed effects. Create functions to estimate the model: 'log_quantity ~ log_ad_stock + log_price + treatment + EntityEffects + TimeEffects' with clustered standard errors at the DMA level. Extract treatment effects, p-values, and confidence intervals."

### **Prompt 7: Monte Carlo Power Analysis**
"Build a Monte Carlo simulation framework to calculate statistical power for detecting the 50% marketing reduction. Create functions to: run single iterations (generate data, apply treatment, estimate model), calculate power across multiple simulations, handle estimation failures gracefully, and return comprehensive power analysis results."

### **Prompt 8: Validation and Diagnostics**
"Create validation functions to verify the implementation: check treatment assignment is correct, validate advertising stock calculations, confirm model estimation produces reasonable results, and compare with expected parameter values from the original paper."

### **Prompt 9: Visualization and Results**
"Implement visualization functions for: treatment effect distributions across simulations, power curves showing power vs. sample size/effect size, model diagnostic plots, and summary tables of key results. Use matplotlib/seaborn with professional styling."

### **Prompt 10: Main Analysis Script**
"Create a main analysis script that orchestrates the complete workflow: generates the experimental dataset, applies treatment, estimates the panel model, runs power analysis, creates visualizations, and produces a comprehensive results summary with statistical interpretation."

## **Key Technical Requirements Across Prompts:**
- **Panel Structure**: 210 DMAs × 78 weeks = 16,380 observations
- **Model Specification**: Shapiro et al. (2021) econometric equation with fixed effects
- **Treatment Design**: 50% reduction, weeks 53-78, randomized assignment
- **Carryover Effects**: δ=0.9 parameter with 52-week lag structure
- **Statistical Methods**: PanelOLS with clustered standard errors
- **Power Analysis**: Monte Carlo simulation with realistic parameter values

## **Expected Outputs:**
- Complete panel dataset with treatment assignment
- Panel regression results with treatment effect estimates
- Monte Carlo power analysis (typically 80%+ power for 50% effect)
- Professional visualizations of results
- Validation of implementation against known parameters

This sequence builds from basic setup through sophisticated econometric implementation, ensuring each component works before adding complexity.
