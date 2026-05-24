import streamlit as st

import pandas as pd

import numpy as np

st.title("💰 Finance Insights Dashboard")

# Sample data

months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun"]

income = [3000, 3200, 3100, 4000, 4200, 4500]

expenses = [2500, 2600, 2400, 3000, 3100, 3300]

df = pd.DataFrame({

    "Month": months,

    "Income": income,

    "Expenses": expenses

})

st.subheader("Income vs Expenses")

st.line_chart(df.set_index("Month"))

st.subheader("Summary")

st.write(df)

net = sum(income) - sum(expenses)

st.metric("Net Savings (6 months)", f"${net}")
