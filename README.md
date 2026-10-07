# Data-Visualisation

🚖 Taxi Trip Data Analysis

Data cleaning, exploration and visualization of the Seaborn taxis dataset using Pandas, Matplotlib and Seaborn.

📌 Project Overview

Taxi services generate large volumes of trip data every day. Raw data usually contains missing values and is hard to interpret without analysis. In this project I act as a data analyst to:

Load and inspect the taxi dataset
Detect and handle missing values
Visualize trends in fare, distance, tips and customer behavior

🗂 Dataset

Loaded directly from Seaborn:

python
import seaborn as sns
df = sns.load_dataset("taxis")

The dataset contains 6,433 trips and 14 columns, including pickup, dropoff, passengers, distance, fare, tip, tolls, total, payment, pickup_zone, dropoff_zone, pickup_borough and dropoff_borough.

🧹 Handling Missing Values

Columns with missing data:

Column	Missing	Strategy

payment	44	Imputed with mode

dropoff_zone	45	Imputed with mode

dropoff_borough	45	Imputed with mode

pickup_zone	26	Rows dropped (critical)

pickup_borough	26	Rows dropped (critical)

Reasoning:

Pickup location is used for grouping and colouring in many plots, and guessing it would distort borough-level results, so those rows were removed (6,433 → 6,407 rows).

Other categorical columns are imputed with the mode; the script also handles numeric columns with the median if any are missing.

After cleaning, the dataset has 0 missing values.

📊 Visualizations

Matplotlib / Pandas Plot

Chart	Description	Output

Line chart	Fare over time (pickup converted to datetime)

Bar chart	Total fare per pickup_borough	

Pie chart	Trip share by payment method	

Histogram	Distribution of distance (40 bins)	

Seaborn
Chart	Description	Output
Count plot	Trips per pickup_borough

Violin plot	fare distribution by payment method

🔍 Key Takeaways

Add your own observations after viewing the plots, for example:

Which borough generates the most total fare and the most trips?

How strongly do distance and fare correlate (see scatter plot and heatmap)?

Which payment method is most common, and how do tips differ by borough?

🛠 Tech Stack

Python 3

Pandas

Matplotlib

Seaborn


