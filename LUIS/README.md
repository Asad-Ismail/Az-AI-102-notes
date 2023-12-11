# LUIS stands for language understanding

Converts User uttrance to actiionable outcomes


## Docker Deployment

Need following for docker deployment

1. {ENDPOINT_URI}
2. {API_KEY}
3. {APP_ID} (From LUIS Portal)
4. {AUTHORING_KEY} (From LUIS portal)

## Export Package using CLI


GET /luis/api/v2.0/package/{APP_ID}/versions/{APP_VERSION}/gzip HTTP/1.1
Host: {AZURE_REGION}.api.cognitive.microsoft.com
Ocp-Apim-Subscription-Key: {AUTHORING_KEY}


## Run Docker Container

docker run --rm -it -p 5000:5000 ^
--memory 4g ^
--cpus 2 ^
--mount type=bind,src=c:\input,target=/input ^
--mount type=bind,src=c:\output\,target=/output ^
mcr.microsoft.com/azure-cognitive-services/language/luis ^
Eula=accept ^
Billing={ENDPOINT_URI} ^
ApiKey={API_KEY}


## CLU is new version of LUIS

