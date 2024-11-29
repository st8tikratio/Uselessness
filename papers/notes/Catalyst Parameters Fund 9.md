---
title: Catalyst Parameters Fund 9

---

---
title: Catalyst Parameters Fund 9
tag: parameters
---

# Catalyst Parameters Fund 9

### Product/Business/Informative Parameters

|PARAMETER | VALUE | DESCRIPTION |
| -------- | ----- | ----------- |
| Direct Voting privacy state | Yes | Are votes public or not? |
|Fund name | Fund9 | |
| Challenges Title and Budget | [The Great Migration (from Ethereum)](https://app.ideascale.com/t/UM5UZBw7N) $500,000 | |
|                             | [DAOs <3 Cardano](https://app.ideascale.com/t/UM5UZBvaV) $1,000,000                   | |
|                             | [Legal & Financial Implementations](https://app.ideascale.com/t/UM5UZBvbn) $500,000   | |
|                             | [Developer Ecosystem](https://app.ideascale.com/t/UM5UZBvNu) $1,000,000               | |
|                             | [Dapps, Products & Integrations](https://app.ideascale.com/t/UM5UZBw78) $7,850,000    | |
|                             | [Cross-Chain Collaboration](https://app.ideascale.com/t/UM5UZBunq) $900,000           | |
|                             | [Challenge & Scouted for Students](https://app.ideascale.com/t/UM5UZBvbE) $100,000    | |
|                             | [Grow Africa, Grow Cardano](https://app.ideascale.com/t/UM5UZBuk1) $500,000           | |
|                             | [dRep improvement and onboarding](https://app.ideascale.com/t/UM5UZBvsJ) $150,000     | |
|                             | [Grow East Asia, Grow Cardano](https://app.ideascale.com/t/UM5UZBvV3) $250,000        | |
|                             | [Building (on) Blockfrost](https://app.ideascale.com/t/UM5UZBvum) $50,000             | |
| Proposals submission fee    | Free                                                                                  | Proposers can submit a proposal for discussion on Ideascale.|
| Funds under control         | 16,000,000 ada                                                                        | Fund will Control 16M ada |
| Funds MIR date              | Date + CR                                                                             | |
| Reward distribution date    | 02/Sep/2022 - 09/Sep/2022                                                             | When funding tx’s actually go out |
| Mechanism to prevent price fluctuation | Proposals will be paid the $ value they requested in ada, according to ada valuation at reward distribution date. 3,200,000ada total rewards for Voters + advisors + referrers + challenge teams will be provided according to ada valuation on reward distribution date. | |
| Fund goals | Attract more developers <p></p> Build real live solutions based on the Cardano blockchain. <p></p> Improve tooling to support human processes in Catalyst | Fund goals to be presented in the Voting App. <p></p> Survey results collected between 4/20 - 5/19. 1045 votes cast, on 31 statements, by 47 unique participants. [Results](https://pol.is/report/r4dafyewbkcrkm8c7exjb). Took top 3 by (yes minus no). Combined 2 / 26 due to similarity, taking the more general “solutions” over “applications”. Broke tie on 10 / 19 based on number of participants + disagreement.|
| Maximum proposals that can be put on the ballot | No limit | |
| Community advisor registration | Through Ideascale | Everyone can register as a Community Advisor. They can’t do CA work in the challenge they are proposing to or are involved with a proposal team.|
| Proposals registration on the blockchain | Rust/Devops dev | The registration of proposals on the blockchain will be done in the future by an elected committee. |
| Voting power threshold | 450,000,000 lovelace. (450 ada) <p></p> Communicate threshold as 500 to account for tx fees | Minimal stake threshold to become a voter, based on the efficiency benchmarks of the voting protocol. <p></p> Specific value of the voting stake threshold will be defined by the protocol benchmarks. <p></p> Note that threshold must be lowered by 50 ada from the amount stated to the community to address registration fees.|
| Registration start time | 07/Apr/2022, 12:00 UTC | Registrations made after 03/06/2021 16:00 UTC are valid. Official registration start time starts an hour after the previous Fund snapshot. | 
| Registration snapshot date | 04/Aug/2022, 11:00 UTC | | 
| Voting period start time| 11/Aug/2022, 07:00 UTC <p></p> Communicate: 11/Aug/2022, 11:00 UTC | (A block height bound to) UTC date and time when voters can start voting on proposals |
| Voting period end time | 25/Aug/2022, 11:00 UTC | |
| Start of tallying | 25/Aug/2022, 11:00 UTC | | 
| End of tallying | 02/Sep/2022, 11:00 UTC | UTC date and time by which the committee shall post the decrypted tally. |
| next_fund_start_time | 04/Aug/2022, 12:00 UTC | When registration phase for the next Fund starts | 
| fund_id | 9 | Fund_id as described in vote plan |
| Jormungandr Tallying optimization | 1 ADA = 1 voting token (i.e. the stake amount in lovelace is divided by 1000000) | How voting power is being proportionally reduced in order to optimize tallying performance |

---

### Reward Parameters

|PARAMETER | VALUE | DESCRIPTION |
| -------- | ----- | ----------- |
| Proposal Funding logic (winner selection rule) | Proposals are ranked by the difference of Yes and No votes and funded one by one until challenge budget is exhausted | Proposals are ranked by sum of votes and funded in order. If the amount requested by a proposal is larger than the remaining challenge amount, it is skipped. | 
| Proposal acceptance threshold | 1% of total voting power <p></p> 15% more ‘Yes’ than ‘No’ | At least 1% of the total registered stake must vote on a proposal. <p></p> E.g., there is 1 billion ADA as a total registered stake. Then to be accepted (become an ‘approved proposal’ as well as be eligible for funding), a proposal must be voted by at least 0.01 * (1 * 10^9) = 10 millions of ADA. <p></p> 'Yes'-'No' difference of the stake voted on proposal must be at least 15% <p></p> (e.g., 90% 'Yes' and 10% 'No', or 57.5% 'Yes' and 42.5% 'No', or 100% 'Yes' and 0% 'No', etc.; it is assumed that abstained stake does not vote on the proposal in the current architecture).|
| $Vr_{total}$ | 13% <br> 2,080,000ada | Total amount of rewards for voters out of total funds in treasury |
| $Rr_{total}$ | 1% <br> 160,000ada | Referral rewards |
| $Ar_{total}$ | 4% <br> 640,000ada | Community advisor reward | 
| $AAr_{total}$ | 1% <br> 160,000ada | Reviewing reviewers reward |
|               | 1% <br> 5,000ada per team <br> Up to 160,000ada | Challenge team reward <p></p> Base reward of 5k per team Remaining funds after base rewards will be split proportionally among challenge teams according to number of funded proposals relative to total <p></p> “CT rewards total: 160,000ada CT base rewards: 5,000ada Leftovers: 45,000ada (23 teams x 5,000ada = 115,000ada; 160,000ada - 115,000ada = 45,000ada) after voting we can define bonus incentive per proposal, let's assume 500 proposals will get funded <br> Bonus per proposal: 90ada (45,000ada / 500 proposals = 90ada) <br> So for example, assuming that in Gamers On-Chained proposal 15 proposals get funds then its Challenge Team reward will be: 6,350ada (5,000ada base + 1,350ada bonus)” |
| Voter reward formula | $Vr_j = (stake_j/stake_{total})Vr_{total}$ | Voter rewards will be given for active participants only in proportion to the voting power votes have. <p></p> $stake_j$ - voter’s stake; <br> $stake_{total}$ - total amount of ‘active’ stake.|
| Advisor reward formula | Each proposal rewards budget fits 2 Excellent and 3 Good assessments. If there are more than 2 Excellent or 3 Good assessments, a lottery system is used. Bonus rewards are available (20% of total CA rewards budget) for assessments ‘Approved’ by the community, proportional to the proposal budget | If there are more assessments than what the budget can pay for, a [double lottery system](https://docs.google.com/presentation/d/1wYMgoNJ8Pf2pGVKCiblniEbMERjtrLrAHC6Zs2JbfyU/edit#slide=id.gb84ae6e7f7_0_10) is used. The total CAs assessments budget for that proposal is divided in 36 parts. Each ‘Excellent’ assessment receives 12 lottery tickets, and each ‘Good’ assessment, 4 tickets. |
| Referral reward calculation | Equal amount distributed between all referrers who referred to a funded proposal per funded proposal | |
| Reviewing the reviews formula | Min threshold = 200 <br> Rewards eligible rank cap = inf <br> Reputation eligible rank cap = inf <p></p> Agreement rate cutoff 1 = .9 <p></p> Cutoff 1 multiplier / discount rate = 1.25 <p></p> Agreement rate cutoff 2 = .8 <p></p> Cutoff 2 multiplier / discount rate = 1 <p></p> Agreement rate cutoff 3 = .7 <p></p> Cutoff 3 multiplier / discount rate = .75 <p></p> Below cutoff discount rate = 0 <p></p> IF agreement >= (.9) THEN final eligible ranking = rewards eligible ranking * BONUS (1.25) <br> IF agreement >= (.8) THEN final eligible ranking = rewards eligible ranking * REGULAR (1) <br> IF agreement >= (.7) THEN final eligible ranking = rewards eligible ranking * SLASH (.75) <br> IF agreement < (.7) THEN final eligible ranking = rewards eligible ranking * FORFEIT (0) and these reviews/rankings will be excluded before voting | Veteran community advisors should receive rewards proportional to the number of eligible rankings, to avoid incentivizing bad faith or negligent participation <p></p> Veteran community advisors rankings should be eligible for rewards only when they agree with the majority, in order to incentivize rational and honest participation. For simplicity, only consider filtered out vs good / excellent <p></p> Formulas and references can be found in the [Fund8 - vCA Eligibility & Incentives Requirements](https://docs.google.com/document/d/14qHSZ2uSHq2CZyeqju6KLBcGVfagesCLvavZMAgcbWo/edit) |
| Contingency for vCA rewards | 5% of $AAr_{total}$ <br> 8,000ada | Funds allocated to pay vCAs after petition outcome |

---

### Back-End Parameters

|PARAMETER | VALUE | DESCRIPTION |
| -------- | ----- | ----------- |
| Direct Voting privacy state | Yes | Are votes public or not? |
| dReps Voting privacy state (if applicable) | No | Are dReps votes public or not? |
| Funds under control | 16,000,000 ada | Fund will Control 16M ada |
| Fund goals | Goal 1 <br> Goal 2 <br> Goal 3 | Fund goals to be presented in the Voting App |
| Voting power threshold | 450,000,000 lovelace. (**450 ada**) <p></p> **Communicate threshold as 500 to account for tx fees** | Minimal stake threshold to become a voter, based on the efficiency benchmarks of the voting protocol. <p></p> Specific value of the voting stake threshold will be defined by the protocol benchmarks. <p></p> Note that threshold must be lowered by 50 ada from the amount stated to the community to address registration fees. |
| current_fund_name | Fund9 | |
| current_insight_sharing_sta rt |  Jun 2, 2022 | |
| current_proposal_submissi on_start | Jun 9, 2022 | |
| current_refine_proposals_s tart | Jun 16, 2022 | |
| current_finalize_proposals_ start | Jun 23, 2022 | |
| current_proposal_assessm ent | Jun 30, 2022 | |
| current_assessment_qa_st art | Jul 21, 2022 | |
| current_snapshot_start | Aug 4, 2022 | |
| current_voting_start | Sep 5, 2022 | |
| current_voting_end | Sep 19, 2022 | |
| current_tallying_end | Sep 22, 2022 | |