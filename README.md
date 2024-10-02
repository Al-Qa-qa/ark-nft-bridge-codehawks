# Ark NFT Bridge Contest CodeHawks

This is the reposatory of the Issues subitted by [Al-Qa'qa'](https://x.com/Al_Qa_qa) on [Ark NFT Bridge](https://x.com/ArkProjectNFTs) contest on [Codehawks](https://www.codehawks.com/)

This is a new strategy for me where I categorized findings according to there Flow. It is like Separating the hope codebase into chunks and focusing on each chunk separately, similar to Divide and Conquer algorithms.

Using this methodology I managed to win the contest reaching 1st place, finding all High findings in the contest (5 Highs), 3/6 Medium findings, and 5/6 Low findings, besides other findings that were downgraded to informational, and some findings were invalid.

The process is simple.

1. Don't revise the whole codebase at once, this is a Bridge contract focused on Bridging NFTs between Ethereum and Starknet. First, check the flow from Ethereum to Starknet. Then, from Stakrknet to Ethereum, etc...

2. At this point, there are some Bugs you will find, maybe the obvious ones, store them in you Private GitHub repo categorizing them into there flow.

3. After revising all flow of execution, you should have understood all the codebase. You can make a hole review for it as total in that point.

4. After revising each flow separately, getting bugs, and revising the Hole Codebase, you should take each flow separately and dig too deep in it. Focusing in that flow itself, besides putting other flows of executions in your eyes, as the complex can happen in Flow1 if something occurs in Flow2, so you should go deep into each flow, to get all bugs it has that will occur if any state changes occur in the other flows.

---

I will explain each folder, where each folder explains a flow of execution or a separatable chunk in a codebase that can be revised alone.

- `L1 -> L2 Pack`: Has all issues that relate to Bridging NFTs from L1 (Ethereum) to L2 (Starknet)
- `L2 -> L1 Pack`: Has all issues that relate to Bridging NFTs from L2 (Starknet) to L1 (Ethereum)
- `Initializer Pack`: Since The Protocol is an Upgradable contract, I made the upgrading logic from the L1 Bridge (Ethereum Bridge) in a single flow
- `Stark Init Pack`: Same in L2 Bridge (Starknet Bridge) it is an Upgradable contract too, so I made its upgradability process in another flow
- `TokenUtils Pack`: Before Bridging Tokens, there are functions that check the collection type ERC721, metadata, etc..., I separated its logic in a single folder
- `Canceling Messages`: When Bridging NFTs from L1 to L2 the message can revert on L2 side, so there is a feature in Starknet Messaging core protocol to cancel your message, I separated it to.
- `Collection Upgrade`: The collections (NFT collections) that are made in the destination chain are upgradable (this is the design of Ark Bridge), so upgrading collection has some functions like changing ownership, upgrading implementation contracts, deploying new collections, etc... I separated it too.
- `WhiteListing Logic pack`: Ark Bridge has WhiteListing logic that makes only whitelisted collections are able to get Bridged, I separated this too in a separate folder as the logic of whitelisting new NFTs was a bit complex.
- `Others`: Other issues that can't get grouped in a single flow or a single category, I made them in this folder.

---

So in brief, the Execution flow strategy is not new, but in this new strategy we are not stuck with just execution flows, we are trying to separate our codebase into pieces that don't have a direct relationship with each other. Using this method we can focus more on a single piece of code and get all the issues it contains.

After understanding the full codebase, and storing the issues, we will have a clean codebase that doesn't have `audit` tage on every line, being able to revise our issues in a single piece of code, revising the Hole codebase will be easy as we will revise a single flow/piece of code deeply and try to know if another flow will affect it (this is done after understanding all of the codebases).

And thats it, hope this repo is useful to you guys.

- Twitter: [@Al_qa_qa](https://x.com/Al_Qa_qa)
- Audit Portfolio: https://github.com/Al-Qa-qa/audits

