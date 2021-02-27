# Errors

<aside class="notice">
This defines all the error codes you might encounter in the code
</aside>

The Credgenics API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Authentication failed. API credentials are incorrect.
403 | Forbidden -- You do not have permission to perform this action.
404 | Not Found
405 | Method Not Allowed -- You tried to access an endpoint with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
