# Customer API Demo
- - - -

The project demonstrates a customer experience API with the resources which allows the following.

HTTP Method   | Resource Function
------------- | -------------
GET           | List All customer records
GET           | Get record by first Name
POST          | Create a new customer
PUT			  |	Update a customer
DELETE		  | Deletes a customer

## Use cases and commentary
- - - -

1. A consumer may periodically (every 5 minutes) consume the API to enable it (the consumer) to maintain a copy of the provider API's customers (the API represents the system of record)
   
   *As part of this use case the API has to carry only last updated records from the provider to client . Loading of full records all the time for
    every 5 minutes will kill the memory and data over the network will be high. 
	To avoid this we need to get the last updated range of records from a given time to current time . This is provided as a query parameter for the get all customer records call.*
	
2. A mobile application used by customer service representatives that uses the API to retrieve and update the customers details

3. Simple extension of the API to support future resources such as orders and products 