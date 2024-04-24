# Coffee Break: How to standout in the competitive US Coffee Industry
## Click here to view Coffee break report
Power BI dashboard link: https://app.powerbi.com/view?r=eyJrIjoiNDQ4YTdkOTYtMDYxMS00YmY5LThhMzItZjc0MDljY2JmNGE3IiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9
## Challenge Objective:
 From analyzing survey responses from 4,000 Americans after a blind coffee taste test conducted by YouTube coffee expert James Hoffmann and Cometeer "The Great American Coffee Taste Test", Providing an explanatory report with data-driven strategy for opening their first coffee shop for the investors.

### Requirements from the investors:
1. Target audience: What type of customer should we target, and what are their preferences?
2. Product offering: What types of coffee beans and drinks should we offer?
3. Pricing strategy: How can we align prices with customer value perception?

### Challenges in the Survey data:
1. Many of the survey responses were incomplete / blank.
2. It had many inconsistent data naming in columns like favorite coffee drink and the things you would like to add in coffee.
3.There are some outliers in the price columns.

### Tools used:
Data cleaning & preprocessing - Python
Data visualization - Power Bi

### Steps followed:
- Data is imported in Power BI
- Trimmed, Cleanned, replaced & removed Duplicates from the dataset.
- Created new table for min, max & avg price.

![Screenshot (46)](https://github.com/karthikhariharan7/CoffeeBreak/assets/167401723/0d7e5bd3-b366-4784-897b-cd37530c3838)


![Screenshot (47)](https://github.com/karthikhariharan7/CoffeeBreak/assets/167401723/60fe9094-884d-4db9-a524-9b88fbdbcddf)


- Perfomed Data modelling.
- created Measures to perform calculations some are -

            Favorite Coffee Drink-Top1 = FIRSTNONBLANK(TOPN(1,VALUES(New_coffee_file[Favorite Coffee Drink]),CALCULATE(COUNT(New_coffee_file[survey number])),DESC),1)
            Coffee_At_Home = COUNTROWS(FILTER(New_coffee_file,New_coffee_file[Where do you typically drink coffee? (At home)]=True))
            Coffee_At_Cafe = COUNTROWS(FILTER(New_coffee_file,New_coffee_file[Where do you typically drink coffee? (At a cafe)]=True))/[No_Of_Participants]
            %OfPeopleKnowsTheirCoffeeBean = CALCULATE(COUNT(New_coffee_file[Do you know where your coffee comes from?]),FILTER(New_coffee_file,New_coffee_file[Do you know where your coffee comes from?]="Yes"))/count(New_coffee_file[survey number])
            AgeSort = SWITCH(New_coffee_file[Age Category],"<18 years old",1,"18-24 years old",2,"25-34 years old",3,"35-44 years old",4,"45-54 years old",5,"55-64 years old",6,">65 years old",7)

### Key achievements:
1. Developed a Power BI report which provides insights from "The Great American Coffee Taste Test".
2. The reports shows the Target customers, Age category and their coffee preferences.
3. It provides recommendations for prize ranges for the top 20 preferred coffees.

### Insights & Recommendations
- White/Caucasians & Employed full-time Males between Age Category 25 to 34 years old are the target customer Categories who drinks minimum 1 to 2 coffee per day and their preferred caffeine level is Full caffeine and strong level is somewhat strong.
- The people's pick for the best roast level is Light roast & Naturaly processed bean.
- Most of the people can spend $20-$40 dollars a month for coffee with a minimum of $8-$10 for a cup of coffee.
- Our recommendation for a cup of coffee prize starts from minimum $6 to maximun $18 dollars per cup of coffee which is well within the range of customers willingness to pay for a cup of coffee.




### Report contains:
1. Cards provides the total survey participants and the percentage of people likes to drink coffee at coffee shop.
2. Donut carts shows us the percentage of participants by gender, preferred caffeine level and preferred light roast process.
3. Pie chart shows us percentage of participants by Age category, Ethnicity/Race, Employment status, How strong you like your coffee, preferred coffee bean process, preferred roast level.
4. Bar charts shows us how many cups of coffee they drink per day by Age category and Employment status, Top 10 people's favorite coffee drinks, combinations usually added in coffee, Amount of money spent on coffee per month and People's preferred prize range for a cup of coffee.
5. A table which shows recommended minimum, maximum and average price range for top 20 coffees in survey.
6. A text box provides a short summary at the end of each page.
