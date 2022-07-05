

***

![/Solidity_logo.svg](/Solidity_logo.svg)

### Learning Solidity

I am not too experienced with Solidity at the moment, and I do not intend to go further with it. This document will go over my knowledge of the Solidity language.

This document used version 0.8.4 of the Solidity programming language.

#### Comments in Solidity

Comments in Solidity are the same as comments in languages like C, C++, Java, C#, etc.

```solidity
// This is a single line comment
/* This is
a multi-
line comment */
/* This is
* also
* a multi-line
* comment */
```

#### Break keyword in Solidity

```solidity
break;
```

To this day, I am still not entirely sure what the `break` keyword does, but most languages support it.

_/!\ This example has not been tested yet, and may not work_

#### Hello World in Solidity

A hello world program in Solidity is pretty simple. It is not similar to any language I am currently familiar with.

```solidity
pragma solidity ^0.8.4;

contract HelloWorld {
    function render () public pure returns (string memory) {
        return 'Hello World';
    }
}
```

#### Contracts in Solidity

This example is taken from [Wikipedia: Solidity (revision 1094734727)](https://en.wikipedia.org/w/index.php?title=Solidity&oldid=1094734727)

I am only including it as an example, I don't know what it does, or how it works 100% of the way.

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.4;

contract Coin {
    // The keyword "public" makes variables
    // accessible from other contracts
    address public minter;
    mapping (address => uint) public balances;

    // Events allow clients to react to specific
    // contract changes you declare
    event Sent(address from, address to, uint amount);

    // Constructor code is only run when the contract
    // is created
    constructor() {
        minter = msg.sender;
    }

    // Sends an amount of newly created coins to an address
    // Can only be called by the contract creator
    function mint(address receiver, uint amount) public {
        require(msg.sender == minter);
        balances[receiver] += amount;
    }

    // Errors allow you to provide information about
    // why an operation failed. They are returned
    // to the caller of the function.
    error InsufficientBalance(uint requested, uint available);

    // Sends an amount of existing coins
    // from any caller to an address
    function send(address receiver, uint amount) public {
        if (amount > balances[msg.sender])
            revert InsufficientBalance({
                requested: amount,
                available: balances[msg.sender]
            });

        balances[msg.sender] -= amount;
        balances[receiver] += amount;
        emit Sent(msg.sender, receiver, amount);
    }
}
```

_/!\ This example has not been tested yet, and may not work_

#### Source

The majority of my Soliity knowledge comes from Wikipedia, and [this repository](https://github.com/leachim6/hello-world)

#### Other knowledge of Solidity

1. Solidity is a curly bracket language and semicolon language

2. Solidity is a contract-based language, designed for blockchain contracts. This is the reason why I don't plan to use the language anymore: it is platform-dependant, and bad for the environment.

3. Solidity uses the `.sol` file extension (side comment: GitHub is recognizing most of the source code so far as `Gerber Image` source code)

4. Solidity is a language recognized by GitHub

5. Solidity is owned by Etherium

6. Solidity is a "web3" language

7. No other knowledge of Solidity at the moment.

***

### File info

<details open><summary><p lang="en"><b><u>Click/tap here to expand/collapse this section</u></b></p></summary>

**File type:** `Markdown (*.md *.mkd *.mdown *.markdown)`

**File version:** `1 (2022, Monday, July 4th at 6:12 pm PST)`

**Line count (including blank lines and compiler line):** `182`

**Current article language:** `English (EN_USA)` / `Markdown (CommonMark)` / `Solidity 0.8.9` / `HTML5 (HyperText Markup Language 5.3)`

**Encoding:** `UTF-8`

**All times are UTC-7 (PDT/Pacific Time)** `(Please also account for DST (Daylight Savings Time) for older/newer entries up until it is abolished/no longer followed)`

_Note that on 2022, Sunday, March 13th at 2:00 am PST, the time jumped ahead 1 hour to 3:00 am._

**You may need special rendering support for the `<details>` HTML tag being used in this document**

</details>

***

## File history

<details><summary><p lang="en"><b>Click/tap here to expand/collapse the file history section for this project</b></p></summary>

<details><summary><p lang="en"><b>Version 1 (2022, Monday, July 4th at 6:12 pm PST)</b></p></summary>

**This version was made by:** [`@seanpm2001`](https://github.com/seanpm2001/)

> Changes:

- [x] Started the file
- [x] Added the title section
- [X] Added the `Learning solidity` section
- - [x] Added the `Comments in Solidity` section
- - [x] Added the `Break keyword in Solidity` section
- - [x] Added the `Hello World in Solidity` section
- - [x] Added the `Contracts in Solidity` section
- [x] Added the `Source` section
- [x] Added the `Other knowledge of Solidity` section
- [x] Added the `file info` section
- [x] Added the `file history` section
- [ ] No other changes in version 1

</details>

</details>

***
