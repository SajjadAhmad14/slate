# Errors

<aside class="warning">
API endpoints return a status code in response of a request. Please go through the list below if your request returns an error code.
</aside>

The Clarity API uses the following error codes:

| Error Code | Meaning                                                                |
| ---------- | ---------------------------------------------------------------------- | --- |
| 400        | Bad Request -- Your request is invalid.                                |
| 400        | Donor error messages.                                                  |     |
| 400        | Beneficiary error messages.                                            |     |
| 400        | Post error messages.                                                   |     |
| 401        | Unauthorized -- Your API key is wrong.                                 |
| 404        | Not Found -- Custom field not found.                                   |
| 422        | Method Not Allowed -- Default field can not be deleted.                |
| 422        | Method Not Allowed -- Please make sure the user exists to send invite. |
| 422        | Method Not Allowed -- User has no email to send the invite to.         |
