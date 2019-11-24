---
title: 'Data science meets system dynamics (part 1)'
date: 2018-05-16
#permalink: /posts/2013/08/blog-post-2/
tags:
  - system dynamics
---

Developed at MIT’s [Sloan School of Management](https://mitsloan.mit.edu/faculty/academic-groups/system-dynamics/about-us) in 1950s system dynamics is a methodological approach to model the behavior of complex systems, where change in one component leads to change in others (like the domino effect with feedback loops added). This approach is widely applied in industries such as healthcare, disease research, public transportation, business management and revenue forecasting. The most famous application of system dynamics probably is in Limits to Growth.

A system dynamic model represents a complex system in terms of stocks & flows and their interactions via feedback loops to predict the behavior of the system. Let’s say a bank account has a Stock of $100. Every month $20 is deposited (represented by Flow 1) and an amount of $15/month is withdrawn (represented by Flow 2).

 

![](/images/misc/system-dynamics.png)

 

Now if the account owner is interested in how much money she is going to save after one period, it is a simple calculation and needs no calculators:

Stock 2 = Stock 1 + Flow 1 – Flow 2

However, a calculator may be needed if she’s to calculate savings over 5 years. And things begin to complicate even more variables such as interest rate is added. A system dynamic approach comes handy in representing and simulating behavior of these interactions, showing them in nice visual interfaces.

What does data science have to do with system dynamics? Coming soon, get your popcorn…...
