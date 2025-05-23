# Getting Starteed with Generative AI

## Overview

This repository contains a collection of links and resources to help you get started with generative AI. It includes tutorials, articles, and other materials that cover various aspects of generative AI, including its applications, techniques, and tools.

## Step 1: Understand the Basics

- **[Introduction to generative AI](https://learn.microsoft.com/en-us/training/modules/fundamentals-generative-ai/)**: In this module, you explore the way in which language models enable AI applications and services to generate original content based on natural language input. 

## Step 2: Start Interacting with Generative AI

1. Navigate to the [Azure AI Foundry | Azure OpenAI](https://oai.azure.com/) page.
1. Sign in with your Microsoft account.
1. Either select an existing resource or create a new one.
1. Click on "Playground" in the left navigation pane. 
1. Then click the "Try the Chat playground" button.
1. Either select an existing model (e.g. gpt-4o) that you have deployed or create a new one.


## Step 3: Understand the UI Interface

The Chat Playground UI in Azure AI Foundry is designed to provide users, especially those new to large language models, with a visual and intuitive interface for experimenting with prompts and model parameters. 

![image](/docs/images/chat-playground.png)

The interface is divided into several sections, each serving a specific purpose.

At the top of the interface, users can select the **deployed model** (in this case, gpt-4o) and optionally set instructions in the **"model instructions and context"** box *(also known as **"System Instructions"**)* to guide the assistant’s behavior. This area is ideal for defining the assistant’s tone, personality, or domain-specific knowledge. 

There’s also a **"Generate system prompt"** button that can assist beginners by auto-suggesting a baseline configuration.

Below that, the **parameter section** allows for precise control over the model's behavior. Users can set various parameters to customize the interaction:
- **Past Messages Included**: Select the number of past messages to include in each new API request. This helps give the model context for new user queries. Setting this number to 10 will include 5 user queries and 5 system responses.
- **Max Response**: Set a limit on the number of tokens per model response. The supported number of tokens are shared between the prompt (including system message, examples, message history, and user query) and the model's response. One token is roughly 4 characters for typical English text.
- **Temperature**: Controls randomness. Lowering the temperature means that the model will produce more repetitive and deterministic responses. Increasing the temperature will result in more unexpected or creative responses. Try adjusting temperature or Top P but not both.
- **Top P**: CSimilar to temperature, this controls randomness but uses a different method. Lowering Top P will narrow the model’s token selection to likelier tokens. Increasing Top P will let the model choose from tokens with both high and low likelihood. Try adjusting temperature or Top P but not both.
- **Stop Sequence**: Make the model end its response at a desired point. The model response will end before the specified sequence, so it won't contain the stop sequence text. For ChatGPT, using <|im_end|> ensures that the model response doesn't generate a follow-up user query. You can include as many as four stop sequences.

On the right side, the **chat history panel** displays the ongoing conversation, with sample prompts provided to inspire interaction. Users can type directly into the chat box at the bottom to begin experimenting. 

## Step 4: Start Experimenting

### Activity 1: Basic Chat 
- **Goal**: Observe default assistant behavior without any system messages.  
- **System Instructions**: Leave blank. (Remember to click "Apply Changes" after editing.)
- **User Message**: 
    ```
    Hello
    ```
- **Observations**: Note the tone and style of the assistant's reply.  
- **Extra Credit**: Try asking the assistant to tell you a joke.

### Activity 2: Single-Turn Q&A  
- **Goal**: Practice asking factual questions. 
- **System Instructions**: Leave blank.
- **User Message**: 
    ```
    What is the capital of France?
    ```
- **Observations**: Note the accuracy and relevance of the assistant's reply.
- **Extra Credit**: Now ask a follow up question that the model might not know based on the cutoff date of the model. 
    ```
    What is the capital of France? What is the population of Paris?
    ```

### Activity 3: System Prompt Basics  
- **Goal**: Set assistant behavior using a system message. 
- **System Instructions**: 
    ```
    You are a procurement-savvy assistant.
    ```
- **User Message**: 
    ```
    Hello
    ```
- **Observations**: Note how the assistant's tone and style change based on the system message.

### Activity 4: Role Messages  
- **Goal**: Understand the influence of system, user, and assistant roles. 
- **System Instructions**: 
    ```
    You are an expert RFP drafter.  
    ```
- **User Message**: 
    ```
    Draft an introduction for an RFP on city road maintenance.  
    ```
- **Observations**: Note how the assistant's response is influenced by the system message.
- **Extra Credit**: Determine which parts are influenced by system vs. user messages.  

### Activity 5: Instruction Mode  
- **Goal**: Enforce a specific output format.  
- **System Instructions**: 
    ```
    You are a procurement-savvy assistant. 
    Reply as bulleted lists. 
    ```
- **User Message**: 
    ```
    What are the key components of a successful RFP?
    ```
- **Observations**: Note how the assistant's response is influenced by the system message.
- **Extra Credit**: Try asking the assistant to provide a list of 5 items. 
    ```
    What are the key components of a successful RFP? Provide a list of 5 items.
    ```

### Activity 6: Use the "Generate System Prompt" Button
- **Goal**: Use the "Generate System Prompt" button to create a system message.
- **Activity**: 
    - Click the "Generate System Prompt" button. This should open up a modal window that asks you to describe what you want the model to do.
    - Type in 
        ```
        An AI Assistant designed to help interpret and analyze existing Requests for Proposals (RFPs).
        ```
    - Click the "Generate" button.
- **User Message**: 
    ```
    What are the key components of a successful RFP?
    ```
- **Observations**: Note how the assistant's response is influenced by the system message.


### Activity 7: Temperature Control  
- **Goal**: Compare creativity at different temperatures.  
- **System Instructions**: Leave blank.
- **User Message**: 
    ```
    Draft a cover-letter snippet for a bid.
    ```
- **Temp = 0.0 vs. Temp = 1.0**  
- **Observations**: Note the creativity and variability of the assistant's response.

### Activity 8: Top P Control
- **Goal**: Compare creativity at different Top P values.
- **System Instructions**: Leave blank.
- **User Message**: 
    ```
    Generate an executive summary of our bid portal.
    ```
- **Top P** = 0.3 vs. top_p = 1.0**  
- **Observations**: Note the creativity and variability of the assistant's response.

### Activity 9. Max Response  
- **Goal**: Limit response length.  
- **System Instructions**: Leave blank.
- **User Message**: 
    ```
    Draft a cover-letter snippet for a bid.
    ```
- **Max Response = 50 vs. Max Response = 200**
- **Observations**: Observe truncation vs. detailed summary.  


### Activity 10: Attaching Files
- **Goal**: Upload a file and ask the assistant to analyze it.
- **System Instructions**: 
    ```
    You are an AI Assistant designed to help users interpret and analyze existing Requests for Proposals (RFPs). Your role is to assist in extracting key details, breaking down the requirements, and identifying actionable insights from an RFP document. Provide clarity, structure, and actionable recommendations to support the user in understanding and responding effectively to the RFP.
    ```
- **User Message**: 
    ```
    What is the due date?
    ```
- **File**: Save this file locally by right-clicking and selecting "Save As" or "Download". [Sample RFP](/docs/resources/sample-rfp-brand-usa-0010.png)![Sample RFP](/docs/resources/sample-rfp-brand-usa-0010.png)
- **Upload**: Click the "Upload" button in the chat interface and select the file you saved.
- **Observations**: Note how the assistant interprets the file and reasons over it.

### Activity 11: Summarize an RFP based on a recommended format
- **Goal**: Use the assistant to summarize an RFP based on a recommended format.
- **System Instructions**: 
    ```
    Summarize the RFP based on the following format:
    1. Executive Summary
    2. Key Dates
    3. Scope of Work
    4. Evaluation Criteria
    5. Submission Requirements
    ```
- **User Message**: Copy and paste the RFP text using this [sample rfp](/docs/resources/sample-digital-advertising-rfp.md) as a reference.
- **Observations**: Note how the assistant organizes the information based on the provided format.
- **Extra Credit**: Check for accuracy and completeness of the summary. If it is inaccurate could you try changing the system instructions to be more specific e.g. "Do not include any information that is not in the RFP. Do not make any assumptions about the RFP. Only include information that is in the RFP."

### Activity 12: Zero-Shot, One-Shot, and Few-Shot 
- **Goal**: Understand the difference between zero-shot, one-shot, and few-shot learning.
- **System Instructions**: 
    ```
    You are an AI Assistant designed to help users interpret, analyze or draft Requests for Proposals (RFPs). 
    ```
- **User Message**: 
    ```
    Draft a cover-letter snippet for a bid.
    ```
- **Zero-Shot**: No examples provided.
- **One-Shot**: Provide one example of a cover letter snippet followed by the user message with an expected output.
- **Few-Shot**: Provide two or three examples of cover letter snippets followed by the user message with an expected output.
- **Observations**: Note how the assistant's response changes based on the number of examples provided.

### Activity 13: Self-Critique
- **Goal**: Use the assistant to critique its own response and observe changes in accuracy.
- **System Instructions**: 
    ```
    You will be provided one or more RPFs, and your task is to carefully analyze their contents to answer specific questions or provide requested feedback. 
    ```
- **User Message**: 
    ```
    What is the minimum number of quality applications per month that FicticiousPD expects as a result of the digital advertising campaign?

    <RFP>

    PLEASE REPLACE THIS TEXT WITH THE RFP CONTENT FROM [this file](/docs/resources/sample-digital-advertising-rfp.md)

    </RFP>
    ```
- **Observations**: Note how the assistant critiques its own response and whether it improves accuracy.
- **Extra Credit**: Ask the assistant to critique its own response and then ask it to provide a better response. 
    ```
    Provide reasoning for your answer.
    ```

    In addition add the following system instructions:
    ```
    Focus on clarity, completeness, and relevance when analyzing the content. Use logical reasoning to extract pertinent details before forming conclusions or crafting responses.
    ```

### Activity 14: Classification
- **Goal**: Use the assistant to classify RFPs based on their content.
- **System Instructions**: 
    ```
    Classify the RFP based on the following categories:
    1. Digital Advertising
    2. Branding
    3. Social Media
    4. Public Relations
    5. Market Research
    ```
- **User Message**: Use the sample RFP text from [this file](/docs/resources/sample-digital-advertising-rfp.md).
- **Observations**: Note how the assistant classifies the RFP based on the provided categories.


### Activity 15: Response Generation (specify a format)
- **Goal**: Expect responses in a specfic format. (e.g. JSON, CSV, etc.)
- **System Instructions**: 
    ```
    Classify the RFP based on the following categories:
    1. Digital Advertising
    2. Branding
    3. Social Media
    4. Public Relations
    5. Market Research

    Provide the response in JSON format. 
    ```
- **User Message**: Use the sample RFP text from [this file](/docs/resources/sample-digital-advertising-rfp.md).
- **Observations**: Note how the assistant generates the response in the specified format.
- **Extra Credit**: Be more specific about the format you want. For example, you can specify the JSON format to be:
    ```
    {
        "categories": [
            "Digital Advertising",
            "Branding",
            "Social Media",
            "Public Relations",
            "Market Research"
        ]
    }
    ```