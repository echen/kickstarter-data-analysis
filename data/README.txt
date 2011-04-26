# currently-funding.txt
* Scraped around 4/22/11.
* Data is from the "currently funding" page (e.g., http://www.kickstarter.com/discover/cities/los-angeles-ca/funding) of the top 10 cities.
* Tab-delimited columns are "name, link, author, description, location, pct_funded, amt_pledged, units_left, unit", where units_left = 5 and unit = hour means that 5 hours remain until the deadline.

# ending-soon.txt
* Scraped around 4/24/11.
* Data is from the "ending soon" page: http://www.kickstarter.com/discover/ending-soon.

# successful.txt
* Scraped around 4/22/11.
* Data is from the "successful" page (e.g., http://www.kickstarter.com/discover/categories/art/successful?ref=more) of all the categories.
* Tab-delimited columns are "name, link, author, description, location, pct_funded, amt_pledged, date_funded, category".

# pledge-amt-counts.txt
* Scraped a sample of successful project pages around 4/22/11.
    * The sample is currently missing projects from the music category, since the scraper borked while going through that category.
* Each line indicates a single backer at the pledge amount on the line.

# low-priced-rewards.txt
* From the same scrape as pledge_amt_counts.txt.
* The first column ("amt1") contains the cost of the lowest-priced reward. The second column ("num1") contains the number of backers of this reward. Similarly for the third and fourth columns.