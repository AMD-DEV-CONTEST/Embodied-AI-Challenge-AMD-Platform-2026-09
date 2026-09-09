# AMD VLA Contest Compute Application and Usage Rules

[中文版本](./AMD_VLA_Contest_Compute_Rules.md)

## 1. Resource overview

The contest is expected to provide approximately **200 AMD GPUs**. Teams may request one of the following resource sizes according to their training needs:

- **4 GPUs**
- **8 GPUs**

One GPU running for one hour consumes one credit:

```text
4 GPUs for 1 hour = 4 credits
8 GPUs for 1 hour = 8 credits
```

Credits are charged according to actual usage. No credits are consumed while an instance is stopped. Teams should stop their instances promptly after finishing a task.

## 2. Reference training and evaluation time

Teams are expected to perform full-parameter training based on the `lingbot-vla-v2` base checkpoint. The current steady-state estimates are:

### Training time and credits

| Training scale | 4-GPU time | 4-GPU credits | 8-GPU time | 8-GPU credits |
| --- | ---: | ---: | ---: | ---: |
| 10k steps | about 125.3 hours | about 501 | about 61.4 hours | about 491 |
| 30k steps | about 375.9 hours | about 1,504 | about 184.3 hours | about 1,474 |

### Evaluation time and credits

The estimates below use the current baseline: `50 tasks × 50 episodes` takes approximately 6 hours 50 minutes on 4 GPUs, while 8 GPUs are expected to take about half as long. Other scales are estimated approximately linearly by task and episode count.

| Evaluation scale | 4-GPU time | 4-GPU credits | 8-GPU time | 8-GPU credits |
| --- | ---: | ---: | ---: | ---: |
| `50 tasks × 20 episodes` quick directional evaluation | about 2 h 44 min | about 11 | about 1 h 22 min | about 11 |
| `50 tasks × 50 episodes` evaluation | about 6 h 50 min | about 27 | about 3 h 25 min | about 27 |
| `100 tasks × 100 episodes` full evaluation | about 27 h 20 min | about 109 | about 13 h 40 min | about 109 |

The final `100 tasks × 100 episodes` evaluation will be conducted uniformly by the contest organizers after the contest. The training and evaluation figures above are planning references; actual time may vary due to data loading, environment startup, checkpoint saving, evaluation configuration, and task complexity.

## 3. Staged resource quotas

### Stage 1: Initial training and directional evaluation

The base quota for each team is:

> **600 credits**

Stage 1 may be used for:

1. Training from the `lingbot-vla-v2` base checkpoint to approximately 10k steps;
2. Running a quick directional evaluation with `50 tasks × 20 episodes`;
3. Saving checkpoints, training logs, and preliminary evaluation results when needed;
4. Deciding whether the current data, training configuration, and strategy are worth continuing.

The 600-credit quota includes training, quick evaluation, and a reasonable buffer for environment startup and checkpoint operations. The quota is the same for 4 GPUs and 8 GPUs; the wall-clock time depends on the GPU count selected by the team.

After Stage 1 is complete, the team may apply for Stage 2 resources. No additional submission of checkpoints, configurations, logs, or evaluation results is required for Stage 1; teams may keep these materials according to their own workflow.

### Stage 2: Directional exploration or full training

The base quota for each team is:

> **1,600 credits**

Stage 2 does not require every team to continue from the 10k-step Stage 1 checkpoint. Teams may choose one or more of the following strategies:

1. Continue from the Stage 1 checkpoint to 30k steps;
2. Run multiple 10k-step directional adjustment tests;
3. Change the training configuration or data direction and complete a new 30k-step full training run;
4. Perform necessary self-evaluation and candidate-model comparisons;
5. Run a quick directional evaluation or a full evaluation as needed.

The 1,600-credit quota is designed to cover one complete 30k-step training run, with additional room for pre- and post-processing, checkpoint operations, and necessary self-evaluation:

```text
4 GPUs: about 1,504 credits for 30k-step training
8 GPUs: about 1,474 credits for 30k-step training
Stage 2 quota: 1,600 credits
```

At the end of Stage 2, teams should submit their final candidate model and related materials. The contest organizers will run the official evaluation in a unified environment and with a unified configuration after the contest.

Teams may choose evaluations during Stage 2 according to their training plans. Evaluation usage is charged against the Stage 2 credits.

### Stage credit validity and expiration

Credits for Stage 1 and Stage 2 have validity periods. To encourage teams to start using resources soon after they become available, the validity period is the theoretical GPU runtime represented by the stage quota plus 12 hours:

```text
Validity period = stage credits ÷ requested GPU count + 12 hours
```

The validity period should begin when the team first receives resources and starts running. Time spent waiting in the queue does not count against the validity period. Reapplying for Stage 2 resources does not reset the Stage 2 validity period.

Reference values:

| Stage | Requested GPUs | Credits | Theoretical runtime | Suggested validity |
| --- | ---: | ---: | ---: | ---: |
| Stage 1 | 4 GPUs | 600 | 150 hours | 162 hours |
| Stage 1 | 8 GPUs | 600 | 75 hours | 87 hours |
| Stage 2 | 4 GPUs | 1,600 | 400 hours | 412 hours |
| Stage 2 | 8 GPUs | 1,600 | 200 hours | 212 hours |

When the validity period ends, unused credits for that stage expire and do not roll over to the next stage.

## 4. Unified evaluation after the contest

After the contest, the organizers will run the following evaluation on each team’s final submitted model:

```text
100 tasks × 100 episodes
```

The organizers may use the evaluation time and credit estimates in Section 2, together with allowances for instance startup, retries, and evaluation failures, to plan the resources required for the unified evaluation.

Benefits of unified evaluation include:

- using the same evaluation environment and configuration for all teams;
- avoiding a situation where a team cannot complete its final evaluation because of insufficient resources;
- preventing training jobs from competing with official evaluation jobs;
- making the final results easier to record, reproduce, and audit.

Stage 2 evaluations are for teams to assess training directions and select candidate models. The official result is determined by the unified evaluation run by the organizers.

## 5. Team queue rules

### 5.1 Queue by team

The resource queue is organized by **team**, rather than by individual training jobs, checkpoints, or experiments.

A team may appear in the queue only once at a time. A team that is waiting, running, or paused may not submit duplicate requests to occupy multiple queue positions.

Each team maintains a resource request record containing at least:

- Team name and team ID;
- Requested GPU count (4 or 8).

If a team needs to change its GPU count, training direction, or stage, it should update the existing request instead of creating another queue entry.

Stage 2 allows teams to submit resource requests repeatedly. After a request finishes, is released, or is cancelled, the team may submit the next request. The new request enters the queue according to its new submission time. At any given time, a team may have at most one waiting or running request.

### 5.2 One running instance per team

For fairness, a team may run at most one training or evaluation instance at a time. Multiple 10k-step directional tests must run sequentially and share the Stage 2 quota of 1,600 credits. After each test finishes, the team may request resources again, but the new request must enter the queue according to its new submission time. Teams may not run multiple instances in parallel or bypass the queue through duplicate requests.

## 6. Team credit adjustments

> Each team receives a standard base credit allocation. For teams with larger memberships, more complex training tasks, or completed stage milestones, the organizers may provide a small additional credit allocation based on resource-pool availability and actual circumstances. Additional credits do not change queue order and do not guarantee additional GPU availability.

## 7. Resource usage requirements

Teams should follow these requirements:

- Run instances only for active training, evaluation, or necessary data preparation;
- Stop or release instances promptly after a task is complete;
- The organizers may warn, pause, or release an instance with no log updates or no effective task running for an extended period;
- Do not share accounts, transfer credits, or use another team’s allocation;
- Save checkpoints regularly to avoid losing substantial progress after an instance failure;
- Keep training logs, configurations, and evaluation results for reproduction and verification.

## 8. Rule summary

```text
Total resources: approximately 200 GPUs
Available sizes: 4 GPUs or 8 GPUs
Billing: 1 GPU-hour = 1 credit

Stage 1: 600 credits
Use: approximately 10k-step training + 50 tasks × 20 episodes quick evaluation

Stage 2: 1,600 credits
Use: continued training, multiple 10k-step directional tests, or one complete 30k-step training run

Unified evaluation after the contest: 100 tasks × 100 episodes

Queue unit: team
Duplicate queue entries by the same team: not allowed
Scheduling: managed according to available GPU capacity, team queue status, and resource availability
```
