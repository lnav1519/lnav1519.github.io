---
title: "Resource Visualization & Learning D3"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Data Visualization
  - D3.js
  - Resource Management
---


One skill a data professional must have in their tool kit is the ability to visualize data. 
Most of my experience is in Power BI, with a little bit of Qlik Sense and Tableu thrown in the mix. 
In my masters program I primarily worked in Python and R for visualizing data and I enjoyed the flexibility that coding your visualization provided.
However, that flexibility and freedom comes at the cost of longer development time and having to figure out how to deploy your interactive chart somehow, which may not always be an option when working under tight timelines. 
If you have your data readily available  (which is not always the case...), a dashboarding tool like Power BI can help you quickly reach the minimum viable product to meet those timelines. 
Additionally, if you are fortunate enough to work at a company that has Power BI licenses for everyone, sharing your new fancy dashboard is a piece of cake. 
Publish that dashboard to the service and send everyone the link. 


All that being said, there is a satisfaction I get from coding up a visualization. I really enjoy plotly for generating interactive charts with Python, and used that package a lot in one of my classes.
I've also been briefly exposed to a tool called [D3.js](https://d3js.org/), a javascript library that can be used to create bespoke data visualizations. 
Since learning about D3, I've always been curious but corporate demands don't always see eye to eye with fanciful endeavors. 
So I figured I would play around with it here and there in my free time, but its not enough for me to want to learn a new skill.
I want to use it to solve an issue or a problem, or answer a question. 


And here is where my long winded story finds its purpose. How does one visualize resource load? 
How do you make a visual to understand a resource's capacity and how full that capacity is?


One of my professors always said to stick to the basics, use bar charts for comparison and line charts for trends over time. 
Don't complicate the visualization, focus on the data and the story you are trying to tell with it. 
I think that is very sound advice, but I'm here to have some fun and learn something new. I've built those boring charts before. 

A GANTT chart could be an option.

![gantt](https://github.com/user-attachments/assets/39a5422b-d1c1-407a-b75a-b12b78236c1b)

I recently presented on the current workload of the analyst team to my management at my work and I used a GANTT chart. 
Frankly, I was disappointed with the GANTT chart. 
The chart visualized the timelines well, but did it show how much was on my plate? 
If I consider myself a resource, how do I visualize how much more capacity I have for additional responsibilities.
I have family, I have work, I have friends, and I have my own personal hobbies to juggle.

If we try to visualize my capacity as parts of a whole, being split up to upkeep those four categories in my life, 
and then further split up those categories into the tasks that I'm performing... I start to think of a treemap. 

![treemap](https://github.com/user-attachments/assets/9cdffee1-c42c-42eb-85b4-d2f11901d4cc)


A tree map can show parts of a whole in a tiered fashion. A category can be made up of smaller categories. 
Or in this case a workload is made up of different categories of tasks and then those tasks can take up a different percentage of time. 

I think I'm happy with a treemap as a snapshot of what my capacity looks like right now, this instant.
But what if I want to look ahead, and plan around my current workload to free myself up for a vacation, or a new hobby?
Then we would need to add the time dimension back into this visualization. Which brings us back to the GANTT chart. 

So we need a visualization that shows parts of a whole, and can show how these parts of a whole change across time.
Taking these requirements into account we can now create a bespoke data visualization, albeit with simpler data than mapping out my day to day life activities. 

![d3_prototype](https://github.com/user-attachments/assets/226d718c-4edc-497d-b92c-1526f7d342f7)

Here we have a grid of mini grids. The x-axis are different factories, and the y-axis spans from 2025 - 2027.
The grids represent the total capacity of the factory in rows of 10 mini squares. For example Factory A has a capacity of "94".
For this example lets say the factories make shirts and here it shows that Factory A can make 94 shirts in 2025. 
Some of these 94 squares are colored, which indicates the category of the shirt they will make. 
In 2025, Factory B will make 13 shirts, 10 "Category 5" shirts and 3 "Category 11" shirts. Categories can be different colors of shirts or something. 

If I'm the owner of the shirt company I can see that Factory B is at full capacity in 2026 and 2027. 
So if I need more shirts made in 2025, I will need to make them at another factory, probably factory D since they are completely open in 2025. 


Now there are other neat features, and you will have to trust me because my web dev skills are not great so I haven't figured out how to embed the visualization. 
But its fully interactive!
If you hover over on the squares it will tell you what category of shirt it is and how much total demand there is for that category of shirt at that factory.

![Screenshot 2025-06-02 at 9 32 49 PM](https://github.com/user-attachments/assets/5497858b-e762-4146-88a7-ac59300a402f)

Additionally, if you select an option on the filter in the top right, you can filter for a specific type of shirt!. Lets pretend "Option 1" is a button down shirt.
We see that our factories don't have a lot of capacity for button downs and only Factory A and D have a lot of open capacity to make more. 
If we filter to "Option 3" (let's pretend this option is tank tops), we see that we should start giving Factory D more tank tops to make, because they have a lot of open capacity. 

![Screenshot 2025-06-02 at 10 15 39 PM](https://github.com/user-attachments/assets/0dcea1c0-f4f3-44d2-be2e-b994ac0ca5ad)

This is very much a work in progress, and I'll continue to refine this visualization as my D3 skills grow. I'd also absolutely love to extend this visualization to 
see how well it would work using people as a resource. I think people as resources can introduce additional layers to load management because a person's experience and personality need to be taken into account. 
