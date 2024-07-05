Look for a solution for a problem.
AI tries to get from a initial position to some sort of goals by taking some sequence of actions.
## Terminology
### agent
entity that perceives its environment and acts upon that environment.
### state
a configuration of the agent and its environment.
**initial state** is the state in which the agent begins.
### actions
choices that can be made in a state.
$ACTIONS\,(s)$ returns the set of actions that can be executed in state $s$.
### transition model
a description of what state results from performing any applicable action in any state.
$RESULT\, (s,\,a)$ returns the state resulting from performing action $a$ in state $s$.
### state space
the set of all states reachable from the initial state by any sequence of actions.
### goal test
way to determine whether a given state is a goal state.
### path cost
numerical cost associated with a given path.
### solution
a sequence of actions that leads from the initial state to a goal state.
### optimal solution
a solution that has the lowest path cost among solutions.
### node
a data structure that keeps track of
- a state
- a parent (node that generated this node)
- an action (action applied to parent to get node)
- a path cost (from initial state to node)
## Approach
- start with a frontier that contains the initial state.
- start with an empty explored set.
- Repeat:
	- If the frontier is empty, then no solution.
	- Remove a node from the frontier.
	- If the node contains goal state, return the solution.
	- Add the node to the explore set.
	- Expand node, add resulting nodes to the frontier if they are not already in the frontier or the explored set.

**Depth First Search** (DFS) : **Stack**
**Breadth First Search** (BFS) : **Queue**

### uninformed search
search strategy that uses no problem-specific knowledge.
### informed search
search strategy that uses problem-specific knowledge to find solutions more efficiently.

### Minimax
- Given a state $s$ :
	- $MAX$ picks action $a$ in $ACTIONS\,(s)$ that produces highest value of $MIN\,(RESULT(s,\,a))$ 
	- $MIN$ picks action $a$ in $ACTIONS(s)$ that produces smallest value of $MAX(RESULT(s, a))$
- MAX
```
def MAX(state):
	if TERMINAL(state):
		return UTILITY(state)
	v = NEGATIVE INFINITY
	for action in ACTIONS(state):
		return max(v, MIN(RESULT(state, action)))
	return v
```
- MIN
```
def MIN(state):
	if TEMINAL(state):
		return UTILITY(state)
	v = POSITIVE INFINITY
	for action in ACTIONS(state):
		return min(v, MAX(state, action))
	return v
```
