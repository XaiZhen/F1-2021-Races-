# F1-2021-Races
<br>
<h2>
Introduction of the Project </h2>

<h5>
Formula 1, also known as F1, is a motorsport that is currently the top competition and one of the most popular motorsports in the world of track racing (Wright, 2001).The focus of this individual project is to properly analyze the results of the 2021 Formula 1, analyze the data exploratively, summarize and report insights. </h5>

<br>
<h2>Section 1: Analysis of Racing Driver’s Winning Time in 2021</h2>
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

<h2>Section 2: Brief Descriptions on Three F1 races results - 2021 </h2>

As done in section 1, in this section, we still need to use the Beautiful Soup package (bs4) to extract information from the web page again, but this time we need to find the hyperlink URLs by examining the 'a' elements. Then, use a 'for' loop to load those hyperlink URLs that we want. Here are three examples of URLs I found; the table below contains some basic information for each webpage.

URLs | Location | Winner| Car | points
-|-|-|-|-
https://www.formula1.com/en/results.html/2021/races/1065/italy/race-result.html | Italy|Max Verstappen | Red Bull Honda | 25
https://www.formula1.com/en/results.html/2021/races/1070/france/race-result.html| France |Max Verstappen | Red Bull Honda | 25
https://www.formula1.com/en/results.html/2021/races/1104/brazil/race-result.html|Brazil | Lewis Hamilton | Mercedes | 25

<h2>Section 3: Average Speed for each of the drivers in 21 races – 2021 </h2>

In fact, there were 22 tournaments on the schedule, but due to the cancellation of one race due to weather conditions, only 21 games were held as normal.  The plot in Figure 2 illustrates the average speed for each of the drivers in 21 races.
In this subtask, we require several key codes in python to prepare some information for the visualization that follows.  Firstly, replace ‘race-result.html’ with ‘fastest-laps.html’.  The method I used is to create a DataFrame for all the hyperlinks that regarding information with race results, and then replace those string (URLs) inside the DataFrame.  In this case I will get a new DataFrame which contains all the URLs that regarding information with fastest laps.

Secondly, delete the one race which is not being held by using `df.drop(df. index[ ])` and then using `df. reset_index (Drop = True, inplace = True)` to rearrange the index of the DataFrame(Fatest-laps).  Thirdly, create a new DataFrame that contains all the information of the 21 races, drop columns with unnecessary variables.  Lastly, use `seaborn` packages to sketch a bar plot.

 <p align="center">
<img width="600" alt="image" src="https://github.com/XaiZhen/F1-2021-Races-/assets/157572976/d23f88dc-2a4c-4a05-abee-294c4b3e57b4">
 </p>

  <p align="center">
Figure 2: The Average Speed for Each of the Drivers in 21 races
</p>

<h2>Section 4: Visualization for Cumulative points of all the drivers against the races </h2>

In this section, I designed a line plot that can indicate the cumulative points of all drivers in the 2021 race season.  Before plotting the figure, it is necessary to do some essential processing of the csv files, for example, it is important to create a new DataFrame which can display the cumulative points of each F1 driver, so here it is necessary to use the code of pandas.DataFrame.cumsum.  After getting a new Table containing cumulative points, next step is to convert the table of this DataFrame into a table which is suitable for plotting, for example, I create a DataFrame table which has drivers' names as columns and the rows represent the location of the tournament (in chronological order) and the number of points earned by the players.
With the information ready, I directly used the `sns. lineplot` from the seaborn package to draw the figure, as shown in Figure 3 below.  In the process of plotting, I used some code to make the figure more beautiful than the normal one.  For example, I used `sns. set ( palette = 'RdBu' )` to set the color, the reason I didn't use `sns. set(style = )` is because the original default darkgrid style is what I needed.  In addition to this, I added a label to the y-axis by `plt. ylabel`, added a title to the image by `plt.  title`, and most importantly, added a box showing different color lines for different driver names using `plt.legend`.

From Figure 3, it can be clearly observed that Max Verstappen was the top point earner for the entire season, with Lewis Hamilton in second place。


<p align="center">
<img width="800" alt="image" src="https://github.com/XaiZhen/F1-2021-Races-/assets/157572976/d9648ead-29c7-4f0c-ae53-eac67a0d6a28">
 </p>

   <p align="center">
Figure 3: Cumulative Points of All the Drivers Against the Races from 28 March 2021 and 12 December 2021
</p>

<h2> Analysis, Insights and Conclusion</h2>

From the analysis of the F1 data in the first four subtasks, it is evident that when seeking to analyze different research questions, it is imperative that we acquire the information that will allow us to answer the research questions.   As discussed in Section 1, under different circumstances, we have to read additional data depending on what the problem requires us to study in order to perform the appropriate analysis.   Furthermore, when visualizing data, organizing and cleaning the source data are crucial steps before plotting.   Occasionally, in situations where it is particularly challenging to compare data in close proximity (e.g., Figure 2), it is desirable to use code to add label to each of the bar to reveal specific data in order to make the graph more informative and aesthetically pleasing.

To conclude the analysis from Formula 1 races in season 2021, from the above analysis, it can be seen that Max Verstappen and Lewis Hamilton have superior strength in F1, and the two of them are competing neck and neck in every race.
