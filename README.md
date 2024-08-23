# Prompt Engineering 101

Or: *How to talk to an LLM to get it to do what you want.*

## 1. Elements of a prompt

 <img src='https://drive.google.com/uc?export=view&id=1Ey5SaKoBL16Gb2L9QNlqWL4j2Zg7G_5W' width=500px>

 At least an instruction or question should be present.

- Instructions

```
> Translate from English to German: How are you?
```

- Questions

```
> What is the meaning of life?
```

- Input data / Context

```
> Here is a transcript of a podcast about Generative AI: {transcript}.

  What do they say about LLMs?
```

- Examples

-> Few-shot prompting

```
> Question: The capital of France is?
  Answer: Paris

  Question: The capital of Germany is?
  Answer:
```

- Output format

```
> ...

Output: Yes, No

or

Output: Provide a short answer, and then explain your reasoning.
```

## 2. Use cases

 <img src='https://drive.google.com/uc?export=view&id=1TFlCrzyJT1YO9ChIGEOWCqMWfCCjHlmT' width=500px>

- Summarization

```
> Summarize the following text:

  Text: ...
```

- Text classification

```
> Classify the following text into one of the classes - sports, finance, education.

  Text: ...
```

- Translation

```
> Translate from English to German:

  The best programming language is Python.
```

- Text Generation / Text completion

```
> AI is
```

- Question / Answering

```
> What is the meaning of life?

> Based on the following podcast transcript, what is the host's opinion about AI?

  Transcript: ...
```

- Coaching

```
> How would you improve the following script for a YouTube video about Generative AI?

  Script:
```

- Image generation

```
> Generate an image of a cute puppy.
```

## 3. General tips

- Use direct instructions or a clear question. Use concise and unambiguous language.
- Provide any relevant information or data as context.
- Give examples in prompts (=few-shot prompting).
- Specify the desired output format.
- Encourage the model to be factual through other means:

```
> Are mRNA vaccines safe?
Answer only using reliable sources and cite those sources.
```

- Align prompt instructions with the task's end goal:

```
> This is a conversation between a customer and a polite, helpful customer support service agent.

Customer: Can you help me?

Assistamt: Of course! What is your question?
```

- Use personas to get more specific voices:

```
> You are a kind customer support service agent. ...
```

## 4. Prompting techniques to control the output

- Length control: Specify desired output length

```
> Write a 150 word summary on…
```

- Tone control:

```
> Write a polite response
```

- Style control:

```
> Give me the summary as bullet points
```

- Audience control:

```
> Explain this topic to a 5 year old kid
```

- Context control (How much context you share)

- Scenario-based guiding:

```
> You are a customer support expert.
```

- Chain of thought prompting: provides a "chain of thought" process that showcases how the correct answer to a question should be reached.
Provide the chain of thought either with examples (few-shot), or simply by adding "Let's think step by step".

```
I went to the market and bought 10 apples.
I gave 2 apples to the neighbor and 2 to the repairman.
I then went and bought 5 more apples and ate 1.
How many apples did I remain with?

Answer:
First, you started with 10 apples.
You gave away 2 apples to the neighbor and 2 to the repairman, so you had 6 apples left.
Then you bought 5 more apples, so now you had 11 apples.
Finally, you ate 1 apple, so you would remain with 10 apples.


I went to the market and bought 50 apples.
I gave 3 apples to the neighbor and 7 to the repairman.
I then went and bought 15 more apples and ate 3.
How many apples did I remain with?

Answer:
```

Or zero-shot COT:

```
I went to the market and bought 10 apples.
I gave 2 apples to the neighbor and 2 to the repairman.
I then went and bought 5 more apples and ate 1.
How many apples did I remain with?

Let's think step by step.
```

- Avoid hallucination:

```
> Don't make anything up.

> Select one or two relevant quotations from the text to back up your claims.
```

## 5. Hacks
From [Anthropic docs](https://docs.anthropic.com/claude/docs/ask-claude-for-rewrites):
- Let the model say "I don't know" to prevent hallucinations

```
> Answer the following question only if you know the answer or can make a well-informed guess; otherwise tell me you don't know it.

What was the heaviest hippo ever recorded?
```

- Give the model room to "think" before responding

```
> Instruction

When you reply, first find exact quotes in the FAQ relevant to the user's question and write them down word for word.

This is a space for you to write down relevant content and will not be shown to the user.

Once you are done extracting relevant quotes, answer the question.
```

- Break complex tasks into subtasks

```
> Please follow these steps:
1. Write three topic sentences arguing for {{STATEMENT}}.
2. Write three topic sentences arguing against {{STATEMENT}}.
3. Write an essay by expanding each topic sentence from Steps 1 and 2, and adding a conclusion to synthesize the arguments. Please enclose the essay in <essay></essay> tags.

Assistant:
```

- Check the model's comprehension

```
> Human: I am going to give you a sentence and you need to tell me how many times it contains the word "apple".
For example, if I say "I would like an apple" then the answer is "1" because the word "apple" is in the sentence once.
You can reason through or explain anything you'd like before responding, but make sure at the very end, you end your answer with just the final answer in brackets, like this: [1].

Do you understand the instructions?

Assistant:
```

## 6. Iterating Tips:
- Try different prompts to find what works best
- When attempting few-shot learning, try also including direct instructions
- Rephrase a direct instruction set to be more or less concise, e.g. taking a previous example of just saying "Translate." and expanding on the instruction to say "Translate from English to Spanish."
- Try different persona keywords to see how it affects the response style
- Use fewer or more examples in your few-shot learning

## 7. Summary
- Keep the elements of a prompt in mind
- Apply basic tips
- Apply prompting techniques to control the output
- Iterate!

## 8. Resources

- https://amatriain.net/blog/PromptEngineering
- https://humanloop.com/blog/prompt-engineering-101
- https://github.com/SudalaiRajkumar/Talks_Webinars/blob/master/Slides/PromptEngineering_20230208.pdf
- https://docs.cohere.com/docs/prompt-engineering
- https://www.mihaileric.com/posts/a-complete-introduction-to-prompt-engineering/
- https://github.com/f/awesome-chatgpt-prompts
- https://github.com/promptslab/Awesome-Prompt-Engineering
- https://youtu.be/v2gD8BHOaX4
- https://docs.anthropic.com/claude/docs/optimizing-your-prompt
- https://www.assemblyai.com/docs/Guides/lemur_best_practices
