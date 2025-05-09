# 🏆 Kaggle

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Maintained by @pesnik](https://img.shields.io/badge/Maintained%20by-@pesnik-blueviolet)
[![Kaggle](https://img.shields.io/badge/Kaggle-Profile-teal)](https://www.kaggle.com/yourprofile)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)

A battle-tested template for systematic Kaggle competitions and data science projects. Designed by [@pesnik](https://github.com/pesnik) to maximize reproducibility, modularity, and knowledge retention. Powered by `uv` for fast and efficient Python package management.

```bash
# 🚀 Quick Start
1. Fork this repo
2. Clone your fork: git clone https://github.com/pesnik/kaggle.git
3. Install uv: pip install uv
4. Create virtual environment: uv venv
5. Activate environment: source .venv/bin/activate (Linux/macOS) or .venv\Scripts\activate (Windows)
6. Install dependencies: uv pip install -r requirements.txt
7. Start new competition: ./scripts/init_competition.sh <competition_name>
```

## 🌟 Why This Structure?

✔ **Modular** - Reuse components across competitions  
✔ **Reproducible** - Version-controlled data/code with `uv` for dependency management  
✔ **Documented** - Knowledge never gets lost  
✔ **Scalable** - From solo hackathons to team projects  

---

## 🏗 Full Repository Structure

```bash
kaggle/
│
├── .github/                  # GitHub Automation
│   └── workflows/            # CI/CD pipelines
│       ├── tests.yml         # Automated testing
│       └── data-checks.yml   # Data validation
│
├── config/                   # Centralized Control
│   ├── paths.py              # OS-agnostic path management
│   └── params/              # Hyperparameter storage
│       ├── base.yaml         # Shared configs
│       └── competition1/     # Competition-specific
│           ├── model.yaml
│           └── features.yaml
│
├── data/                     # Immutable Data Flow
│   ├── raw/                  # Original untouched data
│   ├── external/             # Third-party supplements
│   ├── interim/              # Cleaned/merged data
│   └── processed/            # Feature-engineered final
│
├── docs/                     # Knowledge Management
│   ├── experiment_logs/      # Detailed run records
│   ├── methodology/         # Technical approach
│   ├── references/          # Research papers
│   └── cheatsheets/         # Quick references
│
├── notebooks/                # Interactive Workspace
│   ├── exploration/          # EDA playground
│   │   └── scratchpad.py     # Quick experiments (Marimo or Jupyter)
│   ├── competitions/         # Organized by event
│   │   └── titanic/
│   │       ├── 01_eda.py
│   │       └── 02_baseline.py
│   └── prototyping/         # Model experiments
│       └── proof_of_concept.py
│
├── reports/                  # Final Deliverables
│   ├── figures/             # Visual assets
│   │   ├── eda/            # Exploration plots
│   │   └── final/          # Publication-ready
│   ├── slides/             # Presentation decks
│   └── competition_summary.md
│
├── src/                      # Production Code
│   ├── data/                # Data pipelines
│   │   ├── make_dataset.py
│   │   └── process_features.py
│   ├── features/            # Feature engineering
│   │   ├── transformations.py
│   │   └── selection.py
│   ├── models/              # ML components
│   │   ├── train.py
│   │   └── predict.py
│   └── visualization/       # Plot utilities
│       └── plot_utils.py
│
├── templates/                # Quickstart Blueprints
│   ├── new_competition/
│   │   ├── config.yaml
│   │   ├── report.md
│   │   └── README.md
│   └── notebooks/
│       ├── EDA_template.py
│       ├── modeling.py
│       └── submission.py
│
├── models/                   # Model Storage
│   ├── titanic/             # Organized by competition
│   │   ├── model_v1.pkl
│   │   └── metrics.json
│   └── versioning/         # Experiment tracking
│       └── mlflow/
│
├── scripts/                  # Automation
│   ├── setup/
│   │   ├── init_competition.sh
│   │   └── download_data.py
│   └── reporting/
│       └── generate_report.py
│
├── submissions/              # Competition Outputs
│   └── titanic/
│       ├── submission_v1.csv
│       └── leaderboard.txt
│
├── tests/                    # Quality Assurance
│   ├── unit/                # Isolated tests
│   │   ├── test_data.py
│   │   └── test_features.py
│   └── integration/         # System tests
│       └── test_pipeline.py
│
├── .gitignore               # Version control
├── requirements.txt         # Pip dependencies for uv
├── pyproject.toml           # Build configuration
├── LICENSE                  # Usage terms
└── README.md                # Project compass
```

---

## 🛠️ @pesnik's Pro Toolkit

### 🔄 Data Versioning
```bash
# Using DVC (Data Version Control)
dvc add data/raw/titanic.csv
dvc push origin
```

### 📊 Experiment Tracking
```python
# Sample MLflow logging
import mlflow
mlflow.log_params(params)
mlflow.log_metric("accuracy", 0.92)
mlflow.sklearn.log_model(model, "model")
```

### 🧹 Code Quality
```yaml
# .pre-commit-config.yaml
repos:
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.4.0
  hooks:
    - id: check-yaml
    - id: trailing-whitespace
```

### 📈 Workflow Automation
```bash
# Makefile example
train:
    python src/models/train.py --config config/params.yaml

visualize:
    python src/visualization/plot.py --input data/processed --output reports/figures
```

### ⚡ Using `uv` for Dependency Management
```bash
# Create and activate a virtual environment
uv venv
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate     # Windows

# Install dependencies
uv pip install -r requirements.txt
```

---

## 🧭 Navigation Guide

| Directory          | When to Use                          | Pro Tip                                  |
|--------------------|--------------------------------------|------------------------------------------|
| **notebooks/**     | Initial exploration                  | Use Marimo for reactive notebooks; refactor to `src/` after prototyping |
| **src/**           | Reusable pipeline components         | Write unit tests for critical functions  |
| **templates/**     | Starting new competitions            | Customize for your common workflows     |
| **reports/**       | Final presentation                   | Use Jupyter Book for HTML exports       |
| **models/**        | Storing trained models              | Include evaluation metrics in filenames |

---

## 🤝 Contribution Roadmap

1. **Fork & Clone**
   ```bash
   git clone https://github.com/pesnik/kaggle.git
   cd kaggle
   ```

2. **Set Up Environment with `uv`**
   ```bash
   pip install uv
   uv venv
   source .venv/bin/activate  # Linux/macOS
   .venv\Scripts\activate     # Windows
   uv pip install -r requirements.txt
   ```

3. **Start Developing**
   ```bash
   # For new competition
   ./scripts/setup/init_competition.sh housing-prices
   ```

4. **Submit Changes**
   ```bash
   git checkout -b feature/new-model
   git commit -m "Add XGBoost baseline"
   git push origin feature/new-model
   ```

---

## 📝 Notes on Tools

- **uv**: Used for fast Python package and environment management. Ensures lightweight, reproducible setups.
- **Marimo**: Preferred for interactive notebooks in `notebooks/` (saved as `.py` files) for reactivity and collaboration. Jupyter notebooks are supported for legacy or specialized tasks.
- **DVC/MLflow**: Integrated for data versioning and experiment tracking, enhancing reproducibility.

---

## 📜 License

MIT © [@pesnik](https://github.com/pesnik)  
Kaggle datasets belong to their respective owners

---

> "Data science is 80% preparation, 15% frustration, and 5% elation."  
> — Adapted by @pesnik from a Kaggle discussion
