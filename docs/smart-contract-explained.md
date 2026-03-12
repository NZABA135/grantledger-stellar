# GrantLedger Smart Contract Explanation

## Overview
The GrantLedger smart contract is responsible for managing grant funding in a transparent and controlled way. It acts as a programmable escrow that stores grant information and ensures that funds are released only under defined conditions.

The contract is written in **Rust using the Soroban SDK** and deployed on the **Stellar network**.
The purpose of the contract is to automate trust between donors and grant recipients.

# Core Concept
Traditional grant systems rely on manual oversight and trust between institutions. GrantLedger replaces this with programmable logic.
The smart contract controls three key processes:
• Grant creation
• Fund control through escrow
• Conditional fund release
This allows donors to ensure that funds are distributed according to project progress.

# Roles in the Contract
The contract defines three participants.

## Donor
The donor is the organization or individual providing the funding.
Responsibilities:
• Creates a grant
• Defines the recipient organization
• Specifies the total funding amount
The donor must authorize the creation of the grant within the smart contract.

## NGO (Recipient)
The NGO is the organization implementing the funded project.
Responsibilities:
• Receives funding once conditions are satisfied
• Executes project milestones
The NGO does not directly control the release of funds.

## Verifier
The verifier is responsible for confirming project progress.
Responsibilities:
• Approves the release of funds
• Ensures that milestone conditions have been met
The verifier provides an additional layer of accountability.

# Contract Data Structure
The contract stores grant information in a structure called `Grant`.
The structure contains:
• Donor address
• NGO address
• Verifier address
• Total grant amount
• Amount already released
This information is stored in the smart contract storage on-chain.

# Smart Contract Functions
The contract exposes three main functions.

## 1. Create Grant
Function:

```
create_grant()
```
Purpose:
Creates a new grant record in the smart contract.
This function:
• Stores the donor address
• Stores the recipient organization
• Stores the verifier
• Records the total funding amount
Only the donor is allowed to execute this function.

## 2. Release Funds
Function:
```
release_funds()
```
Purpose:
Releases a portion of the grant funds to the recipient organization.
Conditions enforced:
• Only the verifier can approve fund release
• The released amount cannot exceed the total grant amount
This ensures that funds cannot be withdrawn arbitrarily.

## 3. Get Grant Information
Function:
```
get_grant()
```

Purpose:
Returns the current state of the grant.
This allows users or applications to view:
• Grant participants
• Total funding amount
• Amount already released
This function improves transparency and enables monitoring tools.

# Security Mechanisms
Several mechanisms ensure the contract behaves securely.

## Authorization
Each critical function requires authentication.
Examples:
• Donor must authorize grant creation
• Verifier must authorize fund release
This prevents unauthorized users from modifying contract state.

## Escrow Control
Funds remain locked within the smart contract until the correct conditions are satisfied.
This prevents misuse of funds.

## Controlled Release
The contract checks that released funds never exceed the original grant amount.
This prevents overspending or malicious withdrawal attempts.

# Contract Lifecycle
The lifecycle of a grant within the contract follows a simple sequence.
1. A donor creates a grant in the smart contract
2. Funds are transferred to the contract escrow
3. The project progresses
4. A verifier authorizes fund release
5. Funds are distributed to the NGO
This process ensures that grant funding remains transparent and controlled.

# Limitations of the Current MVP

The current implementation is intentionally simple because it is designed as a **minimum viable prototype**.
Current limitations include:
• Single grant storage per contract instance
• External milestone verification logic
• Basic authorization model
These limitations are acceptable for an early-stage prototype.

# Future Improvements
Future versions of the smart contract may include:
• Multiple grant management within a single contract
• On-chain milestone tracking
• Automated milestone verification systems
• Multi-verifier approval mechanisms
These improvements will make the platform more robust and scalable.

# Conclusion
The GrantLedger smart contract provides the foundation for a transparent grant funding system. By combining programmable escrow with role-based authorization, the contract ensures that funding is distributed responsibly and according to verified progress.
