------------------------------------------------------------------------
Unsupervised Learning and Dimensionality Reduction on Wine and Student Data
------------------------------------------------------------------------
This repository contains the code used to explore unsupervised learning 
algorithms – mainly clustering and dimensionality reduction. The code is written
in Python and uses scikit-learn library for algorithms and matplotlib, seaborn,
and yellowbrick for plots and analyses.

All code and documentation is written by Patricia Bata while the data used was 
obtained from the UCI database.

------------------------------------------------------------------------
Running the Code
------------------------------------------------------------------------
To run the code, you need to have Python 3.7 or higher installed on your
machine. You can install the required packages by running the following
command in the terminal:

```
pip install -r requirements.txt
```

After installing the required packages, you can rerun the Jupyter notebook
`eda.ipynb` to replicate results from parts 1-3. Neural network results can
be replicated by running the following command in the terminal:

```
python main.py --data {dataset} --model {model_name} --tune {tuning_type}
```

where:
- `{dataset}` is the name of the dataset to use (either `student` or `wine`)
- `{model_name}` is the name of the model to use (restricted to `nn`
- `{tuning_type}` is the type of tuning to use (either `initial`, `gridsearch`, or `final`)
    - `initial` runs the model with learning (params) and validation curves (hyperparams)
    - `gridsearch` runs the model with the grid search tuning parameters (hyperparams)
    - `final` runs the model with the final tuning parameters (params)

To change configuration of models, you can modify `wine.yml` in the `configs/`
directory.

All results from experiments were saved into CSV files where the plots in
results/ are based on.

------------------------------------------------------------------------
Directory Structure
------------------------------------------------------------------------
The directory structure of the repository is as follows:
```
unsupervised-learning
|--configs/                     - configuration files for the models
    |--wine.yaml
|--src/                         - source code for the project
    |--utils                    - dataset cleaning and parsing functions
        |--DataSetup.py
        |--eval_utils.py
        |--parsing_utils.py
    |--clustering               - clustering related helper functions
        |--modeling.py
    |--models                   - machine learning model helper functions
        |--cluster_utils.py
  |--data/                      - dataset files (* denotes the files used)
      |--wine-data/
          |--wine.data*
          |--wine.names
      |--student-data/
          |--student.csv*
          |--student-por.csv
          |--student-merge.R
|--*results/                    - results of the report
|--analysis-report.pdf          - report of the analysis
|--main.py                      - main file to run the NN on terminal
|--eda.ipynb                    - exploratory data analysis notebook
|--requirements.txt             - required packages for the project
|--README.md
```

* The results of this assignment are compressed and uploaded separately
to OneDrive due to its large file size. 
------------------------------------------------------------------------
References
------------------------------------------------------------------------
- Wine Data Set: https://archive.ics.uci.edu/ml/datasets/wine
- Student Performance Data Set: https://archive.ics.uci.edu/ml/datasets/student+performance