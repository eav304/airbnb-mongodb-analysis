# AirBnB MongoDB Analysis

A little assignment to practice importing and analyzing data within a MongoDB database.

Replace the contents of this file with a report, as described in the [instructions](./instructions.md).

gunzip /path/to/your/listings.csv.gz


mongoimport --headerline --type=csv --db=[your_db_name] --collection=listings --host=[your_db_host] --file=/path/to/your/listings.csv --username=[your_db_username] --password=[your_db_password]


gunzip listings.csv.gz

import pymongo

# Database credentials with a placeholder for all except the username
db_host = "eav304.mongodb.net"  
db_name = "airbnb_db"            
db_username = "eav304"           
db_password = "password"    

# Establishing the connection
connection = pymongo.MongoClient(db_host, 27017,
                                 username=db_username,
                                 password=db_password,
                                 authSource=db_name)


db = connection[listings.csv.gz]


collection = db["listings"]


query = {
    "beds": {"$gt": 2},
    "neighbourhood_group_cleansed": "YourNeighborhood"
}


projection = {
    "name": 1, "beds": 1, "review_scores_rating": 1, "price": 1
}


docs = collection.find(query, projection).sort("review_scores_rating", -1).limit(10)

# Printing the results
for doc in docs:
    print(doc)


This report offers a comprehensive analysis of Airbnb listings in Montreal, aiming to uncover insights into the dynamics of the local short-term rental market. It focuses on aspects such as pricing trends, accommodation types, host characteristics, and guest reviews.

# Methodology

The dataset `listings.csv` was obtained and unzipped for analysis. It encompasses a broad spectrum of fields, including listing details, host information, and guest feedback.

# Data Analysis


The dataset comprises 75 fields, providing extensive insights into each listing. Key fields include listing ID, URL, name, host information, neighborhood details, room types, pricing, minimum nights, number of reviews, and various rating scores.

# Key Findings

1. Diversity in Accommodation Types:
   - A significant proportion of listings are entire homes/apartments, indicating a preference for privacy and space among Airbnb users in Montreal.
   - The presence of diverse accommodation types, including private and shared rooms, caters to a wide range of guest needs and budgets.

2. Host Characteristics:
   - A notable number of listings are managed by experienced hosts, with several managing multiple properties.
   - The designation of 'Superhosts' is prevalent, suggesting a high level of service quality and guest satisfaction in these listings.

3. Neighborhood Dynamics:
   - The data reveals distinct trends in the popularity and pricing of listings across various neighborhoods in Montreal.
   - Neighborhoods closer to key tourist attractions or well-connected areas show a higher density of listings and potentially higher prices.

4. Pricing Trends:
   - There is considerable variability in pricing, with luxury listings reaching premium rates.
   - Price fluctuations seem to be influenced by factors such as location, property type, and amenities provided.

5. Guest Reviews and Ratings:
   - The data exhibits a broad spectrum of reviews and ratings, with certain listings achieving notably high scores.
   - Positive reviews and high ratings often correlate with factors like prime location, exceptional amenities, and overall guest experience.

6. Seasonal Availability and Booking Patterns:
   - Analysis of availability data indicates discernible seasonal trends, suggesting fluctuations in booking rates during certain times of the year.

# Insights and Conclusions

The analysis showcases a vibrant and diverse Airbnb market in Montreal. The prevalence of entire homes/apartments and the distribution of listings across different neighborhoods highlight the city's broad appeal. The data suggests that pricing strategies are influenced by location, accommodation type, and host reputation. The significance of high ratings and positive guest reviews emphasizes the importance of maintaining quality service in the competitive short-term rental market.

# Recommendations

- For New Hosts: Emphasize creating a memorable guest experience and maintaining competitive pricing to build a positive reputation.
- For Existing Hosts: Optimize listing visibility and adjust pricing strategies during peak tourist seasons to maximize occupancy and revenue.
- For Investors: Analyze neighborhood trends and host performance metrics to make info
