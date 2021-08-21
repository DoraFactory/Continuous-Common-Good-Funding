# Continuous Common Good Funding

Goda Takeshi

*To pour forth benefits for the common good is divine.
-- Benjamin Franklin*

## Common Goods and Funding Schemes

Since the early stage of civilization, people have been innovating for common goods. The common goods we now take for granted were mostly ingenious inventions of its time — city parks, libraries, dams, universities, hospitals, the Web, and recently, a large number of open source software.

Funding common goods has always been a challenge. In the old days, common goods have been mostly funded by states and wealthy private citizens. Over the past century, non-profit organizations became popular. In the past decade, the open source community has made tremendous contributions to create many common goods in the digital space. Many major open source projects are funded via non-profit organizations too (e.g. the Mozilla Foundation and the Linux Foundation). However, as the open source community grows, the incentive model of non-profit organizations is clearly not fitting the needs of common good innovators and open source developers — high administration cost, a lack of contributor and innovator incentives, just to name two.

The blockchain communities have always valued common goods (or public goods). Since the end of the 2017-hype, it’s clear that the value of common goods in the crypto space is recognized by the community.

There have been several classes of common good funding mechanisms that have been successful and accepted by various projects on Ethereum, Polkadot, and other blockchain infrastructures. 

Here are some examples:

**Quadratic funding** rounds are widely used by public chain ecosystems and potentially adopted by small / medium size projects and DAOs to provide grants for their ecosystem projects. Quadratic funding allows individual contributors to donate and impact the distribution of a matching fund. DoraHacks HackerLink, Gitcoin, and clr.fund are running quadratic funding grants on a regular basis to fund open source developer projects.

**MolochDAO** has become a prominent way to build guilds that support projects case by case. It’s now useful to build grant DAOs and venture DAOs.

**Foundation Grants** are provided by many cryptocurrency and infrastructure projects to fund project and ecosystem development. The Web3 Foundation Open Grant and the Ethereum Foundation grant are good examples. Through such grants, many important developments can be funded and speed up.

New mechanisms are being proposed within the Ethereum community. Recently, the Optimism team and Vitalk Buterin proposed **Retroactive Public Good Funding**, which could potentially help DAOs (or foundations) to fund new projects retroactively within their ecosystem.

## An In-depth Discussion on Bonding Curves

In this article, we describe **Continuous Common Good Funding**. The scheme provides a funding mechanism for permissionless, instantaneous contribution and participation of projects that build common goods. The word “continuous” means that the token supply and price are continuous on a bonding curve.

Bonding curve was first proposed by Simon de la Rouviere in his original article *[Tokens 2.0: Curved Token Bonding in Curation Markets](https://medium.com/@simondlr/tokens-2-0-curved-token-bonding-in-curation-markets-1764a2e0bee5)*. Simon himself was interested in curation markets and hoped that bonding curves can be used to facilitate curation markets. The Bancor team independently used bonding curve as a model for token sales.

The original design of bonding curve includes the following features:

1. Mint (buy)
2. Burn (sell)

Later, Thibauld Favre wrote about *[Continuous Organizations](https://github.com/C-ORG/whitepaper)* (C-ORGs). A continuous organization is generating tokens on a bonding curve, and whenever there’s someone buying a token, a percentage of the fund is reserved on the curve to provide liquidity. Moreover, when a continuous organization has revenue, it’s supposed that it’s going to use some of the profit to buy tokens on the bonding curve so that other people can sell tokens at a better price (effectively equivalent to dividend distribution). Eventually a company called FiarMint was created to help startups issue stocks on a bonding curve, and backed by some renown venture capitals.

I attended one of DoraHacks' quadratic funding grant hackathons on [HackerLink](https://hackerlink.io/en/grant/BSC/1), and built a [bonding curve auction tool](https://www.binance.org/zh/blog/bsc-grants-spotlight-bcto-pentalaunch/) during the hackathon. Later the development was further supported by Dora Factory and became a permissionless token auction protocol called PentaLaunch.

It’s not hard to see that unlike the indifference curve from the AMM protocols like Uniswap, excessive capital on bonding curves will not create profits. So a bonding curve offers low capital efficiency if funds are partially kept on the curve to provide “possible” sell off (that's probably one of the reasons why bonding curves haven't been widely used!).

On the other hand, bonding curve supports a different kind of organization. Here is the characters of this kind of organization:

1. Infinite token supply
2. Programmatic token issuance and price curve
3. Permissionless token minting
4. Fair mint

A bonding curve simulates the fact that when an organization is issuing its tokens, the price of the token increases as the organization’s tokens are accepted by a larger community. While other auction schemes (like dutch auction, candle auction, fixed-price auction) are effective when a project sells tokens in a discrete manner at momentums, continuous funding on bonding curves is a long-term auction / minting mechanism.

## Continuous Common Good Funding (CF)

Assume there is a secondary market (e.g. a Uniswap liquidity pool) of a project token minted from a bonding curve. At any given supply, price discovery happens on the secondary market. There are two possibilities. First let’s say the price on the curve is Pc, the price on the secondary market is Ps.

1. Pc >= Ps

There will be no token minted from the bonding curve, therefore no further funding to the project. Since the curve price is higher, people can buy the project tokens from secondary markets.

2. Pc < Ps

An arbitrage opportunity emerges. When Pc < Ps, it can be profitable to mint new tokens from the curve. Therefore, new tokens will be minted from the curve. The newly minted tokens will likely be sold on the secondary market for profit until a new equilibrium is reached. Although minting new supply will likely create sell pressure on the secondary market, the increase of price on a bonding curve will limit the ability to mint new tokens from the curve. The higher the curve price is, the less tokens can be minted with a fixed amount of capital.

![Chart3-1备份.png](https://ssimg.frontenduse.top/article/2021/08/21/6c095f3bcee018c76f2080e84edda403.png)


![Chart4-1备份.png](https://ssimg.frontenduse.top/article/2021/08/21/452708c85c2f8adb3d137ece9a9cf652.png)

When an increase of price drives new supply to be minted, $\Delta$ represents additional capital required to actually mint compared to the same amount of supply minted previously. When the token supply is becoming large, $\Delta$ will be increasingly larger, requiring more fundings to admit a larger curve market cap.

![Chart2-2.png](https://ssimg.frontenduse.top/article/2021/08/21/0224d6ff7254ac87902e6ab4c573cee9.png)

In theory, any continuous function would work to serve as a bonding curve. There have been many discussions over types of bonding curves we can use in practice -- linear, quadratic, polynomial, logarithm, sigmoid, or even piecewise-defined functions.

A more steep curve will require more capital to mint new tokens, and suppress new supply.

## Continuous Public Good Funding

When a common good mints token from a bonding curve in a way as described above, the common good can be funded by the curve when people buy their project token from the bonding curve. We then call the common good a *Continuous Common Good*. The supply of the project token and mint price of the token are totally subject to the curve.

![Chart1-3.png](https://ssimg.frontenduse.top/article/2021/08/21/ddd6e7136dda3feb7fe35b67fbd79f14.png)

Therefore, extra tokens are minted only when the community agrees that the curve market cap is undervalued, then extra supply is minted. On a curve, if supply of project tokens moves from S0 to S1, then the curve market cap grows from M1 to M1 + M2.

Here is a recap of *Continuous Funding* of a *Continuous Common Good*:

1. All tokens are minted through bonding curves
2. Monotonically increasing curve (mostly)
3. Infinite token supply
4. Supply controlled by curve price
5. Directly funding projects
6. No pre-minted token

## Utility of Continuous Common Good Tokens (Project Tokens)

A common good funding mechanism can be independent of the nature of project tokens. A project token can be defined by the organization itself, based on the utility of the token. Some examples of simple project token utilities are:

- Governance Token
- Contribution Badges / Memes
- Protocol / Network Utilities
- Security Token
- More to be invented…

The utility of project tokens should be determined by the organization that builds the common good based on its actual utility.

## Examples of Continuous Common Goods

- Open Source Projects
- Non-profit organizations and public good projects will be natural BCOs. 
- Non-profit Organizations
- Blockchain Protocols
- DAOs

## Continuous Common Good Funding and Retroactive Public Good Funding

Continuous public good funding is a way to implement retroactive public good funding. 

In the article *[Retroactive Public Good Funding](https://medium.com/ethereum-optimism/retroactive-public-goods-funding-33c9b7d00f0c)*, a result oracle is used to distribute funds to a project token. If the project is a continuous common good, the result oracle can just use the funds to mint new tokens and funds will be distributed to the project automatically. In this case, continuous public good funding provides transparency and certainty.
