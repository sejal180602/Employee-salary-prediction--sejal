<h1> 💼 Employee Salary Prediction</h1>

<p>This project predicts whether an employee’s salary is <b> >50K or ≤50K  </b> per year based on demographic and work-related attributes. It uses the <b>Adult Census Income Dataset </b>and applies various machine learning models to build a robust salary classification system.</p>

<h2> 🚀 Project Workflow</h2>

<h4>1.Data Preprocessing</h4>
<ul>
<li>Loaded and cleaned the dataset (adult.csv)</li>

<li>Handled missing values (? replaced with "Others")</li>

<li>Removed irrelevant/redundant features (like education)</li>

<li>Treated outliers in features such as age, educational-num, hours-per-week, etc.</li>

<li>Encoded categorical variables using Label Encoding</li>
</ul>
<h4>2.Model Building & Training</h4>
<ul>
<li>Split dataset into train (80%) and test (20%)</li>

<li>Tested multiple algorithms:</li>

  <li>Logistic Regression</li>

  <li>Random Forest</li>

  <li>K-Nearest Neighbors (KNN)</li>

  <li>Support Vector Machine (SVM)</li>

  <li>Gradient Boosting</li>

<li>Evaluated models using accuracy score & classification report</li>

<li>Visualized model comparison with bar plots</li>
</ul>
<h4>3.Best Model Selection</h4>
<ul>
<li>Selected the best-performing model (saved as best_model.pkl using Joblib)</li>
</ul>
<h4>Deployment with Streamlit</h4>
<ul>
<li>Created a Streamlit web app (app.py) for interactive predictions</li>
</ul>
<ul>
<li>Features:</li>

<li>User input via sidebar (age, education, occupation, hours-per-week, experience)</li>

<li>Batch prediction using uploaded CSV files</li>

<li>Downloadable results</li>
</ul>
<h2>🛠️ Tech Stack</h2>
<ul>
<li>Python (Pandas, NumPy, Matplotlib, Scikit-learn, Joblib)</li>

<li>Streamlit (for deployment)</li>

<li>Machine Learning Models (Logistic Regression, Random Forest, KNN, SVM, Gradient Boosting)</li>
</ul>
<h2>📊 Results</h2>
<ul>
<li>Compared accuracy across multiple ML models</li>

<li>Selected the best-performing model for deployment</li>

<li>Deployed an easy-to-use web app to predict employee salary class</li>
</ul>
<h2>🌱 Future Scope</h2>
<ul>
<li>Hyperparameter tuning for higher accuracy</li>

<li>Integration with cloud platforms (AWS/GCP) for large-scale deployment</li>

<li>Adding more advanced models like XGBoost or Neural Networks</li>
</ul>
