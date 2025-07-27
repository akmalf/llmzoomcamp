# Evaluating LLM: The Framework

for each record in FAQ:
   generate 5 questions

for each of this question: we will know that the answer is in the record

The most time-consuming (the gold standard) is to find existing users questions and match it with the knowlege base by an domain expert.

# First things first: Add ID to the records

- Simpliest way is to add 'id' to the record
- BUT if we add new record, we need to update all the IDs
- The actual best way for the FAQ identification is to take the first x digits of the hash of the record


# Metrics
- Hit rate (recall)
- Mean Reciprocal Rank (MRR)

# RAG evaluation
- Offline evaluation
  - Develop a system => get metrics => iterate => deploy
  - Metrics:
    - Cosine similarity
    - LLM-as-a-judge

    Concept:
      - In the ground truth dataset: answer_original --> question
      - From LLM: question --> answer_generated
      - Compare the two answer, e.g. cosine(answer_original,answer_generated)
      - Can also use LLM to judge the quality of the answer, cosine(question, answer_generated)

- Online evaluation
    - A/B testing
    - User feedback (thumbs up/down)

- Monitoring
    - Overall health of the system




