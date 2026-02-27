# 📊 Reproducing DQN, PPO, and SAC in AgarCL

This repository provides all code, configurations, and scripts to reproduce every experiment in **The Cell Must Go On**. Below you’ll find a one-to-one mapping of each experiment to its exact launch command (DQN, PPO, SAC), using the best hyperparameters from our tuning tables.

---

## 🐍 Environment Setup

\*Same as before: Compute Canada modules, `pip install -r requirements.txt`, `pip install -e .`

---
## To generate the results in the paper The Cell Must Go On: Agar.io for Continual Reinforcement Learning, see commands below:  
### 1. Episodic Mini-Games (1–6)

Each mini-game has its own config `task_configs/mini_game_{i}.json`. Use the following “best hyperparameter” commands:

<details>
<summary><strong>Mini-Game 1</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-4 \
  --batch_accumulator="mean" \
  --tau=5e-5 \
  --minibatch_size=64 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg1"\
  --mini_game="task_configs/mini_game_1.json"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=1e-4 \
  --epochs=15 \
  --max-grad-norm=0.7 \
  --entropy-coef=0.01 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --outdir="$RESULTS/PPO_mg1"\
  --mini_game="task_configs/mini_game_1.json"
# SAC
python SAC_full_action_set.py \
  --reward="min_max" \
  --lr=3e-5 \
  --soft-update-tau=0.001 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.7 \
  --seed=3..12 \
  --outdir="$RESULTS/SAC_mg1"\
  --mini_game="task_configs/mini_game_1.json"
```

</details>

<details>
<summary><strong>Mini-Game 2</strong></summary>

```bash
# DQN
python DQN_full_action_set.py\
  --lr=3e-4 \
  --batch_accumulator="sum" \
  --tau=5e-5 \
  --minibatch_size=32 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg2"\
   --mini_game="task_configs/mini_game_2.json"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=1e-5 \
  --epochs=10 \
  --max-grad-norm=0.7 \
  --entropy-coef=0.01 \
  --clip-eps=0.2 \
  --seed=3..12 \
  --outdir="$RESULTS/PPO_mg2"\
  --mini_game="task_configs/mini_game_2.json"

# SAC
python  SAC_full_action_set.py \
  --reward="min_max" \
  --lr=3e-5 \
  --soft-update-tau=0.001 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.7 \
  --seed=3..12 I am running a few minutes late; my previous meeting is running over.
  --outdir="$RESULTS/SAC_mg2"\
  --mini_game="task_configs/mini_game_2.json"
```

</details>

<details>
<summary><strong>Mini-Game 3</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-4 \
  --batch_accumulator="mean" \
  --tau=5e-5 \
  --minibatch_size=32 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg3"\
  --mini_game="task_configs/mini_game_3.json"
# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=1e-5 \
  --epochs=10 \
  --max-grad-norm=0.9 \
  --entropy-coef=0.01 \
  --clip-eps=0.2 \
  --seed=3..12 \
  --outdir="$RESULTS/PPO_mg3"\
  --mini_game="task_configs/mini_game_3.json"
# SAC
python SAC_full_action_set.py \
  --reward="min_max" \
  --lr=1e-4 \
  --soft-update-tau=0.01 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.7 \
  --seed=3..12 \
  --outdir="$RESULTS/SAC_mg3"\
  --mini_game="task_configs/mini_game_3.json"
```

</details>

<details>
<summary><strong>Mini-Game 4</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=3e-4 \
  --batch_accumulator="sum" \
  --tau=1e-2 \
  --minibatch_size=32 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg4"\
   --mini_game="task_configs/mini_game_4.json"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=1e-5 \
  --epochs=15 \
  --max-grad-norm=0.9 \
  --entropy-coef=0.05 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --outdir="$RESULTS/PPO_mg4"\
  --mini_game="task_configs/mini_game_4.json"
# SAC
python  SAC_full_action_set.py \
  --reward="min_max" \
  --lr=1e-5 \
  --soft-update-tau=0.001 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.7 \
  --seed=3..12 \
  --outdir="$RESULTS/SAC_mg4"\
  --mini_game="task_configs/mini_game_4.json"
```

</details>

<details>
<summary><strong>Mini-Game 5</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-5 \
  --batch_accumulator="mean" \
  --tau=1e-2 \
  --minibatch_size=64 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg5"\
  --mini_game="task_configs/mini_game_5.json"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=1e-4 \
  --epochs=10 \
  --max-grad-norm=0.7 \
  --entropy-coef=0.01 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --outdir="$RESULTS/PPO_mg5"\
  --mini_game="task_configs/mini_game_5.json"

# SAC
python  SAC_full_action_set.py \
  --reward="min_max" \
  --lr=1e-5 \
  --soft-update-tau=0.001 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.7 \
  --seed=3..12 \
  --outdir="$RESULTS/SAC_mg5"\
  --mini_game="task_configs/mini_game_5.json"
```

</details>

<details>
<summary><strong>Mini-Game 6</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-5 \
  --batch_accumulator="mean" \
  --tau=1e-2 \
  --minibatch_size=64 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg6"\
  --mini_game="task_configs/mini_game_6.json"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=3e-5 \
  --epochs=10 \
  --max-grad-norm=0.5 \
  --entropy-coef=0.05 \
  --clip-eps=0.2 \
  --seed=3..12 \
  --outdir="$RESULTS/PPO_mg6"\
  --mini_game="task_configs/mini_game_6.json"

# SAC
python  SAC_full_action_set.py \
  --reward="min_max" \
  --lr=1e-4 \
  --soft-update-tau=0.001 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.5 \
  --seed=3..12 \
  --outdir="$RESULTS/SAC_mg6"\
  --mini_game="task_configs/mini_game_6.json"
```

</details>

### 2. Continual (Non-episodic) Mini-Games (1–6)

Add `--env_type=1` to run the continual setting with mass difference as reward. Use the same best hyperparameters mentioned in the paper, pointing to each JSON:

<details>
<summary><strong>Continual Mini-Game 1</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-4 \
  --batch_accumulator="mean" \
  --tau=5e-5 \
  --minibatch_size=64 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_1.json" \
  --outdir="$RESULTS/DQN_cont_mg1"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="variance_norm" \
  --lr=1e-4 \
  --epochs=4 \
  --max-grad-norm=0.5 \
  --entropy-coef=0.005 \
  --clip-eps=0.2 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_1.json" \
  --outdir="$RESULTS/PPO_cont_mg1"

# SAC
python  SAC_full_action_set.py \
  --reward="variance_norm" \
  --lr=3e-5 \
  --soft-update-tau=0.001 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.5 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_1.json" \
  --outdir="$RESULTS/SAC_cont_mg1"
```

</details>

<details>
<summary><strong>Continual Mini-Game 2</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=3e-4 \
  --batch_accumulator="sum" \
  --tau=1e-2 \
  --minibatch_size=32 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_2.json" \
  --outdir="$RESULTS/DQN_cont_mg2"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="variance_norm" \
  --lr=1e-5 \
  --epochs=10 \
  --max-grad-norm=0.5 \
  --entropy-coef=0.05 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_2.json" \
  --outdir="$RESULTS/PPO_cont_mg2"

# SAC
python  SAC_full_action_set.py \
  --reward="variance_norm" \
  --lr=3e-5 \
  --soft-update-tau=0.005 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.7 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_2.json" \
  --outdir="$RESULTS/SAC_cont_mg2"
```

</details>


<details>
<summary><strong>Continual Mini-Game 3</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-4 \
  --batch_accumulator="mean" \
  --tau=5e-5 \
  --minibatch_size=32 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_3.json" \
  --outdir="$RESULTS/DQN_cont_mg3"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="still_running" \
  --lr=1e-4 \
  --epochs=4 \
  --max-grad-norm=0.5 \
  --entropy-coef=0.01 \
  --clip-eps=0.3 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_3.json" \
  --outdir="$RESULTS/PPO_cont_mg3"

# SAC
python  SAC_full_action_set.py \
  --reward="variance_norm" \
  --lr=1e-4 \
  --soft-update-tau=0.01 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.5 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_3.json" \
  --outdir="$RESULTS/SAC_cont_mg3"
```

</details>

<details>
<summary><strong>Continual Mini-Game 4</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-4 \
  --batch_accumulator="sum" \
  --tau=5e-5 \
  --minibatch_size=32 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_4.json" \
  --outdir="$RESULTS/DQN_cont_mg4"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="variance_norm" \
  --lr=1e-5 \
  --epochs=10 \
  --max-grad-norm=0.5 \
  --entropy-coef=0.1 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_4.json" \
  --outdir="$RESULTS/PPO_cont_mg4"

# SAC
python  SAC_full_action_set.py \
  --reward="variance_norm" \
  --lr=1e-5 \
  --soft-update-tau=0.01 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.5 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_4.json" \
  --outdir="$RESULTS/SAC_cont_mg4"
```

</details>

<details>
<summary><strong>Continual Mini-Game 5</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-5 \
  --batch_accumulator="mean" \
  --tau=1e-2 \
  --minibatch_size=64 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_5.json" \
  --outdir="$RESULTS/DQN_cont_mg5"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=3e-5 \
  --epochs=10 \
  --max-grad-norm=0.7 \
  --entropy-coef=0.05 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_5.json" \
  --outdir="$RESULTS/PPO_cont_mg5"

# SAC
python  SAC_full_action_set.py \
  --reward="variance_norm" \
  --lr=1e-5 \
  --soft-update-tau=0.001 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.7 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_5.json" \
  --outdir="$RESULTS/SAC_cont_mg5"
```

</details>

<details>
<summary><strong>Continual Mini-Game 6</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=3e-4 \
  --batch_accumulator="mean" \
  --tau=1e-2 \
  --minibatch_size=32 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_6.json" \
  --outdir="$RESULTS/DQN_cont_mg6"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=3e-5 \
  --epochs=10 \
  --max-grad-norm=0.5 \
  --entropy-coef=0.05 \
  --clip-eps=0.2 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_6.json" \
  --outdir="$RESULTS/PPO_cont_mg6"

# SAC
python  SAC_full_action_set.py \
  --reward="variance_norm" \
  --lr=3e-5 \
  --soft-update-tau=0.005 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.9 \
  --seed=3..12 \
  --env_type=1 \
  --mini_game="task_configs/mini_game_6.json" \
  --outdir="$RESULTS/SAC_cont_mg6"
```

</details>

---
### 3. Other-Agent Interaction (Modes 7 & 8)

Run the best episodic hyperparameters on:

* **Mode 7 Small-Sparse** (200×200, 200 pellets)
* **Mode 8 Normal-Dense** (350×350, 500 pellets)

<details>
<summary><strong>Mode 7: Small-Sparse</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=1e-5 \
  --batch_accumulator="mean" \
  --tau=5e-2 \
  --minibatch_size=32 \
  --seed=3..12 \
  --mini_game="task_configs/mini_game_7.json" \
  --outdir="$RESULTS/DQN_mode7"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="min_max" \
  --lr=3e-5 \
  --epochs=10 \
  --max-grad-norm=0.5 \
  --entropy-coef=0.05 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --mini_game="task_configs/mini_game_7.json" \
  --outdir="$RESULTS/PPO_mode7"

# SAC
python  SAC_full_action_set.py \
  --reward="min_max" \
  --lr=1e-4 \
  --soft-update-tau=1e-2 \
  --temperature-lr=1e-4 \
  --max-grad-norm=0.9 \
  --seed=3..12 \
  --mini_game="task_configs/mini_game_7.json" \
  --outdir="$RESULTS/SAC_mode7"
```

</details>

<details>
<summary><strong>Mode 8: Normal-Dense</strong></summary>

```bash
# DQN
python DQN_full_action_set.py \
  --lr=3e-4 \
  --batch_accumulator="mean" \
  --tau=1e-2 \
  --minibatch_size=64 \
  --seed=3..12 \
  --mini_game="task_configs/mini_game_8.json" \
  --outdir="$RESULTS/DQN_mode8"

# PPO
python PPO_multi_heads_full_action.py \
  --reward="variance_norm" \
  --lr=1e-5 \
  --epochs=10 \
  --max-grad-norm=0.9 \
  --entropy-coef=0.1 \
  --clip-eps=0.4 \
  --seed=3..12 \
  --mini_game="task_configs/mini_game_8.json" \
  --outdir="$RESULTS/PPO_mode8"

# SAC
python  SAC_full_action_set.py \
  --reward="variance_norm" \
  --lr=1e-4 \
  --soft-update-tau=1e-2 \
  --temperature-lr=1e-5 \
  --max-grad-norm=0.7 \
  --seed=3..12 \
  --mini_game="task_configs/mini_game_8.json" \
  --outdir="$RESULTS/SAC_mode8"
```

</details>

### Cross Hyperparameter evaluation

Simply, you will use the hyperparameter of mini-game 1,2, and 3 in Mini-Game config 1: 

```bash
python DQN_full_action_set.py \
  --lr=1e-4 \
  --batch_accumulator="mean" \
  --tau=5e-5 \
  --minibatch_size=64 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg1" \
  --mini_game="task_configs/mini_game_1.json"
  
python DQN_full_action_set.py \
--lr=3e-4 \
--batch_accumulator="sum" \
--tau=5e-5 \
--minibatch_size=32 \
--seed=3..12 \
--outdir="$RESULTS/DQN_mg1_hy2"
--mini_game="task_configs/mini_game_1.json"

python DQN_full_action_set.py \
  --lr=1e-4 \
  --batch_accumulator="mean" \
  --tau=5e-5 \
  --minibatch_size=32 \
  --seed=3..12 \
  --outdir="$RESULTS/DQN_mg3_hy2"
--mini_game="task_configs/mini_game_1.json"
```
And so on.

### 4. Full-Game Evaluation

Use Mini-Game 4’s best hyperparameters on `full_game_config.json`:

```bash
python PPO_multi_heads_full_action.py \
  --config=full_game_config.json \
  --reward="min_max" --lr=1e-5 --epochs=15 \
  --max-grad-norm=0.7 --entropy-coef=0.05 \
  --clip-eps=0.4 --value-func-coef=0.9 \
  --seed=3..12 \
  --mini_game="full_game_config.json" \
  --outdir="$RESULTS/PPO_full_game"
```

(and similarly for DQN & SAC)

---


---

## ✅ Reproducibility Checklist

* [x] One-to-one mapping: experiment ↔️ command
* [x] All configs & scripts included
* [x] Hyperparameters embedded directly in commands

---

If anything is missing or unclear, please open an issue! Feel free to propose PRs to fill gaps.
