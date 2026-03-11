GrantLedger Demo Walkthrough
Overview

This document explains how the GrantLedger prototype works during a demonstration. The goal of the demo is to show how grant funds can be securely managed and released using a Soroban smart contract on the Stellar network.

The demonstration focuses on the core concept of grant escrow with controlled fund release.

Demo Scenario

For this demonstration, we simulate a simple grant agreement between three participants.

Participants in the demo:

Donor
Provides funding for a development project.

NGO
Implements the project and receives funds.

Verifier
Confirms that the project milestone has been completed.

The grant will be released in stages based on verification.

Demo Objective

The demo aims to show three main capabilities:

• Creating a grant agreement on-chain
• Locking funds in a smart contract escrow
• Releasing funds after verification

This demonstrates how GrantLedger improves transparency and accountability in grant funding.

Demo Environment

The prototype is deployed on the Stellar Testnet using Soroban smart contracts.

Tools used in the demo may include:

• Soroban CLI
• Stellar Testnet accounts
• A simple interface or command line interaction

All transactions are executed on the test network to simulate real blockchain behavior.

Step 1 — Create a Grant

The donor initializes a new grant using the smart contract.

Information provided:

• Donor address
• NGO address
• Verifier address
• Total funding amount

The smart contract stores this information and creates a new grant record.

Outcome:

A grant agreement is now registered on-chain.

Step 2 — Lock Grant Funds

The donor transfers the grant funds to the smart contract escrow.

This means the funds are no longer controlled directly by the donor or the NGO.

Instead, they are managed by the contract according to predefined rules.

Outcome:

The funds are now securely locked and cannot be withdrawn without authorization.

Step 3 — Project Progress

The NGO begins implementing the project associated with the grant.

In a real scenario, this stage may include:

• Building infrastructure
• Delivering services
• Completing project milestones

For the demo, this step is simulated.

Step 4 — Verification

The verifier reviews the project progress and confirms that the milestone has been completed.

Once the verifier approves the milestone, they trigger the contract function responsible for releasing funds.

Outcome:

The smart contract verifies the authorization of the verifier.

Step 5 — Release Funds

After verification, the contract releases a portion of the funds to the NGO.

The contract checks two conditions:

• The verifier is authorized
• The amount released does not exceed the total grant amount

If both conditions are satisfied, the funds are released.

Outcome:

The NGO receives the funds associated with the completed milestone.

Step 6 — View Grant Status

Users can query the contract to view the current state of the grant.

Information returned includes:

• Grant participants
• Total grant value
• Amount already released

This allows donors and stakeholders to monitor funding progress.

Key Takeaways From the Demo

The demo illustrates several advantages of the GrantLedger approach.

Transparency

All grant transactions are recorded on the blockchain.

Controlled funding

Funds are released only when authorized conditions are satisfied.

Improved accountability

Donors gain confidence that funds are used according to project milestones.

Limitations of the Prototype

This demonstration focuses only on the core concept of programmable grant escrow.

The prototype does not yet include:

• Full milestone management
• A production user interface
• Advanced reporting dashboards

These features are planned for future development.

Conclusion

The demo shows how GrantLedger can improve grant funding transparency using blockchain technology. By automating fund control through smart contracts, the platform reduces the risk of misuse and increases trust between donors and implementing organizations.
