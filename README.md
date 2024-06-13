# Solidity-Token
In this project we have created a token includes a hash function with sample transaction
// SPDX-License-Identifier: MIT
contract Token{
  string public TokenName = "Abhinav";
  string public TokenAbbrv = "ABHI";
  uint public totalSupply = 0;

  mapping(address => uint) public balances;
  
  function mint(address _to, uint _value)public {
    totalSupply += _value;
    balances[_to] += _value;
  }
  function burn(address _from, uint _value)public {
    if (balances[_from] >= _value){
     totalSupply -= _value;
     balances[_from] -= _value;
    }
  }
}
