# Social Network Data Analyzer

A Python-based data analysis project that explores and analyzes social network data using JSON datasets.

The project demonstrates how raw social-network data can be loaded, explored, cleaned, and analyzed to discover relationships between users and pages. It also implements a **"People You May Know"** recommendation system based on mutual friends.

---

## 📌 Project Overview

Social-network datasets contain information about users, friendships, and pages they interact with.

This project focuses on processing such data using Python and answering questions such as:

- Who are the users in the network?
- Who is connected to whom?
- Which users have incomplete or duplicate data?
- How can the dataset be cleaned?
- Who might a user know based on mutual friends?
- Which pages are available in the network?

The project follows a simple data-analysis workflow:

**Raw Data → Data Exploration → Data Cleaning → Relationship Analysis → Recommendations**

---

# 🔄 Project Workflow

![Project Workflow](images/workflow.png)

## 🚀 Features

### 1. Load JSON Data

The project loads social-network data from JSON files using Python's built-in `json` module.

# 2. Explore User Data

The project displays:

- User ID
- User name
- Friend connections
- Liked pages

# 3. Data Cleaning

The dataset is cleaned by:

- Removing users with missing names
- Removing duplicate friend connections
- Removing inactive users
- Removing duplicate pages

# 4. Social Network Analysis

User friendships are represented as relationships between users.

The project creates a user-to-friends mapping to make relationship analysis easier.

# 5. People You May Know

The project recommends potential friends using a **mutual-friend approach**.

If two users have common friends, they can be considered potential connections.

For example:

```text
User 10
   |
   ├── User 20
   │      |
   │      └── User 30
   |
   └── User 40
          |
          └── User 30
```

# 🧠 Recommendation Logic
The recommendation system works using the following approach:
1. Select a user.
2. Find the user's direct friends.
3. Find the friends of those friends.
4. Remove:  
        - The original user  
        -  Users who are already direct friends  
5. Count how many mutual friends each candidate has.  
6. Rank candidates by the number of mutual friends.  
The more mutual friends a candidate has, the higher the candidate appears in the recommendation list.


# 📊 Example
For a given user:  
Recommendations for User 10:  
```
User 25 → 4 mutual friends  

User 18 → 3 mutual friends  

User 7  → 2 mutual friends  
``` 
This means User 25 has the strongest mutual connection with User 10 among the recommended users.


# 🗂️ Project Structure

```
social-network-data-analyzer/
│
├── data/
│   ├── data.json
│   ├── data2.json
│   ├── cleaned_data2.json
│   └── massive_data.json
│
├── notebooks/
│   ├── 01_Initialphase.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_people_you_may_know.ipynb
│   └── 04_pages_you_might_like.ipynb
│
├── images/
│   ├── workflow.png
│   └── recommendation-output.png
│
├── README.md
└── .gitignore
```

# 📁 Dataset

The project uses JSON files containing information about users, friendships, and pages.  
A typical user record contains information such as:

```
{
    "id": 1,
    "name": "User Name",
    "friends": [2, 3, 4],
    "liked_pages": [101, 102]
}
```

A page record contains information such as:
```
{
    "id": 101,
    "name": "Technology"
}
```

```
```

# 🧹 Data Cleaning
Data cleaning is performed before analysis to improve the quality of the dataset.  
The cleaning process includes:   

Remove Missing Names  
Users whose names are empty or contain only whitespace are removed.  

Remove Duplicate Friends  
Duplicate friend IDs are removed from each user's friend list.

Remove Inactive Users
Users without friends or liked pages are removed from the dataset.
Remove Duplicate Pages
Pages with duplicate IDs are reduced to a single record.

# 📓 Jupyter Notebooks
The analysis is organized into multiple notebooks.
01_Initialphase.ipynb
Initial exploration and understanding of the social-network dataset.
02_data_cleaning.ipynb
Cleans and prepares the dataset for further analysis.
03_people_you_may_know.ipynb
Implements the mutual-friend recommendation logic.
04_pages_you_might_like.ipynb
Explores page-related information and potential page recommendations.

# 🛠️ Technologies Used
Python
Jupyter Notebook
JSON
Data Cleaning
Data Structures
Graph-based Relationship Analysis
Python Concepts
The project uses:
Lists
Dictionaries
Sets
Loops
Functions
List comprehensions
Sorting
File handling
JSON processing

# ⏱️ Algorithm Complexity
The recommendation algorithm depends on the number of direct friends, their connections, and the number of generated recommendation candidates.
The main operations include:
Building the user-friend mapping
Traversing friends-of-friends
Counting mutual connections
Sorting recommendation candidates
The sorting step takes:
O(S log S)
where S is the number of recommendation candidates.
The overall cost therefore depends on the structure and density of the social network.

# 🎯 Learning Objectives
This project helped demonstrate practical applications of:
Python data structures
JSON data processing
Data cleaning
File handling
Social-network relationships
Graph-style traversal
Recommendation logic
Jupyter Notebook workflows

# 🔮 Future Improvements  
Possible improvements include:
Add page recommendation based on liked pages
Build interactive network visualizations
Add NetworkX for graph analysis
Add Pandas for structured data analysis
Create user-specific recommendation reports
Add recommendation scores
Build a Streamlit dashboard
Add unit tests
Support larger datasets
Improve recommendation ranking using multiple signals

# 📌 Key Takeaway  
This project demonstrates how Python can be used to transform raw social-network data into meaningful insights.
It combines data loading, data cleaning, relationship analysis, and recommendation logic into a practical social-network analytics workflow.

# 👨‍💻 Author  
Mandeep Kumar 


