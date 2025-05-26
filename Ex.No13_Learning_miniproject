# Purchasing Intention Classifier
### DATE: 13.05.2025                                                                       
### REGISTER NUMBER : 212222040118
### AIM: 
To implement a ml project on purchasing intention classifier
### Algorithm:
Start the program.

Import necessary libraries and load the dataset using pandas.

Encode categorical and boolean columns into numeric format using LabelEncoder.

Split the dataset into features (X) and target variable (y = Revenue).

Scale the feature values using StandardScaler to normalize the data.

Split the data into training and testing sets using train_test_split() with 80-20 ratio.

Train a Random Forest Classifier using the training data and predict outcomes for the test data.

Evaluate the model using accuracy score and classification report, then predict one test sample and stop the program.
# Program:
```
# Step 1: Import libraries
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder, StandardScaler
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, classification_report

# Step 2: Load dataset from UCI (fresh version)
df = pd.read_csv("/content/online_shoppers_intention.csv")

print("Data loaded successfully.")

# Step 3: Encode categorical features
categorical_cols = df.select_dtypes(include=['object', 'bool']).columns
for col in categorical_cols:
    df[col] = LabelEncoder().fit_transform(df[col])

# Step 4: Feature-target split
X = df.drop("Revenue", axis=1)
y = df["Revenue"]

# Step 5: Scale features
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Step 6: Train-test split
X_train, X_test, y_train, y_test = train_test_split(
    X_scaled, y, test_size=0.2, random_state=42, stratify=y
)

# Step 7: Train a simple classifier
clf = RandomForestClassifier(random_state=42)
clf.fit(X_train, y_train)

# Step 8: Evaluate model
y_pred = clf.predict(X_test)
print("Accuracy:", accuracy_score(y_test, y_pred))
print("\nClassification Report:\n", classification_report(y_test, y_pred))

# Step 9: Predict on one test sample
sample = X_test[0].reshape(1, -1)
prediction = clf.predict(sample)
print("Test Prediction:", prediction[0])

```

# Output:
![image](https://github.com/user-attachments/assets/215fa4e7-ffe7-46c9-bcb2-43e7f2846fec)




### Result:
The ML based project implemented sucessfully.
