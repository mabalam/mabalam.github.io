## Data Science: Thinking like a scientist

As a data scientist in an organization you could be in a couple of different situations:  
1) you have a dataset now you need to know what to do with it  
2) you have a question or a problem, now you need to solve it.

[NEED SOME INTRO]. I will try to go through how you could go about in each situation.

The first problem is a common one. Every organization deliberately (or not) generates data, often in a large amount, on different aspect of their business such as employees info product sales, revenue, cost etc. You just joined the organization as a data scientist/analyst and yet to start your first project. So one morning the sales folks showed up at your desk and says - hey, welcome to this organization; we are excited to have you onboard! we have this data siting in my computer for days, can you see what you can do with it?

So they sent you the data in a csv file, you just downloaded it. Now what?

There are 3 things you could do with it:
a) describe the data,
b) ask a question of the data and answer it, and
c) discover something previously unknown

Each of the above comes with increasing level of complexity. Describing a the data is the most basic thing you could do. You could generate some basic statistics (data shape, mean, distribution). You could also visualize some of the variables that are interesting. You could see if there are any problems with the dataset such as missing values, any outliers (as aresult of a mistake in data inputs). And so on. This is basically all you have learnt and did all your data science life in exploratory data analysis (EDA).
The next level of complexity is asking a question of the data set and answering it. Remember we are asking a question, not thinking how to do a correlation matrix yet. (So don't think about how to apply a tool that you know, rather how to ask and answer your questions. Tools come later.) If it's an emplyee data set you could ask: what is the composition of the employees in the organization in terms of gender & race? Or what is the salary distribution? Most organizations will already have such basic employee information summarized but you get the idea how to ask a question and not how to apply a tool.
The third level of complexity is a tough one. You may not be able to discover anything until you studied the data well and understand the business as a whole. As you spend more time in the org and become familiar with it's business practices, along the way you will develop hypotheses. A single dataset that you have may not answer your question, you may need to pull together information from various sources to test your hypotheses.

And this leads to the second kind of situation you might find yourself in. You have been long enough in the org to know its ins and outs and it's data. And you developed a hypothesis/question along the way you need answer for. Or, just may be your manager/CEO/CTO/CFO is asking you to get an answer for a question they were having trouble with.

If you are experienced enough you will probably subconscously know what your next steps are. But if you are a newbie yo may not know. In any case here is a pretty algorithmic way to think about the problem to solution.

In step 1, you have a question or a problem. You could break it down to seveal smaller pieces of problems if needed. For example, if the question is forecasting how the company sales will gro in next 10 years, you could break it down to smaller pieces like how's the sales trending? How's the demand trending in the market? Etc.

In step 2, no, we are not thinking about what tools to use it. We are thinking about a methodological process that you think will answer your question. You lay a out a list of datasets, where to find them, may be a list of tools that might be useful etc. You haven't decided yet but having an overall process developed in your mind or in the paper (it's the same in an academic setting that you do in your research proposal before actually executing your study).

In step 3, you think about what tools can help answer this question. Is it a forecasting problem? Is it a linear regression problem? Do you need GIS technology? Is there a good package in Rstats? Or may be in Python?

Once you have decided on your tools and chose a particular set of tools now you are ready to go data hunting. Data that you need can be multi-million rows or may very well be some points dataset - depending on your problem and model you choose. For example if you have a forecasting problem you could uuse time series tools that needs time series data or you could be a great system dynamics modeler who learnt to use a system dynamic model that requires only few parameters. Have you found the data for the chosen model? If you have chosen time series forecasting, you will need a time series data. But if there is no time series data you don't have it. You could stop here and tell your manager/ceo/cto that you don't have data so you can't solve it? Or, else you could go back to your methodological process. May be there are other tools that don't require time series data. How about a system dynamic model?

Finally, you have chunked your big problem into smaller pieces. In aggregate have you been able to answer to the question? Are you and if your audience convinced you did it right? If yes, kudos. If not, go back to step 2.

The bottom line is that being a scientist means going through a process of exploration/discovery. We are often hung up with what tools/models we know and how to find some nails to use your hammer. But the tool is a small part of a problem solving process. So it's never about tools, it's always about solving problems.
