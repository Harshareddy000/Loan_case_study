# Loan_case_study
# List of numerical columns
numerical_columns = ['col1', 'col2', 'col3']  # Replace with your numerical columns

# Function for univariate analysis of numerical columns
def analyze_numerical_columns(data, numerical_columns):
    for column in numerical_columns:
        plt.figure(figsize=(12, 6))
        
        # KDE plot
        sns.kdeplot(data[column], shade=True)
        plt.title(f"KDE Plot for {column}")
        plt.show()
        
        # Histogram
        data[column].hist(bins=30)
        plt.title(f"Histogram for {column}")
        plt.show()
        
        # Boxplot
        sns.boxplot(x=data[column])
        plt.title(f"Boxplot for {column}")
        plt.show()
        
        # Bar graph (value counts)
        data[column].value_counts().plot(kind='bar')
        plt.title(f"Bar Graph for {column}")
        plt.show()

# Call the function
analyze_numerical_columns(df, numerical_columns)

# List of categorical columns
categorical_columns = ['cat_col1', 'cat_col2', 'cat_col3']  # Replace with your categorical columns

# Function for univariate analysis of categorical columns
def analyze_categorical_columns(data, categorical_columns):
    for column in categorical_columns:
        plt.figure(figsize=(12, 6))
        
        # Count plot
        sns.countplot(x=data[column])
        plt.title(f"Count Plot for {column}")
        plt.show()
        
        # Pie chart
        data[column].value_counts().plot.pie(autopct='%1.1f%%', startangle=90, figsize=(8, 8))
        plt.title(f"Pie Chart for {column}")
        plt.ylabel('')
        plt.show()

# Call the function
analyze_categorical_columns(df, categorical_columns)
