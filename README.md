# survival-collaborate
Collaboratative Repo For Analyzing Survival During Great Recession
Collaborators: Moussa Doumbia and Sean Carver

Note: To run the code, you'll need the data, which are too big to place in a GitHub Repo.  

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
