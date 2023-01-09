---
title: Ownership transfer in ERC721

---

Here's an example of ownership transfer of the [[web3/ethereum/ERC721]] token (from [CryptoZombies](https://cryptozombies.io/)):

```solidity
contract ZombieOwnership is ZombieAttack, ERC721 {

  mapping (uint => address) zombieApprovals;

  function balanceOf(address _owner) external view returns (uint256) {
    return ownerZombieCount[_owner];
  }

  function ownerOf(uint256 _tokenId) external view returns (address) {
    return zombieToOwner[_tokenId];
  }

  function _transfer(address _from, address _to, uint256 _tokenId) private {
    ownerZombieCount[_to]++;
    ownerZombieCount[_from]--;
    zombieToOwner[_tokenId] = _to;
    emit Transfer(_from, _to, _tokenId);
  }

  function transferFrom(address _from, address _to, uint256 _tokenId) external payable {
    require (zombieToOwner[_tokenId] == msg.sender || zombieApprovals[_tokenId] == msg.sender);
    _transfer(_from, _to, _tokenId);
  }

  function approve(address _approved, uint256 _tokenId) external payable onlyOwnerOf(_tokenId) {
    zombieApprovals[_tokenId] = _approved;

    emit Approval(msg.sender, _approved, _tokenId);
  }
}
```

In [[web3/solidity/approve]], we want to make sure only the owner of the token can give someone approval to take it. So we need to add the `onlyOwnerOf` modifier to `approve` (`onlyOwnerOf` is a custom [[web3/solidity/modifiers|modifier]]). Then we need to set `zombieApprovals` [[web3/solidity/mapping]] for `_tokenId` equal to the `_approved` address. Ultimately, the `Approval` event needs to be fired to comply with [[web3/ethereum/ERC721]] standard.

It also would be helpful to do:

- extra checks to prevent [[web3/ethereum/burning-token]]
- prevent [[web3/solidity/overflows]] and underflows
- prevent the year 2038 problem (xd but why not)
