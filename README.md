# UNDERSTANDING-OF-OPEN-AI
 This repo is designed to deepen  understanding of the parameters used with the OpenAI Chat Completion API. i will explain the purpose and functionality of the following terms or parameters .  
 **Terms/Parameters to Explain:** 
 - Messages
 - Model
 - Max Completion Tokens
 - n
 - Stream
 - Temperature
 - Top_p
 - Tools

**1. Messages**

It is used to show up history from the user with respect to the AI, following are list of message objects

**Functionality:**  
 - Each message object will contain a `role` (user, assistant, or system) along with its respective `content`.

 - The `system` role specifies instructions, the `user` role specifies prompts, and the `assistant` role specifies AI's responses.

**Example:**

  ```json

  [

      { "role": "system", "content": "You are a helpful assistant." },

      { "role": "user", "content": "What is the weather today?" }

  ]

  ```

**2. Model**

It Specifies which AI model to use for generating responses.

**Functionality:**  

  - Different models have different capabilities, latency, and costs (e.g., `gpt-4`, `gpt-3.5-turbo`).

  - Affects the quality and depth of responses.

 **Example:** `model="gpt-3.5-turbo"`


**3. Max Completion Tokens**

It limits the number of tokens (words/characters) the AI can generate in a single response.

**Functionality:**  

  - A higher value allows longer responses but consumes more computational resources.

- Total tokens add input + output tokens; capped at the model's maximum token limit.

**Example:** `max_tokens=100`


**4. n**

It controls how many completion variations are returned for every prompt.

**Functionality:**
 - Useful for exploring different outputs, such as ways for: to phrase an answer

 - More variations are produced with higher `n` values, increasing resource consumption.

**Example:** `n=3` returns three distinct completions.


**5. Stream**

It allows streaming of responses as they are generated, instead of having the full response.

**Functionality:**
 - When set to `true`, the API returns tokens as they are generated. Increases user experience for longer output

**Example:** `stream=true`


**6. Temperature**

It controls the randomness of the output.

**Functionality:** 
 - The lower the value, the more deterministic and focused the response will be, e.g., when using `0.2`.

- Greater values (e.g., `0.8`) involve more creativity and more variety.

**Example:** `temperature=0.7`


 **7. Top_p**

- Purpose: It controls the diversity of the output by operating with nucleus sampling.

- How it works:  Only considers the top `p` probability mass of token options. It can be used as an alternative to temperature; the values around `1.0` includes all the token options, while smaller values (for example, `0.3`) limit the pool.

**Example:** `top_p=0.9`


**8. Tools**

It is used to integrates external tools or plugins the AI can use to enhance responses.

**Functionality:**  

  - Allows the model to perform actions like querying databases, retrieving live information, or executing tasks.

  - Examples: Browsers, calculators, or custom APIs integrated via tool definitions.

 **Example:** Providing a tool for math calculations ensures accurate results beyond the model’s language capabilities.


