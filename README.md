# SampleSC_Swisstronik

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.9;

contract Register {
    string public github;
    address public owner;

    struct Refferal {
        address referralAddress;
        string referralString;
    }

    Refferal[] public referrals;

    constructor() {  
        github = "arfiyan81";
        owner = 0xc10D0e70e6337a55BB330C7B06fF1c986697237d;
    }

    function addReferral(address _referralAddress, string memory _referralString) external {
        require(msg.sender == owner, "Only the owner can add referrals");
        referrals.push(Refferal(_referralAddress, _referralString));
    }

    function totalReferrals() public view returns (uint256) {
        return referrals.length;
    }
}
