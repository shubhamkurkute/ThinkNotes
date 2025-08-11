- Naive Bayes is probabilisitic classifier based on bayes theorem.
- Naive Bayes is called naive because it assumes that the variables are independent of each other.
- This is strong and unrealistic assumption in real world data. It is widely used in large datasets.
- Mathematical Concept:
	Bayes Theorem - Naive Bayes relies on bayes theorem, which states

  $$P(A|B) =  \frac{P(B|A) \times P(A)}{P(B)}$$

  where,

  - $P(A), P(B) $ : are the independent probabilities of event `A` and event `B`

  - $P(B|A)$ : is the probability for event `B` given event `A` has already happened

  - $P(A|B)$ : is the probability for event `A` given event `B` has already happened
 - Bayes Theorem calculates the probability of an event occuring given that the other event has already happened.
 - Prominently used in NLP, Sentiment Analysis, Text Classification etc.