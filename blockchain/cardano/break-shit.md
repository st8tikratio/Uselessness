### FORMULAS:
- `Incentive Formula`
  - $f=(\alpha,z,\sigma,\lambda) = \frac{1}{1+\alpha} (\sigma+\alpha\lambda \frac{\sigma-\lambda\frac{z-\sigma}{z}}{z} ) $

- `Expanding the original`
  - $f=(\alpha,z,\sigma,\lambda) = \frac{1}{1+\alpha}\sigma + \frac{1}{1+\alpha} [ \sigma \frac{\lambda}{z} + \sigma (\frac{\lambda}{z})^2 - z (\frac{\lambda}{z})^2 ] $

- `Saturation Level`
  - $z = \frac{S}{k}$

- `Pool x with stake(x)`
  - $\sigma = \frac{stake^x}{S} $

- `Pledge as a Fraction of the Stake  of the Pool`
  - $\lambda_{percent} = \frac{\lambda}{\sigma} $

- `Stake of the Pool as a Fraction of the Stake at Saturation`
  - $\sigma_{percent} = \frac{\sigma}{z} $

#### Where:
- $\alpha = a_0$
- $\sigma = active Stake$
- $\lambda = pledge$
- $S = total Stake$
- $z = saturation Level$
- $k = desired NumberOfPools$

#### EXAMPLES:
- Stake saturation = $70M = \lambda_{percent} = \frac{1.4M}{7M} = 0.20$ = 20%
- Stake of our pool = $7M = \sigma_{percent} = \frac{7M}{70M}  = 0.10$ = 10%
- Pledge = $1.4M = \lambda$

#### METRICS (whitepaper)
| Item                                 | Epoch 300 - 470 <br> (whitepaper)| Epoch 539 <br> (18-Feb-2025)      | Epoch 539 less `Abandoned Pools` <br> (18-FEb-2025)  |
| -----                                | :---------------:             | :-------:          | :----------------------------:    |
| $\sigma$ <br> active stake           | $6,893,338 - 7,950,258$       | $7,425,094.86$     | $8,996,305.09$                    |
| $\lambda_{range}$ <br> pledge range  | $1,186,745 - 1,657,484$       | $1,199,677.30$     | $576,574.02$                      |
| circulating supply <br> `from > to`  | $34B > 37B$                   | $36,018,816,731.97$| $36,018,816,731.97$               |
| $k$                                  | $500$                         | $500$              | $500$                             |                 
| $z$ <br> size of saturated pool      | $70M$                         | $70M$              | $70M$                             |

#### CURRENT VALUES
- a_0 = 70M ??
- k $= 500$ 

# GATHERING DATA ON CARDANO POS PARAMTERS FOR MODEL INPUT
##### Article - [here](https://www.cardanofoundation.org/blog/deep-dive-cardano-economic-parameters)
##### Whitepaper - [add PDF to end of downloaded file](https://ucarecdn.com/dc66cfa9-03a8-4247-acaa-55bc69a0e956/) - [PDF](https://github.com/st8tikratio/Uselessness/blob/main/papers/pdfs/Cardano%20Economic%20Parameters%20Morini.pdf)
##### Additional Markdown Notes - [here](https://github.com/st8tikratio/Uselessness/blob/main/md-spec-char.md)
##### LaTeX and Markdown Helper - [here](https://en.wikibooks.org/wiki/LaTeX/Mathematics)
##### Another Cheat Sheet - [here](https://www.upyesp.org/posts/makrdown-vscode-math-notation/)
##### Jupyter Cheat Sheet - [here](https://jupyterbook.org/en/stable/content/math.html)

## Helpful Formula Creation Notes

| Name                                             | Meaning       |  To get this           | Type this statement <br> Enclosed in `$` w/o spaces <br> i.e. `$ Statement $` |
| ---------------                                  | ------------- |  :----------:          | ----------------------------------------------------------------------------- |
| For All <br> Subset                              |               | $\forall x$            | \forall x                                                                     |
| In <br> Subset                                   |               | $\in x$ <br> $\subset x$ | \in x <br> \subset x                                                        |
| There exists                                     |               | $\quad \exists y$      | \quad \exists y                                                               |
| Less than, equal to <br> Greater than, equal to  |               | $\leq$ <br> $\geq$     | \leq <br> \geq                                                                |
| Epsilon                                          |               | $\epsilon$             | \epsilon                                                                      |
| alpha <br> beta                                  |               | $\alpha$ <br> $\beta$  | \alpha <br> \beta                                                             |
| Alpha <br> Beta                                  |               | $A$ <br> $B$           | A <br> B                                                                      |
| gamma <br> Gamma                                 |               | $\gamma$ <br> $\Gamma$ | \gamma <br> \Gamma                                                            |
| Infinity                                         |               | $\infty$               | \infty                                                                        |
| mu                                               |               | $\mu$                  | \mu                                                                           |
| phi <br> Phi                                     |               | $\phi$ <br> $\Phi$     | \phi <br> \Phi                                                                |
| pi <br> Pi                                       |               | $\pi$ <br> $\Pi$       | \pi <br> \Pi                                                                  |
| sigma <br> Sigma                                 |               | $\sigma$ <br> $\Sigma$ | \sigma <br> \Sigma                                                            |
| tau                                              |               | $\tau$                 | \tau                                                                          |
| Therefore                                        |               | $\therefore$           | \therefore                                                                    |
| theta <br> Theta                                 |               | $\theta$ <br> $\Theta$ | \theta <br> \Theta                                                            |
| varPhi                                           |               | $\varphi$              | \varphi                                                                       |

---




#### MARKDOWN VERSIONS
##### Incentive Formula

`$f=(\alpha,z,\sigma,\lambda) = \frac{1}{1+\alpha} (\sigma+\alpha\lambda \frac{\sigma-\lambda\frac{z-\sigma}{z}}{z} )$`

#####

| $\lambda$

- \in x `results in` $\in x$
- $f (\forall x)$ $(\tau z)$
  $\quad \exists x | x2>x$
