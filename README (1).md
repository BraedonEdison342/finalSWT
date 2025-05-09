# Spaceship Titanic AI Prediction System
Jira: https://braedonedison0305.atlassian.net/jira/software/projects/SPACESHIP/boards/105/backlog

**Project Board & Contact**  
For full task tracking, issue reporting, and sprint planning, visit our Jira site at: https://yourcompany.atlassian.net/projects/SPACESHIP. You can create tickets there for bugs, feature requests, or general questions, and monitor development progress in real time.

**Formal Objective Breakdown**  
Our pipeline is organized into clear, incremental objectives:  
1. **Data Preprocessing** – load and clean the Kaggle CSV data, impute missing values, encode categoricals, and scale features.  
2. **Model Development** – train an XGBoost classifier (with configurable hyperparameters) on an 80/20 train/validation split.  
3. **Explainability** – compute SHAP global feature-importance and local force-plots, exported as an HTML report.  
4. **Interactive Dashboard** – deploy a Dash application to visualize predictions, performance metrics, and SHAP explanations, with filtering and export capability.

**Why This Software Matters**  
This project transforms raw interstellar passenger data into actionable insights. By accurately predicting which passengers were transported by the spacetime anomaly—and explaining “why” via SHAP—the system empowers rescue analysts to prioritize efforts and demonstrates best practices in reproducible ML, configuration management, and real-time monitoring. It’s a showcase of end-to-end data science, from ingestion through deployment, and a template for future anomaly-detection solutions.

**Getting Started: Download & Access**  
1. **Clone the Repo**  
   ```bash
   git clone https://github.com/yourusername/spaceship-titanic-ai.git
   cd spaceship-titanic-ai
   ```  
2. **Install Dependencies**  
   ```bash
   python3 -m venv venv
   source venv/bin/activate       # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```  
3. **Add Data & Configure**  
   - Download `train.csv`, `test.csv` from Kaggle and place them in `data/`.  
   - Edit `config.json` with your file paths, model settings, and Slack webhook (for alerts).  
4. **Run the Pipeline**  
   ```bash
   python src/pipeline.py --config config.json
   ```  
5. **Launch the Dashboard**  
   ```bash
   cd src/dashboard
   python app.py --config ../../config.json
   ```  
   Then open [http://localhost:8050](http://localhost:8050) in your browser.
