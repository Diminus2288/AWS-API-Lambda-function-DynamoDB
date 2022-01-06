# AWS-API-Lambda-function-DynamoDB
URL Get
https://5ttkomii61.execute-api.us-east-1.amazonaws.com/Prod
URL Post
https://37sfkbd2i8.execute-api.us-east-1.amazonaws.com/Prod
First Lambda cod
exports.handler = function(event, context, callback) {
   console.log("Incoming Event: ", event);
   const bucket = event.Records[0].s3.bucket.name;
   const filename = decodeURIComponent(event.Records[0].s3.object.key.replace(/\+/g, ' '));
   const message = `File is uploaded in - ${bucket} -> ${filename}`;
   console.log(message);
   callback(null, message);
};
Second Lambda cod
exports.handler = async (event) => {
    // TODO implement
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from Lambda!'),
    };
    return response;
};
I also have a DinamoDB and it's all connected and works
