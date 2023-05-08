Download Link: https://assignmentchef.com/product/solved-stats507-homework-6-pandas
<br>
<h1>1         Warmup: constructing pandas objects</h1>

In this problem, you will create two simple pandas objects.

<ol>

 <li>Create a pandas Series object with indices given by the first 10 letters of the English alphabet and values given by the first 10 primes.</li>

 <li>Below is a table that might arise in a genetics experiment. Reconstruct this as apandas</li>

</ol>

<h1>2         Working with pandas DataFrames</h1>

In this problem, you’ll get practice working with pandas DataFrames, reading them into and out of memory, changing their contents and performing aggregation operations. For this problem, you’ll need to download the celebrated iris data set, available as a




<ol>

 <li>Download the iris data set from the link above. Please include this file in yoursubmission. Read csv into Python as a pandas DataFrame. Note that the CSV file includes column headers. How many data points are there in this data set? What are the data types of the columns? What are the column names? The column names correspond to flower species names, as well as four basic measurements one can make of a flower: the width and length of its petals and the width and length of its sepal (the part of the pant that supports and protects the flower itself). How many species of flower are included in the data?</li>

 <li>The data that I uploaded to my website, which you have downloaded, is based on thedata initially uploaded to the UC Irvine machine learning repository. It is now known that this data contains errors in two of its rows (see the documentation at <a href="https://archive.ics.uci.edu/ml/datasets/Iris">https: </a><a href="https://archive.ics.uci.edu/ml/datasets/Iris">//archive.ics.uci.edu/ml/datasets/Iris</a><a href="https://archive.ics.uci.edu/ml/datasets/Iris">)</a>. Using 1-indexing, these errors are in the 35th and 38th rows. The 35th row should read 9,3.1,1.5,0.2,”setosa”, where the fourth feature is incorrect as it appears in the file, and the 38th row should read 4.9,3.6,1.4,0.1,”setosa”, where the second and third features are incorrect as they appear in the file. Correct these entries of your DataFrame.</li>

 <li>The iris dataset is commonly used in machine learning as a proving ground forclustering and classification algorithms. Some researchers have found it useful to use two additional features, called <em>Petal ratio </em>and <em>Sepal ratio</em>, defined as the ratio of the petal length to petal width and the ratio of the sepal length to sepal width, respectively. Add two columns to you DataFrame corresponding to these two new features. Name these columns Ratio and Sepal.Ratio, respectively.</li>

 <li>Save your corrected and extended iris DataFrame to a csv file called csv. Please include this file in your submission.</li>

 <li>Use a pandas aggregate operation to determine the mean, median, minimum, maximum and standard deviation of the petal and sepal ratio for each of the three species in the data set. <strong>Note: </strong>you should be able to get all of these numbers in a single table (indeed, in a single line of code) using a well-chosen group-by or aggregate operation.</li>

</ol>

<h1>3         Plotting Dataframes: Major League Baseball</h1>

In this problem, you’ll get more practice working with pandas data frames and perform some basic plotting. We’ll work with a data set consisting of all the baseball games from the 2018 Major League Baseball (MLB) regular season, compiled by retrosheet. org. Don’t worry– you don’t need to know anything about baseball to complete this assignment! You can download the relevant CSV file either from the course web page at <a href="http://www-personal.umich.edu/~klevin/teaching/Winter2019/STATS507/mlb2018.zip">www-personal.umich.edu/</a><a href="http://www-personal.umich.edu/~klevin/teaching/Winter2019/STATS507/mlb2018.zip">~</a><a href="http://www-personal.umich.edu/~klevin/teaching/Winter2019/STATS507/mlb2018.zip">klevin/teaching/Winter2019/STATS507/mlb2018.zip</a> or directly from the original source at <a href="https://www.retrosheet.org/gamelogs/gl2018.zip">https://www.retrosheet.org/gamelogs/gl2018. </a><a href="https://www.retrosheet.org/gamelogs/gl2018.zip">zip</a><a href="https://www.retrosheet.org/gamelogs/gl2018.zip">.</a> <strong>Note: </strong>even though the zipped file is named as a .txt file, it is in fact a CSV file, which pandas will still be able to read.

<strong>Requisite legal boilerplate: </strong>The information used here was obtained free of charge from and is copyrighted by Retrosheet. Interested parties may contact Retrosheet at ”www.retrosheet.org”.

<ol>

 <li>Read the data into a table called mlb_df. Each row of the table represents the outcome of a single game from the 2018 MLB season. Take note that the file does not have columns names; see the header keyword to the read_csv function. The columns are explained in a .txt file which you can download from <a href="https://www.retrosheet.org/gamelogs/glfields.txt">https://www. </a><a href="https://www.retrosheet.org/gamelogs/glfields.txt">retrosheet.org/gamelogs/glfields.txt</a><a href="https://www.retrosheet.org/gamelogs/glfields.txt">,</a> but we will only make use of a few of them in this problem. The 10-th and 11-th columns (using 1-indexing) are the scores of the visiting and home teams, respectively. Rename these columns v_score and h_score, respectively. MLB comprises two leagues, the American League and the National League, encoded as AL and NL in the table. The 5-th and 8-th columns (also 1-indexed) are the league affiliations of the visiting and home team, respectively. Rename these columns v_league and h_league.</li>

 <li>Create a plot with two subplots, placed side-by-side. Each subplot should be a scatter plot in which the x- and y-axes correspond to the home and visitor scores, respectively, and in which each point corresponds to a game from the season. In the left-hand plot, include all games in which both teams were in the NL, and in the righthand plot, include all games in which both teams were in the AL. Games in which the teams were from different leagues should be ignored. Specify the transparency (cf. the alpha parameter in the matplotlib documentation) so that scores that occur more often will be shaded darker than rare scores. Color the points in the scatter plot according to the league affiliation of the two teams as follows: games between two teams both in the AL should be rendered as red points in the scatter plot. Games between two teams both in the NL should be rendered as blue points in the scatter plot. Label your axes and provide an appropriate title for your plot as well as its subplots. <strong>Note: </strong>you may find it useful to create an extra column in the data frame encoding whether a given game is AL vs AL, NL vs NL or mixed.</li>

 <li>The Skellam distribution (<a href="https://en.wikipedia.org/wiki/Skellam_distribution">https://en.wikipedia.org/wiki/Skellam_distribution</a><a href="https://en.wikipedia.org/wiki/Skellam_distribution">) </a>is the distribution that results from taking the difference between two Poisson random variables. It is often suggested as a model for the difference between scores in sports games, particularly baseball. Add a new column to the data frame called score_diff, given by the home score minus the away score. Make a histogram of this score difference and give the plot an appropriate title.</li>

 <li>Read the documentation about the scipy implementation of the Skellam distribution at <a href="https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.skellam.html">https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.ske</a></li>

</ol>

<a href="https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.skellam.html">html</a><a href="https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.skellam.html">.</a> If <em>λ<sub>H </sub></em>and <em>λ<sub>V </sub></em>are the means of two independent Poisson random variables <em>K<sub>H </sub></em>and <em>K<sub>V </sub></em>, respectively, then the Skellam distribution that describes the difference <em>K<sub>H</sub></em>−<em>K<sub>V </sub></em>has parameters <em>λ<sub>H </sub></em>and <em>λ<sub>V </sub></em>. We will assume (perhaps incorrectly) that the location parameter of the Skellam distribution is 0. To fit a Skellam distribution to the data, we will first fit Poisson distributions to the home and away teams.

Estimate parameters <em>λ</em><sup>ˆ</sup><em><sub>H </sub></em>and <em>λ</em><sup>ˆ</sup><em><sub>V </sub></em>as the means of the home and visitor scores, respectively. Use scipy to run a Kolmogorov-Smirnov test assessing whether or not the

Skellam distribution with parameters (<em>µ</em><sub>1</sub><em>,µ</em><sub>2</sub>) = (<em>λ</em><sup>ˆ</sup><em><sub>H</sub>,λ</em><sup>ˆ</sup><em><sub>V </sub></em>) and location parameter 0 is a good fit for the score differences. <strong>Hint: </strong>see the documentation at <a href="https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.kstest.html">https://docs. </a><a href="https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.kstest.html">scipy.org/doc/scipy/reference/generated/scipy.stats.kstest.html</a> to see how to perform such a test. Is the Skellam distribution a reasonable model to use? What might we do to build a more accurate model?