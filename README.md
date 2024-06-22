This simple smart contract creates a token with basic minting and burning functionality. It ensures that:
-New tokens can be created and assigned to an address.
-Tokens can be destroyed from an address, provided the address has sufficient balance.
-The total supply is updated accordingly with minting and burning operations.
1. Public variables
force
Copy code
string public TokenName = "TUSHAR";
string public TokenAbbrv = "TUSHI";
public uint TotalSupply = 0;
TokenName: This is a public variable that stores the name of the token, which is "TUSHAR".
TokenAbbrv: This is a public variable that stores the token abbreviation, which is "TUSHI".
TotalSupply: This is a public variable that controls the total supply of the token. It is initially set to 0.
2. Mapping
severity
Copy the code
mapping (address => ​​uint) public balances;
balances: This is a mapping of addresses to unsigned integers (uint). It tracks the balance of each address. It's basically a ledger that stores the number of characters in each address. 3. Mint Function
solidity
Copy the code
function mint(address _address, uint _value) public {
TotalSupply += _value;
balance[_address] += _value;
}
mint: This function can be used to create new tokens.
Parameters:
_address: Address where newly minted tokens will be credited.
_value: number of characters.
Logic:
Increases TotalSupply by _value.
Increases _address balance by _value.
4. Burn function
solidity
Copy the code
function burn(address _address, uint _value) public {
if (balances[_address] >= _value) {
TotalSupply -= _value;
balance[_address] -= _value;
}
}
burning: This function allows you to destroy characters.
Parameters:
_address: the address from which the tokens will be burned.
_value: number of characters to burn.
Logic:
Checks if the balance of _address is greater than or equal to _value.
If true, decrements TotalSupply by _value.
Decreases _address balance by _value.
Explanation
The contract is initialized with the token "TUSHAR" and the abbreviation "TUSHI" and a total supply of 0.
Balance mapping keeps track of how many tokens each address has.
The mint function allows you to add new tokens to the entire supply and assign them to a specific address.
The burn function allows you to remove tokens from the entire store and subtract from a given address, but only if there are enough burn tokens at that address..
