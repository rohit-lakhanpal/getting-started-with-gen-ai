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


