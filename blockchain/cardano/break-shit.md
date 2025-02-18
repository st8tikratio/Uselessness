### FORMULAS:
- `Incentive Formula`
  - $f=(\alpha,z,\sigma,\lambda) = \frac{1}{1+\alpha} (\sigma+\alpha\lambda \frac{\sigma-\lambda\frac{z-\sigma}{z}}{z} ) $
  
- `Expanded Incentive Formula`
  - $f=(\alpha,z,\sigma,\lambda) = \frac{1}{1+\alpha}\sigma + \frac{1}{1+\alpha} [ \sigma \frac{\lambda}{z} + \sigma (\frac{\lambda}{z})^2 - z (\frac{\lambda}{z})^2 ] $

- `Saturation Level`
  - $z = \frac{S}{k}$

- `Pool x with stake(x)`
  - $\sigma = \frac{stake^x}{S} $

- `Pledge as a Fraction of the Stake of the Pool`
  - $\lambda_{percent} = \frac{\lambda}{\sigma} $

- `Stake of the Pool as a Fraction of the Stake at Saturation`
  - $\sigma_{percent} = \frac{\sigma}{z} $ 

#### WHERE:
- $\alpha = a_0$
- $\sigma = active Stake$
- $\lambda = pledge$
- $S = CirculatingSupply$ `aka total Stake`
- $z = saturation Level$
- $k = desired NumberOfPools$

#### EXAMPLE POOL:
- Stake saturation = $70M = \lambda_{percent} = \frac{1.4M}{7M} = 0.20$ = 20%
- Stake of our pool = $7M = \sigma_{percent} = \frac{7M}{70M}  = 0.10$ = 10%
- Pledge = $1.4M = \lambda$

#### METRICS (whitepaper) + CURRENT
| Item                                 | Epoch 300 - 470 <br> (whitepaper)| Epoch 539(1) <br> (18-Feb-2025)            | Epoch 539(2) less `Abandoned Pools` <br> (18-FEb-2025)  |
| -----                                | :---------------:             | :-------:                                  | :----------------------------:    |
| $\sigma$ <br> active stake           | $6,893,338 - 7,950,258$       |                                            |                                   |
| $\sigma_{avg}$ <br> avg active stake | $7,421,798$                   | $7,425,095$                                | $8,996,305$                       |
| $\lambda$ <br> pledge range          | $1,186,745 - 1,657,484$       |                                            |                                   |
| $\lambda_{avg}$ <br> avg pledge      | $1,422,115$                   | $1,199,677$                                | $576,574$                         |
| $S$ <br> circulating supply range    | $34B > 37B$                   | $36,018,816,732$                           | $36,018,816,732$                  |
| $k$ <br> desired numPools            | $500$                         | $500$                                      | $500$                             |                 
| $z$ <br> size of saturated pool      | $70M$                         | $72,037,633$ <br> $= 36,018,816,732 / 500$ | $72,037,633$ <br> $= 36,018,816,732 / 500 $ |                             |

- Notes:
  - (1) dbSync Logic: 
    ```
    select avg(active_stake), avg(pledge), count(*) from grest.pool_history_cache phc inner join pool_update pu on phc.pool_id = pu.hash_id where epoch_no = 539 and not exists (select null from pool_update pu2 where pu2.hash_id = pu.hash_id and pu2.id > pu.id);
    ```
    
  - (2) dbSync Logic:
    ```
    select avg(active_stake), avg(pledge), count(*) from grest.pool_history_cache phc inner join pool_update pu on phc.pool_id = pu.hash_id where epoch_no = 539 and not exists (select null from pool_update pu2 where pu2.hash_id = pu.hash_id and pu2.id > pu.id) and phc.active_stake > pu.pledge;
    ```


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
