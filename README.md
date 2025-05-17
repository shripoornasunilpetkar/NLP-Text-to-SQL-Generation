 Project Description: SQL Generation from Natural Language using T5
This project fine-tunes a T5-large transformer model to convert natural language questions into SQL queries using structured database schema information. The model was trained and evaluated on the Spider and SQL Create Context datasets.

🛠️ Preprocessing & Input Construction
Schema and questions were normalized and combined into input strings like:
translate to SQL: <question> [SEP] <schema>

The tokenizer from transformers was used to convert these strings into model-ready format.

Custom functions were written to extract schema details from tables.json.

🤖 Model Training
Model: T5ForConditionalGeneration (pretrained t5-large)

Dataset: Spider dataset (xlangai/spider), split 80/20 into training and validation sets.

Training Arguments:

3 epochs

Batch size = 4

Learning rate = 2e-5

Evaluated every 500 steps

Framework: Hugging Face Trainer

🧪 Evaluation
Model predictions were generated for sample queries using unseen schemas.

SQL output was compared against manually written ground truth queries.

Accuracy Calculation: A custom exact-match function compared predicted SQL queries to reference queries.

Final Accuracy Achieved: ~90% on 10 test cases

✅ Outcome
The fine-tuned model accurately translated natural language to SQL with structured input.

It generalized well to both seen and unseen schemas, demonstrating strong SQL generation capabilities.

