# MegaEth ABIs 

This repository contains Application Binary Interfaces (ABIs) for MegaEth smart contracts.

## Adding Your ABI

To add your contract ABI to this repository:

1. Create a new JSON file in the `contracts/` directory
2. Name it descriptively (e.g., `my-contract.json`)
3. Use this format:

```json
{
  "name": "YourContractName",
  "abi": [
    {
      "inputs": [...],
      "name": "functionName",
      "outputs": [...],
      "stateMutability": "view|pure|payable|nonpayable",
      "type": "function|event|error|constructor"
    }
  ]
}
```

4. Update `abis.json` to include your contract:

```json
{
  "0xYourContractAddress": {
    "name": "YourContractName",
    "file": "contracts/your-contract.json"
  }
}
```

5. Submit a pull request

## Usage

Load any contract ABI directly:

```javascript
const fs = require('fs');
const abi = JSON.parse(fs.readFileSync('./contracts/your-contract.json', 'utf8'));
const contract = new web3.eth.Contract(abi.abi, contractAddress);
```

## Validation

This repository includes automated validation via GitHub Actions that validates every pull request.

The validation ensures:
- All contract files have valid JSON structure
- Required fields (`name`, `abi`) are present
- ABI items have valid types (`function`, `event`, `error`, `constructor`, `fallback`, `receive`)
- Contract index is consistent with files
- No duplicate addresses
- All addresses have valid format
