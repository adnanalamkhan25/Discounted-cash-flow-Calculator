# Discounted-cash-flow-Calculator
#Discounted cash flow is a valuation method that estimates the value of an investment based on its expected future cash flows. 
def discounted_cash_flow():
    # User inputs
    n = int(input("Enter the number of years for projection: "))
    fcf_list = []
    
    for i in range(1, n + 1):
        fcf = float(input(f"Enter Free Cash Flow for Year {i}: "))
        fcf_list.append(fcf)
    
    discount_rate = float(input("Enter Discount Rate (WACC) in %: ")) / 100
    growth_rate = float(input("Enter Terminal Growth Rate in %: ")) / 100

    

    # Calculate Terminal Value (TV) using Perpetual Growth Model
    terminal_value = (fcf_list[-1] * (1 + growth_rate)) / (discount_rate - growth_rate)

    # Present Value of Terminal Value
    pv_terminal_value = terminal_value / ((1 + discount_rate) ** n)

    # Total Enterprise Value (EV)
    enterprise_value = pv_fcf + pv_terminal_value

    # Display Results
    print("\n--- By Adnan Alam Khan,ACCA ---")
    print("\n--- Discounted Cash Flow (DCF) Results ---")
    print(f"Present Value of Free Cash Flows: Rs{pv_fcf:.2f}M")
    print(f"Terminal Value: Rs{terminal_value:.2f}M")
    print(f"Present Value of Terminal Value: Rs{pv_terminal_value:.2f}M")
    print(f"Total Enterprise Value (EV): Rs{enterprise_value:.2f}M")

# Run the function
discounted_cash_flow()
