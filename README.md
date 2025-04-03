Project: Simple Habit Tracker

import datetime

habits = {}

def add_habit(habit_name): if habit_name not in habits: habits[habit_name] = [] return f"Habit '{habit_name}' added successfully." return "Habit already exists."

def mark_habit_completed(habit_name): if habit_name in habits: today = datetime.date.today().strftime("%Y-%m-%d") if today not in habits[habit_name]: habits[habit_name].append(today) return f"Habit '{habit_name}' marked as completed for {today}." return "Habit already marked as completed today." return "Habit not found."

def view_habits(): if not habits: return "No habits tracked." return "\n".join([f"{habit}: {', '.join(dates)}" for habit, dates in habits.items()])

Example Usage

if name == "main": print(add_habit("Exercise")) print(add_habit("Read")) print(mark_habit_completed("Exercise")) print(mark_habit_completed("Read")) print("\nHabit Tracking:\n", view_habits())# Simple-Habit-Tracker
