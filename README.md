# Machine-Learning-Yearning-Study-Notes
Study notes on Andrew Ng's Machine Learning Yearning books

## Basic Error Anaysis

- When starting a new project, especially if it is in an area in which not an expert, it is hard to correctly guess the most promising directions

- So dont start off trying to design and build the perfect system. Instead build and train a basic system as quickly as possible - perhaps in  a few days. Then use error analysis to help to identify the most promising directions and iteratively improve algorithm from there

- The process of looking at misclassified examples is called error analysis

### Example case study of error analysis:
- Cat app - several examples where it mistakes dogs for cats, some dogs do look like cats!
- A team member proposed incorporating 3rd party software that will make the system do better on dog images. These changes will take a month, and the team member is enthusiastic, Shoud you ask them to go ahead?
- Before investing a month on this task, I recommend that you first estimate how much it will actually improve the system's accuracy. Then we can more rationally decide if this is worth the month of development time, or if you're better off using that time on othet tasks.

### In detail, here's what we can do:
1. Gather a sample of 100 dev set examples that your system misclassfied, i.e. examples that the system made an error
2. Look at these examples manually, and count what fraction of them are dog images

### At the case where the dog error rate is 5% of the dev sets
The process of looking at misclassified examples is called error analysis. In this example, if we find that only 5% of the misclassified images are dogs, then no matter how much improve our algorithm's performance on dog images, we cant get rid of more than 5% of the errors. In other words, 5% is a "celling" (meaning the maximum possible amount) for how much the proposed project could help.

Thus if the overall system is currently 90% accurate (10% error), then no matter how much we improve our algorithms performance on dog images, the improvement is likely to result in at best 90.5% accuracy (9.5% error, which is 5% less error than the original 10% error)

- Dog error rate is 5% of the dev sets, And if overall system is 90% accuracy -> Improvement = 90% + 5%/100 = 90.5%
- 100 misclassify images, 5% improvements, 95 still misclassify images, 
new improvement = (90%)  + (100-5)/100 = 90.5%
new improvement is at best 90.5%, which is 5% less error than the original 10% error


### At the case where the 50% of the mistakes are dogs

In contrast, if I find that 50% of the mistakes are dogs, then I can be more confident that the proposed project will have a big impact.
- new improvements = 90% + (100-50%)/100% = 95%
It could boost accuracy from 90% to 95% (a 50% relative reduction in error, from 10% to 5%)


### The simple counting of error analysis give us a quick way to estimate the possible value of incorporating the 3rd party software for dog images. It provides a quantitative basis on which to decide whether to make this investment

### Error analysis can often help us to figure on how promising different directions are. Andrew Ng said he seen many engineers reluctant to carry out error analysis - > He pointed out that straight jump in and implement some ideas, rather than question if the idea is worth the time investment, This is common mistake, it might result in the team spending a month only to realize afterward that it resulted in little benefit


### Error analysis refer to the process of examining dev set examples that your algorithm misclassifed, so that if we understand the underlying causes of the errors, This can help to priortize the projects, as in this example, and inspire new directions.

