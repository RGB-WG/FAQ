# Assignment

**Assignment** is an owned right \(defined by _owned right type_ `u8` value\) + state data + UTXO, which forms a single-use-seal definition when it is assigned that owned right.  

**So: nothing can prevent some given UTXO from having multiple assignments, of different owned right type, and even for each owned right type there might be multiple assignments.**

UTXO &lt;-one to many-&gt; owned right type &lt;-one to many-&gt; assignment of some state:

* assign an inflation right to it \(one\)
* assign ownership right of 100 of USDT
* assign ownership right of 10 Apple shares under different contract
* assign ownership right of 10000 of USDT again

This is a very bad situation, but we can’t prevent it from happening. Especially if you assign different types of owned rights under **the same contract** you may not be able to create a state transition without losing some of the rights or assets \(since state transitions have a very strict set of owned rights type for which they can close seals\). That is why we have created **“split rights" state transition**, which does only one thing - gives the ability to split those mixed rights into different UTXOs. Management of these UTXOs stays an opened question.
