# Loan_case_stu
corr = loan[['loan_amnt', 'int_rate', 'annual_inc', 'installment']].corr()
sns.heatmap(corr, annot=True, cmap='viridis')
plt.title('Correlation Matrix')
plt.show()



scatter_matrix(loan[['loan_amnt', 'int_rate', 'annual_inc', 'installment']].dropna(), figsize=(8, 8))
plt.suptitle('Scatter Matrix of Key Features')
plt.show()
