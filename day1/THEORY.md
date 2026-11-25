# Day 1: Set Up Python and Start the Project

## Today's Topics

1. What is this course project about?
2. Install Python and VS Code
3. Run a Python file and display text using `print`
4. Variables: store a product name, product code, and stock quantity
5. What is a SKU?
6. GitHub account and repository
7. First commit, push, README, and `.gitignore`
8. Important terms

---

## 1. What Is This Course Project About?

### Project Title

> **Inventory and Order Management System** for a small store

### The Project in One Sentence

> We build a program that helps a small store **keep track of its products, stock, and customer orders**.

### First, Understand the Words

| Word | Simple meaning | Example |
|---|---|---|
| **Inventory** | All the products a store has | Pens, notebooks, bags |
| **Stock** | The number of units available for sale | 25 notebooks |
| **Order** | A customer's request to buy products | 2 pens + 1 notebook |

### What Our System Will Do

- Keep a **product list** and track **stock**.
- Save **supplier** (who sells to the store) and **customer** details.
- Record **new stock** arriving at the store.
- Create **customer orders** with one or more products.
- Confirm an order **only if enough stock is available**.
- **Cancel** an order and return its stock (without counting it twice).
- Show **sales reports**, **low-stock reports**, and a **history of stock changes**.
- Add a **login** and simple **web pages** for the store operator (the person who runs the system).

### How We Will Build It

| Days | Topic | What we do |
|---|---|---|
| **Days 1–15** | **Python** | Learn programming and build the first version |
| **Days 16–22** | **SQL** | Store the data in a database |
| **Days 23–30** | **Flask** | Turn it into a web application |

> We start building the project **today**, and save our code to **GitHub** at the end of every class.

### Tools We Will Use

| Tool | What it is used for |
|---|---|
| **Python** | Write the rules and calculations |
| **SQLite** | Store products, customers, orders, and stock in a database |
| **Flask** | Build the web application |
| **VS Code** | Write and run our code |
| **Git and GitHub** | Save code changes and share the project |
| **Postman and pytest** | Check that the application works correctly |

---

## 2. Install Python and VS Code

### What Is Python?

**Python** is a programming language. We use it to give instructions to the computer.
It is simple to read, so it is great for beginners.

### What Is VS Code?

**VS Code (Visual Studio Code)** is a free code editor. It is the place where we **write** and **run** our code.

### Install Python

1. Go to [python.org/downloads](https://www.python.org/downloads/).
2. Download and run the installer.
3. **Windows only:** tick ✅ **"Add Python to PATH"** before clicking Install.

Check it works. Open a terminal (Command Prompt on Windows, Terminal on Mac) and type:

```bash
python --version
```

> On Mac, you may need to type `python3 --version`.

If you see a version number (for example `Python 3.13.0`), Python is installed.

### Install VS Code

1. Go to [code.visualstudio.com](https://code.visualstudio.com/).
2. Download and install it.
3. Open VS Code → go to **Extensions** (left side) → search **Python** → click **Install**.

### Install Git

We also need **Git** to save our code history.

1. Go to [git-scm.com/downloads](https://git-scm.com/downloads).
2. Download and install it.
3. Check it works:

```bash
git --version
```

---

## 3. Run a Python File and Display Text Using `print`

### Create a Python File

1. Create a folder, for example `store-project`.
2. Open the folder in VS Code: **File → Open Folder**.
3. Create a new file called `main.py`.

> Python files always end with **`.py`**.

### Display Text with `print`

`print()` shows text on the screen.

```python
print("Welcome to our store!")
```

**Output:**
```
Welcome to our store!
```

- Text must be inside **quotes**: `"..."` or `'...'`.
- Text inside quotes is called a **string**.

### Run the File

**Option 1:** Click the **▶ Run** button at the top right of VS Code.

**Option 2:** In the terminal, type:

```bash
python main.py
```

---

## 4. Variables

A **variable** is a **name that stores a value**, so we can use it later.

> **Think of a variable as a labelled box.** The label is the name; the thing inside is the value.

```python
product_name = "Notebook"
product_code = "NB-001"
stock_quantity = 25
```

| Variable | Value | Type of value |
|---|---|---|
| `product_name` | `"Notebook"` | Text (string) |
| `product_code` | `"NB-001"` | Text (string) |
| `stock_quantity` | `25` | Whole number |

- `=` means **"store this value in this variable"**.
- Text needs quotes. Numbers do **not** need quotes.

### Printing Variables

```python
print(product_name)
print("Stock:", stock_quantity)
```

**Output:**
```
Notebook
Stock: 25
```

> Notice: **no quotes** around a variable name. With quotes, Python prints the word itself, not the value.

### Rules for Variable Names

| ✅ Allowed | ❌ Not allowed |
|---|---|
| `product_name` | `product name` (no spaces) |
| `stock2` | `2stock` (cannot start with a number) |
| `price` | `print` (don't use Python's own words) |

- Use **lowercase** words joined with an **underscore** `_`.
- Choose names that **explain** the value: `stock_quantity` is better than `x`.

---

## 5. What Is a SKU?

**SKU (Stock Keeping Unit)** is a **unique code used to identify a product**.

- **Unique** means **no two products have the same SKU**.
- Stores use the SKU to find a product quickly, even if two products have similar names.

| Product | SKU |
|---|---|
| Blue Notebook | `NB-001` |
| Red Notebook | `NB-002` |
| Black Pen | `PN-001` |

> The two notebooks have similar names, but **different SKUs**. So the store never mixes them up.

In our code, the **product code** is the SKU:

```python
product_code = "NB-001"   # this is the SKU
```

---

## 6. GitHub Account and Repository

### What Are Git and GitHub?

| | Git | GitHub |
|---|---|---|
| **What it is** | A tool on your computer | A website |
| **What it does** | Saves the history of your code | Stores your code online |
| **Simple idea** | Like "Save points" in a game | Like Google Drive for code |

### What Is a Repository?

A **repository (repo)** is a **place to store the project and its history**.

### Create a GitHub Account

1. Go to [github.com](https://github.com).
2. Click **Sign up** and create an account.

### Create a Repository

1. On GitHub, click **New** (or the **+** at the top right → **New repository**).
2. Give it a name, for example `store-inventory-system`.
3. Click **Create repository**.

> Keep the repository **empty** (don't tick "Add a README file"). We will add our own.

---

## 7. First Commit, Push, README, and `.gitignore`

### What Is a Commit?

A **commit** is a **saved snapshot** of your code at one moment, with a short message describing what changed.

### What Is a Push?

A **push** **uploads** your commits from your computer to GitHub.

### The `README.md` File

`README.md` is the **front page** of your project on GitHub. It tells people **what the project is**.

```markdown
# Store Inventory System

A program to manage products, stock, and orders for a small store.
```

### The `.gitignore` File

`.gitignore` is a list of **files that Git should skip** (not save or upload).

```
__pycache__/
.venv/
.vscode/
```

### Commands for Your First Commit and Push

```bash
git init                                  # start tracking this folder with Git
git add .                                 # choose all files to save
git commit -m "First commit: show product and stock"   # save a snapshot
git branch -M main                        # name the main branch "main"
git remote add origin <your-repo-url>     # connect to your GitHub repository
git push -u origin main                   # upload to GitHub
```

> **First time only:** Git asks who you are. Run these once:
> ```bash
> git config --global user.name "Your Name"
> git config --global user.email "you@example.com"
> ```

After the first time, you only need:

```bash
git add .
git commit -m "your message"
git push
```

---

## 8. Important Terms

| Term | Simple Meaning |
|---|---|
| **Inventory** | All the products a store has |
| **Stock** | The number of units available for sale |
| **Order** | A customer's request to buy products |
| **Supplier** | A company that sells products to the store |
| **Store operator** | The person who uses and manages the system |
| **Python** | A programming language |
| **VS Code** | A code editor to write and run code |
| **`.py` file** | A file that contains Python code |
| **`print()`** | Shows text on the screen |
| **String** | Text inside quotes, like `"Notebook"` |
| **Variable** | A name that stores a value |
| **SKU** | Stock Keeping Unit: a unique code for a product |
| **Git** | A tool that saves the history of your code |
| **GitHub** | A website that stores your code online |
| **Repository (Repo)** | A place to store the project and its history |
| **Commit** | A saved snapshot of your code |
| **Push** | Uploading commits to GitHub |
| **README.md** | The front page that describes your project |
| **.gitignore** | A list of files Git should skip |

---

## Today's Hands-On

Create a program that **displays one product and its available stock**.

Example output:
```
Product: Notebook
SKU: NB-001
Stock: 25
```

## Today's Git Task

1. Make your **first commit** to record the code.
2. **Push** it to GitHub.
3. Add a **README** introduction.
4. Add a **`.gitignore`** file.

---

## Day 1 Summary

- **Project:** an **Inventory and Order Management System** for a small store.
- We use **Python** (Days 1–15), **SQL** (Days 16–22), and **Flask** (Days 23–30).
- We installed **Python**, **VS Code**, and **Git**.
- `print()` shows text on the screen.
- **Variables** store values like a product name, code, and stock.
- A **SKU** is a unique code for each product.
- A **repository** stores the project; a **commit** saves a snapshot; a **push** uploads it to GitHub.
