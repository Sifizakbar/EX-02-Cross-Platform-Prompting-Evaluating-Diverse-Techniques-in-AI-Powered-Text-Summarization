# EX-02-Cross-Platform-Prompting-Evaluating-Diverse-Techniques-in-AI-Powered-Text-Summarization.

## AIM

To analyze and compare the performance of various prompting techniques (**Zero-Shot, Few-Shot, Chain-of-Thought, and Role-Based Prompting**) across different AI platforms (**ChatGPT, Gemini, Claude AI, and Microsoft Copilot**) for the purpose of **text summarization**.

---

# Scenario

You are a member of a content development team for an online learning platform that delivers simplified summaries of research articles to undergraduate students.

The objective is to summarize a **500-word technical article** on **"The Basics of Blockchain Technology"** using multiple AI platforms and prompting methods.

The generated summaries are assessed based on these factors:

- Accuracy
- Coherence
- Simplicity
- Speed
- User Experience

---

# Prompting Techniques Used

## 1. Basic Prompt

### Prompt Used
```text
Provide a summary of the following article on "The Basics of Blockchain Technology" in around 150 words.

The summary should:

Include the key ideas.
Be understandable for undergraduate students.
Preserve the original meaning.

Article:
[Paste the article here]
```

## 2. Role Prompt

### Prompt Used
``` text
Assume you are a university lecturer teaching Blockchain Technology to first-year engineering students.

Read the article below and prepare a summary of approximately 150 words.

Requirements:

Write in simple language.
Emphasize the important concepts.
Minimize technical terminology where possible.

Article:
[Paste the article here]
```

## 3. Context Prompt

### Prompt Used

``` text 
You are creating concise revision material for an educational platform designed for undergraduate students.

Read the following Blockchain Technology article and produce a summary of about 150 words.

The summary should:

Cover the essential concepts.
Remain accurate and well-organized.
Help students review the topic efficiently before exams.

Article:
[Paste the article here]
```


## 4. Constraint Prompt

### Prompt Used

``` text 
Summarize the following article on Blockchain Technology while following these conditions:

Limit the summary to 150 words
Use clear and simple English
Avoid bullet points
Suitable for first-year undergraduate students
Keep the original meaning intact
Mention only the essential concepts

Article:
[Paste the article here]
```

## 5. Output Format Prompt

### Prompt Used

``` text 
Summarize the following article on Blockchain Technology.

Present the output using the following format:

Title:
Summary:
Key Concepts:

Concept 1
Concept 2
Concept 3
Conclusion:

Requirements:

Around 150 words
Easy to understand
Appropriate for undergraduate students

Article:
[Paste the article here]
```



# AI Platform Evaluation

## ChatGPT + Zero-Shot Prompting

### Prompt Used

``` text 
Summarize the following Blockchain Technology article using simple language suitable for undergraduate students.
```


### Summary Generated

> Blockchain is a distributed digital ledger that securely stores data across multiple computers instead of relying on a single authority. Information is organized into linked blocks protected through cryptography, ensuring security and transparency. The technology is widely used in cryptocurrencies such as Bitcoin and is also applied in sectors including banking, healthcare, and supply chain management. Although blockchain offers improved trust and security, it still faces issues related to scalability and high energy consumption.

### Evaluation

| **CriterionResult** |           |
| ------------------- | --------- |
| Accuracy            | High      |
| Coherence           | Good      |
| Simplicity          | Excellent |
| Speed               | Very Fast |
| User Experience     | Excellent |

---

## Gemini + Few-Shot Prompting

### Prompt Used

``` text 
Review the following sample summaries and create a summary of the blockchain article in the same style.
```


### Summary Generated

> Blockchain is a decentralized digital ledger that stores records in interconnected blocks. Since every participant shares the same version of the data, the system becomes transparent and resistant to tampering. It is the foundation of cryptocurrency networks and also supports applications in finance, healthcare, and logistics. Despite its benefits, blockchain continues to face limitations such as slower processing speeds and increased energy requirements.

### Evaluation

| **CriterionResult** |           |
| ------------------- | --------- |
| Accuracy            | Very High |
| Coherence           | Excellent |
| Simplicity          | Moderate  |
| Speed               | Fast      |
| User Experience     | Good      |

---

## Claude AI + Chain-of-Thought Prompting

### Prompt Used

Carefully analyze the article, identify the main concepts step by step, and then prepare a concise summary suitable for undergraduate students.


### Summary Generated

> Blockchain is a decentralized ledger technology that records transactions securely across a network of computers. Transactions are grouped into blocks, which are linked together using cryptographic hashes to maintain integrity. Consensus mechanisms such as Proof of Work and Proof of Stake ensure secure validation of transactions. Blockchain is extensively used in cryptocurrency systems and has growing applications in banking, healthcare, and supply chain management. Its primary strengths include transparency and security, while scalability and energy consumption remain significant challenges.

### Evaluation

| **CriterionResult** |           |
| ------------------- | --------- |
| Accuracy            | Excellent |
| Coherence           | Excellent |
| Simplicity          | Good      |
| Speed               | Moderate  |
| User Experience     | Very Good |

---

## Microsoft Copilot + Role-Based Prompting

### Prompt Used

Act as a university instructor and provide a brief explanation of blockchain technology for undergraduate students.


### Summary Generated

> Blockchain is a digital technology that stores information in connected blocks across multiple computer systems. Because the information is shared among many participants, it is highly secure and difficult to alter. The technology reduces dependence on central authorities while improving transparency and trust. Blockchain is widely used in cryptocurrency and financial applications, although concerns such as energy usage and transaction speed continue to exist.

### Evaluation

| **CriterionResult** |           |
| ------------------- | --------- |
| Accuracy            | Good      |
| Coherence           | Good      |
| Simplicity          | Excellent |
| Speed               | Fast      |
| User Experience     | Good      |

---

# Comparison Table

| **AI PlatformPrompting TechniqueAccuracyCoherenceSimplicitySpeedUser Experience** |                  |           |           |           |           |           |
| --------------------------------------------------------------------------------- | ---------------- | --------- | --------- | --------- | --------- | --------- |
| ChatGPT                                                                           | Zero-Shot        | High      | Good      | Excellent | Very Fast | Excellent |
| Gemini                                                                            | Few-Shot         | Very High | Excellent | Moderate  | Fast      | Good      |
| Claude AI                                                                         | Chain-of-Thought | Excellent | Excellent | Good      | Moderate  | Very Good |
| Microsoft Copilot                                                                 | Role-Based       | Good      | Good      | Excellent | Fast      | Good      |

---

# Overall Findings

| **PlatformKey StrengthLimitation** |                                                    |                                              |
| ---------------------------------- | -------------------------------------------------- | -------------------------------------------- |
| ChatGPT                            | Delivers an excellent combination of clarity, readability, and speed | Provides slightly fewer technical details than Claude AI |
| Gemini                             | Produces organized and highly accurate summaries | Uses somewhat more advanced technical terms |
| Claude AI                          | Generates the most detailed and logically consistent summaries | Takes a little longer to generate responses |
| Microsoft Copilot                  | Offers concise and beginner-friendly explanations | Covers fewer details compared to Claude AI and Gemini |

---

# Final Result

Different prompting techniques were tested across several AI platforms for summarizing a technical article on **Blockchain Technology**.

The experiment led to the following conclusions:

- **Claude AI with Chain-of-Thought Prompting** created the most accurate, coherent, and well-structured summaries by first identifying the core concepts before generating the final response.
- **ChatGPT with Zero-Shot Prompting** provided the best combination of simplicity, readability, response speed, and overall user experience, making it an excellent choice for undergraduate learners.
- **Gemini with Few-Shot Prompting** produced accurate and well-organized summaries, although the language was slightly more technical.
- **Microsoft Copilot with Role-Based Prompting** generated short, easy-to-understand summaries that were beginner-friendly but contained fewer technical details.
