# isto_custom_jwt_filter
Custom Istio/Envoy Filter to send JWT for an external service for custom validation

This is an example filter to send all the calls that are received on *services-ingressgateway* to an external authentication service for validation, so that you can invalidate tokens and control the tokens that have access to the services.

We're sending the JWT token to the service in HTTP Header *x-authentication* , Service Host being hit on *x-service* and Verb being executed on *x-verb*. 

Validation service should check those headers against a database, for example.

We're using a custom *services-gateway* for the authentication. Example in *services-gateway.yaml* file.  
Filter applied is in *custom-filter.yaml* file.  
The JWT policy applied to the *services-gateway* is available on *jwt-policy.yaml* file.


