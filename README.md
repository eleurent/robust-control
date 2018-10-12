## Abstract

This work studies the design of safe control policies for large-scale non-linear systems operating in uncertain environments. In such a case, the robust control framework is a principled approach to safety that aims to maximize the worst-case performance of a system. However, the resulting optimization problem is generally intractable for non-linear systems with continuous states. To overcome this issue, we introduce two tractable methods that are based either on sampling or on a conservative approximation of the robust objective. The proposed approaches are applied to the problem of autonomous driving.

## Video

<p align="center"><iframe width="560" height="315" src="https://www.youtube.com/embed/9WvO_dm8khI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe></p>

## Reproduce the experiments

### Install requirements

* The environment: [highway-env](https://github.com/eleurent/highway-env)
* The agents: [rl-agents](https://github.com/eleurent/rl-agents)

### Run the benchmark

```shell
cd <path-to-rl-agents>/scripts/
python experiments.py benchmark configs/RoundaboutEnv/benchmark_robust_control.json \
                      --test --episodes=100 --processes=4
```

The following agents will be evaluated:
```json
{
    "environments": [
        "configs/RoundaboutEnv/env.json"
    ],
    "agents": [
        "configs/RoundaboutEnv/agents/DeterministicPlannerAgent/baseline.json",
        "configs/RoundaboutEnv/agents/DeterministicPlannerAgent/assume_random_route.json",
        "configs/RoundaboutEnv/agents/DiscreteRobustPlannerAgent/routes.json",
        "configs/RoundaboutEnv/agents/DeterministicPlannerAgent/assume_random_behaviour.json",
        "configs/RoundaboutEnv/agents/IntervalRobustPlannerAgent/behaviours.json"
    ]
}
```
