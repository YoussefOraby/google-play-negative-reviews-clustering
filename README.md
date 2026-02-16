# Google Play Negative Reviews Clustering (NLP Project)

##  Project Overview

App publishers need to understand why users leave negative reviews.
This project applies Natural Language Processing (NLP) and Unsupervised Learning to cluster negative reviews from the Google Play Store into meaningful complaint categories.

The objective is to automatically discover the main issues users report.

---

##  Dataset

* Source: Google Play Store reviews dataset
* Filtered to include only negative reviews (score = 1 or 2)
* Text column used: `content`

---

##  Methodology

### 1️) Data Filtering

Selected only negative reviews based on the `score` column.

### 2️) Text Preprocessing

* Tokenization
* Lowercasing
* Removal of non-alphabetic tokens
* Stopword removal
* Rejoining cleaned tokens into text

### 3️) Feature Extraction

Used **TF-IDF (Term Frequency–Inverse Document Frequency)** to convert text into numerical feature vectors.

### 4️) Clustering

Applied **K-Means clustering (k=5)** to group similar reviews together.

### 5️) Topic Interpretation

For each cluster:

* Summed TF-IDF scores
* Extracted top terms
* Interpreted complaint category

---

##  Results

The model identified 5 main complaint categories:

### Cluster 0 – Login & Account Issues

Top terms: account, create, login, google, microsoft
Users report problems related to account creation and login authentication.

### Cluster 1 – Subscription & Payment Issues

Top terms: version, premium, pay, paid, buy
Complaints about paid features and subscription limitations.

### Cluster 2 – Feature & Sync Issues

Top terms: calendar, sync, events, ads
Problems related to feature functionality and synchronization.

### Cluster 3 – App Functionality & Performance

Top terms: app, work, tasks, working
Issues related to core functionality and task management.

### Cluster 4 – Mixed / Mild Feedback

Top terms: good, fast, nice
Reviews containing mixed or mild complaints.

---

##  Technologies Used

* Python
* Pandas
* NumPy
* NLTK
* Scikit-learn

---

##  Key Takeaways

* Unsupervised learning can uncover meaningful structure in unlabelled text data.
* TF-IDF + KMeans effectively groups user complaints.
* The extracted clusters provide actionable insights for product improvement.
