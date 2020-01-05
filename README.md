## Project description

This package includes financial math calculations for actuarial calculations such as annuity calculations, amortization schedule, sinking fund calculations and constructing tables with those formulas.

## Installation

pip install actuarialCalculations

## Calculate Amortization & Sinking Fund

**_method takes 4 parameters_**

1. Interest rate
2. Years
3. Frequency of the interest that hits in that period of time
4. Loan Amount

### Calculating Amortization Table

```python
'''Create an instance of CalctulateAmortization class and pass the parameters as intergers '''
calculate = CalctulateAmortization(interestRate, years, frequency, loanAmount)
'''To run the calculations we need to call execute funtion '''
calculate.execute()

```

**_method takes 4 parameters_**

1. Interest rate
2. Years
3. Frequency of the interest that hits in that period of time
4. Money Amount

### Calculating Sinking Fund Table

```python
''' Create an instance of CalculateSinkingFund class and pass the parameters as integers'''
calculate = CalculateSinkingFund(interestRate, years, frequency, amount)
'''To run the calculations we need to call execute funtion '''
calculate.execute()
```

### Calcuating present value

**_Assuming our user would like to know the downpayment amount with provided kwargs below;_**

###### Logic

> terms, period and interest amount rate.
> Price - (presentValue\* _N _ Repay Amount ) = Down payment

### Calculating the future value

**_Assuming our user pays at the end of the given period, so our program should accumulate the value with gthe iven interest rate;_**

###### Logic

> Accumulated Down payment(1+i)**N = Accumulated Price(1+i)**N - (AccumulatedValue\*_N _ Repay Amount)

### Calculating The Down Payment with Given Time Value

**_Assuming our user wants to calculate the downpayment with the given period of time_**

###### Logic

> Accumulated Down payment = Accumulated Price ** T -(presentValue \* Repay Amount ) ** T- (AccumulatedValue \* Repay Amount)**-(N+T) / (1+i)**T

```python
'''
Present Value method takes 5 parameters as intergers and returns downpayment amount
'''
presentValue = PresentValue(
    InterestRate, effectiveInterestTerms, fixedPeriod, repayAmount, price)

'''
Accumulated Value method takes 5 parameters as intergers and returns downpayment amount (future value)
'''
accumulatedValue = AccumulatedValue(
    InterestRate, effectiveInterestTerms, fixedPeriod, repayAmount, price)


'''
Calculate Given Time method takes 5 parameters as intergers and returns downpayment amount at any given time.
'''
calculateGivenTime = CalculateGivenTime(
    InterestRate, effectiveInterestTerms, fixedPeriod, repayAmount, price)

```
