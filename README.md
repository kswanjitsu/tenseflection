
# This is a custom NLP script that I used for a startup to change the verb tense and person of medical notes
### The point of this was aid our extractive summarizer to make the output sound more natural

- The reason for this is because most medical notes are written in the first person and use mostly present tense verbs
- When we (physicians, or providers) want to summarize a note we had to inflect the verbs and change the person of a sentence
- For example:
- "The patient will follow up with me in 6 weeks. I have sent a precription for Zoloft to her pharmacy."
- Becomes:
- "The patient would follow up with the provider in 6 weeks. The provider sent a prescription to her pharmacy."

While this is a simple change it is a little complicated since there are so many rules surrounding the person (1st. 2nd. 3rd) and tense of a verb, and whether that verb is the main verb, an auxillary verb, a linking verb, a gerund, etc. To handle this need I decided between, finetuning the model (requires training data), training another model to correct our current models output (requires training data and latency cost), or just doing a rule based approach. I chose the latter and this is the result.
- Of note: the remainder of the startup's pipeline and goal is proprietary, but I am okay to share this specific part as an example of my work.

- If you want to use this, realize it is for a very specific use case, but if you'd like a more robust use case this is easily modifiable to handle changing to any tense and handling personhood of a sentence.
- Also you'd probably want to take the functions and modularize them in a script.