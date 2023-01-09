# Result_Probability

This Notebook calculates the possibility for every possible result, depending on the number of shots, based on the xG of every shot and creates a graphic for that match in the graphics folder.
xG-values are from Opta as found on fbref.com.

Run either **prob_chart(url)** if you only want the probability chart, or **viz_game(url)** if you want the whole graphic including additional info.
As url you need the url of the match from fbref.com, for example: "https://fbref.com/en/matches/7140acae/Argentina-France-December-18-2022-World-Cup", as a string.

Please be mindful of Sports Reference's policy regarding scraping, found here: "https://www.sports-reference.com/bot-traffic.html".
As of writing there is a limit of 20 requests per minute.
