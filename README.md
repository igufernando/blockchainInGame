# Palm
An example ERC721 smart contract with opt-in centralized modification for supporting real-time blockchain-based video games.

## Exchange Trust Model

Typically, real-time video games simulate their world using a fixed simulation timestep known as the "tick rate." For example, Valve Corporation's popular multiplayer first-person shooter _Counter-Strike: Source_ supports servers with a tick rate of 66Hz.<sup>1</sup> That is, the game servers update state 66 times per second. Game logic, physics simulations, and player input signals are all processed in frequent, discrete time quanta. These state updates are decoupled from the client-side rendering frame rate, allowing for smooth rendering to be maintained across a variety of tick rates.

image1

Real-time games can update their state more frequently than transaction times for Ethereum can currently support. The all-time peak transaction rate for the Ethereum network was 15.6 transactions per second.<sup>2</sup> Even games with less frequent tick rates like Epic Games' _Fortnite_ outpace this peak transaction rate.<sup>3</sup>

It is currently infeasible for a real-time game to track and update its state directly on Ethereum, even if its tick rate was dramatically reduced. The time it takes to interact with Ethereum and wait for a miner to commit a state update transaction to the chain is variable. A fixed tick rate is not currently possible to maintain, which makes processing logic, physics, and input much more difficult. Lastly, operating the game server would require constantly burning gas for small, short-lived updates and would be very costly.

Clearly, traditional servers are more appropriate than Ethereum for handling the frequent game state updates required to simulate a multiplayer game. What role then, if any, can Ethereum play in video games?

## Using Assets in Multiple Games

## Trustless Economy

["GameExchange"](https://ropsten.etherscan.io/address/0x5e469871e80474e231af5c252471b6d6817fc990)
["RivalExchange"](https://ropsten.etherscan.io/address/0x09099905e4f5e8383ee33b843eeea014be4f8037)
["SwapAndBurn"](https://ropsten.etherscan.io/address/0x6e6af08a1fa2fd0837dbdd01448c8ec36f63ec29)

## References
The following resources are important references for the information presented in this project:
1. [Valve Networking Guide](https://developer.valvesoftware.com/wiki/Source_Multiplayer_Networking), an excellent primer on multiplayer game networking with specifics for Valve titles.
2. [Ethereum Transaction Rate](https://etherscan.io/chart/tx), as of 4/25/2018 the rate peaked at 1,349,890 transactions on 1/4/2018.
3. [Battle Royale Tick Rates](https://www.youtube.com/watch?v=u0dWDFDUF8s), an analysis of the tick rates in several multiplayer games of the battle royale genre.

## Supporting Projects
I'd like to thank the following guides, tools, and projects which greatly supported the development of Palm:
- [The Online ABI Encoding Tool by HashEx](https://abi.hashex.org/), to convert constructor parameters to ABI encoding for verification.
- [Etherscan](etherscan.io), for providing an easy interface to validate deployment and contract state.
- [JavaScript Promises in Web3](http://shawntabrizi.com/crypto/making-web3-js-work-asynchronously-javascript-promises-await/), this article provides an overview on converting Web3 calls to Promises seamlessly.
