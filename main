import streamlit as st
import pandas as pd

# --- Main Navigation ---
def main():
    st.set_page_config(page_title="Comprehensive Accounting Course", layout="wide")
    st.sidebar.title("Course Navigation")
    pages = [
        "Introduction",
        "Module 1: Accounting Fundamentals & the 5 Categories",
        "Module 2: Journal Entries, Accruals & Balancing",
        "Module 3: Managing the Chart of Accounts",
        "Module 4: Budgeting, Forecasting & Consolidation",
        "Module 5: Real Estate Practices & Product Integration",
        "Module 6: Review & Assessment",
        "Appendix: Tools & Extra Resources"
    ]
    choice = st.sidebar.radio("Go to", pages)
    
    if choice == pages[0]:
        show_introduction()
    elif choice == pages[1]:
        show_module1()
    elif choice == pages[2]:
        show_module2()
    elif choice == pages[3]:
        show_module3()
    elif choice == pages[4]:
        show_module4()
    elif choice == pages[5]:
        show_module5()
    elif choice == pages[6]:
        show_module6()
    elif choice == pages[7]:
        show_appendix()

# --- Module Functions ---

def show_introduction():
    st.title("Comprehensive Accounting for Real Estate & Leasing")
    st.markdown("""
    **Objective:**  
    This course is designed to give product managers and engineers a thorough, hands-on understanding of accounting concepts in the real estate and leasing context. You will:
    - Learn the five fundamental categories: **Assets, Liabilities, Equity, Revenue, and Expenses**.
    - Understand how every transaction is recorded as balanced debits and credits.
    - Simulate the creation of accruals and their reversing entries.
    - Build and manage your own Chart of Accounts.
    - Explore budgeting, forecasting, consolidation, and real‑world lease accounting.
    
    Use the sidebar to navigate through the modules. Each module combines teaching with interactive examples and quizzes.
    """)

def show_module1():
    st.header("Module 1: Accounting Fundamentals & the 5 Categories")
    st.markdown("### Teaching Section")
    with st.expander("Learn the Basics"):
        st.markdown("""
        In accounting, every transaction falls into one of five key categories:
        
        **Assets:**  
        - Resources owned by a business (e.g., Cash, Property, Equipment).
        
        **Liabilities:**  
        - Debts or obligations (e.g., Loans, Accounts Payable, Accrued Expenses).
        
        **Equity:**  
        - The residual interest after liabilities are deducted from assets (e.g., Owner’s Equity, Retained Earnings).
        
        **Revenue:**  
        - Income earned from business operations (e.g., Rental Income, Sales Revenue).
        
        **Expenses:**  
        - Costs incurred in generating revenue (e.g., Maintenance, Utilities, Marketing).
        
        **Double-Entry Principle:**  
        Every transaction is recorded with at least one debit and one credit. For a balanced entry, total debits must equal total credits.
        """)
        st.markdown("**Example Transaction: A company receives $2,000 in rental income.**")
        rental_data = {
            "Account": ["Cash (Asset)", "Rental Income (Revenue)"],
            "Debit": [2000, 0],
            "Credit": [0, 2000]
        }
        rental_df = pd.DataFrame(rental_data)
        st.table(rental_df)
    
    st.markdown("### Quiz: Transaction Recording for a Pipe Replacement")
    st.markdown("""
    **Scenario:**  
    A $500 pipe replacement is performed on March 18th, and you receive an invoice. The invoice is due on April 1st, and payment is made on April 1st.
    
    **Instructions:**  
    Fill in the tables below:
    - **Invoice Receipt (March 18th):** Record the accrual transaction when you receive the invoice.  
      *Hint: Debit the appropriate Expense account and Credit a Liability account (e.g., Accrued Expenses or Accounts Payable).*
    - **Payment (April 1st):** Record the payment transaction when you pay the invoice.  
      *Hint: Debit the Liability account and Credit Cash.*
    """)
    
    invoice_account_options = ["Pipe Replacement Expense", "Maintenance Expense", "Accounts Payable", "Accrued Expenses"]
    payment_account_options = ["Accounts Payable", "Accrued Expenses", "Cash"]
    entry_type_options = ["Debit", "Credit"]
    
    st.markdown("#### Invoice Receipt (March 18th)")
    invoice_df = pd.DataFrame({
        "Account": ["", ""],
        "Entry Type": ["", ""],
        "Amount ($)": [0, 0]
    }, index=["Line 1", "Line 2"])
    edited_invoice_df = st.data_editor(
        invoice_df,
        num_rows="fixed",
        key="invoice_editor",
        column_config={
            "Account": st.column_config.SelectboxColumn("Account", options=invoice_account_options),
            "Entry Type": st.column_config.SelectboxColumn("Entry Type", options=entry_type_options),
        }
    )
    
    st.markdown("#### Payment (April 1st)")
    payment_df = pd.DataFrame({
        "Account": ["", ""],
        "Entry Type": ["", ""],
        "Amount ($)": [0, 0]
    }, index=["Line 1", "Line 2"])
    edited_payment_df = st.data_editor(
        payment_df,
        num_rows="fixed",
        key="payment_editor",
        column_config={
            "Account": st.column_config.SelectboxColumn("Account", options=payment_account_options),
            "Entry Type": st.column_config.SelectboxColumn("Entry Type", options=entry_type_options),
        }
    )
    
    if st.button("Submit Answers for Quiz", key="submit_quiz_mod1_table"):
        st.markdown("### Your Submitted Answers")
        st.write("#### Invoice Receipt (March 18th)")
        st.table(edited_invoice_df)
        st.write("#### Payment (April 1st)")
        st.table(edited_payment_df)
        st.markdown("**Expected Answer:**")
        st.markdown("""
        **Invoice Receipt (March 18th):**  
        - **Line 1:** Debit: Pipe Replacement Expense (or Maintenance Expense) $500  
        - **Line 2:** Credit: Accounts Payable (or Accrued Expenses) $500  
        
        **Payment (April 1st):**  
        - **Line 1:** Debit: Accounts Payable (or Accrued Expenses) $500  
        - **Line 2:** Credit: Cash $500  
        """)
        st.success("Review your submitted answers against the expected answers above.")

def show_module2():
    st.header("Module 2: Journal Entries, Accruals & Balancing")
    st.markdown("### Teaching Section")
    with st.expander("Recording Transactions & Accruals"):
        st.markdown("""
        **Journal Entries:**  
        - Every transaction is recorded as a journal entry with debits and credits that must balance.
        
        **Accruals:**  
        - Record revenues or expenses when they occur, even if cash hasn’t exchanged hands.
        - Example: If a $500 repair expense is incurred in December but paid in January, record an accrual in December.
        
        **Reversing Entries:**  
        - In the following period, a reversing entry is made to cancel out the accrual.
        
        **Example of an Accrual Entry:**  
        - **Debit:** Repair Expense $500  
        - **Credit:** Accrued Expenses $500
        
        **Reversing Entry in Next Period:**  
        - **Debit:** Accrued Expenses $500  
        - **Credit:** Repair Expense $500
        """)
    
    st.markdown("### Interactive Exercise: Record a Repair Expense Accrual")
    accrual_df = pd.DataFrame({
        "Account": ["", ""],
        "Entry Type": ["", ""],
        "Amount ($)": [0, 0]
    }, index=["Line 1", "Line 2"])
    edited_accrual_df = st.data_editor(
        accrual_df,
        num_rows="fixed",
        key="accrual_editor",
        column_config={
            "Account": st.column_config.SelectboxColumn("Account", options=["Repair Expense", "Accrued Expenses"]),
            "Entry Type": st.column_config.SelectboxColumn("Entry Type", options=["Debit", "Credit"]),
        }
    )
    if st.button("Submit Accrual Entry", key="submit_accrual_entry"):
        try:
            df = edited_accrual_df
            total_debits = df[df["Entry Type"] == "Debit"]["Amount ($)"].sum()
            total_credits = df[df["Entry Type"] == "Credit"]["Amount ($)"].sum()
        except Exception as e:
            st.error("Error calculating totals. Ensure all amounts are numeric.")
            total_debits = total_credits = 0
        
        st.markdown("**Your Accrual Journal Entry:**")
        st.table(edited_accrual_df)
        st.write("Total Debits: $", total_debits)
        st.write("Total Credits: $", total_credits)
        if total_debits == total_credits and total_debits > 0:
            st.success("Balanced Entry: Debits equal Credits!")
        else:
            st.error("Unbalanced Entry: Please ensure total debits equal total credits.")
    
    st.markdown("### Interactive Exercise: Record a Reversing Entry")
    reversing_df = pd.DataFrame({
        "Account": ["", ""],
        "Entry Type": ["", ""],
        "Amount ($)": [0, 0]
    }, index=["Line 1", "Line 2"])
    edited_reversing_df = st.data_editor(
        reversing_df,
        num_rows="fixed",
        key="reversing_editor",
        column_config={
            "Account": st.column_config.SelectboxColumn("Account", options=["Accrued Expenses", "Repair Expense"]),
            "Entry Type": st.column_config.SelectboxColumn("Entry Type", options=["Debit", "Credit"]),
        }
    )
    if st.button("Submit Reversing Entry", key="submit_reversing_entry"):
        try:
            rev_df = edited_reversing_df
            total_debits_rev = rev_df[rev_df["Entry Type"] == "Debit"]["Amount ($)"].sum()
            total_credits_rev = rev_df[rev_df["Entry Type"] == "Credit"]["Amount ($)"].sum()
        except Exception as e:
            st.error("Error calculating totals for reversing entry.")
            total_debits_rev = total_credits_rev = 0
        
        st.markdown("**Your Reversing Journal Entry:**")
        st.table(edited_reversing_df)
        st.write("Total Debits: $", total_debits_rev)
        st.write("Total Credits: $", total_credits_rev)
        if total_debits_rev == total_credits_rev and total_debits_rev > 0:
            st.success("Balanced Entry: Debits equal Credits!")
        else:
            st.error("Unbalanced Entry: Please ensure total debits equal total credits.")
    
    st.markdown("### Hands-On: Simulate Your Own Journal Entry")
    with st.expander("Enter details for a new transaction"):
        debit_account = st.text_input("Debit Account", "Cash", key="debit_account_own")
        debit_amt = st.number_input("Debit Amount ($)", min_value=0.0, value=1000.0, step=50.0, key="debit_amt_own")
        credit_account = st.text_input("Credit Account", "Rental Income", key="credit_account_own")
        credit_amt = st.number_input("Credit Amount ($)", min_value=0.0, value=1000.0, step=50.0, key="credit_amt_own")
        if st.button("Submit Journal Entry", key="submit_journal_own"):
            st.markdown("**Your Journal Entry:**")
            st.markdown(f"- **Debit:** {debit_account} ${debit_amt}")
            st.markdown(f"- **Credit:** {credit_account} ${credit_amt}")
            if debit_amt == credit_amt:
                st.success("Balanced Entry: Debits equal Credits!")
            else:
                st.error("Unbalanced Entry: Please ensure total debits equal total credits.")

def show_module3():
    st.header("Module 3: Managing the Chart of Accounts")
    st.markdown("### Teaching Section: Chart of Accounts Overview")
    with st.expander("What is a Chart of Accounts?"):
        st.markdown("""
        A Chart of Accounts (COA) is an organized listing of all accounts in your accounting system, grouped into the five fundamental categories:
        
        1. **Assets:** e.g., Cash, Accounts Receivable, Property Assets.
        2. **Liabilities:** e.g., Loans, Accrued Expenses.
        3. **Equity:** e.g., Owner’s Equity, Retained Earnings.
        4. **Revenue:** e.g., Rental Income, Service Revenue.
        5. **Expenses:** e.g., Maintenance, Utilities, Marketing.
        
        A well-structured COA allows you to record transactions accurately and generate financial statements that inform decision-making.
        """)
    
    st.markdown("### Interactive Exercise: Build Your Chart of Accounts")
    st.markdown("**Instructions:** Enter account names and select the category for each account.")
    coa_df = pd.DataFrame({
        "Category": ["", "", ""],
        "Account Name": ["", "", ""]
    })
    edited_coa_df = st.data_editor(
        coa_df,
        num_rows="fixed",
        key="coa_editor",
        column_config={
            "Category": st.column_config.SelectboxColumn("Category", options=["Assets", "Liabilities", "Equity", "Revenue", "Expenses"])
        }
    )
    if st.button("Submit COA", key="submit_coa_editor"):
        st.markdown("### Your Chart of Accounts")
        st.table(edited_coa_df)
        st.success("Your Chart of Accounts has been created!")

def show_module4():
    st.header("Module 4: Budgeting, Forecasting & Consolidation")
    st.markdown("### Teaching Section: Financial Planning")
    with st.expander("Budgeting & Forecasting Basics"):
        st.markdown("""
        **Budgeting:**  
        - Create financial plans for property operations.
        - Include projected revenues and anticipated expenses.
        
        **Forecasting:**  
        - Use historical data and trends to predict future performance.
        - Consider various scenarios to plan for potential changes.
        
        **Consolidation:**  
        - Combine financial data from multiple properties.
        - Adjust for intercompany transactions to produce a single, coherent financial statement.
        """)
    
    st.markdown("### Interactive Exercise: Budget Builder")
    st.markdown("Imagine a property with the following monthly details:")
    st.write("- **Rental Income:** $5,000")
    st.write("- **Expenses:** Maintenance $800, Utilities $300, Marketing $400")
    rental_income = st.number_input("Monthly Rental Income ($)", value=5000, step=100, key="mod4_rental")
    maintenance = st.number_input("Maintenance Expense ($)", value=800, step=50, key="mod4_maintenance")
    utilities = st.number_input("Utilities Expense ($)", value=300, step=50, key="mod4_utilities")
    marketing = st.number_input("Marketing Expense ($)", value=400, step=50, key="mod4_marketing")
    total_expenses = maintenance + utilities + marketing
    net_income = rental_income - total_expenses
    st.write("**Calculated Monthly Net Income:** $", net_income)
    
    months = [f"Month {i}" for i in range(1, 7)]
    forecast_df = pd.DataFrame({
        "Rental Income": [rental_income]*6,
        "Total Expenses": [total_expenses]*6,
        "Net Income": [net_income]*6
    }, index=months)
    st.dataframe(forecast_df)
    st.line_chart(forecast_df[["Rental Income", "Total Expenses", "Net Income"]])
    
    st.markdown("### Quiz: Why Reconcile Budgets?")
    recon_answer = st.text_area("Explain why it’s important to reconcile budgets with actuals:", key="mod4_quiz_answer")
    if st.button("Submit Answer - Module 4", key="submit_mod4_answer"):
        st.write("Your response:")
        st.write(recon_answer)
        st.info("Reconciliation helps identify variances, improves forecasting, and ensures financial accuracy.")

def show_module5():
    st.header("Module 5: Real Estate Practices & Product Integration")
    st.markdown("### Teaching Section: Real Estate Specifics")
    with st.expander("Lease Accounting & Operational Metrics"):
        st.markdown("""
        **Lease Accounting:**  
        - **Revenue Recognition:** How and when rental income is recorded.
        - **Depreciation:** Spreading the cost of property assets over their useful lives.
        - **Lease Incentives:** Discounts or incentives spread over the lease term.
        
        **Operational Metrics:**  
        - Track key performance indicators (KPIs) such as occupancy rate and net operating income.
        - Integrate real-time financial data into property management dashboards.
        """)
    
    st.markdown("### Interactive Exercise: Lease Incentive Simulator")
    lease_term = st.selectbox("Lease Term (months)", options=[12, 24, 36], key="lease_term")
    total_incentive = st.number_input("Total Incentive Discount ($)", value=1200, step=100, key="lease_incentive")
    monthly_adjustment = total_incentive / lease_term
    st.write("Monthly incentive adjustment: $", monthly_adjustment)
    
    st.markdown("### Workshop Discussion: Integrating Accounting into Your Product")
    st.markdown("""
    **Discussion Points:**
    - Which financial metrics (e.g., net operating income, occupancy rate) are most important to display in your property management dashboard?
    - How can real-time accounting data improve operational decisions?
    - Consider any challenges with integrating legacy accounting systems into a new digital platform.
    """)
    st.info("Discuss these points with your team offline or in a breakout session.")

def show_module6():
    st.header("Module 6: Review & Assessment")
    st.markdown("### Course Recap")
    with st.expander("Review Key Concepts"):
        st.markdown("""
        **Recap:**
        - **Module 1:** The five fundamental categories and balanced transactions.
        - **Module 2:** Recording journal entries, accruals, and reversing entries.
        - **Module 3:** Building and managing a Chart of Accounts.
        - **Module 4:** Budgeting, forecasting, and consolidating financial data.
        - **Module 5:** Real estate-specific accounting practices and integrating them into product design.
        """)
    
    st.markdown("### Final Quiz")
    st.markdown("1. **Explain the double-entry system in your own words.**")
    final_ans1 = st.text_area("Answer for Question 1:", key="final_q1")
    st.markdown("2. **Describe how you would record an accrual and its reversing entry.**")
    final_ans2 = st.text_area("Answer for Question 2:", key="final_q2")
    st.markdown("3. **Outline the structure and importance of a Chart of Accounts.**")
    final_ans3 = st.text_area("Answer for Question 3:", key="final_q3")
    
    st.markdown("4. **Multiple Choice: What is the correct journal entry for recording an accrual?**")
    final_choice = st.radio("Select the correct entry", options=[
        "Debit: Expense, Credit: Accrued Expenses",
        "Debit: Accrued Expenses, Credit: Expense",
        "Debit: Cash, Credit: Revenue"
    ], key="final_mcq")
    
    if st.button("Submit Final Quiz", key="submit_final_quiz"):
        st.write("Your final quiz responses:")
        st.write("Q1:", final_ans1)
        st.write("Q2:", final_ans2)
        st.write("Q3:", final_ans3)
        if final_choice == "Debit: Expense, Credit: Accrued Expenses":
            st.write("Q4: Correct!")
        else:
            st.write("Q4: Incorrect. The correct entry is: Debit: Expense, Credit: Accrued Expenses.")
        st.info("Review your answers and discuss as a team to ensure a solid understanding of the material.")
    
    st.markdown("### Next Steps")
    st.markdown("""
    - **Further Learning:** Consider additional resources (books, online courses) on accounting fundamentals.
    - **Action Plan:** Identify one key process or concept from this course that you will apply to your work.
    """)

def show_appendix():
    st.header("Appendix: Tools & Extra Resources")
    st.markdown("""
    **Interactive Tools Provided:**
    - **Journal Entry Simulator:** Practice recording transactions and watch how the ledger updates.
    - **Budget Builder:** Simulate how changes in revenue or expenses impact your forecast.
    
    **Additional Resources:**
    - Online tutorials on accounting principles.
    - Articles and books on real estate finance.
    - Webinars and courses on integrating financial data with product management.
    """)
    st.info("Use these resources to further enhance your understanding and apply the concepts learned in this course.")

if __name__ == '__main__':
    main()
