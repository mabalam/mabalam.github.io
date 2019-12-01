As a data scientist in an organization you could be in a couple of situations:  
1) you have a dataset, you want to mine it for insights
2) you have a business problem, you want to find a solution

[NEED SOME INTRO]. 

The first situation is a common one. Often in large amount, every organization generates data on different aspects of business operations such as sales, revenue, cost, employee info etc. Let's say you've just joined an organization as a junior data scientist and you're yet to start your first project. One morning the product manager/someone from sales showed up at your desk and says - hey, welcome to the organization; we are excited to have you onboard! I have this data siting in my computer for sometime, can you see what you can do with it?

You get the data. Now you are thinking what to do with it? You have several options, with different levels of complexity. 

Describing the data is the most basic thing you could do. You could see if there are any problems with the dataset such as missing values, any outliers (as aresult of a mistake in data inputs). You could generate some basic statistics (e.g. mean, mediun, min-max, distribution etc.). You could also visualize variables that are interesting. And so on. This is basically all you have learnt and done as a data scientist all your life, known as exploratory data analysis (EDA).  

At the next level of complexity you are asking a good question and answering it. Remember that you are asking a question, not thinking what model to fit; not just yet. If it's an emplyee dataset you could ask: what is the composition of the employees in the organization in terms of gender & race? Or what is the salary distribution? Are there some odds that you discovered and want to highlight to the management? Most organizations will have already known them basic questions but you get the idea how to ask a question.  

The third level of complexity is a difficult one. You may not be able to discover anything until you studied the data well and understand the business as a whole. As you spend more time in the org and become familiar with it's business practices, along the way you will develop hypotheses. A single dataset that you now have may not answer your question, but you may need to pull together information from various sources to test your hypotheses.

And this leads to the second kind of situation you might find yourself in. You have been long enough in the org to know its ins and outs. And you developed a hypothesis/question along the way. Or, just may be your manager/CEO/CTO/CFO is asking you to get an answer for a question they were having trouble with.

If you are experienced enough you will probably subconscously know what your next steps are. But if you are a newbie yo may not know. In any case here is a pretty algorithmic way to think about the problem to solution.

![Project cycle in data scinece (@DataEnthus)](/images/misc/ds-cycle.png)

In step 1, you have a question or a problem. You could break it down to seveal smaller pieces of problems if needed. For example, if the question is forecasting how the company sales will gro in next 10 years, you could break it down to smaller pieces like how's the sales trending? How's the demand trending in the market? Etc.

In step 2, no, we are not thinking about what tools to use it. We are thinking about a methodological process that you think will answer your question. You lay a out a list of datasets, where to find them, may be a list of tools that might be useful etc. You haven't decided yet but having an overall process developed in your mind or in the paper (it's the same in an academic setting that you do in your research proposal before actually executing your study).

In step 3, you think about what tools can help answer this question. Is it a forecasting problem? Is it a linear regression problem? Do you need GIS technology? Is there a good package in Rstats? Or may be in Python?

Once you have decided on your tools and chose a particular set of tools now you are ready to go data hunting. Data that you need can be multi-million rows or may very well be some points dataset - depending on your problem and model you choose. For example if you have a forecasting problem you could uuse time series tools that needs time series data or you could be a great system dynamics modeler who learnt to use a system dynamic model that requires only few parameters. Have you found the data for the chosen model? If you have chosen time series forecasting, you will need a time series data. But if there is no time series data you don't have it. You could stop here and tell your manager/ceo/cto that you don't have data so you can't solve it? Or, else you could go back to your methodological process. May be there are other tools that don't require time series data. How about a system dynamic model?

Finally, you have chunked your big problem into smaller pieces. In aggregate have you been able to answer to the question? Are you and if your audience convinced you did it right? If yes, kudos. If not, go back to step 2.

The bottom line is that being a scientist means going through a process of exploration/discovery. We are often hung up with what tools/models we know and how to find some nails to use your hammer. But the tool is a small part of a problem solving process. So it's never about tools, it's always about solving problems.
