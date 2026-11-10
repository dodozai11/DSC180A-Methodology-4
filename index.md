# DSC 180A Methodology Assignment 4

**Name:** Terry Su
**Email:** [t9su@ucsd.edu](mailto:t9su@ucsd.edu)

**Section:** D21
**Mentor:** Professor Armin Schwartzman

---

**What is the most interesting topic covered in your domain this quarter?**

The most interesting topic covered this quarter is learning to identify confounders and reducing bias. In our prior data science courses, it was always the same routine 
when it came to data preparation such as cleaning, stripping unwanted spaces or characters, and then identifying missing values and accounting for them. However, in the
process of designing our own project and setting out own parameters, there is so much factors, some that are difficult to account for, such as the Claude servers in which
we send API calls to are subject to change in comparison to local servers. However, in using local servers such as Qwen models, the load and scale is compromised as it
is difficult to run so much trials without a big server. Our project proposal is based on efficiency of a model and how it outputs tokens based on different data formats
inputted. We also learn to account for variables such as temperature and prompt structure.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**

In my results, prose used about 1.7× more output tokens than JSON, and it would be interesting to pursue why. The likely reason is that JSON 
prose has no parser, so the model had to write its own, usually regex or string splitting that pull each value out of a templated sentence. That meant 
more lines of code, more comments explaining the extraction logic, and often extra helper functions. Interestingly, prose was actually cheaper than JSON on the 
input side (900 vs. 1,500 tokens), since JSON repeats every key on every row. So the tradeoff is that JSON costs more to send but less to process, while
prose is the reverse.

**What is a potential change you'd make to the approach taken in your current Quarter 1 Project?**

A potential change is to incorporate other aspects and do a deep dive on how data formats are processed. In our first proposal, we kind of just focus on efficiency 
and the input/output token trade-off. This has given us interesting information such as cost per X number of calls, which is applicable in scalability studies. However,
we also want to focus on other aspects such as accuracy of the model based on formats. This was our original idea but we found it difficult to implement due to frontier
AI models being so smart and just 100% everything with little variability. However, by increasing the difficulty of problems or using weaker models, I believe we could
find some more interesting findings when it comes to understanding how AI parses our inputs.

**What other techniques would you be interested in using in your project?**

A technique we would like to use is multiple regression to predict how many output tokens a reply will use. This was a technique suggested by 
our domain mentor. Instead of comparing the data formats two at a time, a regression 
looks at several factors together, the data format, which task it is, and how many rows of data are in the prompt. This would show how much each factor affects
token usage on its own, while holding the others constant. It could tell me whether prose still costs more than JSON once differences between
tasks are taken into account.
