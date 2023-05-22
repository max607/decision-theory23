<!-- Decision Theory -->

[TOC]

# Preliminary

## Orga

* TA $\rightarrow$ 23.05., CJ $\rightarrow$ 05.06.
* We can have access to old videos (recorded Zoom lecture)
* Monday 10:05 -- 11:45
* Tuesday 17:05 -- 19:45 + break
* Timeseries may be interesting

## Learning objectives

* Learn to design and solve decision problems
* Get an outside perspective on / widen the horizons of "common statistics and machine learning"
  * Frame it into decision problems
  * Reflect on the notion of uncertainty

# Introduction

* Choose an action out of many \
  $\rightarrow$ Consequences (Utility / loss, depend on an unknown nature) \
  $\rightarrow$ Optimize
* Unknown $\rightarrow$ uncertainty (statistics yay)
  * Also data
  * And losses
* Interdisciplinary importance
  * Rational choice theory
  * Uncertainty in AI, expert systems, decision support systems
  * Decision theory

## Rational choice

* Macro-level by aggregation of individual actions
* Goal-oriented rational actor
* Game theory
* In sociology: e.g., Coleman: Foundations of Social Theory
* Modern: bounded rationality $\rightarrow$ behavioural economics (Kahneman & Tversky 1979, Nobel prize 2002)
* Munich Center for Mathematical Philosophy (MCMP)

## Uncertainty in AI

* Expert systems
* Uncertainty in AI (based on name of a group)
* E.g., portfolio management
* How would an expert behave? Model that
* Make expert knowledge widely available
* Paper on autonomous driving systems (ADS)
* Two types of uncertainty
  * Parameter uncertainty - epistemic uncertainty
  * Prediction uncertainty
* MYCIN $\rightarrow$ methodological consequences
  * Uncertainty factors
  * Comparative probabilities
  * $A \cup B$ is likely, but we don't know which
  * $\mathbb{P}(A \cup B)$ high
  * $\mathbb{P}(A) + \mathbb{P}(B):$ where is the mass?
  * Probabilities are based on sets $\rightarrow$ move to fuzzy sets <!-- TODO Konstruktivismus? -->

# Missed

$\rightarrow$ slides 34 -- 79
* What this is: $(\mathbb{A}, \Theta, u(\cdot))$
* Type I vs type II uncertainty

## Semantics of the data-free decision problem

* $(\mathbb{A}, \Theta, u(\cdot))$
* $\mathbb{A}$ is known
* $\Theta$ is known (closed world assumption)
* Consequences $c(\alpha, \vartheta), \alpha \in \mathbb{A}, \vartheta \in \Theta$ are unique
* ...
* "Marxist Group" -- Wer war das?
* Decisions theory to handle non-linearity of money
  * 1000€ for an average person vs. football player
* Difficult: act-state independence (e.g., more rockets, war)

# Examples

* Hiking
* Lotto
* Cake
* Investment
* Production planing
  * $a = \left( \begin{matrix} a(1) \\
                               \vdots \\
                               a(q) \\
                \end{matrix} \right)$
  * $a(\ell)$: Production of $a(\ell)$ units of good $\ell, \ell = 1, ..., q$
  * $u: \mathbb{A} \times \Theta \rightarrow \mathbb{R}$
  * $(\alpha, \vartheta) \mapsto u(\alpha, \vartheta)$
* TODO slides 96 -- 98
* Slide 103 $\rightarrow$ nice tutorial paper

# Randomized actions - mixed extension

* Hardcore definition
* Utility under fixed state-of-nature is the expectancy w.r.t. the actions
* $\mathbb{P}(a) = \delta(a_\ell) \rightarrow$ pure action
* Discussion of randomized actions $\rightarrow$ next Monday (a.k.a. problem sheet)

# Deciding with data

* Observation of random experiment (sampling, asking an expert, ...)
* Decision functions of sample
  * $d: \mathcal{X} \rightarrow \mathbb{A}$
  * $x \mapsto d(x)$ \
    $\rightarrow$ evaluate decision functions
  * $p_{\vartheta_1}(\{x_1\}) = p(\{x_1\} || \vartheta_1)$
  * $||:$ frequentist: $\vartheta_1$ is not random!
  * TODO statistics and constructivism
* Now: randomized actions, but the randomness is from sampling given true data
  * Fix strategy before seeing the data. E.g., tempting in the case of searching for new medicine
  * $U(d^+, \vartheta_j) := \sum_{l = 1}^s u(d^+(x_\ell), \vartheta_j)\ p_{\vartheta_j}(\{x_\ell\})$
* Data-based decision problem
  * $((\mathbb{A}, \Theta, u(a)), (\mathcal{X}, \sigma(\mathcal{X}), p_\vartheta))$
  * $a \in \mathbb{A}, \vartheta \in \Theta$
  * Need $\vartheta$ two times: for the utility function and for the probability for actions
* Common to use loss - so risk notation $\rightarrow$ similar to machine learning
* Data-free problem can be induced by data $\rightarrow$ just a special case
* Formally every decision problem can be written as a data-free decision problem

# Re-framing estimation and testing

* Estimation part on Monday
* Testing part on Tuesday
* From slide 141

# Decision rules and principles

* Rules give optimal decisions, but only under certain conditions
* Principles: only avoid obviously dumb actions
  * One curve is completely under another $\rightarrow$ principle
  * Curves overlap $\rightarrow$ aggregate by rule (loose information, make a lot of assumptions)
* Meta rules: interesting paper, decision rules for decision rules <!-- TODO -->

## Order theory

* Is about $<, >, \leq, \geq, ...$
* Easy: $\left( \begin{matrix} 1 \\ 2 \\ \end{matrix} \right) \overset{?}{<} \left( \begin{matrix} 2 \\ 3 \\ \end{matrix} \right) \rightarrow$ principle
* Problem: $\left( \begin{matrix} 1 \\ 2 \\ \end{matrix} \right) \overset{?}{<} \left( \begin{matrix} 2 \\ 1 \\ \end{matrix} \right) \rightarrow$ rule
* Pareto front
* Dominance: not reasonable to choose an inadmissible action
* Admissible: action, which is not strictly dominated by any action
* Admissibility of a certain action can be lost when moving to mixed extension
* Mixed extension makes Pareto front smooth (Pareto front: smallest set of admissible actions, relation to complete cases)
* Randomization: decision based on information-less data

```r
# Example Pareto front
plot(c(7, 6, 6, 4, 1, 2, 6, 6.5), c(3, 5, 5, 4, 6, 5, 4, 3.5))
lines(c(1, 6, 6.5, 7), c(6, 5, 3.5, 3))
```

## Complete classes

* $\forall a \in \mathbb{A} \setminus \mathbb{C}\ \exists a^* \in \mathbb{C}: a^* \succ a$
* Set $\mathbb{C}$

## Optimality criterion

* Lexicographic order: Like in a dictionary (aa, ab, ba, ...)
  * q-step optimality criterion $\rightarrow$ makes an odering, rule: take the best
<!-- slide 181 -->

## Exercise 2

### Problem 3

<!-- TODO What is a sigma space? -->

| decision theory           | estimation theory                            | testing theory                                                                                                                     |
|---------------------------|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| state space $\Theta$      | parameter space                              | $\{H_0, H_1\}$                                                                                                                     |
| state $\vartheta$         | true parameter                               | $H_i$                                                                                                                              |
| action space $\mathbb{A}$ | all possible estimates                       | (don't) reject $H_0$                                                                                                               |
| loss function             | negative log-likelihood, distance measure    | decide for a vier-Felder-Tafel                                                                                                     |
| **data based**            |                                              |                                                                                                                                    |
| decision function         | estimator, $\hat{\vartheta}(Z_1, ..., Z_n)$  | $d(T(\bm{Z}) = t) = \begin{cases} H_1,& \text{if } t \in \mathbb{C}(q_{\Upsilon_0}, \alpha) \\ H_0,& \text{otherwise} \end{cases}$ |
| risk function             | see below                                    | $\mathcal{R}(d, H_i) = \mathbb{E}_X(\mathcal{L}(d(X),H_i))$                                                                               |
| information structure     | $\mathcal{X}$, $\sigma$-field, $p_\vartheta$ |                                                                                                                                    |

* $Z_i \overset{iid}{\sim} N(\mu, \sigma^2)$
* $\mathcal{X} = \mathbb{R}^n$
* $p_\vartheta$: How are the data distributed? $\rightarrow p_\vartheta^{\otimes n} \overset{ind}{=} \prod_{i = 1}^n q_\vartheta(Z_i = z_i)$
* risk function: $f(\text{decision function}, \text{true parameter})$
* $\mathcal{R}(\hat{\vartheta}(Z_1, ..., Z_n), \vartheta) = \mathbb{E}_{p_\vartheta}(\mathcal{L}(\hat{\vartheta}(Z_1, ..., Z_n), \vartheta))= \text{MSE}_\vartheta(\hat{\vartheta}(Z_1, ..., Z_n), \vartheta) \overset{unbiased}{=} \mathbb{V}_{p_\vartheta}(\hat{\vartheta}(Z_1, ..., Z_n))$
* Uniformly optimal procedure?
  * $\mathcal{R}(\hat{\vartheta}^*(Z_1, ..., Z_n), \vartheta) \le \mathcal{R}(\hat{\vartheta}(Z_1, ..., Z_n), \vartheta), \forall \hat\vartheta \in \mathcal{D}, \vartheta \in \Theta$
  * Impossible, e.g., for $\text{MSE}$: choose $\hat\vartheta \equiv \vartheta, \forall \vartheta \in \Theta$

### Problem 6

```r
plot(c(7, 6, 6, 4, 1, 2, 6, 6.5), c(3, 5, 5, 4, 6, 5, 4, 3.5))
points(c(6.5, 4.6), c(4, 4.1), col = "red")
lines(c(1, 6, 6.5, 7), c(6, 5, 4, 3))
lines(c(1, 2, 4, 7), c(6, 5, 4, 3))
```

