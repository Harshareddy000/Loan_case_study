# Loan_case_study
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load your dataset
df = pd.read_csv('your_dataset.csv')  # Replace with your dataset file

# List of numerical columns
numerical_columns = ['col1', 'col2', 'col3']  # Replace with your numerical columns

# Univariate analysis with subplots for numerical columns
def analyze_numerical_columns_subplots(data, numerical_columns):
    fig, axes = plt.subplots(len(numerical_columns), 4, figsize=(20, 5 * len(numerical_columns)))
    
    for i, column in enumerate(numerical_columns):
        # KDE plot
        sns.kdeplot(data[column], ax=axes[i, 0], shade=True)
        axes[i, 0].set_title(f"KDE Plot for {column}")
        
        # Histogram
        data[column].plot(kind='hist', ax=axes[i, 1], bins=30)
        axes[i, 1].set_title(f"Histogram for {column}")
        
        # Boxplot
        sns.boxplot(x=data[column], ax=axes[i, 2])
        axes[i, 2].set_title(f"Boxplot for {column}")
        
        # Bar graph
        data[column].value_counts().plot(kind='bar', ax=axes[i, 3])
        axes[i, 3].set_title(f"Bar Graph for {column}")
    
    plt.tight_layout()
    plt.show()

# Call the function
analyze_numerical_columns_subplots(df, numerical_columns)

