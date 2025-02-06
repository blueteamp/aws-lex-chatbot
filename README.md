# Amazon Lex Chatbot with AWS Lambda

## Overview
This project showcases an Amazon Lex chatbot integrated with AWS Lambda. The chatbot understands user intents, manages slots, and dynamically interacts using a Lambda function.

## Features
- **Amazon Lex Integration**: Conversational AI chatbot with intent recognition.
- **AWS Lambda**: Handles dynamic responses and custom logic.
- **Code Hooks**: Enhances chatbot functionality with external processing.
- **Customizable Responses**: Modify the chatbot's behavior and messages.

## Project Components
- **Amazon Lex Bot**: Configured to recognize user intents and trigger Lambda.
- **AWS Lambda Function**: Generates random account balances upon request.
- **Chatbot Alias**: Connects different versions for easier updates.

## Setup Instructions
1. **Create an Amazon Lex Bot**
   - Define intents and slot types.
   - Configure fulfillment using AWS Lambda.
2. **Deploy an AWS Lambda Function**
   - Write a Python function to return a simulated bank balance.
   - Connect Lambda to Lex using code hooks.
3. **Test the Chatbot**
   - Use the Lex console to interact with the bot.
   - Verify Lambda execution and response.

## Repository Structure
```
📂 aws-lex-chatbot
├── README.md  # Project overview
├── deployment_steps.md  # Step-by-step guide
├── source_code/  # Lambda function scripts
├── screenshots/  # Setup images from PDF
```

## Next Steps
- **Enhance the bot with more intents.**
- **Deploy on AWS using Terraform for automation.**

## Connect
Interested in AI & Cloud projects? Let's collaborate!
