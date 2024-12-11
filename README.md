# Final
import streamlit as st
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
url = "https://raw.githubusercontent.com/iantonios/dsc205/refs/heads/main/bike_sharing.csv"
df = pd.read_csv(url)
#line chart for problem 1
plt.figure(figsize=(12, 6))
plt.plot(df.index, df['cnt'], label='Total Ridership', color='blue')
plt.title('Total Ridership Over Time')
plt.xlabel('Date')
plt.ylabel('Total Ridership')
plt.legend()
plt.show()

#bar chart for problem 2
plt.figure(figsize=(12, 6))
plt.bar(df.index, df['cnt'], color='skyblue')
plt.title('Total Ridership Over Time (Bar Chart)')
plt.xlabel('Date')
plt.ylabel('Total Ridership')
plt.grid(True, axis='y', linestyle='--', alpha=0.7)
plt.show()

#line chart for problem 3 with rolling averages
def plot_rolling_average(window_size):
    df['rolling_avg'] = df['cnt'].rolling(window=window_size).mean()
    plt.figure(figsize=(12, 6))
    plt.plot(df.index, df['cnt'], label='Total Ridership', color='blue', alpha=0.5)
    plt.plot(df.index, df['rolling_avg'], label=f'{window_size}-Day Rolling Average', color='red', linewidth=2)
    plt.title(f'Total Ridership and {window_size}-Day Rolling Average')
    plt.xlabel('Date')
    plt.ylabel('Total Ridership')
    plt.grid(True)
    plt.show()
st.radio('Select Day Average') #trying to create radio button for 7-day average and 14-day average
if == 'Total ridership'
    df = df.loc[df['Total Ridership']=='7-day_averag'] #radio button for 7-day average
    else:
        df = df.loc[df['Total Ridership']=='14-day_average'] #radio button for 14-day average
