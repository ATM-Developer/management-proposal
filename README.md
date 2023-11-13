# management-proposal
ATM management contract proposal

Management Contract Method Invocation Description：

1.addNodePropose 
  For proposals that add node addresses, only the added node addresses have the right to propose and vote.
  For example, add a new node address：0xC82bE99C4Cba83C30C2236D561f0741B264529C6
    <img width="531" alt="image" src="https://github.com/ATM-Developer/management-proposal/assets/51522215/d9d3c457-f1e8-4e1e-a644-2d0981021e79">

2.deleteNodePropose
  Delete the node address proposal, the deleted node address will no longer have the power of proposal and voting.
  For example, delete a node address：0xC82bE99C4Cba83C30C2236D561f0741B264529C6
  <img width="485" alt="image" src="https://github.com/ATM-Developer/management-proposal/assets/51522215/6df851a8-ca38-459a-a528-7dfbf777f2ff">

3.excContractPropose
  A proposal to perform a contract operation, used to call the relevant methods of the corresponding contract
  For example, calling the setMinter method of a LUCA contract，
      _targetAddr：The contract object to invoke
      _data：The call data for the contract to be executed
  <img width="683" alt="image" src="https://github.com/ATM-Developer/management-proposal/assets/51522215/4cf51f4c-bedd-472d-bd68-32a273ad6bab">

4.updateProxyAdminPropose 
  Change the address of the contract admin. This admin is the permission address of the upgrade contract. This method needs to be called only when you change the new management contract.

5.updateProxyUpgradPropose 
  Upgrade the logical contract of the corresponding contract
  For example, upgrading the logical contract of an Incentive contract
      _targetAddr：The contract object to invoke
      _addr：New Logical Contract Address
  <img width="652" alt="image" src="https://github.com/ATM-Developer/management-proposal/assets/51522215/f4710b21-61fe-4826-ac30-c21e3023a1ad">

6.vote
  Vote for the specified proposal. If the number of votes exceeds half of the nodes, the corresponding operation is performed.
    _proposalId：Proposal ID
