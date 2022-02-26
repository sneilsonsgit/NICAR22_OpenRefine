
# Learning to love OpenRefine

![OpenRefine is shiny and brilliant like a lil blue diamond](https://images.g2crowd.com/uploads/product/image/social_landscape/social_landscape_7bbddfe86a11f15ceb710ca21da17b97/openrefine.jpg)

<h2> OpenRefine is shiny and brilliant like its logo, the blue diamond above. </h2> 

And it can help you clean big datasets even if you don't know how to code!

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

First, click on the triangle next to the `2003` column name. Then select `Transpose` and then `Transpose Cells Across Columns into Rows.`

<a href="https://drive.google.com/uc?export=view&id=1_lS-i-hJzSI3VTcmtEl6dFdDab0C1Vw_"><img src="https://drive.google.com/uc?export=view&id=1_lS-i-hJzSI3VTcmtEl6dFdDab0C1Vw_" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

This will "pivot" the data from individual columns for each year to putting all of the years into one column and creating a bunch more rows, essentially making it longer and thinner.  If this wording doesn't feel super intuitive yet, don't worry. It's quite common to feel that way.

But before we pivot, let's make sure the data comes out looking the way we want it to. Make sure the box marked `Fill down in other columns` is checked, and select `2003` to `(last column)` to make sure you're transposing all of the year columns into a single column. 

<a href="https://drive.google.com/uc?export=view&id=1BdQz0jr-JmzQjZyDP6GjDi_HHaAdUm-j"><img src="https://drive.google.com/uc?export=view&id=1BdQz0jr-JmzQjZyDP6GjDi_HHaAdUm-j" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Give your `Key Column` the name `year`, and your `Value Column` the name `drug_incidents` or `incidents` or whatever you'd like. Then click `Transpose.`

Your data should now look like this:

<a href="https://drive.google.com/uc?export=view&id=1CTstpPXAOUvs29IT44WLKTkwM3R3MCQO"><img src="https://drive.google.com/uc?export=view&id=1CTstpPXAOUvs29IT44WLKTkwM3R3MCQO" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Now let's switch it back, because why not?! Click the triangle next to the `year` column and select `Columnize by Key/Value Columns.` The following window will pop up.

<a href="https://drive.google.com/uc?export=view&id=1sQa0uBxj4UHmA_VzLx-8DDojVwCkgrG_"><img src="https://drive.google.com/uc?export=view&id=1sQa0uBxj4UHmA_VzLx-8DDojVwCkgrG_" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

We want to "columnize" the `year` column, and make sure the numbers in the `drug_incidents` column fill in the values for each year, so this looks good! Go ahead and click OK.

<a href="https://drive.google.com/uc?export=view&id=1cBsph2w6Q03kcXmM1pCt0O8kxMon7gbv"><img src="https://drive.google.com/uc?export=view&id=1cBsph2w6Q03kcXmM1pCt0O8kxMon7gbv" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

There we go, back to wide format. And end of part I.

<h1> Part 2: Cleaning dirty data </h1>

Cleaning dirty data is OpenRefine's superpower. While I generally use simple R commands to pivot my data, I still will often run data through OpenRefine before I open it in RStudio because it is very smart at recognizing patterns in cells that might take me a long time to address in a script. 

We are going to practice these skills with a spreadsheet called `ucb_stanford_2014.csv`. This data is an ideal type of messy for this class, so props to Peter Aldhous, my former professor, for digging it up. The data includes federal government grants to UC Berkeley and Stanford University in 2014, downloaded from <a href="https://www.usaspending.gov/">USASpending.gov.</a> 

Go ahead and click the `Open...` button in the top right corner of your OpenRefine window. That should take you back to the OpenRefine landing page. Then click `Choose Files` again, and this time, select `ucb_stanford_2014.csv`. Go ahead and hit `next`. Make sure to click `Attempt to parse cell text into numbers` so that columns with numeric values get recognized as such. 

After configuring that setting, click `Create Project`. Your window should look like this:

<a href="https://drive.google.com/uc?export=view&id=1SMdDg2lkvOkNKx-HrUoxZzgwHHME55I2"><img src="https://drive.google.com/uc?export=view&id=1SMdDg2lkvOkNKx-HrUoxZzgwHHME55I2" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Now the real fun begins. 

<h2> dealing with additional characters </h2>

Right off the bat, we can see the money column is a bit messy. Some of the values have parentheses to indicate they are negative amounts, and some have commas while others do not. These characters and the $ symbols are making the column get recognized as a text column rather than as numeric, which we'll need if we want to calculate donation totals. 

There's a fancier way to do this, but for now, you can just click on the drop-down arrow next to `Award Amount,` select `Edit Cells` and then click `Replace.` Type in an opening parenthesis `(` into the `Find` box and then in the `Replace` box, type in a `-` dash. Then hit ok. 

<a href="https://drive.google.com/uc?export=view&id=19HINJxs4l076WOxxStzSIgDfmzXXYt9Q"><img src="https://drive.google.com/uc?export=view&id=19HINJxs4l076WOxxStzSIgDfmzXXYt9Q" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Then get rid of the other three annoying characters, `)` `,` and `$`, by typing them into the `Find` box and then leaving the `Replace` box blank. Once you do this, you can once again select `Edit Cells,` but this time select `Common Transforms` and then click `To Number.  Your final column should look like this:

<a href="https://drive.google.com/uc?export=view&id=1eCnUIysQPaVAd9heCYAZNKVfjwruGYJg"><img src="https://drive.google.com/uc?export=view&id=1eCnUIysQPaVAd9heCYAZNKVfjwruGYJg" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>


<h2> Trimming whitespace </h2>





<h2> Convert fields to dates </h2>
<h2> Clustering </h2>
<h2> make a mistake? no worries, just undo </h2>


