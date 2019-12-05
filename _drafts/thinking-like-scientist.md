## A data science project cycle

As a data scientist in an organization you frequently find yourself in a couple of situations:  
1) you have a dataset, you want to extract from it some useful information
2) there's a business problem, you want to find a data-driven solution

The first situation is actually a common one, basically doing all the things you have learnt in the exploratory data analysis (EDA) in your data science journey. In this article I will explain how to navigate the second kind of situations. 

Let's say you have been long enough in your organization to know its business practices and all the kinds of data it generates. And along the way you have developed a hypothesis that you want to test. Or, just may be your manager/CEO/CTO is asking you to get an answer to a question they were having trouble with. If you are experienced enough you will probably know what your next steps are, but newbies often struggle to kick off their thinking in the right direction. So here is a pretty algorithmic way to think about the problem through to solution.

![Project cycle in data scinece (@DataEnthus)](/images/misc/ds-cycle1.png)

In step 1, you have a question or problem. If it's a big one, you could break it down to smaller pieces if needed. For example, if the question is about forecasting sales growth over the next 10 years, you could break it down to pieces such as what's been the historical sales? How's the sales currently trending? How's the demand trending in the market? How are the competitors doing? Etc.

In step 2, no, you are not thinking about what tools to use. You are thinking about a methodological process that will guide you through answering your question. You lay out a list of datasets, locate where to find them, and may be make a list of tools that might be useful. Even if you haven'd made final decisions on specifics of data/tools, having an overall process in your mind or written on paper helps a lot, even if it will change later on with additional information. This approach is kind of similar in academic settings where you write your research proposal before actually executing the research; things often change along the way as you study the problem at hand.

In step 3, now you are thinking about what tools can help answer this question. If it's a forecasting problem, you would think if a time series based model is any useful? Or is it a linear regression problem instead? Do you need GIS technology? Is there a good package in R or Python?

Once you have explored all available options and decided upon a particular set of tools, you are now ready to go data hunting. Data that you need can be a multi-million rows dataset or may very well be a hundred data points - depending on your problem and the model you choose.  

Have you found the required data for the chosen model? If yes, you are good to go fit your model. But if you don't have all required input datasets you should stop here and go back to your methodological process. May be there are other tools/methods that don't require time series data? How about a system dynamic model that requires not many parameters? 

Finally, you have chunked your big problem into smaller pieces, and asnwered them individually. In aggregate have you solved the big picture problem? If yes, kudos. If not, go back to step 2.

In summary, being a scientist means going through a process of exploration/discovery. We are often hung up with what tools/models we know and how use them in datasets. As we have seen, selecting the right tool is a small part of the problem solving process. It's always problems first, tools later.
