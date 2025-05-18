# certificate-contract-assignment-anjitha-0123
certificate-contract-assignment-anjitha-0123 created by GitHub Classroom

## Smart Contract
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.30;

contract CertiApp{

    struct Certificate{
        string name;
        string course;
        string grade;
        string date;
    }

    address admin;
    address admin2;

    constructor(){
        admin=msg.sender;
    }

    mapping (uint256=>Certificate) public Certificates;
    mapping (uint256=>bool) Issued;

    function setAdmin(address _admin) public{
        require(msg.sender==admin,"Only admin can perform this..");
        admin2 = _admin;
    }

    modifier onlyAdmin(){
        require(msg.sender==admin || msg.sender==admin2,"Unauthorized access....");
        _;
    }


    function issue(uint256 _id,string memory name,string memory course,string memory grade,string memory date) public onlyAdmin {
        require(!Issued[_id], "Already Issued");
        Certificates[_id] = Certificate(name,course,grade,date);
        Issued[_id]=true;
    }

    
}

```

## Link for Verify and Publish

```
https://sepolia.etherscan.io/verifyContract-solc?a=0xaf33a2618ac98e26011795d569a0d1706e18b439&c=v0.8.30%2bcommit.73712a01&lictype=3
```
## Link of verified contract
```
https://sepolia.etherscan.io/verifyContract-solc?a=0xaf33a2618ac98e26011795d569a0d1706e18b439&c=v0.8.30%2bcommit.73712a01&lictype=3
```
