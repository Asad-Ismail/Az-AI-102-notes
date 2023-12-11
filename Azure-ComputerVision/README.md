
## FACE API

1. Recognition (one to many mapping. This scenario is used in granting building or airport access to a certain group of people or verifying the user of a device.)
2. Verification (one to one mapping. )


## FACE API General image input requirements:

The supported input image formats are JPEG, PNG, GIF (the first frame), BMP.
The image file size should be no larger than 6 MB.
Input requirements for face detection:

The minimum detectable face size is 36 x 36 pixels in an image that is no larger than 1920 x 1080 pixels. Images with larger than 1920 x 1080 pixels have a proportionally larger minimum face size. Reducing the face size might cause some faces not to be detected, even if they're larger than the minimum detectable face size.
The maximum detectable face size is 4096 x 4096 pixels.
Faces outside the size range of 36 x 36 to 4096 x 4096 pixels will not be detected.
Input requirements for face recognition:

Some faces might not be recognized because of photo composition, such as:
Images with extreme lighting, for example, severe backlighting.
Obstructions that block one or both eyes.
Differences in hair type or facial hair.
Changes in facial appearance because of age.
Extreme facial expressions.

## API call example

curl -v -X POST "https://westus.api.cognitive.microsoft.com/face/v1.0/detect?returnFaceId=true&returnFaceLandmarks=false&returnFaceAttributes={string}&recognitionModel=recognition_04&returnRecognitionModel=false&detectionModel=detection_03&faceIdTimeToLive=86400"
-H "Content-Type: application/json"
-H "Ocp-Apim-Subscription-Key: {subscription key}"

--data-ascii "{body}" 


## Common Errors


### Response 400

BadArgument	JSON parsing error. Bad or unrecognizable request JSON body.
BadArgument	Invalid argument returnFaceAttributes. Supported values are: headPose, glasses, hair, occlusion, accessories, blur, exposure, noise and mask in a comma-separated format.
BadArgument	'recognitionModel' is invalid.

### Response 401

Unspecified	Invalid subscription Key or user/plan is blocked.

### Response 403

Out of call volume quota. Quota will be replenished in 2 days

### Response 408

Operation exceeds maximum execution time.

### Response 415

Unsupported media type error. Content-Type is not in the allowed types:

For an image URL, Content-Type should be application/json
For a local image, Content-Type should be application/octet-stream

### Response 429

Rate limit is exceeded. Try again in 26 seconds



