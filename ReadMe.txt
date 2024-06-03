This project has 3 mini WebAPI services : API1, API2, API3 and a APIGateway.
Ocelot library has been used for APIGateway.
API1 also has Authentication and Authorization.
POSTMAN can be used for testing. 
While making get request to APIGateway for API1, select Authorization tab,
select Type : Bearer Token
In order to create a token, http://jwtbuilder.jamiekurtz.com/ web page can be used 
with filling:
	Issuer : www.myapi.com
	Audience : www.myapi.com
	clear subject textbox
	clear additional claims if there is no authorization
	add a claim => "Role" : "Admin" (only Admin is authorized in the application)
	key : Iam an alien Iam a legal alien Iam an Englishman in New York
        (this key is pulled from API_Gateway's and API1's appsettings.json files)
	create signed jwt and copy jwt to clipboard
paste the copied key to POSTMAN's token field

make get requests to the following endpoints via Postman:
https://localhost:7181/api1
https://localhost:7181/api2
https://localhost:7181/api3
