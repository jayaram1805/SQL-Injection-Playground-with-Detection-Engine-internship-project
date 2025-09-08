#  Project Report  
## SQL Injection Playground

---

##  Introduction
In this project, I built a small web application to **show how SQL Injection works** and how we can fix it.  
SQL Injection is one of the most common attacks where someone can trick a database by entering special inputs in a login form.  

To make it simple, I used **Python with Flask** for the web app and **SQLite** for the database.  
My app has two parts:  
- A **vulnerable login page** where the attack works.  
- A **secure login page** where the attack fails because of safer code.  

---

##  Purpose of the Project
- To understand **what SQL Injection is** and why it’s dangerous.  
- To **practice how attackers exploit databases**.  
- To learn the correct way of writing queries using **parameterized queries**.  
- To connect my knowledge of **DBMS and security** in a practical way.  

---

## ⚙ Tools I Used
- **Python 3**  
- **Flask (Web Framework)**  
- **SQLite3 (Database)**  
- **Windows OS**  
- **Virtual Environment (venv)**  

---

##  Project Files
```
sql_injection_playground/
│── app.py        # Flask code
│── users.db      # SQLite database
│── README.md     # Project guide
│── report.md     # Project report
│── venv/         # Virtual environment
```

---

##  Default Login Users
When the app runs, it creates two users in the database:

- **Username:** admin | **Password:** admin123  
- **Username:** test  | **Password:** test123  

---

##  What I Did

###  Vulnerable Login (`/`)
- Here, the code directly puts user input into the SQL query.  
- Example query:
  ```sql
  SELECT * FROM users WHERE username = '<input>' AND password = '<input>';
  ```
- If I type this:
  ```
  Username: admin' --
  Password: anything
  ```
  I can log in without knowing the real password  
  (That’s SQL Injection in action).

---

###  Secure Login (`/secure`)
- Here, I fixed the problem by using **parameterized queries**.  
- Example query:
  ```sql
  SELECT * FROM users WHERE username=? AND password=?;
  ```
- Now if I try `admin' --`, it doesn’t work .  
- Only the real username and password let me log in.  

---

## What I Learned
- How easy it is to exploit badly written SQL queries.  
- Why **never trust user input** in web apps.  
- How to use **parameterized queries** to make apps safe.  
- Got some good hands-on practice with **Flask and SQLite**.  

---

##  Conclusion
This project gave me a clear idea of how SQL Injection works and how to prevent it.  
It connects directly with what I learned in **DBMS and security subjects**.  
Now I feel more confident about writing safer queries and building secure apps.  

---

##  Note
This project is just for **learning**.  
It should **not** be used in real-world applications without proper security.
