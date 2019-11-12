---
layout: post
title: "Setting-up Jupyter Notebook with IRkernel"
image: '/images/posts/jupyternotebook.png'
comments: true
---

I decided to try the jupyter notebooks for two reasons.

First is that I am a bit tired of programming in the RStudio RMarkdown notebooks where, I noticed, computational time is longer than direct input in the console -- when it is not just simply not working. Also I want to go to something simpler and lighter to give a maximum of RAM for my actual scripts. For this latter, I actually switched to atom and packages like r-exec to directly send the commands to a basic R GUI. But the notebook format has its advantages when one want to quickly share a script and the figures along.

Second is that I am a missing python. The way of thinking is very different between python and R. Jupyter notebook with the magic commands like `%Rpush` makes it very easy to combine both strength of the two languages.

So here is how I installed jupyter:

```bash
conda create -n jupyter python=3.7
source activate jupyter
conda install jupyter
conda install R=3.5.1
conda install -c conda-forge ipython-sql
conda install cython
conda install rpy2
conda install numpy
conda install pandas
conda install tzlocal
conda install seaborn
```

Then in R terminal:

```R
install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest', 'httr', 'RJSONIO', 'Rcpp', 'R6', 'cli', 'fansi', 'rlang'))
devtools::install_github('IRkernel/IRkernel', dependencies = T)
IRkernel::installspec()
```
