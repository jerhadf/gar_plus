# gar_plus

This is an implementation of generation-augmented retrieval (GAR), an older ML method (not RAG) to improve the performance of retrieval-based models. It works by generating additional relevant context for a given input, which is then used to retrieve more accurate and relevant results. This is particularly useful in tasks such as question answering, where the quality of the retrieved documents can significantly impact the final answer. Here, I implement a version of GAR that uses reinforcement learning on top to perform question answering (QA) across different domains. I also include fine-tuning and evaluations scripts.


To fine tune a model, run
```
python fine_tune.py
  --model_name_or_path <model_name> \
  --do_train \
  --do_eval \
  --do_predict \
  --train_file <train_filepath> \
  --validation_file <validation_filepath> \
  --test_file <test_filepath> \
  --output_dir <path_to_output_dir> \
  --overwrite_output_dir \
  --text_column "question" \
  --summary_column "augment" \
  --predict_with_generate \
  --learning_rate 0.00005 \
  --num_train_epochs 15 \
  --sc_scaling 0.98 \
```
