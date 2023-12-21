Project Site located here: https://sites.google.com/view/cs-333-algo-sports-betting/
(Graphs and analysis can be found there, below is an excerpt of some of the details of the algorithm in this repo)



Data Source
The prop_odds API (https://prop-odds.com/) was used to gather NBA games data and the moneyline betting odds across different sportsbooks. It has NBA data available since March 19, 2023 and bettings odds from Pinnacle, FanDuel, DraftKings, Caesars, BetMGM, Barstool, and BetRivers. The free tier allows 1,500 requests/month, which was enough for our use case. 

The balldontlie API (https://www.balldontlie.io/) was used to get the results of each NBA game.


Historical Games
We use the historical games to calculate the weights for each approach, as well as to backtest our algorithm on prior games and evaluate the profitability.

Define functions for probability, vig, statistical edge, expected value, consensus probability, and bet size calculations

Retrieve all available completed NBA games, moneyline odds on each sportsbook, and winner

Calculations

Assign weights to each sportsbook based on even weighting, loss weighting, and vig weighting strategies

Assign implied and consensus probabilities for home/away team

Use the probabilities to calculate bet sizes

Sum expected and actual payouts for each weighting method


Today's Games
The main feature and selling point of our technical demo is its ability to examine the betting market for potential profitable opportunities and then suggest which bets to make.

Choose sportsbook weighting method

Get today's NBA games

Fill in odds

Calculate consensus probabilities

Calculate bet sizing for each game

Calculate expected values for each bet

Print out suggested bets

Output example:
Suggested bets:

$38.59 on Portland Trail Blazers at fanduel (520)

$41.39 on Cleveland Cavaliers at draftkings (-395)

$128.54 on Cleveland Cavaliers at betmgm (-350)

$14.47 on Portland Trail Blazers at barstool (450)

$60.76 on Cleveland Cavaliers at betrivers (-385)

$0.43 on Charlotte Hornets at pinnacle (209)

$36.95 on Indiana Pacers at draftkings (-120)

$15.06 on Indiana Pacers at betmgm (-125)

$5.25 on Miami Heat at betrivers (130)

$8.41 on Atlanta Hawks at betmgm (-120)

$21.04 on Milwaukee Bucks at draftkings (-298)

$28.42 on Milwaukee Bucks at betrivers (-295)

$13.79 on Utah Jazz at fanduel (280)

$2.17 on Utah Jazz at pinnacle (268)

$152.70 on Minnesota Timberwolves at betrivers (-210)

Total expected payout: $596.26

Total amount bet: $567.98

Results
Using our best method, we turned a cumulative bet total of $3515 into $4343 over a betting period from 03/30/2023-11/14/2023. This is a 24% profit, which is quite impressive and exhibits the potential of our strategy when applied to the betting market.

Even weights for each sportsbook

Total expected payout: $3810.45

Total actual payout: $3462.43

Total amount bet: $3414.00

Weighted by historical loss

Total expected payout: $3815.04

Total actual payout: $3392.03

Total amount bet: $3412.03

Weighted by historical vig

Total expected payout: $3892.91

Total actual payout: $4343.63

Total amount bet: $3515.57

Weighting by historical vig provided the best results, followed by even weights, and finally historical loss. This is somewhat expected as vig is a well-established proxy for how accurate a sportsbook is, while we created the loss function that we used based on our own intuition. The even weights and historical loss weights were actually quite similar, leading to similar bets and outcomes. 
