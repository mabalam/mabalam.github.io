## A data science project cycle

As a data scientist in an organization you could be in a couple of situations:  
1) you have a dataset, you want to mine it for some useful information
2) you have a business problem, you want to find a data-driven solution

The first situation is actually a common one, it's basically doing all things you have learnt in exploratory data analysis (EDA) in your data science journey. In this article I will explain how to navigate the second kind of situations. 

Let's say you have been long enough in your organization to know its business practices and all kinds of data it generates. And you developed a hypothesis/question along the way that you want to test. Or, just may be your manager/CEO/CTO/CFO is asking you to get an answer to a question they were having trouble with. If you are experienced enough you will probably know what your next steps are, but newbies often struggle to kick off their thinking in the right direction. So here is a pretty algorithmic way to think about the problem through to solution.

![Project cycle in data scinece (@DataEnthus)](/images/misc/ds-cycle.png)

In step 1, you have a question or a problem. If it's a big problem, you could break it down to seveal smaller pieces if needed. For example, if the question is to make a forecast of how company sales will grow in the next 10 years, you could break it down to pieces such as how's the sales trending? How's the demand trending in the market? How are the competitors doing in the business? Etc.

In step 2, no, you are not thinking about what tools to use. You are thinking about a methodological process that will answer your question. You lay a out a list of datasets, locate where to find them, and may be make a list of tools that might be useful. Even if you haven'd made final decisions on specifics of data/tools, having an overall process developed in your mind/on paper helps a lot, even if it will change later depending on new information. This approach is kind of similar in academic settings where you write your research proposal before actually executing the research; things often change along the way.

In step 3, now you are thinking about what tools can help answer this question. If it's a forecasting problem, would would think if a time series based model is any useful? Or is it a linear regression problem instead? Do you need GIS technology? Is there a good package in R stats? Or may be in Python?

Once you have explored all available options and decided upon a particular set of tools, you are now ready to go data hunting. Data that you need can be a multi-million rows dataset or may very well be a hundred data points - depending on your problem and model you choose. 
Now have you found the required data for the chosen model? If you don't have all required input datasets you would stop here. You could go back to the manager and tell that you don't have data so you can't do it? Or, else you could go back to your methodological process. May be there are other tools/methods that don't require time series data. How about a system dynamic model that requires only a few parameters? 

Finally, you have chunked your big problem into smaller pieces, and asnwered them individually. In aggregate have you solved the big picture problem? If yes, kudos. If not, go back to step 2.

In summary, being a scientist means going through a process of exploration/discovery. We are often hung up with what tools/models we know and how use them in datasets. As we have seen, selecting the right tool is a small part of thea problem solving process. It's always problems first, tools later.
