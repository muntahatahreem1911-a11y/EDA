Task 1 - Exploratory Data Analysis (Titanic)

CodeNova AI/ML Internship, Batch 01.

Dataset: Titanic passengers (891 rows, public CSV in data/). Notebook: eda.ipynb is fully executed, with markdown commentary under every visualization. High-resolution images are in figures/.

Cleaning decisions
Column	Issue	Treatment	Why
Cabin	77% missing	Dropped, kept HasCabin flag	Imputing most of a column invents data; missingness itself is informative
Age	20% missing	Median by (Pclass, Sex)	Skewed variable; group medians keep class/sex structure
Embarked	2 missing	Mode	0.2% missing, negligible impact
Fare	13% IQR outliers	Kept, log scale for plots	Outliers are genuine first-class fares
Key insights
Survival: 74% women vs 19% men; 63% / 47% / 24% for 1st / 2nd / 3rd class. The class gradient holds within each sex (e.g. 3rd-class men 14%).
Children (0-12) survived most (58%); passengers over 60 least (23%).
Small families (2-4 people) survived more than solo travelers (30%) or families of 5+.
Pclass and Fare are strongly related, so beware multicollinearity in models.
Screenshots / Results

Survival rates by sex, class and age group Survival rates

Correlation heatmap Correlation heatmap

Feature distributions Distributions

Boxplots Boxplots

Pairwise scatter plots Pairplot

Run
bash
pip install -r requirements.txt
jupyter notebook eda.ipynb
