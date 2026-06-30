# demographic_parity

# Single file, unweighted only
python dpopt.py model_T5_D3.json \
  --sensitive_features 8 9 --epsilon 0.1 --details bounds.csv

# Single file, both unweighted and weighted
python dpopt.py model_T5_D3.json \
  --sensitive_features 8 9 --epsilon 0.1 \
  --details bounds.csv --dataset adult.csv

# Batch folder
python dpopt.py --folder ./models \
  --sensitive_features 8 9 --epsilon 0.1 \
  --details bounds.csv --dataset adult.csv \
  --out_dir ./results --max_seconds_per_file 1800

# Preview group counts (no solver)
python dpopt.py --preview_groups model_T5_D3.json \
  --details bounds.csv --max_combo_size 2 --out_dir ./results
