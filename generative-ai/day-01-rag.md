# Day 1 — Retrieval-Augmented Generation (RAG)

**Date:** September 16, 2026
**Category:** Generative AI
**Topic:** Retrieval-Augmented Generation (RAG)

---

## 1. What Does RAG Mean?

**RAG** stands for **Retrieval-Augmented Generation**.

RAG is a technique that allows an AI application to **retrieve relevant information from external sources and provide that information to an LLM before generating an answer.**

In simple words:

> **RAG = Retrieve information → Give it to the LLM → Generate an answer**

The external information could come from:

* PDFs
* Company documents
* Websites
* Databases
* Knowledge bases
* Internal documentation

RAG is useful when an AI application needs to answer questions using information that may not be available in the LLM's existing knowledge.

---

## 2. Easy Analogy

### RAG is like an open-book exam.

Imagine a teacher asks:

> "According to this textbook, what is photosynthesis?"

### Without RAG

The student tries to answer from memory.

```text
Question
   ↓
Student's existing knowledge
   ↓
Answer
```

### With RAG

The student:

1. Opens the textbook.
2. Searches for the relevant section.
3. Reads the information.
4. Uses that information to answer.

```text
Question
   ↓
Search the textbook
   ↓
Find relevant information
   ↓
Read it
   ↓
Answer
```

So my simple mental model is:

> **RAG gives an AI model an "open book" before it answers.**

---

## 3. Technical Example

Imagine we have an employee handbook containing:

```text
Employees receive 20 vacation days per year.
```

A user asks:

```text
How many vacation days do employees receive?
```

A basic RAG application could work like this:

```text
User Question
      ↓
Search company documents
      ↓
Find relevant document section
      ↓
Retrieve:
"Employees receive 20 vacation days per year."
      ↓
Send question + retrieved information to LLM
      ↓
Generate answer
      ↓
"Employees receive 20 vacation days per year."
```

The important idea is that the LLM receives **relevant information from an external source** before generating the answer.

---

## 4. How Does RAG Work?

A basic RAG system has two main stages.

### Stage 1 — Prepare the Documents

```text
Documents
    ↓
Chunking
    ↓
Embeddings
    ↓
Vector Database
```

**Documents:** Original files such as PDFs or text files.

**Chunking:** Breaking large documents into smaller pieces.

**Embeddings:** Converting text into numerical representations that capture semantic meaning.

**Vector Database:** Storing embeddings and related document information so relevant content can be searched efficiently.

---

### Stage 2 — Answer a Question

```text
User Question
      ↓
Convert question to embedding
      ↓
Search for similar information
      ↓
Retrieve relevant chunks
      ↓
Send chunks + question to LLM
      ↓
Generate answer
```

This means a RAG application combines:

> **Information Retrieval + LLM Generation**

---

## 5. RAG vs. Normal LLM

| Normal LLM                               | RAG                                        |
| ---------------------------------------- | ------------------------------------------ |
| Mainly relies on learned model knowledge | Can use external knowledge                 |
| May not know private documents           | Can retrieve private documents             |
| Question → Answer                        | Question → Retrieve → Context → Answer     |
| Good for general questions               | Useful for knowledge-grounded applications |

RAG does not mean the LLM permanently learns the documents.

Instead, relevant information is **retrieved at query time and provided as context** to the LLM.

---

## 6. Key Terms

| Term                | Simple Meaning                                                         |
| ------------------- | ---------------------------------------------------------------------- |
| **RAG**             | Retrieve information and give it to an LLM before generating an answer |
| **Retrieval**       | Finding relevant information                                           |
| **Generation**      | Producing the final answer                                             |
| **LLM**             | Large Language Model that generates and understands text               |
| **Document Chunk**  | A smaller section of a larger document                                 |
| **Embedding**       | Numerical representation of the meaning of text                        |
| **Vector Database** | A system used to store and search embeddings                           |
| **Semantic Search** | Searching based on meaning rather than only exact words                |
| **Context**         | Information given to the LLM to help answer the question               |

---

## 7. RAG Architecture

A simplified RAG architecture:

```text
                 DOCUMENT PREPARATION

Documents
    ↓
Chunking
    ↓
Embeddings
    ↓
Vector Database
          │
          │
          ↓
       USER QUESTION
          ↓
     Query Embedding
          ↓
     Similarity Search
          ↓
  Relevant Document Chunks
          ↓
    LLM + Retrieved Context
          ↓
         Answer
```

---

## 8. Practice Exercise

### Exercise 1 — Explain RAG

Without looking at these notes, answer:

> What is RAG and why would we use it?

Try to explain it in **2–3 sentences**.

---

### Exercise 2 — University Chatbot

Imagine building a chatbot for a university.

The chatbot needs to answer questions about:

* Course policies
* Tuition
* Academic calendar
* Graduation requirements
* Student handbook

Answer:

1. Why could RAG be useful?
2. What documents would you give the system?
3. What happens when a student asks a question?
4. Why is retrieving the relevant document information useful?

---

### Exercise 3 — Complete the Pipeline

Complete this pipeline:

```text
Documents
     ↓
__________
     ↓
__________
     ↓
Vector Database
     ↓
Retrieve Relevant Information
     ↓
LLM
     ↓
Answer
```

**Hint:** Think about breaking documents into smaller pieces and converting text into numerical representations.

---

## 9. My Main Takeaway

The most important thing I learned today:

> **RAG allows an AI application to retrieve relevant information from external sources and provide that information to an LLM before generating an answer.**

My simple mental model:

```text
RAG = Retrieve → Add Context → Generate
```

My analogy:

> **RAG is an open-book exam for an AI model.**

---

## 10. What I Still Need to Learn

I understand the overall RAG pipeline, but I still need to understand:

* How embeddings are created
* How text is converted into vectors
* How vector similarity works
* How chunk size affects retrieval
* How vector databases work
* How semantic search works
* How an LLM uses retrieved context
* How to evaluate a RAG system
* How to reduce hallucinations in RAG applications

---

## 11. Next Topic

### Day 2 — Embeddings

Questions I want to answer next:

> What exactly is an embedding?

> How can text be converted into numbers?

> How can numbers represent the meaning of words or sentences?

> How do embeddings help RAG find relevant information?

---

## 12. Learning Hub Summary

**Topic:** Retrieval-Augmented Generation (RAG)
**Category:** Generative AI
**Status:** Learned the fundamentals

### One-sentence summary

> RAG combines information retrieval with LLM generation so an AI application can use relevant external information when answering questions.

### Remember

**Retrieve → Context → Generate**

### Analogy

**Open-book exam**

### Next

**Embeddings**
