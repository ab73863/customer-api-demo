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
   
   *The resource for getting the customer record by first name for retrieval and update is defined in RAML as part of this API. The retrieve record can be cached for lowering the latency 
    with minimal cache expiration time . The resource will not be using any payload instead as per REST principle uri param with first name of the customer is used as the key.
	
	Also the since the API is meant for a mobile application the resource has to be secured with OAuth 2.0 implicit grant type . The current implementation submitted does not cover this security
	set up in proxy as this is ideally part of API manager policy*
	
3. Simple extension of the API to support future resources such as orders and products