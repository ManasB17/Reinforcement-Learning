
# Lecture-1

1. **Google DeepMind RL Course by David Silver**: https://www.youtube.com/watch?v=2pWv7GOvuf0&list=PLqYmG7hTraZDM-OYHWgPebj2MfCFzFObQ&index=1
2. **Slides**: https://www.davidsilver.uk/wp-content/uploads/2020/03/intro_RL.pdf

>[! quote] fyi 
> 1. What makes reinforcement learning different form other machine learning paradigm?
>- There is no supervisor
 >- only thing we have is the feedback(positive or negative)
 >- reward is rare(sparse feedback) which comes after a long action sequence for eg. in game of chess you win after a full game
 
## Introduction

## Key Terms
| key-terms | Description |
| ---- | ---- |
| Agent | An entity that is being trained. |
| State and observation | A state is complete description of the environment.<br>An Observation $O$ is description of a state. |
| action space | A set of valid action in a given environment |
| Policy: | A rule used by agents to decide what action to take. It is denoted by $\mu$.<br><br>Or it may be stochastic, where it is usually denoted by $\pi$ |
| Trajectories | A trajectory $\tau$ is asequence of state and action in the world.<br><br>$\tau=(s_0, a_0, s_1, a_1, ...).$ |
| Reward Signal: | In general terms, a reward signal is a numerical reward that the environment sends to the agent after each action and state.<br><br>The reward signal tells the agent what are the good and what are the bad decisions. |
| Reward and Return | Reward $R$ is the feedback that is given to the agent when specific action is performed at a particular state and what the next state will be.<br><br>$r_t = R(s_t, a_t, s_{t+1})$ <br><br>The goal of the agent is to maximize the cumulative reward over a trajectory. We will notate such cases with $R(\tau)$ |
| Q-Function | A mathematical equation that estimates the expected reward for taking a specific action in a given state. |
| Value function: | A function of state or state action pair that estimates how good it is for an agent to be in a given state or perform an action in a given state.<br><br>It can also be thought as, function that is prediction of future reward. 

## Sequential Decision Making

Think of this concept as a global framework for certain common goal;
*Select action to maximize total future reward.*

*The action may have long term consequences* and *Reward may be delayed*

Hence RL Algorithms cannot be *Greedy*.
**Example**: 
- Financial Investment.
- Refueling of aircraft.
- Thinking of opponent move in games like chess.

## Reward $(R_{t})$
- $R_{t}$ is a scalar feedback signal
- Indicates how well the agent is doing at time stamp $t$.
- **Reward Hypothesis**: All goal can be described by maximizing cumulative reward.
**Example**:
Humanoid Robots: +ve reward for movement / -ve reward for falling
Game of chess: +ve reward for winning / -ve reward for losing
Atari Games: +/- ve reward for increasing / decreasing score

## History and State:

History is the sequence of observation, actions, rewards:
$H_{t}=A_1,O_1,R_1,...,A_t,O_t,R_t$
What happens next depends on history. which means *Agent selects based on the history*, *The environment selects observation/reward*

State is the information used to determine what happens next.
In RL there are different state definition of state;
1. Environment State:
2. Agent State:
3. Information State:
Formally, State is the function of history.
### Environment State $(S^{e}_{t})$

- Is environment's private representation.
- Info used in env to determine what happens next.

"*The environment state is not usually visible to the agent*"
Even if it is visible it may be irrelevant information.

### Agent State $(S^{a}_{t})$

- Is the agent's internal representation.
- What info the agent uses to pick next action.
- This is the information used by reinforcement learning algorithms.
- It can be any function of history.

### Information State(Markov State)

- Contains all useful info from the history.
- The state is Markov if and only if: $$P{[S_{t+1} | S_{t}]} = P[S_{t+1}| S_1,...,S_t]$$"*The future is independent of past given the present*"



# Lecture-2

## Markov Decision Processes
