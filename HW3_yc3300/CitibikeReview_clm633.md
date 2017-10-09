# Review of Proposal

## a. verify that their Null and alternative hypotheses are formulated correctly

The null hypothesis is [here](https://github.com/cmoscardi/PUI2017_yc3300/blob/master/HW3_yc3300/HW3_Assignment2.ipynb), about 4 cells from the top.

LGTM! I think the letters in your LaTeX are off though. Shouldn't it be S and C uniformly? Did you copy this from someone else who was doing men vs. women (hence M,W)? :P

Three small points: 
1. I'd probably be clear that, for example, `Sweekend` refers to the number of rides taken - so we're taking ratios of counts of trips.
2. I'd probably make clear what exactly a "customer" vs. "subscriber" is.
3. I messed this up in mine as well - I think we need to be specific about the timeframe that we're formulating our hypothesis for.

## b. verify that the data supports the project: i.e. if the a data has the appropriate features (variables) to answer the question, and if the data was properly pre-processed to extract the needed values (there is some flexibility here since the test was not chosen yet)

The data itself: I would recommend using more data. It looks like you pulled down March of 2015. Perhaps users behave differently in March than they do in June or July? Also, 2015 and 2017 are far apart from each other - it's possible user behavior has changed since March 2015.

That said, this is a decent enough sample, it seems to me - considering it's the entire population of rides in March of 2015.

Parsing: looks good! A couple of nits.
1. `df['date'][df['usertype'] == 2]` -- personally, I'd write this `df[df['usertype'] ==2]['date']` - while your syntax is functionally identical, it's more readable as "we select into the DF for type Customer, then extract the date column" (vs. "we extract the date column, then index by way of the previous DF for customers"). This is also brittle in certain chained filtering situations - this works because your indicies happen to line up since you're just selecting out a column.
2. Again with the `norm_w` and `norm_m`... still looks correct, however.
3. Plot #2 contains error bars and it's not clear to me if those are necessary. I guess if we consider this as the entire population of rides for January 2015, we don't need them. If we consider this as a sample for rides, what is it a representative sample for? Citibike rides in January each year? 
4. I like plot #3. The normalized counts make things more clear.
5. I think this is wrong. You're comparing the normalized counts for weekday and weekend. Then, you're trying to say the proportion of all rides by subscribers on weekend is less than the proportion of all rides by customers on the weekend. Which is different than your initial null hypothesis.

I think your processing here is correct for a different null hypothesis. But not the null hypothesis you proposed. I'm not sure how you test the null hypothesis you proposed.

## c. chose an appropriate test to test H0 given the type of data, and the question asked. You can refer to the flowchart of statistical tests for this in the slides, or here, or Statistics in a Nutshell.
Right so I'm going to come back to this one after I figure out the correct thing to say for **b.5**
