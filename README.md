# MegaETH Testnet Contract ABIs

Repository containing verified contract ABIs for MegaExplorer.

## Purpose
- Provide ready-to-use verified ABIs for MegaETH testnet contracts
- Maintain a standardized format for explorer verification
- Ensure compatibility with blockchain explorers' ABI validation

## To add new verified contracts:
1. Create an entry in `abis.json` with:
```json
"CONTRACT_ADDRESS": {0xDa672845f8f1B160030180d3977506aDf6ae3859
  "name": "ExactContractName",
  "abi": [/* Full unmodified ABI from compilation */]
}
```
2. Ensure ABIs are:
   - Exactly as deployed
   - Unmodified from compiler output
   - Properly formatted

## Verification Requirements
- ABIs must match deployed bytecode
- Contract names must exactly match deployed names
