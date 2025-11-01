# Power-BI-TMDL-View-
A comprehensive guide to Power BI Tabular Model Definition Language (TMDL) with practical examples, best practices, and quick reference notes for data modeling.

Power BI just got even more powerful!
If you’ve ever struggled with understanding, documenting, or version-controlling your semantic models, then the TMDL View (Tabular Model Definition Language) is something you must explore.

In this post, I’ll explain what TMDL View is, why it matters, and how you can start using it today.

## What is TMDL View?

TMDL (Tabular Model Definition Language) is a human-readable, text-based representation of a Power BI semantic model.

Instead of dealing with a complex .pbix binary file, TMDL converts your model into:

1. Structured folders

2. JSON-like text files

3. YAML-formatted metadata

4. Clearly readable tables, measures, relationships, and roles

This makes your semantic model:

Easier to read

Easier to compare

Easier to maintain

Easier to version-control in Git

## Why TMDL is a Big Deal

Here’s what TMDL View enables:

### 1. Full Transparency

You can now see:

1. Column definitions

2. DAX measures

3. Calculation groups

4. Data sources

5. Relationships

6. …all in plain text!

### 2. Version Control (CI/CD Made Easy)

Before TMDL, semantic models were binary and hard to diff.
Now:

1. Git diff works 

2. Pull requests are meaningful 

3. Code reviews are possible 

### 3. Team Collaboration

Multiple developers can now:

1. Work on the same model

2. Track model changes

3. Avoid overwriting each other’s work

### 4. Better Documentation

The model essentially documents itself — no more guessing where measures or relationships come from.

 ## How to Enable TMDL View

You can access TMDL View through:

🔹 Power BI Desktop (Preview Feature)

Go to File → Options → Preview Features

Enable Semantic Model TMDL View

Restart Power BI Desktop

Open your model → Switch to Model → TMDL View

🔹 Fabric Workspace

If you use Power BI in Fabric:

Export semantic models into Git repositories using Deployment Pipelines

Models appear in TMDL folder structure automatically

## How TMDL Looks (Quick Example)
🔸 Example: Table Definition (tmdl)
table: Sales
  columns:
    - name: OrderDate
      dataType: date
    - name: Revenue
      dataType: decimal
  measures:
    - name: TotalRevenue
      expression: SUM(Sales[Revenue])

🔸 Example: Relationship
relationship:
  from: Sales[CustomerID]
  to: Customers[CustomerID]
  type: manyToOne
  direction: single


Readable 
Maintainable 
Version-friendly 

## When Should You Use TMDL?

Use TMDL View if you:

Work in a BI/Data Engineering team

Use Git for Power BI projects

Have large models with many measures

Use Fabric or deployment pipelines

Need automated semantic model governance

## Final Thoughts

TMDL View bridges the gap between:
1. BI development
2. Software engineering best practices
3. CI/CD pipelines
4. Team workflows

Below some of my steps which I personally follow to create quick measures using TMDL view in PBI.
1. Open TMDL View from Left nevigation section of PBI file
2. Pull the exisitng measure if you want to edit it or else you can use it to create new one if you are new with tmdl syntax 
<img width="1909" height="667" alt="image" src="https://github.com/user-attachments/assets/46102cd3-6739-4368-b562-b9bca7ad1329" />

3. Write as many measure you would like to add 
<img width="1400" height="736" alt="image" src="https://github.com/user-attachments/assets/7b3b911c-f9fa-4849-bee5-220474f95026" />

4. Boom! you can preview it, compare it, and if you feel good you can apply it by clicking the dark green APLLY buton.
<img width="1844" height="744" alt="image" src="https://github.com/user-attachments/assets/574d02ce-5ca6-4a96-a1df-84bbbc9f33e1" />

5. You can create separate scripts for each type of measure you would like to add and then debug it as well.


The above example is more generalize example and I feel it, developer will definitily going to use it at some time. Other advantages of TMDL view I already explained in teh above post.





