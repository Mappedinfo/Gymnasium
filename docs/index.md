---
hide-toc: true
firstpage:
lastpage:
---

```{project-logo} _static/img/gymnasium-text.png
:alt: Gymnasium Logo
```

```{project-heading}
强化学习的API标准，拥有多样化的参考环境集合
```

```{figure} _static/videos/box2d/lunar_lander.gif
   :alt: Lunar Lander
   :width: 500
```

**Gymnasium是OpenAI的Gym库的维护分支。** 本文是官方文档的中文翻译。Gymnasium接口简单、符合Python风格，能够表示通用的强化学习问题，并为旧版Gym环境提供了[迁移指南](introduction/migration_guide)：

```{code-block} python
import gymnasium as gym

# Initialise the environment
env = gym.make("LunarLander-v3", render_mode="human")

# Reset the environment to generate the first observation
observation, info = env.reset(seed=42)
for _ in range(1000):
    # this is where you would insert your policy
    action = env.action_space.sample()

    # step (transition) through the environment with the action
    # receiving the next observation, reward and if the episode has terminated or truncated
    observation, reward, terminated, truncated, info = env.step(action)

    # If the episode has ended then we can reset to start a new episode
    if terminated or truncated:
        observation, info = env.reset()

env.close()
```

```{toctree}
:hidden:
:caption: Introduction

introduction/basic_usage
introduction/train_agent
introduction/create_custom_env
introduction/record_agent
introduction/speed_up_env
introduction/migration_guide
```

```{toctree}
:hidden:
:caption: API

api/env
api/registry
api/spaces
api/wrappers
api/vector
api/utils
api/functional
```

```{toctree}
:hidden:
:caption: Environments

environments/classic_control
environments/box2d
environments/toy_text
environments/mujoco
environments/atari
environments/third_party_environments
```

```{toctree}
:hidden:
:glob:
:caption: Tutorials

tutorials/**/index
tutorials/third-party-tutorials
```

```{toctree}
:hidden:
:caption: Development

Github <https://github.com/Farama-Foundation/Gymnasium>
Paper <https://arxiv.org/abs/2407.17032>
gymnasium_release_notes/index
gym_release_notes/index
Contribute to the Docs <https://github.com/Farama-Foundation/Gymnasium/blob/main/docs/README.md>
```