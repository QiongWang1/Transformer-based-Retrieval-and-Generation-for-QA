# Transformer-based Retrieval and Generation for QA

This project implements a **Transformer-based Question Answering (QA) system**,  
using **DistilBERT** as the retriever and **Mistral-7B** as the generator.

---

## Modern QA Systems

Modern QA systems often consist of two primary parts:

- **Retriever**: Finds the most relevant documents or passages that might contain the answer to a question.
- **Generator**: Uses the retrieved information to craft a final answer in natural language.

By splitting a QA system into a retriever and a generator, we can handle large-scale data more efficiently and ensure the final answers are accurate and coherent.

---

## The Retriever: Finding the Right Information

Imagine you have a huge library of books. A friend asks you a question, and you need to find which book (and which page) has the information needed to answer them. That’s essentially what the retriever does:

- **Search**: The retriever searches through a large pool of documents (e.g., web articles, Wikipedia pages, or scientific papers) to find the most relevant text snippets.  
- **Filtering**: It filters out irrelevant information so that only useful, on-topic passages remain.  
- **Efficiency**: A well-designed retriever cuts down the total amount of text passed to the generator, which speeds up the system and boosts accuracy.  

### Why Retrieval Is Crucial
- **Scalability**: You can maintain huge collections of documents without overloading your system at generation time.  
- **Accuracy**: Generators work best when they have focused, high-quality source text to draw from.  

---

## The Generator: Crafting the Answer

Once the retriever has identified the relevant passages, the generator takes over to create a concise, human-like answer. Here’s how:

- **Reading**: The generator reads the retrieved text carefully.  
- **Reasoning**: It pieces together the key facts and context to address the user’s question directly.  
- **Writing**: Finally, it produces a clear, coherent response in natural language—like a teacher explaining the answer to a student.  

### Why Generation Matters
- **Clarity**: Instead of just copying text, a generator can interpret and summarize information, making the answer more understandable.  
- **Flexibility**: Generators can answer various types of questions (factual, explanatory, etc.) and adapt their style (short answer, longer explanation, etc.).  

---

## Evaluation Metric

Evaluation on Third Kaggle Competition consists of 3 steps:

1. **Precision of Retriever** – how many false positives Retriever found.  
   Precision measures how many of retrieved documents were actually relevant.  
   Formula: `Precision = TP / (TP + FP)`  

2. **Recall of Retriever** – how many false negatives Retriever has.  
   Recall measures how many relevant documents were actually retrieved.  
   Formula: `Recall = TP / (TP + FN)`  

3. **BLEU score of Generator** – how similar is your answer to the ground truth answer.  
   Higher the BLEU → the better your answer is.  

**Final Metric** = (Precision + Recall + BLEU) / 3  


![](images/3.png)
![](images/4.png)