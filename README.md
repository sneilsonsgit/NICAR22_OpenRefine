
# Learning to love OpenRefine

![OpenRefine is shiny and brilliant like a lil blue diamond](https://images.g2crowd.com/uploads/product/image/social_landscape/social_landscape_7bbddfe86a11f15ceb710ca21da17b97/openrefine.jpg)

<h2> OpenRefine is shiny and brilliant like its logo, the blue diamond above. </h2> 

And it can help you clean big datasets even if you don't know how to code.

Objectives of the class: 
- Learn how to open a .CSV file in OpenRefine 
- Learn how to use OpenRefine to pivot data and make it easier to work with
- Learn faceting, clustering
- Export cleaned data
- Fall in love <3 

First, let's navigate to OpenRefine's main page. 

<a href="https://drive.google.com/uc?export=view&id=1mAeF79tvCyM7j2bb_re3PAFrlZKherP4"><img src="https://drive.google.com/uc?export=view&id=1mAeF79tvCyM7j2bb_re3PAFrlZKherP4" style="width: 650px; max-width: 100%; height: auto" title="click" /></a>

You should have the data stored to your computers, so click the `Choose Files` button.

The .CSVs we will be using are in the `data` folder of this repository. Let's start with the first, `drugsbyhood_spread.csv`, a spreadsheet that shows the number of drug-related incidents reported to San Francisco police by year and police district. 

<a href="https://drive.google.com/uc?export=view&id=1MgEIvYPem_r5IYXfGRItI1eBF4Lm5TH7"><img src="https://drive.google.com/uc?export=view&id=1MgEIvYPem_r5IYXfGRItI1eBF4Lm5TH7" style="width: 650px; max-width: 100%; height: auto" title="click" /></a>

Go ahead and click `Next.`

You will hopefully be taken to a window that looks a lil something like this:

<a href="https://drive.google.com/uc?export=view&id=1Vld9F26ouEIuHBtO17G46G7O67Lw6CqU"><img src="https://drive.google.com/uc?export=view&id=1Vld9F26ouEIuHBtO17G46G7O67Lw6CqU" style="width: 650px; max-width: 100%; height: auto" title="click" /></a>

Hmmm, that data looks nice and neat. Go ahead and click the <b>`Create Project`</b> button in the top right corner. 

<h2> Voila. </h2> 

We are now officially in data-editing land.

<a href="https://drive.google.com/uc?export=view&id=1RbKsueGSbTMl8IbNHK-LArapv0i2R429"><img src="https://drive.google.com/uc?export=view&id=1RbKsueGSbTMl8IbNHK-LArapv0i2R429" style="width: 650px; max-width: 100%; height: auto" title="click" /></a>

<h1> Part 1: Changing data from wide to long. </h1>

This data is in a table, which is fine, if you like tables. But what if you want the data lined up so that the years are in their own columns? Perhaps you are a data reporter needing to make a specific kind of chart in DataWrapper that requires the years be in columns, for instance.

This task would be kind of a headache if you did it by hand (and what if we had data on 100 years?!) So let's tell OpenRefine to do it instead, in a few easy steps. 





