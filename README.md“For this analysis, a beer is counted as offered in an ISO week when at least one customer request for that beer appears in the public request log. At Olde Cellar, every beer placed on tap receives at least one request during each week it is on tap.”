“For this analysis, a beer is counted as offered in an ISO week when at least one customer request for that beer appears in the public request log. 
At Olde Cellar, every beer placed on tap receives at least one request during each week it is on tap.”


Requests do not directly affect the current Popularity Score. The score is deliberately volume-based: it measures how much of each week’s total requested litres a beer captured, averaged over its weeks offered, with a mild adjustment for how many weeks it was offered.
So NA Seltzer can lead in total requests and total litres while having a lower score if its demand is spread across many weeks in which it represents a smaller portion of the weekly taplist volume. Market-share-style metrics measure a product’s portion of total sales in the relevant period, rather than its accumulated lifetime total.
What the current score uses
The code currently calculates:
〖"Weekly Volume Share" 〗_(b,w)=("Litres of beer " b" in week " w)/("Total litres requested for all beers in week " w)

Then:
〖"Average Weekly Share" 〗_b=(∑〖"Weekly Volume Share" 〗_(b,w))/〖"Weeks Offered" 〗_b 

And finally:
〖"Popularity Score" 〗_b=100×〖"Average Weekly Share" 〗_b×(〖"Weeks Offered" 〗_b/"Maximum Weeks Offered" )^0.5

The Requests column is displayed as useful context, but it is not an input to the formula.
Why NA Seltzer can rank lower
Imagine this simplified case:
Beer	Weeks offered	Total litres	Average weekly litres	Average weekly share	Score result
NA Seltzer	40	500 L	12.5 L	18%	About 17.55
Czech Mate	16	320 L	20.0 L	27%	Potentially higher
Limited IPA	8	220 L	27.5 L	35%	Potentially higher
NA Seltzer wins in cumulative contribution because it has been offered frequently and steadily. But a beer can beat it on this index if, when that beer is on the taplist, it captures a larger percentage of that week’s total requested litres.
That distinction is intentional:
	Total volume answers: “What product generated the most beverage volume over the full history?”
	Requests answers: “What product was ordered most often?”
	Popularity Score answers: “How strongly did this product pull customer volume compared with all other products during the weeks it was offered?”
A high total for NA Seltzer may indicate it is an indispensable dependable product. A lower popularity score means other beers may have greater per-week competitive pull when they appear on tap.
Why request count and litre share differ
Your request rows can represent different package sizes:
	1 growler = 1.95 L
	1 six-pack = 2.07 L
So request count mostly tracks how frequently people submit orders, while the score tracks requested liquid volume. A beer receiving many one-package requests may have fewer litres per request than another beer with fewer, larger orders.
However, because growler and six-pack volumes are very close in your data—1.95 L versus 2.07 L—request count and volume will usually move together. The much bigger reason NA Seltzer is at 17.55 is likely that it has a large number of weeks offered, and its total volume is accumulated across those weeks rather than concentrated into unusually dominant weekly shares.
The availability adjustment is not the culprit
If NA Seltzer has the most weeks offered, then this component is effectively 1.00:
(〖"Weeks Offered" 〗_"NA Seltzer" /"Maximum Weeks Offered" )^0.5=1

So the adjustment does not reduce NA Seltzer’s score at all if it is the longest-running item. Its 17.55 is almost certainly approximately its average weekly share, expressed as a percentage.
For a beer offered fewer weeks, the adjustment is below 1.00, reducing its score. For example, a beer offered 9 weeks when the maximum is 36:
(9/36)^0.5=0.50

A raw 30% average weekly share would become a 15.00 adjusted score. This is why a high score is meaningful: it requires a strong weekly share and enough repeated availability to support confidence.
What I recommend displaying
Do not remove Requests. It is valuable, but it measures a different thing. The clearest dashboard order is:
Field	Decision use
Popularity Score	Relative pull per week/taplist exposure, adjusted for evidence duration
Avg Weekly Share	The raw unadjusted competitive share
Avg Vol/Week	Expected weekly production/depletion demand
Total Volume	Cumulative commercial contribution
Requests	Order frequency / transaction count
Weeks Offered	Exposure and confidence context
In your case, NA Seltzer may be a core traffic / reliability product: a high-volume, high-frequency item that contributes substantial total litres, even if particular specialty beers take a larger share of the weekly mix during their runs.
If you want requests included
We can make request frequency an explicit second popularity measure rather than silently mixing it into the volume score:
〖"Request Share" 〗_(b,w)=("Requests for beer " b" in week " w)/("Requests for all beers in week " w)

〖"Request Pull Score" 〗_b=100×〖"Average Request Share" 〗_b×(〖"Weeks Offered" 〗_b/"Maximum Weeks Offered" )^0.5

Then the table can show both:
	Volume Popularity Score — best for brewing, packaging, cellar capacity, and litres moved.
	Request Pull Score — best for order frequency and how often people choose the product.
I would keep Volume Popularity Score as the primary operational score, because the growler/six-pack mix is already converted into litres and your production decisions are fundamentally volume-sensitive. Add Request Pull Score only if you want to distinguish “many smaller/frequent orders” from “fewer higher-volume orders.”
Interactive scorecard: build a tool to test how different weights (volume, frequency, recency) impact your product popularity scores
Computer
