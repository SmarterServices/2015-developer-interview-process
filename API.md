# SmarterMeasure REST API Documentation

## Introduction

### This is a mock REST API for SmarterMeasure.  All the data that is returned by this API is completely fake and the API does not interact with the core SmarterMeasure system in any way.

### Helpful Hints

* The sample data is re-generated with each service restart.  So you cannot expect the data to always be the same.  For example, if you are working with a specific user_id and the next day that user is not found, it is due to the services being restarted.
* Since this is purely a mock API there is no authentication.

## Base URL

The base url for connecting is:

```http://mock-api.smartermeasure.com/v4/```

## Resources

### /results

The results resource will return all the assessment results based on the criteria passed.

#### Example Requests

```
	// To get all the results
	curl -X GET http://mock-api.smartermeasure.com/v4/results

	// To get the second page of results
	curl -X GET http://mock-api.smartermeasure.com/v4/results?page=2

	// To limit the number of records to 10 and get the 5th page of results
	curl -X GET http://mock-api.smartermeasure.com/v4/results?page=5&page_size=10

```

#### Example Response

```
	{
	    "page": 1,
	    "num_pages": 20,
	    "page_size": 50,
	    "start": 1,
	    "end": 50,
	    "uri": "/results",
	    "first_page_uri": "/results?page=1",
	    "previous_page_uri": null,
	    "next_page_uri": "/results?page=2",
	    "last_page_uri": "/results?page=20",
	    "results": [
	        {
	            "user_id": 5684521,
	            "first_name": "Shane",
	            "last_name": "Horton",
	            "email_address": "Shane.Horton@smartermeasure.com",
	            "date_started": 1374482756,
	            "assessment_results": [
	                {
	                    "title": "Life Factors",
	                    "code": "life_factors",
	                    "is_complete": true,
	                    "attempt_number": 4,
	                    "percentage": 83,
	                    "readiness": "pass",
	                    "date_completed": 1374483046
	                },
	                {
	                    "title": "Learning Styles",
	                    "code": "learning_styles",
	                    "is_complete": false,
	                    "attempt_number": null,
	                    "percentage": null,
	                    "readiness": null,
	                    "date_completed": null
	                },
	                {
	                    "title": "Individual Attributes",
	                    "code": "individual_attributes",
	                    "is_complete": true,
	                    "attempt_number": 2,
	                    "percentage": 55,
	                    "readiness": "fail",
	                    "date_completed": 1374483456
	                },
	                {
	                    "title": "Technical Competency",
	                    "code": "technical_comp",
	                    "is_complete": false,
	                    "attempt_number": null,
	                    "percentage": null,
	                    "readiness": null,
	                    "date_completed": null
	                },
	                {
	                    "title": "Technical Knowledge",
	                    "code": "technical_knowledge",
	                    "is_complete": true,
	                    "attempt_number": 2,
	                    "percentage": 55,
	                    "readiness": "fail",
	                    "date_completed": 1374483956
	                },
	                {
	                    "title": "Reading Rate & Recall",
	                    "code": "reading",
	                    "is_complete": true,
	                    "attempt_number": 2,
	                    "percentage": 60,
	                    "readiness": "fail",
	                    "date_completed": 1374484156
	                }
	            ],
	            "uri": "/v4/api/user/5684521"
	        },
	        {....}
	    ]
	}

```

### /users/{user_id}

Get the user details and assessment results for a single user.


#### Example Requests

```
	// To get all the results
	curl -X GET http://mock-api.smartermeasure.com/v4/users/5684521
```

#### Example Response

```
	{
	    "user_id": 5684521,
	    "first_name": "Shane",
	    "last_name": "Horton",
	    "email_address": "Shane.Horton@smartermeasure.com",
	    "date_started": 1374482756,
	    "assessment_results": [
	        {
	            "title": "Life Factors",
	            "code": "life_factors",
	            "is_complete": true,
	            "attempt_number": 4,
	            "percentage": 83,
	            "readiness": "pass",
	            "date_completed": 1374483046
	        },
	        {
	            "title": "Learning Styles",
	            "code": "learning_styles",
	            "is_complete": false,
	            "attempt_number": null,
	            "percentage": null,
	            "readiness": null,
	            "date_completed": null
	        },
	        {
	            "title": "Individual Attributes",
	            "code": "individual_attributes",
	            "is_complete": true,
	            "attempt_number": 2,
	            "percentage": 55,
	            "readiness": "fail",
	            "date_completed": 1374483456
	        },
	        {
	            "title": "Technical Competency",
	            "code": "technical_comp",
	            "is_complete": false,
	            "attempt_number": null,
	            "percentage": null,
	            "readiness": null,
	            "date_completed": null
	        },
	        {
	            "title": "Technical Knowledge",
	            "code": "technical_knowledge",
	            "is_complete": true,
	            "attempt_number": 2,
	            "percentage": 55,
	            "readiness": "fail",
	            "date_completed": 1374483956
	        },
	        {
	            "title": "Reading Rate & Recall",
	            "code": "reading",
	            "is_complete": true,
	            "attempt_number": 2,
	            "percentage": 60,
	            "readiness": "fail",
	            "date_completed": 1374484156
	        }
	    ],
	    "uri": "/v4/api/user/5684521"
	}
```

## Pagination

The API provides some parameters that cna be used for quick and easy pagination of the results.

### Query Parameters

* ```page``` provides a method to jump direction to a specific page
* ```page_size``` provides a method to change the number of results that are returned on each page.

### Collection Results

The results of each collection will include some contextual information to aid in paging.  For example, the code below shows that the results are for page 1 of 20 pages with 50 records on each page.  In addition, the paging uri's are also provided for convienence.

```
	{
	    "page": 1,
	    "num_pages": 20,
	    "page_size": 50,
	    "start": 1,
	    "end": 50,
	    "uri": "/results",
	    "first_page_uri": "/results?page=1",
	    "previous_page_uri": null,
	    "next_page_uri": "/results?page=2",
	    "last_page_uri": "/results?page=20",
		....
		
	}    
```



