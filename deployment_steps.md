# Deployment Steps for Amazon Lex Chatbot with AWS Lambda

## Step 1: Create an Amazon Lex Chatbot
1. Log in to the **AWS Management Console**.
2. Navigate to **Amazon Lex**.
3. Click **Create bot** and select **Custom bot**.
4. Define the bot’s **name, language, and IAM permissions**.
5. Set up intents such as:
   - `CheckBalanceIntent` (for retrieving account balances).
6. Configure **slots** (if needed) for gathering user inputs.
7. Save and build the chatbot.
8. Create an **alias** (e.g., `TestBotAlias`) to link the bot version with Lambda.

## Step 2: Create an AWS Lambda Function
1. Navigate to the **AWS Lambda Console**.
2. Click **Create function** → Choose **Author from scratch**.
3. Name the function (e.g., `BankerBotLambda`).
4. Select **Python 3.x** as the runtime.
5. Attach an appropriate IAM role with permissions.
6. Replace the default code with:
   ```python
   import json
   import random
   
   def lambda_handler(event, context):
       balance = random.randint(100, 10000)
       return {
           'dialogAction': {
               'type': 'Close',
               'fulfillmentState': 'Fulfilled',
               'message': {'contentType': 'PlainText', 'content': f'Your account balance is ${balance}.'}
           }
       }
   ```
7. Click **Deploy**.

## Step 3: Connect Lambda to Lex
1. In the **Amazon Lex Console**, open your chatbot.
2. Go to **Alias** → Select `TestBotAlias`.
3. Under **Fulfillment**, select **AWS Lambda Function**.
4. Choose the deployed Lambda function (`BankerBotLambda`).
5. Save and build the chatbot again.

## Step 4: Enable Code Hooks (Optional)
1. Navigate to **Intents** in Amazon Lex.
2. Select `CheckBalanceIntent`.
3. Under **Fulfillment**, choose **Use a Lambda function**.
4. Select `BankerBotLambda` to allow Lex to invoke the function dynamically.
5. Save and build the chatbot.

## Step 5: Test the Chatbot
1. Go to the **Amazon Lex Test Bot** section.
2. Type: `What is my account balance?`.
3. The bot should respond with a randomly generated balance.

## Step 6: Customize the Lambda Function (Optional)
1. Modify the Lambda function to support additional features.
2. Create new intent-handling functions (e.g., `CheckBalance()` and `FollowUpCheckBalance()`).
3. Return customized messages based on user queries.

## Step 7: Deploy and Optimize
- Improve chatbot logic with **additional intents**.
- Deploy the chatbot in applications using **AWS API Gateway & AWS Lambda integrations**.
- Automate infrastructure using **Terraform or CloudFormation**.

## Conclusion
Your chatbot is now fully deployed and can dynamically retrieve and return user account balances through AWS Lambda.

