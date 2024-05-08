# F1-2021-Races
<br>
<h2>
Introduction of the Project </h2>

<h5>
Formula 1, also known as F1, is a motorsport that is currently the top competition and one of the most popular motorsports in the world of track racing (Wright, 2001).The focus of this individual project is to properly analyze the results of the 2021 Formula 1, analyze the data exploratively, summarize and report insights. </h5>

<br>
<h2>Section 1.1: Analysis of Racing Driver’s Winning Time in 2021</h2>
<br>
To begin with, by using beautiful soup packages (bs4) to scrape information from the html files, since the webpage includes a table that contains information that I want, so use `soup.find_all` to take out the table and then create a DataFrame for it. After the information has been processed and prepared, it is time to get in position to visualize the information. This DataFrame contains a lot of information such as ‘Grand Prix’, ‘Date’, ‘Winner’, ‘Car’ etc.   Since I only want to sketch a figure which can show the winning time for all the 22 races in the year, so it is necessary to only take information that are essential for data visualization. 

<br>
<br>
   <p align="center">
<img width="600" alt="image" src="https://github.com/XaiZhen/F1-2021-Races-/assets/157572976/66099f70-bf91-412e-8b71-91cb2e505e08">
 </p>
 

 <p align="center">
Figure 1: The winning F1 drivers and their winning times to complete the race in the 22 races
</p>

Figure 1 is the bar chat which display the winner and their time to complete the races for each of the 22 races between that period.  The variable on x-axis is a new variable create in the DataFrame, it is for the purpose that viewer can easily check the winner’s name and location where the races being hold.  The variable on y-axis is time the winner being taken to complete the race in minutes.  But the x-axis is not arranged in the same order in which the race was held.  This is because it is easier to make comparisons if we use the time spent in order from largest to smallest.  However, note that the bar on the rightmost side of the graph indicates that the competitor took fewer than 10 minutes to complete the race, which visually appears to be faster than the others, but this may be because this race required the fewest number of laps to be completed.  So, sometimes we have to read additional data depending on what the problem requires us to study in order to perform the appropriate analysis.
<br>
<br>
<h2>Section 1.2: Brief Descriptions on Three F1 races results - 2021 </h2>
