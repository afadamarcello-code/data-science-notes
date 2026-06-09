# Day 3: Linear Regression Theory

## 1. The Goal: Finding the Best Line
In high school, you learned the equation for a line: $y = mx + b$ (or in statistics, $y = \beta_0 + \beta_1x$). 
*   **$y$**: The thing we want to predict (Target).
*   **$x$**: The data we have (Feature).
*   **$m$ (or $\beta_1$)**: The slope (How much $y$ changes when $x$ changes).
*   **$b$ (or $\beta_0$)**: The intercept (Where the line crosses the y-axis).

*The Mentor Test: The algorithm doesn't know $m$ and $b$. It has to guess them, check how wrong it is, and adjust until it finds the **best possible line**.*

## 2. Core Vocabulary

| Term | What it actually means | The Analogy |
|------|------------------------|-------------|
| **Residual (Error)** | The vertical distance between an actual data point and our predicted line. | "How far off was my guess?" |
| **Least Squares** | The method of squaring all the residuals, adding them up, and finding the line that makes this sum as small as possible. | We square them so negative and positive errors don't cancel each other out. |
| **Cost Function (MSE)** | The mathematical formula that calculates the average of those squared errors. (Mean Squared Error). | The "Scoreboard" telling the model how badly it's doing. Lower score = better model. |
| **Gradient Descent** | The optimization algorithm used to *minimize* the Cost Function. | A blindfolded hiker trying to find the bottom of a valley by feeling the slope of the ground. |

## 3. Gradient Descent Intuition (The Blindfolded Hiker)
Imagine you are blindfolded on a hilly landscape, and you want to find the lowest point (the minimum of the Cost Function). 
1. You feel the ground with your feet to find which way slopes downward (The **Gradient**).
2. You take a step in that direction. 
3. The size of your step is your **Learning Rate**.
4. You repeat this until the ground feels flat (you've reached the bottom / minimum error).

| Hyperparameter | What it controls | What happens if it's wrong? |
|----------------|------------------|-----------------------------|
| **Learning Rate** | The size of the step the hiker takes. | **Too high:** You overshoot the bottom and bounce around forever. **Too low:** It takes 100 years to reach the bottom. |