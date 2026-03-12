# 🖥️ Coders of Delhi — CodeBook Social Network Analysis

> A pure Python data science project simulating a social media platform for coders.  
> **No pandas. No NumPy. Just Python.**

---

## 📌 About This Project

CodeBook is a fictional social media platform built for coders in Delhi. This project simulates the role of a **Data Scientist Intern** tasked with analyzing raw user data and building intelligent features from scratch — using only Python's built-in tools.

The project progresses in four stages: loading data, cleaning it, then building two recommendation features — one based on social graph analysis (mutual friends) and one based on collaborative filtering (shared page interests). Together, these mirror the kind of features found in production social networks like LinkedIn or Facebook.

---

## 🗂️ Project Structure
```
Coders-of-Delhi/
│
├── notebooks/
│   ├── 01_Introduction.ipynb          # Load and explore user data
│   ├── 02_data_cleaning.ipynb         # Clean messy, real-world data
│   ├── 03_people_you_may_know.ipynb   # Friend recommendation algorithm
│   └── 04_pages_you_might_like.ipynb  # Page recommendation via collaborative filtering
│
├── data/
│   ├── coders.json                    # Base dataset
│   ├── coders2.json                   # Dirty dataset (used for cleaning)
│   └── cleaned_coders2.json           # Output of data cleaning notebook
│
├── docs/
│   └── Coders_of_Delhi.pdf            # Full project brief and documentation
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

## 📓 Notebook Breakdown

### 01 — Introduction
Load and explore the CodeBook dataset. We create a JSON file containing user profiles, friend connections, and liked pages, then write a function to display this data in a readable, structured format.

**Key concepts:** JSON creation, file I/O, dictionary traversal

---

### 02 — Data Cleaning
Real data is never perfect. We take a dirty version of the dataset and systematically clean it by:
- Removing users with missing names
- Eliminating duplicate friend entries
- Dropping inactive users (no friends and no liked pages)
- Deduplicating pages with repeated IDs

**Key concepts:** List comprehensions, sets, dictionary deduplication

---

### 03 — People You May Know
Builds the classic social media feature — suggesting new connections based on mutual friends. The more mutual friends two users share, the higher the recommendation priority.

**Logic:** If A → B and B → C, and A and C aren't friends, suggest C to A.

**Key concepts:** Graph thinking, dictionary lookups, sorting by frequency

---

### 04 — Pages You Might Like
Recommends pages to users based on shared interests with other users. If two users like some of the same pages, they likely share broader interests — so we suggest each other's pages to them.

This is a simplified but real implementation of **collaborative filtering** — the same concept used by Netflix, Spotify, and LinkedIn.

**Key concepts:** Set intersection, similarity scoring, sorted recommendations

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/Coders-of-Delhi.git
cd Coders-of-Delhi
```

**2. No installations needed**

This project uses only Python's standard library. Just make sure you have **Python 3.8+** installed.
```bash
python --version
```

**3. Launch Jupyter and run notebooks in order**
```bash
jupyter notebook
```

Open the `notebooks/` folder and run them from `01` to `04`.

> ⚠️ Make sure the `data/` folder is in the same directory as your notebooks, or update the file paths inside the notebooks accordingly.

---

## 📊 Sample Data

The dataset contains 4 users — **Amit, Priya, Rahul, and Sara** — with friend connections and liked pages across categories like Python, Data Science, AI/ML, and Web Development.

`coders2.json` contains intentionally dirty data (blank names, duplicate friends, inactive users, duplicate page IDs) used to demonstrate the data cleaning process.

---

## 🧠 Concepts Covered

| Concept | Where Used |
|---|---|
| JSON parsing | All notebooks |
| File I/O | Notebook 01, 02 |
| List comprehensions | Notebook 02 |
| Sets and deduplication | Notebook 02, 03 |
| Dictionary operations | Notebook 03, 04 |
| Graph-based social network logic | Notebook 03 |
| Collaborative filtering | Notebook 04 |
| Sorting with lambda functions | Notebook 03, 04 |

---

## 📋 Requirements

No external libraries required. This project runs entirely on Python's standard library.
```
Python >= 3.8
jupyter (to run .ipynb notebooks)
```

To install Jupyter if you don't have it:
```bash
pip install notebook
```

---

## 📄 Documentation

The full project brief — including problem statements, logic explanations, and expected outputs — is available in [`docs/Coders_of_Delhi.pdf`](docs/Coders_of_Delhi.pdf).

---

## 👤 Author

**Akhilesh Kumar Shukla**  
Aspiring Data Scientist | Jharkhand, India  
[LinkedIn](#) · [GitHub](#)

---

## 📜 License

This project is licensed under the MIT License — feel free to use, modify, and share.
