# Programming Foundation Exercises

> **How you'll submit this lab**
>
> This repo is your lab. Fork it, do the work described below in your fork, then open a pull
> request back into this repository. An AI reviewer will check your PR against `rubric.md` and
> leave feedback directly on the PR. See `README.md` for the full workflow.

**Scenario**  
You've been hired by a startup company called HomeGuard to develop a prototype for their smart home monitoring system. The system uses various sensors throughout a house to detect potential security issues, comfort problems, and equipment failures. Your job is to create a simulator that processes sensor readings and triggers appropriate alerts.

**Learning Objectives**
- [ ] Implement conditional logic using if/else statements to check sensor thresholds and system modes
- [ ] Create and use data structures (dictionaries) to represent sensors, alerts, and system state
- [ ] Write functions to process sensor data, generate readings, and trigger alerts
- [ ] Design and implement a Sensor class with properties and methods
- [ ] Integrate all components to build a complete security system simulator

**Estimated Time:** 90-120 minutes

**Prerequisites:**
- [ ] Basic understanding of Python syntax
- [ ] Familiarity with variables and data types
- [ ] Knowledge of how to run Python scripts

---

## Introduction

Welcome to the HomeGuard Security System lab! In this exercise, you'll build a complete simulator for a smart home monitoring system. This lab will help you practice fundamental programming concepts that are essential for AI and software development.

**Why this matters:**
This lab simulates how AI systems preprocess real-world sensor data, make decisions based on thresholds, and trigger appropriate responses. These patterns are used extensively in IoT devices, robotics, and automated systems.

**Success criteria:**
- [ ] Your code runs without errors
- [ ] All sensors can be read and processed
- [ ] Alerts are triggered correctly based on conditions
- [ ] The simulator displays formatted output matching the sample
- [ ] Your code includes proper comments explaining each section

---

## Background Story

HomeGuard's client, the Peterson family, wants to monitor their vacation home while they're away. They've installed:

- **Motion sensors** in each room to detect intruders
- **Temperature sensors** to prevent frozen pipes or fire hazards
- **Door sensors** to track entry points
- **Smoke detectors** for fire safety

Your simulator needs to:
- Generate realistic sensor readings
- Detect abnormal conditions
- Trigger appropriate alerts
- Log all events for review

---

## System Requirements

The simulator must handle these scenarios:

**Security Alerts:**
- Motion detected when house is in "away" mode
- Door opened when house is in "away" mode
- Multiple sensors triggered simultaneously (possible break-in)

**Safety Alerts:**
- Temperature below 35°F (frozen pipe risk)
- Temperature above 95°F (equipment failure)
- Smoke detected (fire risk)

**Comfort Notifications:**
- Temperature outside comfort range (65-75°F) when home is in "home" mode
- Unusual patterns (like a door left open for >5 minutes)


Submit one `lab_proof.md` with the program path, run command, output from fixed cases, and a short explanation of one edge case.

## Pseudocode

```text
INPUT: fixed examples or user inputs
DECIDE: variables, functions, structures, and rules
BUILD: the smallest program that handles the examples
VERIFY: run fixed cases and inspect deterministic output
EXPLAIN: defend one design choice and one edge case
```

## Prompt Discipline

Use AI for review, debugging, or critique. Do not ask it to produce the final artifact or final answer.

```text
Role: Code reviewer
Task: Review my pseudocode and test cases before I submit.
Inputs: pseudocode, program path, test inputs, and observed output.
Constraints: Do not write the program for me. Identify missing cases and unclear evidence.
Output format: three code risks, two test checks, and one simplification.
Verification: Name the output that best proves the program works.
```

## Build

## Step-by-Step Instructions

### Step 1: Setting Up the Project

Do: Create your project file and set up the basic structure.

Do:
1. Create a new Python file named `homeguard_system.py` (or `homeguard_system.ipynb` if you prefer a notebook)
2. Add a header comment with your name and the project description
3. Import the necessary modules (`random` for generating sensor readings and `datetime` for timestamps)

Verify: You should have a Python file that runs without errors (though it won't do anything yet).

**Checkpoint:** Run your file (`python homeguard_system.py` for a `.py` file, or "Run All" in your notebook). It should execute without errors.

---

### Step 2: Creating Data Structures

Do: Define the data structures (dictionaries) that will represent sensors, alerts, and system state.

Do:
1. Create a function that initializes sensor data structures
2. Define the structure for storing sensor information
3. Define the structure for storing alert information

**Explanation:** In Python, we use dictionaries to represent structured data. A dictionary is like a container that stores key-value pairs. For example, a sensor might have an "id", "location", "type", and "current_value".

Verify: You now have functions to create sensor and alert structures, and a list of sensors initialized.

**Checkpoint:** Add a test print statement to verify your sensors are created:

---

### Step 3: Implementing If/Else Logic

Do: Write conditional statements to check sensor thresholds and system modes.

Do:
1. Create a function that checks if a sensor reading is abnormal
2. Use if/else statements to compare values against thresholds
3. Check the system mode to determine if alerts should be triggered

**Explanation:** If/else statements allow your program to make decisions. For example, "IF the temperature is below 35°F, THEN trigger a critical alert."

Verify: You have functions that use if/else statements to make decisions about sensor readings.

**Checkpoint:** Test your functions:

---

### Step 4: Building Functions

Do: Create functions to generate sensor readings, process them, trigger alerts, and log events.

Do:
1. Write a function to generate realistic sensor readings
2. Create a function to process readings and determine if alerts are needed
3. Implement a function to trigger and display alerts
4. Add a logging function to record all events

**Explanation:** Functions are reusable blocks of code that perform specific tasks. They help organize your code and make it easier to maintain.

Verify: You have all the core functions needed to process sensor data and trigger alerts.

**Checkpoint:** Test your functions:

---

### Step 5: Creating Classes

Do: Convert the sensor dictionary into a Sensor class with methods.

Do:
1. Define a Sensor class with an `__init__` method
2. Add methods: `read()`, `isAbnormal()`, and `reset()`
3. Update your code to use the Sensor class instead of dictionaries

**Explanation:** Classes are blueprints for creating objects. They combine data (properties) and functions (methods) into a single unit. This makes your code more organized and easier to work with.

Verify: You have a Sensor class and can create sensor objects.

**Checkpoint:** Test your class:

---

### Step 6: Integrating Everything

Do: Combine all components into a complete simulator that runs continuously.

Do:
1. Create a main simulation loop
2. Integrate all your functions and classes
3. Format the output to match the sample

Verify: You have a complete, working simulator that runs and displays formatted output.

**Checkpoint:** Run your complete program and verify it produces output similar to the sample.

---

### Step 7: Testing Your System

Do: Verify your system works correctly and handles all scenarios.

Do:
1. Run your simulator multiple times to see different scenarios
2. Test different system modes (HOME, AWAY, SLEEP)
3. Verify that alerts trigger correctly
4. Check that the output is formatted properly

**Test scenarios:**
1. **Security Test:** Run with `system_mode="AWAY"` and verify security alerts trigger
2. **Safety Test:** Check that temperature and smoke alerts work
3. **Comfort Test:** Run with `system_mode="HOME"` and verify comfort notifications appear

**Observable output format:**
```
=== HomeGuard Security System ===
Time: 14:30:00
Mode: AWAY

[READING] Living Room Motion: No activity
[READING] Front Door: CLOSED
[READING] Kitchen Temperature: 68°F (Normal)
[READING] Bedroom Smoke: CLEAR

Time: 14:31:00
[READING] Front Door: OPENED
[ALERT!] 🚨 HIGH: SECURITY: Front Door opened while in AWAY mode!
[LOG] [14:31:00] Sending notification to homeowner...
```

**Checkpoint:** Your simulator should run without errors and display formatted output for all sensor types.

---

## Submission Guidelines

### What to Submit

**Required deliverables:**
- [ ] Your complete `homeguard_system.py` or  `homeguard_system.ipynb` file with all code implemented
- [ ] A screenshot or text output showing your simulator running (at least 3 time iterations)
- [ ] A brief explanation (2-3 sentences) of how your code works

### How to Submit

**Upload your work:**
1. **For code files:** Upload your `homeguard_system.py` file directly to the platform
2. **For screenshots:** Upload a PNG or JPG image showing your program's output
3. **For text output:** Copy and paste the output into a text file or directly into the submission field

**Important notes:**
- Make sure your code runs without errors
- Include comments in your code explaining key sections
- Test your code before submitting
- Your output should show at least one alert being triggered

**Due date:** Check with your instructor for the specific due date.

---

## Troubleshooting

**Common issues and solutions:**

**Issue 1: "NameError: name 'sensor' is not defined"**
- **Solution:** Make sure you've created your sensors list before trying to use it. Check that all variable names are spelled correctly.

**Issue 2: "TypeError: '>' not supported between instances of 'str' and 'int'"**
- **Solution:** This happens when comparing different data types. Make sure you're comparing numbers with numbers (e.g., `reading_value < 35` not `reading_value < "35"`).

**Issue 3: "Alerts not triggering when they should"**
- **Solution:** Check your if/else conditions. Make sure you're checking the correct conditions (e.g., `system_mode == "AWAY"` not `system_mode = "AWAY"`). Remember `==` is for comparison, `=` is for assignment.

**Issue 4: "Random values not generating correctly"**
- **Solution:** Make sure you've imported the `random` module at the top of your file with `import random`.

**Issue 5: "Class methods not working"**
- **Solution:** Make sure your class methods include `self` as the first parameter. Check that you're calling methods on instances (e.g., `sensor.read()`) not on the class itself.

**Issue 6: "Output formatting looks wrong"**
- **Solution:** Check your print statements. Make sure you're using f-strings correctly (e.g., `f"Temperature: {value}°F"`).

---

## Bonus Challenges

If you finish early, try these additional challenges:

### Challenge 1: Learning Mode
Add a "learning mode" that adjusts normal temperature ranges based on historical patterns. Track the average temperature over time and adjust the comfort range accordingly.

### Challenge 2: False-Alarm Detection
Implement a system that requires multiple confirmations before triggering a critical alert. For example, require motion to be detected in two different rooms before triggering a break-in alert.

### Challenge 3: Daily Summary Report
Create a function that generates a daily summary report showing:
- Total number of alerts by severity
- Most active sensor
- Time range of alerts
- Recommendations based on patterns

### Challenge 4: Interconnected Alerts
Add logic so that when smoke is detected, the system automatically checks all temperature sensors. If multiple sensors show high temperatures, increase the alert severity.

---

## Additional Resources

**Reference materials:**
- [Python Dictionaries Documentation](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)
- [Python Classes Tutorial](https://docs.python.org/3/tutorial/classes.html)
- [Python If/Else Statements](https://docs.python.org/3/tutorial/controlflow.html#if-statements)
- [Python Functions Guide](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)

**Tools and software:**
- [Python Official Website](https://www.python.org/)
- [Python IDLE](https://docs.python.org/3/library/idle.html) - Built-in Python editor
- [VS Code](https://code.visualstudio.com/) - Popular code editor with Python support

**Further reading:**
- [Real-World IoT Sensor Applications](https://www.iotforall.com/what-are-iot-sensors)
- [Decision Making in Programming](https://realpython.com/python-conditional-statements/)
- [Object-Oriented Programming Basics](https://realpython.com/python3-object-oriented-programming/)

---

## To-Do List

- [ ] Read and understand the lab requirements
- [ ] Complete Step 1: Setting Up the Project
- [ ] Complete Step 2: Creating Data Structures
- [ ] Complete Step 3: Implementing If/Else Logic
- [ ] Complete Step 4: Building Functions
- [ ] Complete Step 5: Creating Classes
- [ ] Complete Step 6: Integrating Everything
- [ ] Complete Step 7: Testing Your System
- [ ] Test your code with different scenarios
- [ ] Review your code and add comments
- [ ] Submit your work

---

## Learning Reflection

After completing this lab, reflect on what you've learned:

1. **If/Else Logic:** How did you use conditional statements to make decisions in your code?
2. **Data Structures:** What information did you store in dictionaries, and why was this useful?
3. **Functions:** How did breaking your code into functions make it easier to work with?
4. **Classes:** What advantages did using a class provide over just using dictionaries?

**Key takeaways:**
- Conditional logic (if/else) is essential for making decisions in programs
- Data structures help organize related information
- Functions make code reusable and easier to maintain
- Classes combine data and behavior into organized units

These concepts form the foundation of all programming and are especially important for AI systems that need to process data and make decisions.

---

*Test your code frequently and ask for help when you get stuck.*

## Verify

The reviewer can run the stated command and see the observable output for the fixed cases.

## Explain

Which edge case did you handle explicitly, and why does it matter?

## Submission Sanity Check

Before you submit:
- Keep only files for this lab.
- Name files clearly.
- Remove secrets, API keys, tokens, and unrelated data.
- Make `lab_proof.md` the entry point for the reviewer.

## Optional Stretch

- Add one meaningful edge case or refactor one repeated block into a function.
- Create a small UI with vibecoding only if it makes the program easier to test. Deploy only if the app has no secrets.
