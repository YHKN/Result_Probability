# Result_Probability

This Notebook calculates the probability for every possible result, depending on the number of shots, based on the xG of every shot and creates a graphic for that match in the graphics folder.
xG-values are from Opta as found on fbref.com.

Run either **prob_chart(url)** if you only want the probability chart, or **viz_game(url)** if you want the whole graphic including additional info.
As url you need the url of the match from fbref.com, for example: "https://fbref.com/en/matches/7140acae/Argentina-France-December-18-2022-World-Cup", as a string.

Please be mindful of Sports Reference's policy regarding scraping, found here: "https://www.sports-reference.com/bot-traffic.html".
As of writing, there is a limit of 20 requests per minute.

## Calculation

To calculate the result probability matrix *P* I first create a matrix of size *n*x*n* with *n* being the maximum number of shots of the teams, full of zeros except a 1 in the top left corner. Now for every shot of the home team I create the matrix *P<sub>m</sub>* being *P* times *(1 - xG value of the shot)* and the matrix *P<sub>g</sub>* being *P* shifted one index to the right times *xG value of the shot*. The new probability matrix *P* is the sum of *P<sub>m</sub>* and *P<sub>g</sub>*. For shots of the away team, *P* gets shifted one index down instead of to the right. Summarizing:

*P = (P \* (1 - xG)) + (P<sub>shift</sub> \* xG)*

The value of *P<sub>i,j</sub>* represents the probability of score *j : i*
