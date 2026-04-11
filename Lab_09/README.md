1) Benign mean - not dangerous/ kind or gentle
  
2) What is Finetuning?
Ans) Think of it in two stages:
Stage 1 — Pre-training (already done by someone else)
BERT was trained by Google on huge amounts of text (Wikipedia + BookCorpus — billions of words). During this, it learned:

Grammar and language structure
Word meanings and context
General world knowledge

This takes weeks and millions of dollars of compute. You don't do this yourself.
Stage 2 — Finetuning (what YOU do)
You take that already-smart BERT and train it a little more on YOUR specific task and YOUR specific data.
In your case:

Your task = "Is this prompt malicious or benign?"
Your data = the prompt injection dataset (labeled 0 or 1)
eg - training of employees after getting hired

3) The Full Pipeline — What Happens Backstage for Part 1
Ans) Dataset (HuggingFace)
        ↓
  Load into pandas DataFrame
        ↓
  Filter label == 1  →  get ~malicious rows
        ↓
  .sample(100)  →  pick 100 random rows
        ↓
  Loop through each prompt (1 to 100)
        ↓
  Send prompt → LLM 1 API → get response
  Send prompt → LLM 2 API → get response
        ↓
  Run verdict() function on each response
        ↓
  Store everything in a DataFrame
        ↓
  Analyze + Plot charts
eg - Pizza Quality Control Analogy
4) 


