\hspace{0.15in} Then, using those Returns, MDPs estimates how "good" it is for the agent to be in a given state and/or to perform a given action. This is called a \textbf{value} and the function that estimates the value is called the \textbf{Value function}. It calculates values with respect to either the state, or the pair of (state, action), which are respectively called \textbf{State Value function}, and \textbf{(State) Action Value function}. Considering the fact that the agent will eventually choose its action in which leads to the highest value and the Value function literally provides that information, Value function is typically defined with respect to \textbf{Policy} $\pi$, the way the agent would behave at each state. Formally, a policy is a mapping from states to probability of selecting each possible actions; $\pi(a|s)$ means the probability of taking action $a$ if the current state is $s$. Then, the value, the expected return, at a state $s$ and following policy $\pi$, denoted as $v_\pi(s)$, is defined as:
\begin{equation}
    v_\pi(s) := \mathbb{E}_\pi[G_t|S_t=s]=\mathbb{E} \Big[\sum^{\infty}_{k=0}\gamma^k R_{t+k+1} \Big| S_t=a \Big] \quad\text{(by Eq (2))}
\end{equation}
Similarly, the value of taking action $a$ at a state $s$ under policy $\pi$, denoted as $q_\pi(s,a)$, is defined as:
\begin{equation}
    q_\pi(s,a):=\mathbb{E}_\pi[G_t|S_t=s, A_t=a]=\mathbb{E} \Big[\sum^{\infty}_{k=0}\gamma^k R_{t+k+1} \Big| S_t=a, A_t=a \Big] \quad\text{(by Eq (2))}
\end{equation}
Where $\mathbb{E}$ denoted as \textit{expected} value. Obviously, there are more than one way to estimate the value, which implies that one might be better than the others (Note that "better" means if the one gives greater expected return than other for every state). Then, there is always at least one value function that is better than or equal to all other policy, this is called \textbf{Optimal Value Function}, denoted as $v_*(s)$ or $q_*(s,a)$. And the policy defined with respect to the optimal value function is called \textbf{Optimal Policy}, denoted as $\pi_*$.
\begin{equation}
    v_{*}(s) := \max_\pi q_\pi(s,a)
\end{equation}

\begin{equation}
    q_{*}(s,a) := \max_\pi q_\pi(s,a)
\end{equation}

However, applying this equation to actual problems to find  has 


\begin{equation}
\begin{aligned}
    G_t&:=R_{t+1}+\gamma R_{t+2}+\gamma^2R_{t+3}\cdots\\
    &=R_{t+1}+\gamma (R_{t+2}+\gamma R_{t+3}\cdots)\\
    &=R_{t+1}+\gamma G_{t+1}
\end{aligned}
\end{equation}