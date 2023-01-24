# GraphQL

# Generate Query Request Payload using Postman

Step-1: Send the request payload by clicking the Send button on the top-right corner, as per the below screenshot, so that we can generate the response.

Query:
query Query 
{ 
country(code: "IN") 
{
name
native 
capital
currency
languages 
{
code
name
}
}
}

<img width="907" alt="image" src="https://user-images.githubusercontent.com/123489168/214366987-4e88a2fb-a3c2-4e56-a6e8-6977f3dd9fd1.png">

Step-2: View code by clicking the </> symbol on the right side, as per the below screenshot.

<img width="912" alt="image" src="https://user-images.githubusercontent.com/123489168/214367314-a6b5c1a7-166a-4b3c-9afa-2304ecf71ffb.png">

Step-3: Select HTTP from the dropdown-list, and copy the contents of Line#6, as per the below screenshot.

<img width="915" alt="Screenshot 2023-01-24 at 11 10 08 PM" src="https://user-images.githubusercontent.com/123489168/214367558-698da4ed-11a9-4922-b2aa-cbfd0ebf0554.png">

# Call GraphQL API using Boomi

Overall Boomi process is as below.

<img width="1377" alt="image" src="https://user-images.githubusercontent.com/123489168/214367826-a501d8f5-0a7f-4963-96b9-f2599ceeb214.png">

Step-1: Paste the contents copied in Step-3: of Generate Query Request Payload using Postman in the Message shape. The "variables" element can be removed as we are not using it.

<img width="570" alt="image" src="https://user-images.githubusercontent.com/123489168/214367960-7adb72c7-6af7-4769-a89f-bae629620848.png">


Step-2: Configure the URL in HTTP Client connection with Send operation

<img width="691" alt="image" src="https://user-images.githubusercontent.com/123489168/214368168-c1a631a4-f5e0-4a29-8bf6-e77426bb8b58.png">

Step-3: Configure the HTTP Client operation, as per the below screesnhot with JSON profile attached. 
Note: Request and response code will be same

<img width="797" alt="image" src="https://user-images.githubusercontent.com/123489168/214368297-9699d53c-3ff9-4565-9b6a-2468f659f1d6.png">

Step-4: Use Decision shape to segregate success and error response.

<img width="516" alt="image" src="https://user-images.githubusercontent.com/123489168/214368482-e9c20872-3615-4ae5-b387-eba17b71ca9b.png">

Step-4: Configure the Map shape with JSON profile attached. 
Note: Request and response code will be same

<img width="1380" alt="image" src="https://user-images.githubusercontent.com/123489168/214369306-677716b1-5ae2-4fde-93b7-bc5c8e723884.png">

Step-5: Configure the Notify shape, as per the below screenshot, or, have the error handling mechanism as per the project requirement.

<img width="490" alt="image" src="https://user-images.githubusercontent.com/123489168/214369698-e8665fdd-c3aa-4fdd-a2a5-b2e1332f3cfd.png">

# Process Execution Details

Below are the screenshots of successful process execution and response from GraphQL API.

<img width="1440" alt="image" src="https://user-images.githubusercontent.com/123489168/214370152-7f9475e3-8e9a-40e0-b1ee-c148a9a5d2ff.png">

# Sample API and Document Details

URL: https://countries.trevorblades.com/graphql

HTTP Method: POST

Query:
'{"query":"query Query {\r\n country(code: "IN") {\r\n name\r\n native\r\n capital\r\n currency\r\n languages {\r\n code\r\n name\r\n }\r\n }\r\n}"}'

Response:
{ "data": { "country": { "name": "India", "native": "भारत", "capital": "New Delhi", "currency": "INR", "languages": [ { "code": "hi", "name": "Hindi" }, { "code": "en", "name": "English" } ] } } }


