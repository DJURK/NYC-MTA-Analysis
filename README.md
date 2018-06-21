# NYC-MTA-Analysis
Crepe Cart (hypothetical) serves on-the-go breakfast, lunch, and dinner every weekday in NYC. Your company has established their food trucks in certain locations, but have experienced a drop in sales after their initial business opening.  We at Kitchen Inc. have used our analytical expertise to provide a solution to this problem.

Our analysis uses MTA turnstile data to identify areas with the most potential customers for each meal period.  Then, using a combination of customer traffic and distance, we recommend the best routes to maximize the sales of your delicious crepes during each breakfast, lunch, and dinner rush. 

This project was essentially a giant exercise using pandas.

## Strategy
1. Read in several months of MTA turnstile data from http://www.mta.info/
2. Find net hourly traffic at each stop on weekdays (entries + exits)
3. Find stations with most net traffic around breakfast/lunch/dinner times
  a. For breakfast and dinner, I used net traffic numbers.  In addition to net traffic at lunch time, however, I also included # of EXITS at BREAKFAST.  The logic behind this is that people who exit at a station around breakfast time are probably working around there, and will be in the area at lunchtime.
4. Create metrics to estimate sales 
  a. CONVERSION RATE - Assume 0.2% (1 in 500) people who pass by the food truck will buy a crepe. 
  b. TRAVEL DOWNTIME - Assume 10 minute per mile travel time
  c. Sales = Traffic * Conversion Rate * (1 - % time spent travelling)

## Top 4 routes:
Breakfast > Lunch > Dinner

1. Grand Central > Grand Central > Grand Central
2. 34th-Penn > 34th-Herald Sq > 34th-Herald Sq
3. 34th-Penn > 34th-Penn > 34th-Penn
4. 23rd St > 14th-Union Sq > 14th-Union Sq

## Next Steps
1. Are there seasonal trends in traffic?
2. Look at other traffic data as well (rideshare, bike traffic, bus traffic)
3. Look at density of other restaurants in each area to gauge competition
