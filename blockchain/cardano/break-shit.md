# CARDANO ECONOMIC PARAMETERS
###### Article - [here](https://www.cardanofoundation.org/blog/deep-dive-cardano-economic-parameters) • Whitepaper - [needs .pdf extension](https://ucarecdn.com/dc66cfa9-03a8-4247-acaa-55bc69a0e956/) • PDF - [here](https://github.com/st8tikratio/Uselessness/blob/main/papers/pdfs/Cardano%20Economic%20Parameters%20Morini.pdf)
###### Markdown Assitance - [here](https://github.com/st8tikratio/Uselessness/blob/main/md-spec-char.md) • [LaTeX and Markdown Helper](https://en.wikibooks.org/wiki/LaTeX/Mathematics) • [Another Cheat Sheet](https://www.upyesp.org/posts/makrdown-vscode-math-notation/) • [Jupyter Cheat Sheet](https://jupyterbook.org/en/stable/content/math.html)

---

## SUMMARY AND ROADMAP
###### pages 1 - 4

- $a_0 =$ `parameter deciding the effect of the pledge on rewards`

  - `aka Pool Pledge Influence` (pg 5)

  - `pledge` - `stake provided by pool operators (SPOs)`

    - `benefit of the pledge is extremely reduced for small and medium pools compared to very large ones`

    - `smaller pools, having a larger pledge, at equal stake, can even reduce rewards slightly`

      - `disappears only for pools with a size of at least half of saturation`

  - `if` $a_0 = 0$  `the pool reward is proportional to the pool's fraction` $\frac {\sigma}{S}$ `of the total possible stake` $[S]$ `up to saturation` $z$

  - `for larger` $a_0$ `values pledge becomes more important`

  - `as` $\sigma$ `approaches` $z$ `then` $a_0$ `becomes more influential`

- $k =$ `desired Number Of Pools`

  - `helps determine saturation level -` $[z]$

- $z =$ `size of saturated stake/pool (or saturation level)`
  
  - `saturation level` - `stake amount above which no additional rewards are paid`

  - `In 2024 ->` $z = 70M$

    - $saturationLEVEL = \frac {circulatingSupply}{desiredNumberOfPools} = z =  \frac {S}{k} = \frac {37B}{500} = 70M $

- $\sigma =$ `amount active stake`

  - `the incentive to small pools is to increase the stake, first by delegation rather than by pledge`

  - `large pools have a clear reward increase if they consist of own stake rather than delegated capital`

    - `discourages large owners from trying to game the system by splitting their stake into many pools`

    - `rewards the security value of large commitments of own money`

    - PROS & CONS:

      - `can increase security and efficiency`

      - `negative effect on inclusion and decentralization`

      - `reduces the rewards of small pool operators, and of delegators of all pools`
     
- $f =$ `staking incentive parameter`

- $p =$ `ratio between active stake and circulating supply`

- $S =$ `Circulating Supply`

  - `aka Total Possible Stake`

  - `used as a measure of total stake for rewards`
 
- `Active stake` - `amount of circulating supply that is actively staked (? & pledged ?)`

  - `used as an aggregate measure for consensus` 

- $\rho =$ `monetary expansion parameter` - $[rho]$

  - $\rho = 0.3$%

  - `due to the fraction which is retained from Rewards distribution, mostly as an incentive to grow stake and pledge or to rescale rewards by the active stake, the actual release has been between 0.165% and 0.185% rather than 0.3%`
 
- $\tau =$ `treasury expansion parameter` - $[tau]$

  - $\tau = 20$%

  - `Rewards should receive` $1−\tau = 80$% `of the release, they actually got just between` $65$% `and` $70$%`, with Treasury taking
a fraction between `$30$%` and `$35$% 

- `the proportion between the growth of Treasury and the Rewards, that could be expected to be` $\frac {\tau}{1-\tau} = 25$%`, has often been more than` $50$%

---

- `Validation reward systems have at least two goals:`
  
  - `making validation sustainable and economically competitive`
  
  - `incentivize commitment to network security in a decentralized way`

- `General description of the parameters is given in` [`Cardano Documentation`](https://docs.cardano.org/about-cardano/explore-more/parameter-guide#types-of-protocol-parameters-on-cardano)

- `in the reward system smaller pools are implicitly incentivized to increase their stake by increasing first delegated stake, rather than own stake`

- `Pools with no pledge are penalized by considering only a fraction of their share of the stake for the purpose of reward computation`

  - $\frac {1}{1+a_0}$

    - `Currently` $a_0 = 0.3$
   
  - $\frac {1}{1+0.3} = \frac {1}{1.3} = 0.7692 \approx 0.77$%

- `Pool with a stake that:`

  - `Is ` $10$% $\leq z \approx 7.7$% `of available rewards rather than` $10$% `even if pledge` $100$%

  - `Aapproaches` $50$% `saturation the pledge impact increases gradually`

  - `Is greater than` $50$% `the pledge becomes beneficial in any amount`

  - `Is fully-saturated can reach full rewards` $\frac {1}{k}$ `by increasing pledge to` $100$%

---

### FORMULAS:
- `Incentive Formula`
  - $f=(\alpha,z,\sigma,\lambda) = \frac{1}{1+\alpha} (\sigma+\alpha\lambda \frac{\sigma-\lambda\frac{z-\sigma}{z}}{z} ) $

- `Saturation Level`
  - $z = \frac{S}{k}$

- `Pool x with stake(x)`
  - $\sigma = \frac{stake^x}{S} $
  
- `Expanded Incentive Formula`
  - $f=(\alpha,z,\sigma,\lambda) = \frac{1}{1+\alpha}\sigma + \frac{1}{1+\alpha} [ \sigma \frac{\lambda}{z} + \sigma (\frac{\lambda}{z})^2 - z (\frac{\lambda}{z})^2 ] $

- `Pledge as a Fraction of the Stake of the Pool`
  - $\lambda_{percent} = \frac{\lambda}{\sigma} $

- `Stake of the Pool as a Fraction of the Stake at Saturation`
  - $\sigma_{percent} = \frac{\sigma}{z} $ 

---

### NUMERICAL EXAMPLE

- `given values`
  - `saturation level` -> $z = 70M$

  - `stake` -> $\sigma = 7M$

  - `pledge` -> $\lambda = 1.4M$

  - $stake_{percent} = \sigma_{percent} = \frac {stake}{saturation-level} = \frac {7}{70} = 0.10$%

  - $pledge_{percent} = \lambda_{percent} = \frac {pledge}{stake} = \frac {1.4}{7} = 0.20$%

  - $k = 500$ 

- `INCENTIVE FORMAULA -> Plugging in` $\lambda_{percent}$ `and` $\sigma_{percent}$

  - $f=(\alpha,z,\sigma_{percent},\lambda_{percent}) = (\frac {1}{1+\alpha} \sigma_{percent} + \frac {\alpha}{1+\alpha} [\sigma^2_{percent} \lambda_{percent} - \sigma^2_{percent}\lambda^2{percent} + \sigma^3_{percent}\lambda^2_{percent} ]) z        $

- `Rewards of a pool as a fraction of the rewards of the desired or optimal pool, which is fully pledged and saturated`

  - `size` $z = 1/k $

  - `receives` $z = 1/k$ `of total available rewards`

- `Further Refined`

  - $f_{percent}(\alpha,z,\sigma_{percent},\lambda_{percent}) = \frac {f(\alpha, z, \sigma_{percent}, \lambda_{percent}}{z} = (\frac {1}{1+\alpha}\sigma_{percent}+\frac {\alpha}{1+\alpha}[\sigma^2_{percent}\lambda^2_{percent} - \sigma^2{percent}\lambda^2_{percent} + \sigma^3_{percent}\lambda^2_{percent}])          $ 

    - `PLEDGE` $= 0$`%`

      - `max-rewards for` $\sigma_{0percent}$ = $f_{percent}$ `is` $\frac {1}{1+\alpha}\sigma_{percent}$

    - `PLEDGE` $= 10$`%`

      - `rewards POTENTIALLY reduced for` $\sigma_{10percent}$ `by a factor of` $\frac {1}{1+\alpha} \approx 0.77 $

        - $0.1 * 0.77 = 0.077 = 7.7$% `of the rewards of the optimal pool`
   
    - `The second biggest term of` $order$ $3$ overall

      - $\frac {\alpha}{1+\alpha} \sigma^2_{percent}\lambda_{percent} $

      - `With current` $\alpha = 0.3$

        - $\frac {\alpha}{1+\alpha} \sigma^2_{percent} \lambda_{percent} = 0.23 * 0.1^2 * 0.2 = 0.00046 = 0.046$ %

    - `The next term is smaller and negative`

      - $-\frac {\alpha}{1 + \alpha}\sigma^2_{percent}\lambda^2_{percent} = - 0.23 * 10$% $* 10$% $* 10$% $* 20$% $* 20$% $= - 0.0009$%

    - `The last term is even higher order and smaller in absolute value`

      -  $\frac {\alpha}{1 + \alpha}\sigma^3_{percent}\lambda^2_{percent} = 0.23 * 0.1^3 * 0.2^2 = 0.0009$%
     
    - `The contribution of 20% of own stake movers rewards from 7.7% of the rewards of a saturated pool to 7.73%, a 0.03% addition`
      - `less pledge or stake, than the 20%, would have less relevant impact on rewards`

---



- RELEVANT NOTE:

  - `When small fractions are multiplied or raised to powers, their values decrease further`


---




---
### NEED CLEANING
- $\alpha = a_0$
- $\sigma = active Stake$
- $\lambda = pledge$
- $S = CirculatingSupply$ `aka total Stake`
- $z = saturation Level$
- 
- 

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
| $z$ <br> size of saturated pool      | $70M$                         | $72,037,633$ <br> $= 36,018,816,732 / 500$ | $72,037,633$ <br> $= 36,018,816,732 / 500 $ |   |
| $a_0$ <br> pledge influence factor  | ?                             | ?                                          | ?                                  |             



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
