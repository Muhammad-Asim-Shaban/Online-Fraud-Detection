# 🕵️‍♂️ Online Fraud Detection Using Machine Learning 💳
This project aims to detect fraudulent financial transactions using machine learning techniques. It processes a dataset of online payments and classifies them as either fraudulent or legitimate based on various transaction features.

# 📦 Dataset
The dataset (data.csv) contains information about online transactions, including:

🔢 type – Type of transaction (e.g., CASH_OUT, TRANSFER)

💰 amount – Transaction amount

🏦 oldbalanceOrg – Originator’s initial balance

🏦 newbalanceOrig – Originator’s balance after the transaction

✅ isFraud – Whether the transaction is fraudulent

# 🧰 Libraries Used
numpy & pandas – Data manipulation

plotly – Interactive visualizations 📊

sklearn – Machine learning & data splitting

warnings – For suppressing non-critical logs

# 🔄 Data Preprocessing
Missing values filled with 0

One-hot encoding applied to type

Dropped identifier columns: nameOrig, nameDest

Fraud labels mapped to "Fraud" and "No Fraud"

```python
df['type'] = df['type'].map({"CASH_OUT":1,"PAYMENT":2,"CASH_IN":3,"TRANSFER":4,"DEBIT":5})
df['isFraud'] = df['isFraud'].map({0:"No Fraud", 1:"Fraud"})
```
# 📈 Visualization
A donut chart shows the distribution of transaction types using Plotly:

```python
figure = px.pie(df, values=quantity, names=transactions, hole=0.5, title="Distribution of Transaction Type")
figure.show()
```
# 🧠 Machine Learning Model
Features used: type, amount, oldbalanceOrg, newbalanceOrig

Labels: isFraud

Data split using train_test_split

