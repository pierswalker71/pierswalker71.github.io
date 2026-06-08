# Simulation Optimisation

## Machine learning and optimisation for cost-aware operational decision support

This project demonstrates how simulation, machine learning and optimisation can be combined to identify low-cost ways of achieving a target business outcome.

Many organisations use simulation models to understand complex operational systems. These models can help answer:

> What happens if we try this scenario?

This project goes further and explores a more useful operational question:

> Which scenario should we choose?

The notebook treats a simulator as a black box, learns its behaviour using a machine learning model, and then uses optimisation to search for input settings that achieve a target output at the lowest cost.

---

## Business Problem

A business has a simulation model that estimates output from a set of operational inputs.

Those inputs could represent resources such as:

* machines
* production lines
* staff groups
* depots
* service teams
* processing units
* capacity in different locations

The business needs to achieve a target level of output, but each input has a cost. Adding more resources may improve performance, but it also increases cost.

The challenge is therefore not simply to maximise output. The challenge is to find the cheapest combination of inputs that still meets the required level of performance.

In this demonstration, the target is to achieve an output of **60 units** using five integer input variables. The optimal answer is the lowest-cost configuration that achieves the target within an acceptable tolerance.

The core question is:

> What combination of inputs achieves the required output at the lowest cost?

This is a common operational analytics problem. The relationship between resources and output may be non-linear, inconsistent and difficult to optimise by inspection.

---

## Why This Matters

Traditional simulation is useful for testing scenarios one at a time.

Simulation optimisation goes further. It helps identify which scenarios are worth choosing.

This approach is valuable where:

* the simulator is slow or expensive to run
* there are many possible input combinations
* the relationship between inputs and outputs is complex
* decision-makers need to balance performance and cost
* the organisation needs explainable candidate solutions
* manual trial and error is inefficient

The result is a practical decision-support workflow rather than a prediction model in isolation.

---

## What the Tool Does

The notebook implements an end-to-end simulation optimisation process.

### 1. Defines the target and cost assumptions

The project starts by defining the business objective:

* target output
* number of input variables
* cost of each input
* acceptable tolerance around the target

This turns the problem into a business decision: find the lowest-cost configuration that meets the required output.

### 2. Generates simulation data

The notebook runs a simulated process across many different input combinations.

Each run records:

* the selected input values
* the simulated output
* the total cost of the inputs

This produces the training data needed to understand how the simulated system behaves.

### 3. Trains a surrogate model

The notebook trains regression models to learn the relationship between the input values and simulator output.

The modelling process includes:

* train/test splitting
* feature scaling
* polynomial feature generation
* model pipelines
* model comparison
* hyperparameter tuning
* cross-validation
* performance testing on unseen data

The chosen model acts as a **surrogate model** for the simulator. It approximates the simulator’s behaviour so that optimisation can be performed more quickly and systematically.

### 4. Optimises the input values

The trained model is then used to search for input combinations that are predicted to meet the target output at minimum cost.

This is more efficient than manually testing scenarios or running the simulator across every possible combination.

### 5. Validates recommended solutions

Candidate solutions are passed back through the original simulator to check whether they perform as expected.

The notebook also explores nearby input combinations to identify alternative low-cost compliant solutions.

### 6. Presents the best compliant results

The final outputs identify input combinations that:

* achieve the target output within tolerance
* minimise cost
* provide candidate scenarios for business review

---

## Project Workflow

```text
Define target and cost assumptions
        ↓
Generate simulation runs
        ↓
Train a machine learning surrogate model
        ↓
Use the model to search the solution space
        ↓
Identify low-cost candidate solutions
        ↓
Validate against the simulator
        ↓
Review the best compliant options
```

---

## Screenshots and Outputs

### Business Problem Complexity

<p>
  <img src="https://github.com/pierswalker71/Simulation_Optimisation/blob/main/images/simulator_optimisation_function_to_optimise.JPG?raw=true"
       alt="Function to optimise"
       width="520">
</p>

*The solution landscape is irregular, making manual optimisation difficult.*

The simulator produces a complex and uneven response surface. Small changes in some input variables can have a significant effect on system performance, which makes simple rule-based optimisation difficult.

---

### Solution Performance and Cost

<p>
  <img src="https://github.com/pierswalker71/Simulation_Optimisation/blob/main/images/simulator_optimisation_output_scatter.JPG?raw=true"
       alt="Output scatter chart"
       width="520">
</p>

*Simulation runs plotted by performance and cost.*

This chart shows the spread of tested solutions. Some configurations achieve the required performance, but many are either too costly or fail to meet the target. The aim is to find compliant solutions at the lowest possible cost.

---

### Regression Model Performance

<p>
  <img src="https://github.com/pierswalker71/Simulation_Optimisation/blob/main/images/simulator_optimisation_regression_performance.JPG?raw=true"
       alt="Regression model performance chart"
       width="520">
</p>

*Regression model performance on unseen data.*

The regression model learns to approximate the simulator’s behaviour. The chart compares predicted outputs with actual simulator outputs. A stronger model provides a more reliable basis for optimisation.

---

### Best Compliant Results

<p>
  <img src="https://github.com/pierswalker71/Simulation_Optimisation/blob/main/images/simulator_optimisation_results_heatmap.JPG?raw=true"
       alt="Results heatmap"
       width="520">
</p>

*Lowest-cost solutions that meet the target requirement.*

The results table highlights the cheapest input combinations that achieve the required output within the accepted tolerance. These are the candidate solutions a decision-maker would review.

---

### Improvement Over Time

<p>
  <img src="https://github.com/pierswalker71/Simulation_Optimisation/blob/main/images/simulator_optimisation_run_improvements.JPG?raw=true"
       alt="Improvement over time"
       width="520">
</p>

*Successive runs identify better compliant solutions.*

As more simulation runs are explored, the process discovers cheaper ways to meet the target. This shows the practical value of using optimisation to guide the search rather than relying only on manual experimentation.

---

## Technical Approach

The project uses Python and standard data science libraries to build a complete simulation optimisation workflow.

Key techniques include:

* simulation data generation
* supervised regression modelling
* surrogate modelling
* scikit-learn pipelines
* train/test validation
* cross-validation
* hyperparameter search
* feature scaling
* polynomial feature engineering
* global optimisation
* cost-based objective functions
* validation of model-generated recommendations

The central idea is to use a machine learning model as an approximation of the simulator. The optimiser can then search this learned model for promising low-cost configurations before those recommendations are checked against the original simulator.

---

## Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* scikit-learn
* SciPy
* Matplotlib

---

## Value Delivered

This project shows how data science can support better operational decisions.

The main value is that it turns simulation from a passive scenario-testing tool into an active optimisation workflow.

Instead of asking users to manually test many combinations, the tool helps identify promising options automatically.

Potential business benefits include:

* faster scenario analysis
* lower-cost resource planning
* better use of existing simulation models
* clearer trade-offs between cost and output
* more systematic decision-making
* reusable optimisation logic for similar operational problems

---

## What This Demonstrates

This project demonstrates the ability to:

* translate a business planning problem into a data science workflow
* generate useful data from a simulated process
* train models to approximate complex input-output relationships
* evaluate model performance using appropriate validation methods
* use optimisation to recommend decisions
* incorporate cost into analytical decision-making
* validate model-generated recommendations against the original process
* communicate technical outputs as practical business options

The project is particularly relevant to:

* operational analytics
* decision-support tools
* simulation modelling
* applied machine learning
* optimisation
* AI-enabled planning tools

---

## Limitations

This is a prototype notebook rather than a production system.

Current limitations include:

* the simulator is synthetic rather than connected to a live business process
* the cost function is simplified
* the example uses a fixed target output
* the input space is limited to five integer variables
* uncertainty in model predictions is not explicitly quantified
* there is no user interface
* results require domain validation before use in real decisions
* the notebook has not yet been refactored into reusable Python modules

These limitations are appropriate for a prototype. They also show where the project could be developed further.

---

## Possible Extensions

Future improvements could include:

* refactoring the notebook into reusable Python modules
* adding a simple user interface for non-technical users
* allowing users to change targets, costs and constraints interactively
* supporting multiple objectives, such as cost, quality, resilience and service level
* adding uncertainty estimates around recommendations
* comparing different optimisation methods
* integrating with a real simulation engine
* exporting recommended scenarios to CSV or Excel
* adding automated reporting for decision-makers

---

## Portfolio Reflection

This project is a useful portfolio example because it shows applied data science beyond prediction alone.

The notebook demonstrates how modelling can be used to support decisions. It combines simulation, machine learning and optimisation to answer a practical business question: how can an organisation achieve a required output at the lowest cost?

The project also demonstrates the value of surrogate modelling. Instead of relying on exhaustive simulation, the workflow learns from simulation runs and uses that learned model to guide the search for better options.

Although this is a prototype, it demonstrates a complete analytical pattern that could be adapted to real-world operational planning problems.

The most important capability demonstrated is the connection between technical methods and business value:

* simulation generates evidence
* machine learning learns system behaviour
* optimisation recommends action
* validation checks whether the recommendation works

That combination is directly relevant to building practical AI and analytics tools for decision support.

---

## Repository

The full notebook is available in the GitHub repository:

[View the Simulation Optimisation repository](https://github.com/pierswalker71/Simulation_Optimisation)

Main notebook:

```text
20220106 Simulation Optimiser.ipynb
```

---

## Summary

This project demonstrates a simulation optimisation workflow in Python.

It shows how a business simulator can be treated as a black box, approximated using machine learning, and then optimised to find low-cost input configurations that achieve a target output.

The result is a practical prototype for cost-aware operational decision support.
