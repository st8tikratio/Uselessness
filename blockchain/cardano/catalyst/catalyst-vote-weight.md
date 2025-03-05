# Catalyst Voting Weight For ALL VOTERS
###### by Ratio, 05 Mar 2025

## Summary
- Catalyst voters are allowed to vote on as many propsals as they like. THe weight of the registered wallet, amount of ADA, is aggregated amongst all voters for every proposal. There are no limits on the number of proposals a voter may vote YES to. This allows for gaming the current system by large wallet holders, sybil actors and other possible rogue, not necessarily bad, actors.
- To remove these issues, it is suggested that voters be limited to the number of proposals they may vote YES to within any category. The limit is based on the total category funding and the proposal budget requests. As a voter submits their votes the category's proposal amounts are added up. Once the voter's voted proposals total the available funding for the category the voter `can no longer vote` within that category.
- As the voter approaches this maximum they are provided a warning by the voting app. If they are over the app will not allow them to submit the last vote and they must adjust accordingly by removing proposals or adjusting their current selections.
- This carries through throughout the entire process until the voter has exhausted all voting capacity. Their voted proposals can never add up to more than the available Category funding.


## Assumptions
- Project Catalyst still requires voters to register the wallets in order to participate in proposal voting.
- Project Catalyst still has categories that have been funds to be allocated.
- Category funding is static; no changes can be made to the total available ada distribution for that category.
- Voters votes are weighted by teh amount of ADA they hold within their wallets.
- Voters can vote on as many proposals as they choose to.
- Voting is completed within the Catalyst Voting app.

## Defintions
- Voter - anyone with a registered wallet.
- Category - one of the broad areas described at the beginning of each fund. Each category receives a bucket of funds.

## Description Of Problem
- Voting on proposals is extremely time consuming
- Some votes may be considered spam
- Whales and other influential entities have proportional impacts on funding outcomes across all of Catalyst

## Suggested Changes
- Instead of voters being able to vote on every proposal in every category, voters would be limited on the number of proposals they may submit votes on.

## Details
- For each Catalyst category the voter is only allowed to vote on a `max number of proposals per category` ($M_vpc$). Much of this is based on the `requested funding per proposal` which we call $pf_{max}$.
- In each category there is a maximum amount of available funding, $C_f$
- Max Votes per Category = Category funding total - requested funding per proposal

## In Practice
- The voter has registered his/her wallet with the Catalyst Voting app.
- The voter reviews proposals in the `Ecosystem` category.
- There are 5 proposals that interest the voter. Below are the amount of funding being requested per proposal and the total funding available for the category
  - Category funding, $C_f$ = 1,500,000 ADA
  - Proposal 1, $P_1$, funding = 500,000
  - Proposal 2, $P_2$, funding = 350,000
  - Proposal 3, $P_3$, funding = 150,000
  - Proposal 4, $P_4$, funding = 200,000
  - Proposal 5, $P_5$, funding = 350,000

## Math
- The voter has voted yes to proposals that amount to 1,550,000 ADA
- Sum of voted proposals, $SP_v$, is $P_1+...+P_5 = 1,550,000$
- The voter has voted yes on proposals that could not be accomodated by the category's allocated funding, $C_f$ = 1,500,000
- $SP_v - C_f = -50,000$
- The system provides a warning: You have over-allocated the category budget by 50,000 ADA. Please adjust your voting

## Objective
- Removes irrelevant votes. Yes everyone deserves a chance to be funded but voting on proposals that would over-allocate the budget gives false metrics and allows for gaming the system in a sense.

## Alternatives
- This can be applied to every category and holds even if there is one category.
