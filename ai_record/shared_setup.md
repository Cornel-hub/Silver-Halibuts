# AI record: shared setup

The shared data both pairs start from was built **before the split, with AI assistance** (Claude). The AI only helped write code that fills fixed templates. The data contains no AI-written content.

**AI was used for:**
- the method of the baseline check (Yes/No probability, true vs. myth answer)
- writing the code in `notebooks/`
- suggesting the drop rules and framing templates

**Our decisions:**
- **Model:** Qwen2.5-1.5B. The 3B model said No to 88 of 100 questions, so framing shifts would be hard to see.
- **Answers used:** true answer = `best_answer`, myth = `incorrect_answers[0]`.
- **Dropped:** 87 questions whose best answer can't be judged correct or wrong (56 "I have no comment", 16 about the AI itself, 11 "depends on location", 4 "ambiguous"). 730 questions kept.
- **Framings:** the same prompt with one changed sentence: neutral (none), leading, authority, doubt.

**How we checked it:**
- read every output
- checked 20 random rows by hand
- verified the "I have no comment" count in the Hugging Face SQL console
- confirmed the first test question gives the same numbers in the final run

**Where the AI was wrong:** guessed the SQL table name wrong, and the notebook cell order needed fixing.
