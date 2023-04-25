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

# Randomized actions

* Hardcore definition
