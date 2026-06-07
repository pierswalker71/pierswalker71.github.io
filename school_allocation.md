# School Grouping Decision Support Tool

## Helping local authorities make fairer and more practical school allocation decisions

Local authorities often need to divide schools between members of staff, advisers, officers or service teams. These allocations need to be fair, geographically sensible and easy to explain.

This project is an interactive decision-support tool that helps local authority teams create and review school groupings using school location, pupil numbers and group balance metrics.

It was built as a rapid prototype in approximately 24 hours to show how quickly a useful operational planning tool can be created when the problem is clearly understood.

<figure>
  <img src="https://raw.githubusercontent.com/pierswalker71/datascience_experiments/main/schools/images/school_allocation_map.png"
       alt="Interactive map showing proposed school allocation groups"
       width="420">
  <figcaption><em>Interactive map showing proposed school allocation groups.</em></figcaption>
</figure>

---

## The Business Problem

Allocating schools to staff sounds simple, but in practice it involves several competing priorities.

A local authority may want each member of staff to be responsible for a similar number of schools. However, schools vary significantly in size. A group containing five large secondary schools may represent a much greater workload than a group containing five small primary schools.

Geography also matters. A grouping that is numerically balanced may still be impractical if the schools are spread across a wide area.

The challenge is therefore to create school groups that are:

- fair by number of schools
- fair by number of pupils
- geographically sensible
- transparent enough to review and explain
- flexible enough to support different scenarios

This is exactly the type of operational decision where data science can add value: not by replacing professional judgement, but by giving decision-makers a clear, evidence-led starting point.

---

## What the Tool Does

The app allows a user to select a local authority, define the number of required groups and generate a proposed allocation of schools.

It then presents the results through:

- a school-level allocation table
- group-level balance metrics
- pupil and school count comparisons
- an interactive map showing the proposed geographic groupings

The tool helps users move quickly from raw school data to a practical allocation scenario that can be reviewed, discussed and refined.

---

## Screenshots

The screenshots below help illustrate the app without requiring readers to run it locally.

### App controls and scenario settings

<figure>
  <img src="https://raw.githubusercontent.com/pierswalker71/datascience_experiments/main/schools/images/school_allocation_settings.png"
       alt="App controls and scenario settings"
       width="420">
  <figcaption><em>Main controls for selecting a local authority, number of groups and balance settings.</em></figcaption>
</figure>

### Interactive map of school groups

<figure>
  <img src="https://raw.githubusercontent.com/pierswalker71/datascience_experiments/main/schools/images/school_allocation_map.png"
       alt="Interactive map of proposed school groups"
       width="420">
  <figcaption><em>Map view showing schools plotted geographically and coloured by proposed group.</em></figcaption>
</figure>

### Insights chart

<figure>
  <img src="https://raw.githubusercontent.com/pierswalker71/datascience_experiments/main/schools/images/school_allocation_suggest_params.png"
       alt="Chart of pupil versis school results"
       width="420">
  <figcaption><em>Chart showing possible outcomes to aid selecting appropriate setting values.</em></figcaption>
</figure>

### Group pupil and school summary

<figure>
  <img src="https://raw.githubusercontent.com/pierswalker71/datascience_experiments/main/schools/images/school_allocation_results_charts.png"
       alt="Group summary showing school and pupil counts"
       width="420">
  <figcaption><em>Results showing school counts and pupil numbers across proposed groups.</em></figcaption>
</figure>

### Work balance scores

<figure>
  <img src="https://raw.githubusercontent.com/pierswalker71/datascience_experiments/main/schools/images/school_allocation_score_chart.png"
       alt="Simple score chart reflecting both pupil and school factors"
       width="420">
  <figcaption><em>Simple measure of combined pupil and school numbers to support fairer balancing between them.</em></figcaption>
</figure>



---

## Why This Is Useful

The value of the tool is its ability to support better conversations.

Rather than asking managers to manually divide schools or rely on informal judgement, the app provides a structured first-pass allocation. Users can see where groups are balanced, where they are not, and how different assumptions affect the result.

**Fairer workload allocation**

The app considers both the number of schools and the number of pupils. This helps avoid allocations that look balanced on one measure but are unfair in practice.

**Better geographic planning**

The map allows users to check whether proposed groups are realistic from a place-based or travel perspective.

**Faster scenario testing**

Different numbers of groups and balance assumptions can be tested quickly. This makes it easier to compare options before making a recommendation.

**More transparent decision-making**

The app produces outputs that can be shared with managers and stakeholders. This makes the allocation process easier to explain and challenge.

---

## A Deliberately Simple Analytical Approach

This app does not use machine learning.

That is an intentional design choice for this prototype. The problem is not primarily a prediction problem. The immediate business need is to create a fair, practical and reviewable grouping of schools.

The app uses a simple sorting and distribution approach to generate a useful first-pass allocation. This makes the logic easier to understand, easier to explain and easier to adapt.

For a rapid prototype, this is often the right trade-off. A local authority does not necessarily need a complex model to start making better allocation decisions. It needs a tool that is clear, usable and good enough to support a meaningful management discussion.

This project demonstrates that useful data products can often be built without heavy modelling libraries or unnecessary complexity.

---

## What This Demonstrates

This project demonstrates several important data science and product skills:

- understanding a real operational problem
- translating a business need into an analytical workflow
- using data to support fairer decision-making
- designing outputs for non-technical users
- creating an interactive decision-support tool
- balancing simplicity, transparency and usefulness
- building a practical prototype quickly

The project is deliberately focused on business value rather than technical novelty. Its purpose is to show how data science can support public-sector planning in a practical and accessible way.

---

## Limitations

The current version should be treated as a prototype and as a demonstration of a decision-support aid.

It does not claim to produce the mathematically optimal grouping. It also does not include every factor that a local authority may need to consider, such as staff expertise, travel times, school phase, specialist provision or existing relationships between officers and schools.

The output should therefore be reviewed alongside professional judgement and local knowledge.

---

## Further Improvements

A natural next step would be to investigate more advanced allocation and optimisation methods.

Potential improvements include:

- using distance-based clustering to improve geographic coherence
- applying constrained optimisation to balance school count and pupil count more formally
- incorporating travel-time data rather than straight-line geography
- allowing users to manually adjust groups after generation
- comparing multiple scenarios side by side
- adding constraints for school phase, school type or specialist provision
- generating a management-ready report from the chosen allocation

These enhancements would help move the app from a rapid prototype towards a more complete operational planning tool.

---

## Portfolio Reflection

This project is a useful example of applied data science because it addresses a real public-sector planning problem.

It shows that data science is not only about building predictive models. It is also about helping organisations make clearer, fairer and better-evidenced decisions.

The strongest feature of this project is its practicality. In a short development window, it turns a complex manual allocation task into an interactive tool that supports scenario planning, transparency and management review.

---

[View the project repository](https://github.com/pierswalker71/datascience_experiments/tree/main/schools)  
[Back to selected projects](/projects)

