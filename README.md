# Foundry ERC20 Token

This repository contains the Solidity smart contracts for the Foundry ERC20 Token and related test scripts.

# Table of Contents

- [Foundry ERC20 Token (Version F23-1)](#foundry-erc20-token-version-f23-1)
  - [Contracts](#contracts)
    - [ManualToken.sol](#manualtokensol)
    - [OurToken.sol](#ourtokensol)
    - [OurTokenTest.sol](#ourtokentestsol)
    - [DeployOurToken.sol](#deployourtokensol)
  - [Usage](#usage)
  - [License](#license)
  - [Contributions](#contributions)
  - [Disclaimer](#disclaimer)

## Contracts

### ManualToken.sol

```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.18;

contract ManualToken {
    // ... (details of ManualToken contract)
}
```

The `ManualToken` contract is a basic ERC20 token with a fixed total supply.

### OurToken.sol

```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.18;

import {ERC20} from "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract OurToken is ERC20 {
    constructor(uint256 initialSupply) ERC20("OurToken", "OT") {
        _mint(msg.sender, initialSupply);
    }
}
```

The `OurToken` contract is an ERC20 token that extends the OpenZeppelin `ERC20` implementation.

### OurTokenTest.sol

```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.18;

import {Test} from "forge-std/Test.sol";
import {DeployOurToken} from "../script/DeployOurToken.s.sol";
import {OurToken} from "../src/OurToken.sol";

// ... (details of OurTokenTest contract)
```

The `OurTokenTest` contract contains tests for the `OurToken` contract and is implemented using the `Test` library.

### DeployOurToken.sol

```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.18;

import {Script} from "forge-std/Script.sol";
import {OurToken} from "../src/OurToken.sol";

// ... (details of DeployOurToken contract)
```

The `DeployOurToken` contract is responsible for deploying the `OurToken` contract with an initial supply. It provides a convenient way to initialize and deploy the token contract.

## Usage

To use these contracts and test scripts, follow these steps:

1. Deploy the `OurToken` contract using the `DeployOurToken` contract, which will create an instance of the `OurToken` contract with an initial supply.

2. Use the `ManualToken` contract or the `OurToken` contract as needed for your project. The `OurToken` contract is an ERC20 token that you can interact with using standard ERC20 functions.

3. Run the tests defined in the `OurTokenTest` contract to ensure the functionality of the `OurToken` contract.

## License

These smart contracts are released under the MIT License.

## Contributions

Contributions to improve these contracts or documentation are welcome. Feel free to open issues or submit pull requests.

## Disclaimer

These contracts are provided as-is and without warranty. Use them at your own risk. The authors and contributors are not responsible for any loss or damage caused by the use of these contracts.
```
