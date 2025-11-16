---
title: Group Classification
published: 2025-11-16T23:11:57.490Z
description: ""
updated: ""
tags:
  - group-theory
draft: true
pin: 0
toc: true
lang: ""
abbrlink: ""
---

> Let $G$ be a group of order $2p$, where $p$ is a prime greater than $2$. Show that $G$ is isomorphic to either $\mathbb Z_{2p}$ or $D_{2p}$.

We divide it into two cases and prove them one by one:
- If $G$ is cyclic, then $G \cong \mathbb{Z}_{2p}$.
- If $G$ is not cyclic, then $G \cong D_{2p}$.

> **Theorem 1**
> When $G$ is not cyclic, it has no generator, then $G \cong D_{2p}$ in this case.

By Lagrange's Theorem, the order of nontrivial and proper subgroups of $G$ are either $2$ or $p$, then the order of any nontrivial element of $G$ is either $2$ or $p$ ($2p$ is impossible since $G$ is not cyclic).

To prove Theorem 1, we begin by proving the following lemmas.

> **Lemma 2**
> $G$ has at least a subgroup of order $p$.

_Proof of Lemma 2_

Assume that each nontrivial element of $G$ are of order $2$, i.e., $G = \{ e, g_{1}, g_{2}, \dots, g_{2p-1} \}$ and $\lvert g_{1} \rvert = \lvert g_{2} \rvert = \dots = \lvert g_{2p-1} \rvert = 2 \implies g_{1}^{2} = g_{2}^{2} = \dots g_{2p-1}^{2} = e$. Previous result from Homework 2 tells us that $G$ now is Abelian, thus $\left< g_{i} \right> \trianglelefteq G$ for all $i = 1, 2, \dots, 2p-1$.

Consider $\left< g_{1} \right>$. Since $\left< g_{1} \right> \trianglelefteq G$, the quotient group $G / \left< g_{1} \right>$ has order $2p / 2 = p$, thus is a cyclic group, and every nontrivial member of it is a generator for that $\varphi(p) = p-1$. Now, $g_{2}\left< g_{1} \right> \neq \left< g_{1} \right>$ generates $G / \left< g_{1} \right>$, then $(g_{2}\left< g_{1} \right>)^{2} = g_{k}\left< g_{1} \right> \neq \left< g_{1} \right>$ for some $k \in \{ g_{3}, g_{4}, \dots, g_{2p-1} \}$. However, $(g_{2}\left< g_{1} \right>)^{2} = g_{2}^{2} \left< g_{1} \right> = e\left< g_{1} \right> = \left< g_{1} \right>$, leading to a contradiction.

Therefore, $G$ contains at least a subgroup of order $p$.

> **Lemma 3**
> $G$ has at least a subgroup of order $2$.

_Proof of Lemma 3_

Similarly, assume that each nontrivial element of $G$ are of order $p$. Let $g \in G$ and $g \neq e$, then $\lvert g \rvert = p$ by assumption. Since $\varphi(p) = p-1$, every nontrivial element of $\left< g \right>$ has order $p$ thus is a generator of $\left< g \right>$.

Let $g' \in G$ be another nontrivial element of order $p$ that is not in $\left< g \right>$. We can prove that $\left< g \right> \cap \left< g' \right> = e$ with the following arguments: If $x \in \left< g \right> \cap \left< g' \right>$ and $x \neq e$, then $\left< x \right> = \left< g \right>$ and $\left< x \right> = \left< g' \right>$, i.e., $\left< g \right> = \left< g' \right>$, which contradicts with our assumption. Now, if we excludes elements of $\left< g \right>$ and $\left< g' \right>$ from $G$, there's only one remaining element, let $h$ denote it, it can only have order $2$ since if $\lvert \left< h \right> \rvert = p$, there's no more element outside $\left< g \right>$ and $\left< g' \right>$ can be assigned to $\left< h \right>$. So our assumption cannot hold true, therefore, $G$ has at least a subgroup of order $2$.

> **Lemma 4**
> If $g \in G$ is an element of order $p$ and $h \in G$ is an element of order $2$, then $\left< g, h \right> = G$ and that $hg^i = g^{-i}h$ for all $0 \leq i < p$.

_Proof of Lemma 4_

Since $\lvert \left< g \right> \rvert = p$ is a prime such that $\varphi(p) = p-1$, every nontrivial element of $\left< g \right>$ has order $p$, thus $h \not\in \left< g \right> \implies h\left< g \right> \cap \left< g \right> = \emptyset$. Adding that $\lvert h\left< g \right> \rvert = \lvert \left< g \right> \rvert = p$, we conclude that $G = \left< g, h \right>$.

Now, every element of $G$ that is not in $\left< g \right>$ is of the form $h g^i$ for some $0 \leq i < p$. Obviously $\lvert hg^i \rvert \neq 1$ for all $0 \leq i <p$. If $\lvert hg^i \rvert = p$, then following the proof of Lemma 2, $\left< hg^i \right> \cap \left< g \right> = \{ e \}$, thus $(hg^i)^{2} = hg^j$ for some $0 \leq j < p$. However,
\[
(hg^i)^{2} = hg^i hg^i = hg^j \implies hg^i = g^{j-i} \in \left< g \right>.
\]
So $\lvert hg^i \rvert$ cannot be $p$, hence $\lvert hg^i \rvert = 2$, which means that $(hg^i)^{-1} = g^{-i}h = hg^i$.

_Proof of Theorem 1_

Suppose $g, h \in G$ and $\lvert g \rvert = p, \lvert h \rvert = 2$, then $G = \left< g, h \right>$ by Lemma 3, i.e., $g' = g^{\alpha}h^{\beta}$ for all $g' \in G$, where $\alpha = 0, 1, \dots, p-1$ and $\beta = 0$ or $1$. Let $D_{2p} = \{ 1, r, \dots, r^{p-1}, s, s r, \dots, s r^{p-1} \}$.

Let $\phi: G \to D_{2p}$ be defined by $g' \mapsto s ^{\alpha} r^{\beta}$, where $g' = h^{\alpha}g^{\beta}, \alpha = 0$ or $1$ and $\beta = 0, 1, \dots, p-1$. We first prove that $\phi$ is a homomorphism:

- $\phi(e) = \phi(h^{0}g^{0}) = s ^{0}r^{0} = 1 \in D_{2p}$.
- Let $g_{1} = h^{\alpha_{1}}g^{\beta_{1}}, g_{2} = h^{\alpha_{2}}g^{\beta_{2}}$ be any two elements of $G$, where $\alpha_{1}, \alpha_{2} = 0$ or $1$ and $\beta_{1}, \beta_{2} = 0, 1, \dots, p-1$. Then,
  $$
          \begin{align*}
              \phi(g_{1} g_{2}) &= \phi(h^{\alpha_{1}}g^{\beta_{1}} h^{\alpha_{2}} g^{\beta_{2}}) \\
              &= \phi(h^{\alpha_1}h^{-\alpha_2}g^{-\beta_1}g^{\beta_2}) \qquad (|g^{\beta_1}h^{\alpha_2}| = 2 \implies g^{\beta_1}h^{\alpha_2} = (g^{\beta_1}h^{\alpha_2})^{-1} = h^{-\alpha_2}g^{-\beta_1}) \\
              &= \phi(h^{\alpha_{2} - \alpha_{1}}g^{\beta_{2} - \beta_{1}}) \qquad (|h| = 2 \implies h^{\alpha_1 - \alpha_2} = h^{\alpha_2 - \alpha_1}) \\
              &= s ^{\alpha_{2} - \alpha_{1}} r^{\beta_{2} - \beta_{1}} \\
              &= s ^{\alpha_{1}}r^{\beta_{1}} s ^{\alpha_{2}} r^{\beta_{2}} \\
              &= \phi(h^{\alpha_{1}}r^{\beta_{2}}) \phi(h^{\alpha_{2}}r^{\beta_{2}}) \\
              &= \phi(g_{1}) \phi(g_{2}).
          \end{align*}
  $$

Thus $\phi$ is a homomorphism.

Also, $\phi(h^{\alpha}g^{\beta}) = s ^{\alpha}r^{\beta} = 1 = s ^{0} r^{0}$ if and only if $\alpha = 0, \beta = 0$, thus only $h^{0}g^{0} = e$ can be mapped into $1$, i.e., $\ker\phi = \{ e \}$, so $\phi$ is injective. Moreover, $\lvert G \rvert = \lvert D_{2p} \rvert = 2p$, this implies that $\phi$ is bijective, hence $\phi$ is an isomorphism, hence $G \cong D_{2p}$.

> **Theorem 5**
> When $G$ is cyclic, $G \cong \mathbb{Z}_{2p}$.

_Proof_

Let $g$ be any generator of $G$, then $\left< g \right> = G$, i.e., every element of $G$ can be written as $g^i$ where $i \in \mathbb{Z}_{2p}$.

Let $\psi: G \to \mathbb{Z}_{2p}$ be defined by $g^i \mapsto i$ for all $i \in \mathbb{Z}_{2p}$. Obviously $1$ is a generator of $\mathbb{Z}_{2p}$ and $0$ is the identity element. To see that $\psi$ is a homomorphism,

- $\psi(e) = \psi(g^{0}) = 0$
- Let $x = g^i, y = g^j$ be any two elements of $G$, where $i, j \in \mathbb{Z}_{2p}$, then
  $$
      \begin{align*}
          \psi(xy) &= \psi(g^{i} g^{j}) \\
          &= \psi(g^{(i+j) \bmod{2p}}) \\
          &= (i+j) \bmod{2p} \\
          &= \psi(g^{i})\psi(g^{j}) \\
          &= \psi(x)\psi(y).
      \end{align*}
  $$

Since for all $i \in \mathbb{Z}_{2p}$, there is $g^i \in G$ that is mapped to $i$, so $\psi$ is surjective. Moreover, $\lvert G \rvert = \lvert \mathbb{Z}_{2p} \rvert = 2p$ implies that $\psi$ is bijective. Therefore, $\psi$ is an isomorphism, then this suggests that $G \cong \mathbb{Z}_{2p}$.

Finally, we conclude that $G$ is isomorphic to either $\mathbb{Z}_{2p}$ or $D_{2p}$ as $G$ is either cyclic or not cyclic.
