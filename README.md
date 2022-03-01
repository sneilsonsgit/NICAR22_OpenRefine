
# Learning to love OpenRefine

![OpenRefine is shiny and brilliant like a lil blue diamond](https://images.g2crowd.com/uploads/product/image/social_landscape/social_landscape_7bbddfe86a11f15ceb710ca21da17b97/openrefine.jpg)

<h2> OpenRefine is shiny and brilliant, just like its logo. </h2> 

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

Hmmm, that data looks nice and neat. Go ahead and select the `Attempt to parse cell text into numbers` box and then click the <b>`Create Project`</b> button in the top right corner. 

<a href="https://drive.google.com/uc?export=view&id=1-svLXKxNKKAPOkokkKvUrUVBlfhzamE5"><img src="https://drive.google.com/uc?export=view&id=1-svLXKxNKKAPOkokkKvUrUVBlfhzamE5" style="width: 650px; max-width: 100%; height: auto" title="click" /></a>

<h2> Voila. </h2> 

We are now officially in data-editing land. Your numbers should appear green, but otherwise the table should look similar to how it looked before.

<h1> Part 1: Changing data from wide to long. </h1>

This data is in a table, which is fine, if you like tables. But what if you want the data lined up so that the years are in their own columns? Perhaps you are a data reporter needing to make a specific kind of chart in DataWrapper that requires the years be in columns, for instance.

This task would be kind of a headache if you did it by hand (and what if we had data on 100 years?!) So let's tell OpenRefine to do it instead, in a few easy steps. 

First, click on the triangle next to the `2003` column name. Then select `Transpose` and then `Transpose Cells Across Columns into Rows.`

<a href="https://drive.google.com/uc?export=view&id=1UFh3Oursm6IdfbRLYLmBKW2Eajdewc7n"><img src="https://drive.google.com/uc?export=view&id=1UFh3Oursm6IdfbRLYLmBKW2Eajdewc7n" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

This will "pivot" the data from individual columns for each year to putting all of the years into one column and creating a bunch more rows, essentially making it longer and thinner.  If this wording doesn't feel super intuitive yet, don't worry. It's quite common to feel that way.

But before we pivot, let's make sure the data comes out looking the way we want it to. Make sure the box marked `Fill down in other columns` is checked, and select `2003` to `(last column)` to make sure you're transposing all of the year columns into a single column. 

<a href="https://drive.google.com/uc?export=view&id=1yPU5nEucXv4bel7VHKyrYcD9iD9I4nND"><img src="https://drive.google.com/uc?export=view&id=1yPU5nEucXv4bel7VHKyrYcD9iD9I4nND" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Give your `Key Column` the name `year`, and your `Value Column` the name `drug_incidents` or `incidents` or whatever you'd like. Then click `Transpose.`

Your data should now look like this:

<a href="https://drive.google.com/uc?export=view&id=1p6dh-DkXHOQ7OyNA9IPSOw39uH0MmakP"><img src="https://drive.google.com/uc?export=view&id=1p6dh-DkXHOQ7OyNA9IPSOw39uH0MmakP" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Now let's switch it back, because why not?! Click the triangle next to the `year` column and select `Columnize by Key/Value Columns.` The following window will pop up.

<a href="https://drive.google.com/uc?export=view&id=1cbbL3R33q_ZD85fHskbgCbdONd3ParXy"><img src="https://drive.google.com/uc?export=view&id=1cbbL3R33q_ZD85fHskbgCbdONd3ParXy" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

We want to "columnize" the `year` column, and make sure the numbers in the `drug_incidents` column fill in the values for each year, so this looks good! Go ahead and click OK.

<a href="https://drive.google.com/uc?export=view&id=10VpcUYkfoxVgQ4zaAftKRyE8upeSFf39"><img src="https://drive.google.com/uc?export=view&id=10VpcUYkfoxVgQ4zaAftKRyE8upeSFf39" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

There we go, back to wide format. For fun, try `sort`ing the neighborhoods by order of most reported drug incidents in 2018. Click the drop-down menu next to the `2018` column, then `Sort` and then `Sort...` 

<a href="https://drive.google.com/uc?export=view&id=1z-SBKw2jeelauD-b4kQqiODE9k1f1LXZ"><img src="https://drive.google.com/uc?export=view&id=
1z-SBKw2jeelauD-b4kQqiODE9k1f1LXZ" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

You can now sort the data as numbers, with the largest number appearing first.

Cool! That is the end of part I.

<h1> Part 2: Cleaning dirty data </h1>

A lot of the stuff we just did can be done in Google Spreadsheets pretty easily. But this next part, which will involve cleaning dirty data, is OpenRefine's superpower. While I generally use simple R commands to pivot my data, I still will often run data through OpenRefine before I open it in RStudio because it is very smart at recognizing patterns in cells that might take me longer to address in an R script. 

We are going to practice these skills with a spreadsheet called `ucb_stanford_2014.csv`. This data is an ideal level of messy for this class, so props to Peter Aldhous, my former professor, for digging it up (and for teaching me much of the steps we will take with the data). This data includes federal government grants to UC Berkeley and Stanford University in 2014, downloaded from <a href="https://www.usaspending.gov/">USASpending.gov.</a> 

Go ahead and click the `Open...` button in the top right corner of your OpenRefine window. That should take you back to the OpenRefine landing page. Then click `Choose Files` again, and this time, select `ucb_stanford_2014.csv`. Go ahead and hit `next`. Make sure to click `Attempt to parse cell text into numbers` so that columns with numeric values get recognized as such. 

After configuring that setting, click `Create Project`. Your window should look like this:

<a href="https://drive.google.com/uc?export=view&id=1SMdDg2lkvOkNKx-HrUoxZzgwHHME55I2"><img src="https://drive.google.com/uc?export=view&id=1SMdDg2lkvOkNKx-HrUoxZzgwHHME55I2" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Now the real fun begins. 

<h2> Dealing with additional characters </h2>

Right off the bat, we can see the money column is a bit messy. Some of the values have parentheses to indicate they are negative amounts, and some have commas while others do not. These characters and the $ symbols are making the column get recognized as a text column rather than as numeric, which we'll need if we want to calculate donation totals. 

There's a fancier way to do this, but for now, you can just click on the drop-down arrow next to `Award Amount,` select `Edit Cells` and then click `Replace.` Type in an opening parenthesis `(` into the `Find` box and then in the `Replace` box, type in a `-` dash. Then hit ok. 

<a href="https://drive.google.com/uc?export=view&id=19HINJxs4l076WOxxStzSIgDfmzXXYt9Q"><img src="https://drive.google.com/uc?export=view&id=19HINJxs4l076WOxxStzSIgDfmzXXYt9Q" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Then get rid of the other three annoying characters, `)` `,` and `$`, by typing them into the `Find` box and then leaving the `Replace` box blank. Once you do this, you can once again select `Edit Cells,` but this time select `Common Transforms` and then click `To Number.`  Your final column should look like this:

<a href="https://drive.google.com/uc?export=view&id=1eCnUIysQPaVAd9heCYAZNKVfjwruGYJg"><img src="https://drive.google.com/uc?export=view&id=1eCnUIysQPaVAd9heCYAZNKVfjwruGYJg" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

<h2> Clustering </h2>

Let's see if we can group by recipient. Select the drop-down menu in the `Recipient` column and then click `Facet` -> `Text Facet.` Your page should now have a bar on the left that looks like this:

<a href="https://drive.google.com/uc?export=view&id=1rPkXpT83xxl4ylHWbuFUcVuH-yYEcWdC"><img src="https://drive.google.com/uc?export=view&id=1rPkXpT83xxl4ylHWbuFUcVuH-yYEcWdC" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Weird. Why are there so many different possible values for `recipient`? There are 28, to be precise, yet we know that the data should only include contributions made to two distinct institutions: Stanford and Berkeley. So let's clean this column up by grouping together values we know to be similar, through a method known as clustering. 

Clustering is my favorite function within OpenRefine, because it can allow you to quickly clean up a big dataset by identifying similar text values without a bunch of fancy fuzzy matching or other complex processes. To me, it is what distinguishes OpenRefine from another low-coding spreadsheet program like Excel. Let's explore the different types of clustering we can do here.

OpenRefine uses two overarching clustering categories. The first, `key collision,` creates alternate versions of strings that contain only the most meaningful parts (the key part), then buckets the strings together based on whether those keys match (the collision part). The second, `nearest neighbor,` compares all the different strings to each other and bins them when they are similar enough. But nearest neighbor methods take forever for big datasets because each pair needs to be compared to every other pair.

Thus, we are going to focus on `key collision` methods because they tend to be more efficient. The first, `fingerprint,` is the default key collision method, because it tends to make the fewest mistakes (`fingerprint` groups different strings together by removing whitespace, changing all characters to lowercase, removing punctuation and several other intuitive steps.) Let's apply the `fingerprint` method to our dataset.

There's also `metaphone3`, a method that transforms strings into how they are typically pronounced. This is useful for errors that involve misspellings. For a more detailed explanation on clustering methods, including a detailed breakdown of `nearest neighbor` methods, see <a href="https://github.com/tfmorris/OpenRefine/wiki/Clustering-In-Depth"> this link. </a>

Let's start with the `fingerprint` method. What does it show? 

<a href="https://drive.google.com/uc?export=view&id=1oTpCeGEb1NFcIdN4Tybco28ZcUVBzHh3"><img src="https://drive.google.com/uc?export=view&id=1oTpCeGEb1NFcIdN4Tybco28ZcUVBzHh3" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Nice, look like it's accurately, effectively binned some similar values. Go ahead and rename these so they will be grouped together; the `REGENTS OF THE UNIVERSITY OF CALIFORNIA` cluster and the 'University of California, Berkeley' cluster can both become `University of California, Berkeley,` while the `LELAND STANFORD JUNIOR UNIVERSITY` cluster can just become `Stanford University.` Make those changes by entering the text in the corresponding boxes, checking the <b>`Merge?`</b> box and hitting <b>`Merge selected & Re-Cluster.`</b>

That should get rid of about nine of the values. Then you'll have the option to re-cluster again; go ahead and do that. Eventually you'll get to a point where you can't cluster with the `fingerprint` method anymore.

<a href="https://drive.google.com/uc?export=view&id=1NBDpEggoom7rRjOq3FDQx1VMTI37eQsS"><img src="https://drive.google.com/uc?export=view&id=1NBDpEggoom7rRjOq3FDQx1VMTI37eQsS" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Time to select the `metaphone` method! Ooh, nice, look at all of these choices. Go ahead and `cluster` these ones using the same names you selected earlier: `University of California, Berkeley` and `Stanford University`. 

<a href="https://drive.google.com/uc?export=view&id=1LwC4jHNRB2EuVEFtEdkU0svcipFPtt1c"><img src="https://drive.google.com/uc?export=view&id=1LwC4jHNRB2EuVEFtEdkU0svcipFPtt1c" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Woohoo, you should be down to six different types now! From here, close your cluster window and go back to the text facet pane. It should be easy now to manually edit the remaining entries. By clicking on the `Interuniveristy Center for Japanese Language` row, you can see it's located at Stanford, so you can edit that one to be `Stanford University` as well. Go ahead and click the small `edit` button next to the name in the `Receipient` facet box, and do the same for the remaining values so they all fall under either `University of California, Berkeley` or `Stanford University`.

Voila:

<a href="https://drive.google.com/uc?export=view&id=1LNi6zPTI7rOKSc_W5lk4BYN2KZmvQlXP"><img src="https://drive.google.com/uc?export=view&id=1LNi6zPTI7rOKSc_W5lk4BYN2KZmvQlXP" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

You can go ahead and click `x` on the Recipient facet box. 

<h2> Trimming whitespace and changing cases </h2>

So now our `Recipient` column has been cleaned up, but it looks like some of the other columns need cleaning. Go ahead and create a `Text facet` for `Recipient city.` Oof, that's a lot of possible cities for just two universities!

<a href="https://drive.google.com/uc?export=view&id=13Lh8yOBcXWtKJgjaon7bJISZiA2xgzfg"><img src="https://drive.google.com/uc?export=view&id=13Lh8yOBcXWtKJgjaon7bJISZiA2xgzfg" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

This time, before we cluster, let's do something simpler because the city field is so short. Select the arrow to drop-down the transformation menu, click `Edit cells` -> `Common transforms` -> `Trim leading and trailing whitespace.` This removes any spaces that are in the cells either before or after the city name. 

<a href="https://drive.google.com/uc?export=view&id=12zaE7FWJ8XRpS2NeF9JlXLCH9jchxgvh"><img src="https://drive.google.com/uc?export=view&id=12zaE7FWJ8XRpS2NeF9JlXLCH9jchxgvh" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Nice, we've matched a bunch of additional values just by taking some spaces out. Now let's do one other easy transform, `Edit cells` -> `Common transforms` -> `To titlecase.` That matches a bunch of other values. We are left only with truly different cities. We couuld take the next step and try to see whether some of these cities are wrongfully entered — after all, again, two universities should only have two cities — but perhaps we can make that call later because questions remain (for instance, should we refer to Stanford by the city that surrounds it, Palo Alto, or the census-designated place on which the university technically sits, Stanford? For now, just manually edit the `Veterans Bureau Hospi` row, located at Stanford, to be in `Palo Alto` (or `Stanford` if you prefer) and move on. 

<a href="https://drive.google.com/uc?export=view&id=1ORowUnO328VlimrEbTNkTgZbenytrN9V"><img src="https://drive.google.com/uc?export=view&id=1ORowUnO328VlimrEbTNkTgZbenytrN9V" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

<h2> Convert fields to dates </h2> 

Looks like we have a column in the data, `Award date`, that should be recognized as a date field — only it's not getting recognized as such! If it were, it would be showing up in green like the other non-text columns in our data. So let's change that. Click on the upside-down triangle next to `Award date`, then click `Edit column` -> `Add column based on this column.` 

<a href="https://drive.google.com/uc?export=view&id=1qvlYfh64tL5yQzBx2Q41kXaOPej8OXi5"><img src="https://drive.google.com/uc?export=view&id=1qvlYfh64tL5yQzBx2Q41kXaOPej8OXi5" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

There are some fancy coding things you can do in this box, but for now, let's keep it as is. We just want to keep the date column as text to make sure the column converts accurately. Give your column a name, maybe something like `Award Date 2` or `Award Date converted`, and click `OK`.

Then open the menu next to your duplicated award date column and select `Edit cells` -> `Common transforms` -> `To date`. Now your column is in standard date format! And you can make sure it converted correctly by comparing it to the column just to its left. Looks good to me.

<a href="https://drive.google.com/uc?export=view&id=19Q2K-8uUN5-w5T-butEygdWGJNq-8dUl"><img src="https://drive.google.com/uc?export=view&id=19Q2K-8uUN5-w5T-butEygdWGJNq-8dUl" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

<h2> Made a mistake? no worries, just undo! </h2>

Let's say I actually don't like the way the date column converted and want to go back to a simpler time, a time where I had just one date column. Or perhaps I want to remember all the things I did to the data step by step from the very beginning. Well, OpenRefine allows you to do that in a controlled and discerning manner by showing all of the steps in the `Undo/Redo` bar. From there, you can go back and undo as many steps as you'd like. Click some of the earlier steps and watch your data get de-cleaned.

<a href="https://drive.google.com/uc?export=view&id=1RZuhicKd2t-EDUVJMZQfgVcy6zWsJ-1A"><img src="https://drive.google.com/uc?export=view&id=1RZuhicKd2t-EDUVJMZQfgVcy6zWsJ-1A" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

<h2> Finally, make your cleaning process repeatable </h2>

This Undo/Redo pane, with all of our steps listed in a linear fashion, is also helpful to use in the future, should we encounter similar data and want to clean it quickly. Click the `Extract...` button and the window `Extract Operation History` should pop up. Check the tasks that you'd want to repeat on similar data that aren't super specific to this dataset. For instance, we'd probably want to keep the transformations we made to the financial award column, the whitespace trimming and the case transformations. 

Open a TextEdit window, or if you have Sublime text or a different text editor you prefer, open that. Then paste the code you generated into a new window and save it with a `.json` extension in an easy-to-remember folder. I saved mine in this GitHub repo!

<a href="https://drive.google.com/uc?export=view&id=1vTMLdmIj-uuQP_OpN2wKWtZz-fNZR6Nc"><img src="https://drive.google.com/uc?export=view&id=1vTMLdmIj-uuQP_OpN2wKWtZz-fNZR6Nc" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

Now if you want to apply the same commands to a similar data file, you can! Just hit `Apply`, paste the `.json` script you saved into the window, and watch the replicable magic happen.

<a href="https://drive.google.com/uc?export=view&id=1OZFMQsilGH6G20A8x3sqCWi7Fu1VpFAd"><img src="https://drive.google.com/uc?export=view&id=1OZFMQsilGH6G20A8x3sqCWi7Fu1VpFAd" style="width: 650px; max-width: 100%; height: auto" title="click"/></a>

That's all from me :) Hope you enjoyed the class, and please let me know if you have additional questions about OpenRefine or other stuff that I know anything about. 



