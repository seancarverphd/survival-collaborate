# survival-collaborate
Collaboratative Repo For Analyzing Survival During Great Recession
Collaborators: Moussa Doumbia and Sean Carver

Note: To run the code, you'll need the data, which are too big to place in a GitHub Repo.  

We obtained data from Kaggle.com.  The data consisted of all death
records (with identifying information redacted) from 2005 to 2015.  We
used the data for 2006 (a boom year) and 2009 (a bust year, during the
Great Recession).  We looked at causes of death.  Many decedents had
several causes assigned to them.  For each cause, we used a binomial
model which assumed that each decedent had the same independent
probability of dying.  We performed inference for this probability,
testing the null hypothesis that the death probabilities were the
same.  There were over 5,000 comparisons so we used a Bonferroni
correction.  Our sample sizes (equal to the US population in 2006 and
2009) were enormous (appox. 300 M).  Using an alpha of 0.0001 (before
the correction) and a two-sided alternative we found 104 signficant
results where the death proportion was greater in 2009 than 2006.  We
ranked these by Cohen's h (effect size for probabilities) and studied
the top 10, shown here.

![](fig/causes_and_explanations.png)

1. Download Death in the United States data from this link: https://www.kaggle.com/cdc/mortality/downloads/mortality.zip/2 
2. If this repository is in ./ then extract the data into ./data/
3. Switch to ./etl and open and run the jupyter notebook trim2006.ipynb       
4. Close all jupyter notebooks and open and run the jupyter notebook trim2009.ipynb
5. Close all jupyter notebooks and open and run the jupyter notebook etl2006.ipynb
6. Close all jupyter notebooks and open and run the jupyter notebook etl2009.ipynb
7. Takes hours, can skip: Close all jupyter notebooks and open and run the jupyter notebook combine.ipynb
8. combine.ipynb will produce two files k6.savepkl and k9.savepkl.  These are in repository under ./etl
9. Close all jupyter notebooks and Switch to ./analysis and run the jupyter notebook calc_pvalues.ipynb
10. link to the presentation https://prezi.com/view/fL4qT4fdPz2KdBWE1euK/
