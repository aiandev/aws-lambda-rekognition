# AWS Lambda + Rekognition

This project shows you how to setup an S3 trigger whenever an image is added to
an S3 bucket. The trigger will invoke a Lambda function. This Lambda function
will call AWS Rekognition, and output the results in the same S3 bucket as a
JSON file.

## Screenshots

![Screenshot](https://user-images.githubusercontent.com/2158187/45521780-63028900-b774-11e8-891b-6d6f2a6a1c01.png)
![Screenshot](https://user-images.githubusercontent.com/2158187/45521781-63028900-b774-11e8-80c1-6f9fdf1a9df4.png)
![Screenshot](https://user-images.githubusercontent.com/2158187/45521779-63028900-b774-11e8-8075-993191ce9074.png)

## How to use

1. Clone this repo!
2. `yarn` to build everything.
3. Go to AWS Console.
4. Create a Node.js 8.10 Lambda function called "rekognize" with dummy
   Javascript. When you create the function, add a Role giving full access to
   CloudWatch, Rekognition, and S3. Bump up the timeout to 30 seconds.
5. `yarn run deploy` to deploy our code to this new Lambda function!
6. Go to your S3 bucket. We are going to add a trigger so that our
   function fires whenever a `png` image is added. Click the "Properties" tab.
   Expand the "Events" panel. Add a Lambda trigger that should look like this:
   ![Screenshot](https://user-images.githubusercontent.com/2158187/45250485-e80b1f80-b2e8-11e8-988b-07fe25212e7d.png)
7. Test it! Upload a png image to the S3 bucket. In a moment or so, you will
   see a JSON file with the results. Cool!
