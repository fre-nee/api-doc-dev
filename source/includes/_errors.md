# Errors
The following is a list of all the error codes that can be returned by the Parse API. You may also refer to RFC2616 for a list of http error codes. Make sure to check the error message for more details.

## API Issues

Following are the API related error codes.

Error Code | Meaning | Description
---------- | ------- | -----------
101 | UserInvalidLoginParams | Invalid login parameters. Check error message for more details.
101 | ObjectNotFound | The specified object or session doesn’t exist or could not be found. Can also indicate that you do not have the necessary permissions to read or write this object. Check error message for more details.
102 | InvalidQuery | There is a problem with the parameters used to construct this query. This could be an invalid field name or an invalid field type for a specific constraint. Check error message for more details..
103 | InvalidClassName | Missing or invalid classname. Classnames are case-sensitive. They must start with a letter, and a-zA-Z0-9_ are the only valid characters.
104 | MissingObjectId | An unspecified object id.
105 | InvalidFieldName | An invalid field name. Keys are case-sensitive. They must start with a letter, and a-zA-Z0-9_ are the only valid characters. Some field names may be reserved. Check error message for more details.
106 | InvalidPointer | A malformed pointer was used. You would typically only see this if you have modified a client SDK.
107 | InvalidJSON | Badly formed JSON was received upstream. This either indicates you have done something unusual with modifying how things encode to JSON, or the network is failing badly. Can also indicate an invalid utf-8 string or use of multiple form encoded values. Check error message for more details.
108 | CommandUnavailable | The feature you tried to access is only available internally for testing purposes.
116 | ObjectTooLarge | The object is too large.
116	| ExceededConfigParamsError | You have reached the limit of 100 config parameters.
117 | InvalidLimitError | An invalid value was set for the limit. Check error message for more details.
118 | InvalidSkipError | An invalid value was set for skip. Check error message for more details.
119 | OperationForbidden | The operation isn’t allowed for clients due to class-level permissions. Check error message for more details.
120 | CacheMiss | The result was not found in the cache.
121 | InvalidNestedKey	| An invalid key was used in a nested JSONObject. Check error message for more details.
123 | InvalidACL | An invalid ACL was provided.
125 | InvalidEmailAddress | The email address was invalid.
137 | DuplicateValue | Unique field was given a value that is already taken.
139 | InvalidRoleName | Role’s name is invalid.
139 | ReservedValue	| Field value is reserved.
140 | ExceededCollectionQuota | You have reached the quota on the number of classes in your app. Please delete some classes if you need to add a new class.
141 | ScriptFailed | Cloud Code script failed. Usually points to a JavaScript error. Check error message for more details.
141 | FunctionNotFound | Cloud function not found. Check that the specified Cloud function is present in your Cloud Code script and has been deployed.
141 | JobNotFound | Background job not found. Check that the specified job is present in your Cloud Code script and has been deployed.
141 | SuccessErrorNotCalled | success/error was not called. A cloud function will return once response.success() or response.error() is called. A background job will similarly finish execution once status.success() or status.error() is called. If a function or job never reaches either of the success/error methods, this error will be returned. This may happen when a function does not handle an error response correctly, preventing code execution from reaching the success() method call.
141 | MultupleSuccessErrorCalls | Can’t call success/error multiple times. A cloud function will return once response.success() or response.error() is called. A background job will similarly finish execution once status.success() or status.error() is called. If a function or job calls success() and/or error() more than once in a single execution path, this error will be returned.
142 | ValidationFailed | Cloud Code validation failed.
143 | WebhookError | Webhook error.
150 | InvalidImageData | Invalid image data.
151 | UnsavedFileError | An unsaved file.
152 | InvalidPushTimeError | An invalid push time was specified.
158 | HostingError | Hosting error.
160 | InvalidEventName | The provided analytics event name is invalid.
255 | ClassNotEmpty | Class is not empty and cannot be dropped.
256 | AppNameInvalid | App name is invalid.
902 | MissingAPIKeyError | The request is missing an API key.
903 | InvalidAPIKeyError | The request is using an invalid API key.

## User related errors

Error Code | Meaning | Description
---------- | ------- | -----------
200 | UsernameMissing | The username is missing or empty.
201 | PasswordMissing | The password is missing or empty.
202 | UsernameTaken | The username has already been taken.
203 | UserEmailTaken | Email has already been used.
204	| UserEmailMissing | The email is missing, and must be specified.
205 | UserWithEmailNotFound | A user with the specified email was not found.
206 | SessionMissing | A user object without a valid session could not be altered.
207 | MustCreateUserThroughSignup | A user can only be created through signup.
208 | AccountAlreadyLinked | An account being linked is already linked to another user.
209 | InvalidSessionToken | The device’s session token is no longer valid. The application should ask the user to log in again.

## Client-only errors
Error Code | Meaning | Description
---------- | ------- | -----------
100 | ConnectionFailed | The connection to the Parse servers failed.
600 | AggregateError | There were multiple errors. Aggregate errors have an “errors” property, which is an array of error objects with more detail about each error that occurred.
601 | FileReadError | Unable to read input for a Parse File on the client.
602 | XDomainRequest | A real error code is unavailable because we had to use an XDomainRequest object to allow CORS requests in Internet Explorer, which strips the body from HTTP responses that have a non-2XX status code.

## Operational issues
Error Code | Meaning | Description
---------- | ------- | -----------
124 | RequestTimeout | The request was slow and timed out. Typically this indicates that the request is too expensive to run. You may see this when a Cloud function did not finish before timing out, or when a Parse.Cloud.httpRequest connection times out.
154 | InefficientQueryError	| An inefficient query was rejected by the server. Refer to the Performance Guide and slow query log.

## Other issues
Error Code | Meaning | Description
---------- | ------- | -----------
-1 | OtherCause | An unknown error or an error unrelated to Parse occurred.
1 | InternalServerError | Internal server error. No information available.
2 | ServiceUnavailable | The service is currently unavailable.
4 | ClientDisconnected | Connection failure.
