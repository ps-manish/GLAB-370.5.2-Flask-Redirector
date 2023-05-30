# GLAB-370.5.2-Flask-Redirector

## Welcome to the "Flask Redirector: Guiding Users Based on Conditions" Guided Lab! 🚀

In this 30-minute guided lab, we'll embark on an exciting coding adventure that focuses on **redirecting users** in a Flask application based on certain conditions. Get ready to guide your users to the right destination dynamically!

### Prerequisites

Before we begin, make sure you have the following:

- Flask installed (if not, run `pip install flask` in your terminal).
- Basic knowledge of Python syntax.
- A Python interpreter or an integrated development environment (IDE) installed on your machine.

### Table of Contents

- [Step 1: Introduction](#step-1-introduction)
- [Step 2: Defining Routes and Redirecting](#step-2-defining-routes-and-redirecting)
- [Step 3: Using Conditional Redirects](#step-3-using-conditional-redirects)
- [Step 4: Challenge](#step-4-challenge)
- [Step 5: Conclusion](#step-5-conclusion)

### Step 1: Introduction

Let's begin our adventure into the world of Flask redirects. Redirects allow us to send users to different routes or external URLs based on certain conditions. In this lab, we'll learn how to define routes and redirect users dynamically in a Flask application.

### Step 2: Defining Routes and Redirecting

To start, create a basic Flask application with a few routes. Open a Python file, e.g., `app.py`, and add the following code:

```python
from flask import Flask, redirect

app = Flask(__name__)

@app.route("/")
def home():
    return "Welcome to my Flask App!"

@app.route("/about")
def about():
    return "This is the About page."

if __name__ == "__main__":
    app.run()
```

In this code, we define two routes: the root route `/` and the `/about` route. Each route has a corresponding view function that returns a simple message.

To redirect users, we'll use the `redirect()` function from Flask.

### Step 3: Using Conditional Redirects

Now, let's modify the view function for the root route `/` to redirect users to different destinations based on certain conditions.

Update the `home()` function as follows:

```python
from flask import request

@app.route("/")
def home():
    user_agent = request.headers.get("User-Agent")
    if "mobile" in user_agent.lower():
        return redirect("/mobile")
    else:
        return redirect("/desktop")
```

In this updated code, we use the `request` object to retrieve the user agent from the request headers. We check if the user agent contains the word "mobile" (case-insensitive), and if so, we redirect the user to `/mobile`; otherwise, we redirect them to `/desktop`.

Make sure to define the `/mobile` and `/desktop` routes with their corresponding view functions to handle the redirections.

### Step 4: Challenge

Now it's time for an exciting challenge! Customize your Flask application by adding more routes and implementing conditional redirects based on different conditions. Experiment with different factors, such as user agent, user authentication, or request parameters, to dynamically guide users to the appropriate destinations.

### Step 5: Conclusion

Congratulations on completing the "Flask Redirector: Guiding Users Based on Conditions" Guided Lab! You've learned how to redirect users in a Flask application based on certain conditions.

Remember to keep exploring Flask's capabilities and experiment with different features and functionalities. Redirects provide a flexible way to guide users to the right destinations dynamically.

Feel free to reach out if you have any questions. Happy coding, and may your Flask redirects

 lead your users on the right path! 🎉
