# HR Analytics: Employee Promotion Prediction

## 📋 Project Overview
This capstone project focuses on predicting employee promotions using machine learning techniques. The project analyzes HR data to identify patterns and key factors that influence employee promotion decisions, helping organizations make data-driven HR decisions.

## 🎯 Objective
To build a predictive model that can accurately identify employees who are likely to be promoted based on their performance metrics, demographics, and career history. This helps HR departments:
- Identify high-potential employees
- Make fair and objective promotion decisions
- Reduce bias in promotion processes
- Optimize talent management strategies

## 📊 Dataset
- **Training Data**: HR employee data with promotion outcomes
- **Test Data**: Employee data for prediction
- **Key Features**: 
  - Employee demographics (age, gender, education)
  - Performance metrics (KPIs, training scores, awards)
  - Career information (department, service length, recruitment channel)
  - Historical ratings and training records

## 🔧 Technologies Used
- **Programming Language**: Python
- **Libraries**: 
  - **Data Manipulation**: pandas, numpy
  - **Visualization**: matplotlib, seaborn
  - **Machine Learning**: scikit-learn, XGBoost
  - **Development**: Jupyter Notebook

## 🎯 Problem Statement
The dataset shows a significant class imbalance with most employees not being promoted, making this a challenging binary classification problem. The goal is to build a model that can effectively identify the minority class (promoted employees) while maintaining good overall accuracy.

## 📈 Key Findings from Exploratory Data Analysis
- **Class Imbalance**: Majority of employees are not promoted (highly imbalanced dataset)
- **Age Distribution**: Age shows a right-skewed distribution with promotion patterns
- **Strong Predictors**: 
  - KPIs met >80% (positive correlation with promotion)
  - Awards won (strong indicator of promotion)
  - Average training score (positive correlation)
- **Education Impact**: Different education levels show varying promotion rates
- **Department Variations**: Some departments have higher promotion rates than others

## 🔍 Data Preprocessing
1. **Missing Value Treatment**:
   - Education: Filled with "Bachelor's" (mode imputation)
   - Previous year rating: Filled with median (due to negative skewness)

2. **Feature Engineering**:
   - Label encoding for categorical variables (department, gender, education, recruitment_channel)
   - Removed irrelevant features (employee_id, region)

3. **Feature Selection**:
   - Selected 11 relevant features based on correlation analysis
   - Focused on features with meaningful business impact

## 🤖 Machine Learning Models
Implemented and compared three different algorithms:

### 1. XGBoost Classifier
- **Parameters**: n_estimators=200, max_depth=10, scale_pos_weight=13
- **Optimization**: Tuned for handling class imbalance

### 2. Random Forest Classifier
- **Parameters**: n_estimators=500, max_depth=10, min_samples_leaf=3
- **Configuration**: Bootstrap=False, optimized for minority class detection

### 3. Gradient Boosting Classifier
- **Parameters**: n_estimators=500, max_depth=10, learning_rate=0.1
- **Focus**: Sequential learning for better pattern recognition

## 📊 Model Performance Comparison

| Model | Predicted Promotions (Class 1) | Predicted Non-Promotions (Class 0) |
|-------|-------------------------------|-----------------------------------|
| XGBoost | 921 | 10,041 |
| Random Forest | 336 | 23,154 |
| Gradient Boosting | 1,221 | 22,269 |

**Key Observation**: The models show different sensitivity levels to the minority class, with XGBoost and Gradient Boosting being more aggressive in predicting promotions.

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.7+
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```

### Installation & Usage
1. Clone the repository
```bash
git clone https://github.com/yashwanth9381/Final_Capstone_project-.git
cd Final_Capstone_project-
```

2. Install required packages
```bash
pip install -r requirements.txt
```

3. Run the analysis
```bash
jupyter notebook F_Pro.ipynb
```

## 📁 Project Structure
```
Final_Capstone_project-/
├── F_Pro.py                 # Main analysis script
├── hr_test.csv             # Training dataset
├── PP11.csv                # Test dataset
├── submission_rf.csv       # Random Forest predictions
├── requirements.txt        # Dependencies
└── README.md              # This file
```

## 🎨 Visualizations Created
- **Distribution Analysis**: Age distribution and promotion patterns
- **Correlation Heatmap**: Feature relationships and importance
- **Count Plots**: Categorical variable analysis with promotion outcomes
- **Box Plots**: Education vs service length by promotion status
- **Scatter Plots**: Age vs service length colored by promotion

## 📝 Business Insights & Recommendations
1. **Focus on High Performers**: Employees meeting >80% KPIs are strong promotion candidates
2. **Recognition Programs**: Award-winning employees show higher promotion probability
3. **Training Investment**: Higher training scores correlate with promotion success
4. **Department Strategy**: Analyze department-specific promotion patterns for equity
5. **Balanced Approach**: Consider model ensemble to balance precision and recall

## 🔮 Future Improvements
- **Feature Engineering**: Create interaction features and polynomial terms
- **Advanced Algorithms**: Implement deep learning models for complex pattern recognition
- **Model Ensemble**: Combine multiple models for better performance
- **Real-time Prediction**: Build API for live promotion probability scoring
- **Fairness Analysis**: Implement bias detection and mitigation techniques

## ⚠️ Model Limitations
- **Class Imbalance**: Models may be conservative in predicting promotions
- **Data Sensitivity**: Performance depends on data quality and completeness
- **Temporal Factors**: Model doesn't account for time-based promotion cycles
- **External Factors**: Business conditions and policy changes not considered

## 📊 Model Evaluation Strategy
- **Primary Metric**: Recall score for identifying potential promotees
- **Secondary Metrics**: F1-score for balanced performance assessment
- **Business Impact**: Focus on reducing false negatives (missing promotion candidates)

## 🤝 Contributing
This project is part of my capstone work. Feedback and suggestions are welcome!
- Open issues for bugs or improvement suggestions
- Fork the repository for your own analysis
- Share insights from your HR analytics experience

## 📧 Contact
**Yashwanth**
- GitHub: [@yashwanth9381](https://github.com/yashwanth9381)
- Email: [Your email]
- LinkedIn: [Your LinkedIn profile]

## 🙏 Acknowledgments
- Thanks to the HR Analytics community for dataset insights
- Special acknowledgment to mentors and instructors for guidance
- Dataset providers for enabling this analysis

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

---
*This project demonstrates the application of machine learning in HR analytics, focusing on fair and data-driven promotion decisions. The analysis reveals key factors influencing employee promotions and provides actionable insights for HR strategy.*
