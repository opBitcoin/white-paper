**opBitcoin**
----------------------------------------------

opBitcoin is a Mineable Token for Ethereum, built as an example of how you can fairly launch a token to a community.

<br>

***This is hightly eperiemental code!!***


<br>

**Noteable Features**
```
▸ Born June 2022.
▸ No Premine.
▸ No ICO.
▸ Tokens are created in exchange for SHA3 Proof-of-Work submitted to the contract.
▸ The contract auto-adjusts difficulty based on hashpower.
▸ Trustless with Zero Human Authority or Contract Owner.
```


<br>


--------------------------------
<br>

**ERC20 COMPATABLE**

opBitcoin is the triple threat taking the great aspects of 0xbitcoin, Ethereum, & Bitcoin and making it mineable on a chain with much cheaper fees, this will make mining and trading much more accessable to everyday users. By default opBitcoin works with all defi exhancges and protocals and can be traded p2p with anyone in the world. 




<br>


--------------------------------
<br>

**HOW TO MINE**

opBitcoin uses a simple Keccak256 (Sha3) algorithm using the following methodology:

``keccak256(nonce, minerEthAddress, challengeNumber) < difficultyTarget``

<br>

We have built a custom python miner that can be used at launch to solo mine and are developing tools to mine as a pool, we will also encourage the community to build and tools that can be used for the protocal.

*Objectives*
<br>

```
▸ Create a new inivative way projects can airdrop tokens safe from sybil attacks.
▸ 5 opBitcoin rewarded per block mined.
▸ Blocks should be mine once aroximatly once per 5 mins.
▸ Difficulty will adjust base on how quickly blocks are being mined.
▸ Anyone can mine using a simple python script and use the opPool to get an exqual share of all rewards mined collectivly.
▸ Make sure enough people know about the miner before launch.
▸ Works with current ecosystem.
```

<br>


--------------------------------
<br>

**STRONG ROOTS NEW CODE**

opBitcoin is based on the 0xBitcoin contract but heavily updated to match todays erc20 standards.

https://0xbitcoin.org/#/

<br>
--------------------------------
 <br>
 
**FAQ**

*Does opBitcoin have its own Blockchain?*

> No.


*Why are there times when a lot of mints get reverted?*

> If difficulty is low compared to over hashrate and multiple valid solutions were submitted to the contract in a very short amount of time only the first will be selected.

*How does pool mining work with opBitcoin?*

> The same way that pool mining works for classic Bitcoin, except opBitcoin pools must pay gas fees to the Optimistic network.

*How does the difficulty update?*
```
    function _reAdjustDifficulty() internal {
        uint ethBlocksSinceLastDifficultyPeriod = block.number - latestDifficultyPeriodStarted;


        //we want miners to spend 5 minutes to mine each 'block', about 60 ethereum blocks = one 0xbitcoin epoch
        uint epochsMined = _BLOCKS_PER_READJUSTMENT; //256

        uint targetEthBlocksPerDiffPeriod = epochsMined * 100; 

        //if there were less eth blocks passed in time than expected we will make it harder to mine to slow down emmsions
        if(ethBlocksSinceLastDifficultyPeriod < targetEthBlocksPerDiffPeriod)  ///    blocks past < 500
        {
            //make it harder
            miningTarget = miningTarget / 2;   //increase difficulty
            
          
        }else{
            //make it easier
            miningTarget = miningTarget * 2;   //decrease difficulty
            
        }

        latestDifficultyPeriodStarted = block.number;

    }
```

*Will there be a reward halvening event and when?*

> Yes, every 210000 mints.


