Create src/day1/structured_outputs.py that:
1. Loads 10 reviews from gen/data/reviews/reviews.jsonl
2. Sends them to Gemini via the Google Generative AI SDK with this prompt:
   "Analyze these e-commerce reviews and return a structured analysis."
3. Define a Pydantic model ReviewAnalysis with: total_reviews, average_rating,
   sentiment_distribution (dict with positive/neutral/negative counts),
   top_complaints (list of strings), top_praises (list of strings)
4. Parse Gemini's response into the ReviewAnalysis model
5. Print the typed result

Use Gemini's structured output capabilities so we get typed JSON back,
not free text. Then run it.
