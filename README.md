# AudioBooks App

Data is from an audio book app. Logically it relates to the audio version of books only.
Each customer in the database has made a purchase at least once. That's the condition to be included.

We want to create a machine learning algorithm based on our data that can predict if a customer will buy again from the audio book company.
The main idea is that the company shouldn't spend its advertising budget targeting individuals who are unlikely to come back.
If we can focus our efforts on customers likely to convert again, We can obtain improved sales and profitability figures.

So our model will take several metrics and we'll try to predict human behavior.
Having the data and the technology to identify prospective customers, creates a lot of value and growth opportunities.

## Data:
Each row represents a person.
Column names :
	- ID
	- Book Length (mins) - overall: the overall book length is the sum of the length of all purchases.
	- Book Length (mins) - average: average book length the average book length is basically the sum divided by the number of purchases.
	- Price overall
	- Price average
	- Review: Review is a boolean. It shows if the customer left a review.
	- Review 10/10
	- Minutes Listened
	- Completion: the total minutes listened divided by the total length of books a person has purchased assuming people don't relisten to books.
	- Support requests: it shows the total number of support requests the person has opened. Support is anything from forgotten password to assistance on using the platform once more.
	- Last visited minus purchase date
	- Targets

The # puchases = the overall length / the average length
Review is a metric that shows engagement with the platform. Our assumption is that people who leave reviews are more likely to convert again. 
Most people leave no review. As in most marketplaces(we can substitute all missing values with the average review which is 8.91=status quo).

We're gonna do supervised learning so we need targets. The targets will be a boolean: one if a person converted and zero if he or she didn't. 
But what does it mean to convert?An extra six months of data have been taken after the two year period to check if a user converted. so we took two years and six months of data the first two years are contained in the data set we have here.
The next six months will show us if a person converted. In other words if he or she bought another book and if that happened we can count them as a conversion and the target will be 1. Otherwise it is zero.
If one buys no new audio book in that period chances are they've gone to a competitor or didn't like the audio book way of digesting information.

## Action plan:
	- Step 1: Since we are working with real life data, We must preprocess it
			Step 1.1: Balabce the dataset
			Step 1.2: Divide the dataset in training, validation and test
			Step 1.3: Save the data in a tensor friendly format
	- Step 2: Create the machine learning algorithm
