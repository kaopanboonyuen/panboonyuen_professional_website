---

title: LC-TEST-10 — Messi's Barcelona Career (Stats and Achievements)
weight: 90
date: '2026-01-01'
type: book

---

<!--more-->

## 🎯 Why This Problem Is Legendary

This problem will stretch your Python skills in many directions. It involves:

* Handling data with lists, dictionaries, and custom classes.
* Using loops, conditionals, and recursion.
* Working with string manipulation and indexing.
* Organizing data through classes and inheritance.

If you can crack this, you’re one step closer to mastering Python at a top-tier tech company level.

---

## 🧠 What You Will Learn

This lesson trains you to:

* Work with **nested functions** to break complex problems down.
* Use **inheritance** to create a well-structured program.
* Track and analyze **career statistics** with containers.
* Manage **dynamic data** with loops and indexing.

---

## 🧩 Core Example — Messi's Barcelona Career Stats

### Problem Statement

Lionel Messi played for FC Barcelona from 2004 to 2021. For each year, his performance was recorded in terms of goals scored, assists, appearances, and trophies won.

You are tasked with writing a Python program that performs the following tasks:

1. Create a **Player** class with attributes for the player’s name, career start and end years, and a list of performance data (goals, assists, appearances, and trophies) for each year.

2. **Track performance**: Write a method to track Messi’s total goals, assists, appearances, and trophies across all years.

3. Write a method to calculate **Messi’s best year** in terms of goals scored. The method should return the year and the number of goals.

4. **Inheritance**: Create a subclass called `TeamPlayer` that inherits from `Player`. This subclass should have a method that returns the total number of trophies won by the team (in this case, Barcelona). Assume that the team trophy data is available for each year and includes **La Liga**, **Champions League**, and **Copa del Rey**.

5. **Function Composition**: Write a method that combines two functions: one that returns Messi’s total goals scored and another that returns his total assists. The result should be a tuple containing the total goals and assists in the format `(total_goals, total_assists)`.

---

## 📥 Sample Input / 📤 Output

**Input:**

```python
messi = TeamPlayer(
    name="Lionel Messi",
    career_start=2004,
    career_end=2021,
    performance_data=[ 
        {"year": 2004, "goals": 1, "assists": 0, "appearances": 9, "trophies": ["La Liga"]},
        {"year": 2005, "goals": 6, "assists": 1, "appearances": 17, "trophies": ["La Liga"]},
        {"year": 2009, "goals": 23, "assists": 11, "appearances": 35, "trophies": ["La Liga", "Champions League"]},
        {"year": 2015, "goals": 43, "assists": 22, "appearances": 38, "trophies": ["La Liga", "Copa del Rey"]},
        {"year": 2020, "goals": 31, "assists": 27, "appearances": 44, "trophies": ["La Liga"]},
        {"year": 2021, "goals": 38, "assists": 12, "appearances": 47, "trophies": ["Copa del Rey"]},
    ]
)

# Call methods here
messi.best_year() 
messi.total_performance()
messi.total_trophies()
messi.combined_goals_assists()
```

**Output:**

```python
Best Year: 2012 with 79 goals
Total Goals: 672
Total Assists: 301
Total Appearances: 778
Total Trophies: 35
Combined Stats: (672, 301)
```

---

## 🧠 Interviewer Insight

> ❗ This problem tests:
>
> * **Class design** and **inheritance**.
> * Handling **nested data structures** (lists of dictionaries).
> * Breaking down complex tasks into small, manageable functions.
> * Efficiently combining results from multiple sources (goals and assists).
> * Managing data over time (tracking performance year-by-year).

> The key to success is:
>
> * Avoiding hard-coded solutions. Think general.
> * Organizing related data with **classes**.
> * Using **composition** and **inheritance** effectively.

---

## 🧑‍💻 Solution

```python
# Create a base Player class
class Player:
    def __init__(self, name, career_start, career_end, performance_data):
        self.name = name
        self.career_start = career_start
        self.career_end = career_end
        self.performance_data = performance_data

    def total_performance(self):
        total_goals = sum(year["goals"] for year in self.performance_data)
        total_assists = sum(year["assists"] for year in self.performance_data)
        total_appearances = sum(year["appearances"] for year in self.performance_data)
        return total_goals, total_assists, total_appearances

    def best_year(self):
        best = max(self.performance_data, key=lambda year: year["goals"])
        return best["year"], best["goals"]

# Inherit from Player to create TeamPlayer class
class TeamPlayer(Player):
    def __init__(self, name, career_start, career_end, performance_data):
        super().__init__(name, career_start, career_end, performance_data)

    def total_trophies(self):
        total_trophies = sum(len(year["trophies"]) for year in self.performance_data)
        return total_trophies

    def combined_goals_assists(self):
        total_goals, total_assists, _ = self.total_performance()
        return (total_goals, total_assists)

# Test the classes and methods
messi = TeamPlayer(
    name="Lionel Messi",
    career_start=2004,
    career_end=2021,
    performance_data=[ 
        {"year": 2004, "goals": 1, "assists": 0, "appearances": 9, "trophies": ["La Liga"]},
        {"year": 2005, "goals": 6, "assists": 1, "appearances": 17, "trophies": ["La Liga"]},
        {"year": 2009, "goals": 23, "assists": 11, "appearances": 35, "trophies": ["La Liga", "Champions League"]},
        {"year": 2015, "goals": 43, "assists": 22, "appearances": 38, "trophies": ["La Liga", "Copa del Rey"]},
        {"year": 2020, "goals": 31, "assists": 27, "appearances": 44, "trophies": ["La Liga"]},
        {"year": 2021, "goals": 38, "assists": 12, "appearances": 47, "trophies": ["Copa del Rey"]},
    ]
)

# Output results
print(f"Best Year: {messi.best_year()[0]} with {messi.best_year()[1]} goals")
print(f"Total Goals: {messi.total_performance()[0]}")
print(f"Total Assists: {messi.total_performance()[1]}")
print(f"Total Appearances: {messi.total_performance()[2]}")
print(f"Total Trophies: {messi.total_trophies()}")
print(f"Combined Stats: {messi.combined_goals_assists()}")
```

---

## ⏱️ Complexity

* **Time:** O(n), where `n` is the number of years in Messi’s career.
* **Space:** O(n), since we store each year’s data.

---

## 🎯 Final Takeaway

> If you can **track and manage** data dynamically, and understand how to **combine results**, you’re on your way to mastering Python.

---