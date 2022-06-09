# ApiGateway setup tips
## Invoke Lambda via ApiGateway
### Add Permission to allow a specified ApiGateway endpoint to invoke the lambda
```
SampleApiPermission:
    Type: AWS::Lambda::Permission
    Properties:
      Action: "lambda:InvokeFunction"
      FunctionName: !Ref MyLambdaFnA1
      Principal: "apigateway.amazonaws.com"
      SourceArn: !Sub "arn:aws:execute-api:${AWS::Region}:${AWS::AccountId}:<api-id>/*/<method>/<resource>"
```
Source: [AWS Knowledge centre](https://aws.amazon.com/premiumsupport/knowledge-center/api-gateway-rest-api-lambda-integrations/)

Note: To see the actual SourceArn navigate into ApiGateway -> Resources -> Method (e.g. POST of a certain resource)
![Screenshot 2022-06-10 065325](https://user-images.githubusercontent.com/30810819/172923498-7e5483a4-20e5-4482-8619-9e6ada7efa5e.png)
