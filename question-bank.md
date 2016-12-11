* Assume you use temporal difference learning in conjunction with a random policy which choses actions randomly assuming a uniform distribution. Do you believe that the estimations obtained are a good measurement of the “goodness” of states, that tell an intelligent agent (assume the agent is smart!!) what states he/she should/should not visit? Give reasons for your answer
  * Not really; as we assume an intelligent agent will take actions that lead to good states and avoids bad states, an agent that uses the random policy might not recognize that a state is a good state if both good and bad states are successors of this state

* What role does the learning rate play in temporal difference learning; how does running temporal difference learning with low values differ from running it with high values ? 
  * It determines how quickly our current beliefs/estimations are updated based on new evidence.

* Assume you run temporal difference learning with high values of learning rate, what are the implications of doing that? 
  * is high the agent will more focus on its long term well-being, and will shy away from taking actions—although they lead to immediate rewards—that will lead to the medium and long term suffering of the agent.

* For an MDP (S, A, T, γ, R) if we only change the reward function R the optimal policy is guaranteed to remain the same.
  * False

* Value iteration is guaranteed to converge if the discount factor (γ) satisfies 0 < γ < 1. 
  * True

*  Policies found by value iteration are superior to policies found by policy iteration.
  * False

* Q-learning can learn the optimal Q-function Q∗ without ever executing the optimal policy.
  * True

*  If an MDP has a transition model T that assigns non-zero probability for all triples T (s, a, s′) then Q-learning will fail.
  * False

*  Q-learning will only learn the optimal q-values if actions are eventually selected according to the optimal policy.
  * False. As long as the policy used explores all the states (even a random policy will work), Q-learning will find the optimal q-values.

* In a deterministic MDP (i.e. one in which each state / action leads to a single deterministic next state), the Q-learning update with a learning rate of α = 1 will correctly learn the optimal q-values.
  * True. Remember that the learning rate is only there because we are trying to approximate a summation with a single sample. In a deterministic MDP where s′ is the single state that always follows when we take action a in state s, we have Q(s, a) = R(s, a, s′) + maxa′ Q(s′, a′), which is exactly the update we make.

* If an MDP has a transition model T that assigns non-zero probability for all triples T (s, a, s′) then Q-learning will fail.

* Inverse reinforcement learning (which makes helicopters fly by themselves) is primarily concerned with learning an expert’s transition model.
  * False. Inverse reinforcement learning focuses on learning an expert’s reward function. Experts and lousy agents alike all use the same transition model.

* For a two-player zero-sum game tree of depth 4 or greater, alpha-beta pruning must prune at least one node.
  * False. As a simple counterexample, if every player only has one legal move at each turn, then there will be no pruning.

*  In a Markov decision process with discount γ = 1, the difference in values for two adjacent states is bounded by the reward between them: |V (s) − V (s′)| ≤ maxa R(s, a, s′).
  * False. Let V (s′) = 0, and R(s, a, s′) = 0 ∀a, but there is an action a′ which takes s to the terminal state T and gives a reward 100. Thus V (s) ≥ 100, but the inequality above says that |V (s) − 0| ≤ 0.

* Value iteration and policy iteration must always converge to the same policy.
  * True and False (everyone wins). Both algorithms are guaranteed to converge to the optimal policy, so we accepted True. If there are multiple policies that are optimal (meaning they yield the same maximal values for every state), then the algorithms might diverge. Both value iteration and policy iteration will always lead to the same optimal values.

* A rational agent may choose to play a game of chance with negative expected payoff.
  * True. Money alone does not determine an agent’s utility function. The agent may realize some utility from playing the game.

* The perceptron algorithm always converges for inseparable data
  * False. It always converges for separable data.

* All MDPs can be solved using expectimax search.
  * MDPs with self loops lead to infinite expectimax trees. Unlike search problems, this issue cannot be addressed with a graph-search variant.

* Any rational agent’s preferences over outcomes can be summarized by a single real valued
utility function over those outcomes.
  * Any set of preferences which conform to the six constraints on rational preferences (orderability, transitivity, continuity, substitutability, monotonicity, decomposability) can be summarized by a single, real-valued function.

* Temporal difference learning of optimal utility values (U) requires knowledge of the transition probability tables (T).
  * Mostly True. Temporal difference learning is a model-less learning technique that requires only example state sequences to learn the utilities for a fixed policy. However, to derive the best policy from those utilities, which would be required to find the optimal utility values, we would need to compute
which of course includes a transition probability. The solution reads “mostly” true because the optimal utility values could be found without the transition probabilities if the agent were also supplied with the optimal policy. In practice, we could also estimate the transition probabilities from the training data (using maximum-likelihood estimates, for example), so they need not necessarily be known in advance. 

* Suppose an agent starts in state s and chooses action a: he observes a reward r and the action leads him to state s′. If the agent is using the SARSA algorithm, then to update its internal estimate of the expected reward associated to the state action pair (s, a) the agent doesn’t need to know which policy it is using to choose actions
  * 

* Q-learning is an on-policy algorithm.
  * 

* A small discount (close to 0) encourages shortsighted, greedy behavior.
  * True

* A large, negative living reward (≪ 0) encourages shortsighted, greedy behavior.
  * True

* A negative living reward can always expressed using a discount < 1.
  * False

* A discount < 1 can always be expressed as a negative living reward.
  * False

* F-learning converges to some fixed values/optimal Q-values
  * for deterministic state transitions. In deterministic MDPs, Q-learning always converges with the usual assumption of all state-actions being ex- perienced infinitely often, and it converges to the optimal values. Learning rate α = 1 is actually optimally efficient for the deterministic setting in the sense that Q-learning will converge in the fewest number of steps. In stochastic MDPs, Q-learning converges when the learning rate is appropriately reduced to 0. F-learning however does not converge: the value is updated to the most recent sample at each step, and so it changes whenever a different transition and reward are experienced. The policy π is a stochastic policy, so the transitions under this policy. This is true even if the MDP itself is deterministic, since the same action is not necessarily taken in the same state. F-learning never converges in this case since the F-value is updated to the most recent sample each time.

* If the only difference between two MDPs is the value of the discount factor then they must have the same optimal policy.
  * False. A counterexample suffices to show the statement is false. Consider an MDP with two sink states. Tran- sitioning into sink state A gives a reward of 1, transitioning into sink state B gives a reward of 10. All other transitions have zero rewards. Let A be one step North from the start state. Let B be two steps South from the start state. Assume actions always succeed. Then if the discount factor γ < 0.1 the optimal policy takes the agent one step North from the start state into A, if the discount factor γ > 0.1 the optimal policy takes the agent two steps South from the start state into B.

* When using features to represent the Q-function it is guaranteed that this feature- based Q-learning finds the same Q-function, Q∗, as would be found when using a tabular representation for the Q-function.
  * False. Whenever the optimal Q-function, Q∗, cannot be represented as a weighted combination of features, then the feature-based representation would not even have the expressiveness to find the optimal Q-function, Q∗.

* For an infinite horizon MDP with a finite number of states and actions and with a discount factor γ, with 0 < γ < 1, value iteration is guaranteed to converge.
  * True. Vk and Vk+1 are at most γk max |R| different so value iteration converges for any 0 ≤ γ < 1. See lecture slides for more details.

* When getting to act only for a finite number of steps in an MDP, the optimal policy is stationary. (A stationary policy is a policy that takes the same action in a given state, independent of at what time the agent is in that state.)
  * False. A simple counter-example suffices. Assume that the agent can reach a reward of $10 within 2 time steps or a reward of $1 withing one time step. If the horizon is less than two then the agent will aim for the latter. See lecture slides for more details.

* If you do not know your opponent's strategy, then your best response is never a pure strategy
  * False. 

* An optimal strategy is one that maximizes one's maximum potential gain.
  * False. Generally it is but not according minimax criteron

*  If you play against a player who chooses moves completely at random, then your optimal mixed strategy is the best you can do.
  * False. In this case your opponent is using a mixed strategy with equal probabilities, so you could counter with a better pure strategy.

* If the row player knows the column player's mixed strategy, then she can respond with a pure strategy for the best outcome. 
  * True

* Your opponent's knowledge that you are using some specific non-optimal strategy does not benefit him in the least.
  * False  In that case your opponent may be able to counter with a better pure strategy.

* Your opponent's knowledge that you are using your optimal strategy does not benefit him in the least. 
  * True

* A mixed strategy is one in which a player chooses different moves in a predetermined sequence.
  * False. Moves are chosen at random but with predetermined probabilities..

* An optimal strategy is one that minimizes the maximum damage the opponent can cause.
  * True.

* A saddle point is the largest number in its column and the smallest number in its row and implies the game is a mixed strategy game.
  * True

* Policy Evaluation not directly applicable in some situations where Temporal Difference learning is able to compute the utility function?
  * Policy Evaluation requires explicit knowledge or T and R, which TD learning does not.
