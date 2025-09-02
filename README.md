<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Employee Salary Prediction — Project Overview</title>
  <meta name="description" content="Employee Salary Prediction using the Adult Census Income dataset. Clean data, train ML models, compare performance, and deploy with Streamlit." />
  <style>
    :root{
      --bg:#0b1020; --card:#121936; --ink:#e7ecff; --muted:#aeb8d0; --brand:#6aa7ff; --accent:#c3ff6a;
      --line:rgba(255,255,255,.08);
    }
    *{box-sizing:border-box}
    body{margin:0; font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial, "Apple Color Emoji", "Segoe UI Emoji"; background:linear-gradient(180deg,#0a0f1e, #0e1430 25%, #0a0f1e 100%); color:var(--ink);}
    a{color:var(--brand); text-decoration:none}
    a:hover{opacity:.9; text-decoration:underline}
    .wrap{max-width:980px; margin:0 auto; padding:28px 20px 60px}
    header{display:flex; gap:18px; align-items:center; justify-content:space-between; padding:18px 0 8px; border-bottom:1px solid var(--line); position:sticky; top:0; backdrop-filter:saturate(140%) blur(6px); background:linear-gradient(180deg, rgba(10,15,30,.9), rgba(10,15,30,.6));}
    .title{display:flex; align-items:center; gap:14px}
    .badge{display:inline-flex; align-items:center; gap:8px; padding:8px 12px; border:1px solid var(--line); border-radius:999px; background:rgba(255,255,255,.03); font-size:12px; color:var(--muted)}
    .grid{display:grid; gap:16px}
    @media(min-width:840px){.grid{grid-template-columns:1.2fr .8fr}}
    .card{background:linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.02)); border:1px solid var(--line); border-radius:18px; padding:20px; box-shadow:0 10px 30px rgba(0,0,0,.25)}
    h1{font-size:28px; margin:0}
    h2{font-size:20px; margin:0 0 10px}
    h3{font-size:16px; margin:18px 0 8px; color:var(--accent)}
    p{color:#dfe6ff; line-height:1.65}
    ul{margin:10px 0 0 18px}
    code, pre{font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;}
    pre{background:#0a1126; color:#e9f2ff; padding:14px; border:1px solid var(--line); border-radius:12px; overflow:auto}
    .toc{display:flex; flex-wrap:wrap; gap:10px}
    .toc a{border:1px solid var(--line); padding:8px 10px; border-radius:10px; background:rgba(255,255,255,.03)}
    .kpi{display:grid; grid-template-columns:repeat(3,1fr); gap:12px}
    .pill{border:1px dashed var(--line); padding:10px 12px; border-radius:12px; color:var(--muted)}
    .footer{margin-top:26px; color:var(--muted)}
    .callout{border:1px solid var(--line); background:rgba(99,255,106,.06); padding:12px 14px; border-radius:12px}
    .tag{display:inline-block; padding:3px 8px; border:1px solid var(--line); border-radius:999px; margin:4px 6px 0 0; color:var(--muted)}
    details{border:1px solid var(--line); background:rgba(255,255,255,.02); padding:12px 14px; border-radius:12px}
    summary{cursor:pointer; font-weight:600}
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="title">
        <svg width="34" height="34" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M4 12a8 8 0 1 1 16 0v6a2 2 0 0 1-2 2h-3.5a.5.5 0 0 1-.5-.5V13h-4v6.5a.5.5 0 0 1-.5.5H6a2 2 0 0 1-2-2v-6Z" stroke="#c3ff6a" stroke-width="1.2"/><path d="M8 10a4 4 0 1 1 8 0" stroke="#6aa7ff" stroke-width="1.2"/></svg>
        <h1>Employee Salary Prediction — Project Overview</h1>
      </div>
      <span class="badge">ML • Classification • Streamlit</span>
    </header>

    <div class="grid" style="margin-top:18px">
      <section class="card">
        <h2 id="about">About</h2>
        <p>This project predicts whether an employee’s annual income is <strong>&gt;50K</strong> or <strong>≤50K</strong> using the Adult Census Income dataset. The pipeline covers data cleaning, encoding, outlier handling, model training & evaluation, and a simple Streamlit app for interactive predictions.</p>
        <div class="kpi">
          <div class="pill">Dataset: Adult Census Income</div>
          <div class="pill">Task: Binary Classification</div>
          <div class="pill">Output: <code>best_model.pkl</code> + Streamlit UI</div>
        </div>
        <div style="margin-top:10px" class="toc">
          <a href="#features">Features</a>
          <a href="#workflow">Workflow</a>
          <a href="#run">How to Run</a>
          <a href="#results">Results</a>
          <a href="#app">Streamlit App</a>
          <a href="#future">Future Scope</a>
          <a href="#structure">Repo Structure</a>
        </div>
      </section>

      <aside class="card">
        <h2>Quick Facts</h2>
        <ul>
          <li>Handles missing values (e.g., <code>?</code> → <em>Others</em>)</li>
          <li>Removes redundant columns (e.g., <code>education</code>)</li>
          <li>Outlier clipping for <code>age</code>, <code>educational-num</code>, <code>hours-per-week</code></li>
          <li>Label-encodes categorical features</li>
          <li>Compares multiple ML algorithms</li>
        </ul>
        <div style="margin-top:10px">
          <span class="tag">Logistic Regression</span>
          <span class="tag">Random Forest</span>
          <span class="tag">KNN</span>
          <span class="tag">SVM</span>
          <span class="tag">Gradient Boosting</span>
        </div>
      </aside>
    </div>

    <section id="features" class="card" style="margin-top:16px">
      <h2>Key Features</h2>
      <ul>
        <li>End‑to‑end ML pipeline: preprocess → train → evaluate → save best model</li>
        <li>Clean handling of noisy categories like <code>workclass</code> and <code>occupation</code></li>
        <li>Model leaderboard with bar‑chart comparison (accuracy)</li>
        <li>Interactive Streamlit app with single and batch prediction (CSV upload)</li>
      </ul>
    </section>

    <section id="workflow" class="card" style="margin-top:16px">
      <h2>Workflow</h2>
      <ol>
        <li><strong>Load & Inspect</strong> the dataset (<code>adult.csv</code>), view head/tail/shape.</li>
        <li><strong>Clean & Encode</strong>: replace <code>?</code> → <em>Others</em>, drop redundant <code>education</code>, label-encode categoricals.</li>
        <li><strong>Outliers</strong>: visualize with boxplots; clip ranges for <code>age</code> (17–75), <code>educational-num</code> (5–16), etc.</li>
        <li><strong>Split</strong> into train/test; fit multiple models (LR, RF, KNN, SVM, GB).</li>
        <li><strong>Evaluate</strong> using accuracy & classification report; plot model comparison.</li>
        <li><strong>Persist</strong> the best model with Joblib → <code>best_model.pkl</code>.</li>
        <li><strong>Deploy</strong> a basic Streamlit app (<code>app.py</code>) for interactive predictions.</li>
      </ol>
    </section>

    <section id="run" class="card" style="margin-top:16px">
      <h2>How to Run Locally</h2>
      <h3>1) Setup</h3>
      <pre><code>python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt  # or: pandas numpy scikit-learn matplotlib streamlit joblib</code></pre>
      <h3>2) Train & Save Best Model</h3>
      <pre><code>python train.py  # if you keep training logic in a script
# or run the notebook cells to generate best_model.pkl</code></pre>
      <h3>3) Launch Streamlit App</h3>
      <pre><code>streamlit run app.py</code></pre>
      <div class="callout" style="margin-top:8px">
        Tip: Ensure <code>adult.csv</code> is present or update the path in your code.
      </div>
    </section>

    <section id="results" class="card" style="margin-top:16px">
      <h2>Results</h2>
      <p>The notebook benchmarks multiple algorithms and visualizes accuracy in a bar chart. The top performer is saved as <code>best_model.pkl</code> and used by the app. (Exact scores will depend on your train/test split and preprocessing choices.)</p>
      <details style="margin-top:8px">
        <summary>What affects accuracy?</summary>
        <ul>
          <li>Encoding scheme and handling of rare categories</li>
          <li>Outlier treatment and feature selection</li>
          <li>Random state used for data splits</li>
          <li>Hyperparameters (e.g., trees in Random Forest, C/gamma for SVM)</li>
        </ul>
      </details>
    </section>

    <section id="app" class="card" style="margin-top:16px">
      <h2>Streamlit App (Usage)</h2>
      <ul>
        <li>Fill sidebar fields (age, occupation, hours-per-week, etc.) for single prediction.</li>
        <li>Upload a CSV for batch predictions and download the results.</li>
        <li>Behind the scenes, inputs are transformed to match training encodings before inference.</li>
      </ul>
      <pre><code># Example: run app
streamlit run app.py</code></pre>
    </section>

    <section id="future" class="card" style="margin-top:16px">
      <h2>Future Scope</h2>
      <ul>
        <li>Hyperparameter tuning (Grid/Random Search, Optuna)</li>
        <li>Advanced models (XGBoost/LightGBM, simple neural nets)</li>
        <li>Improved categorical handling (Target/One‑Hot encoding)</li>
        <li>Model monitoring & drift checks; logging with MLflow</li>
        <li>Containerize & deploy to cloud (Streamlit Cloud / Hugging Face / AWS)</li>
      </ul>
    </section>

    <section id="structure" class="card" style="margin-top:16px">
      <h2>Suggested Repo Structure</h2>
      <pre><code>employee-salary-prediction/
├─ data/
│  └─ adult.csv
├─ notebooks/
│  └─ employee_salary_prediction.ipynb
├─ app.py
├─ train.py               # (optional) script form of training
├─ best_model.pkl         # created after training
├─ requirements.txt
└─ README.html            # this file (GitHub preview-friendly)
</code></pre>
    </section>

    <p class="footer">© 2025 • Employee Salary Prediction • Built by Sejal Karnwal</p>
  </div>
</body>
</html>
