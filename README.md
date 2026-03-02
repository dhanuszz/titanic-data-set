titanic data set remane 

Gotcha — you want to rename columns in the Titanic dataset 👍
Here are the most common ways people do it, assuming you’re using Python + pandas.

Basic example
import pandas as pd

df = pd.read_csv("titanic.csv")

df = df.rename(columns={
    "Survived": "survival_status",
    "Pclass": "passenger_class",
    "Sex": "gender",
    "Age": "age",
    "Fare": "ticket_fare"
})
Rename all columns at once
df.columns = [
    "passenger_id",
    "survived",
    "class",
    "name",
    "sex",
    "age",
    "siblings_spouses",
    "parents_children",
    "ticket",
    "fare",
    "cabin",
    "embarked"
]
Make column names cleaner (very common)
df.columns = (
    df.columns
      .str.lower()
      .str.replace(" ", "_")
)
Rename a single column
df.rename(columns={"Sex": "gender"}, inplace=True
