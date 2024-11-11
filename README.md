# charter_Task-2_21BCE10369

# Robust Distribution System for Fiat to USDC Conversion

A robust, automated system enabling users to convert fiat (traditional currency) into USDC (a stablecoin) and seamlessly transfer it to their wallets. This system ensures secure distribution, accurate reconciliation, and efficient error handling for all fiat-to-USDC transactions.<br>
**Documentation**- <a href="https://hackmd.io/@QYDbn8-FRVi8k3IdjrW95Q/CharterLabs_Task-2">hackmd </a> <br>
**Flowchart**- <a href="https://excalidraw.com/#json=dQs5USSZXBONk1MoSTmP1,PcgjDZ9r1ADzak-smSgeow">excalidraw</a> 

## Features
- **Fiat-to-USDC Conversion**: Seamlessly converts fiat deposits into USDC.
- **Automated USDC Transfer**: Automatically transfers USDC to the user’s wallet once fiat is received.
- **Real-Time Deposit Detection**: Monitors incoming fiat deposits and initiates the conversion process.
- **Liquidity Management**: Ensures sufficient liquidity for smooth conversions by verifying USDC availability.
- **Transaction Monitoring**: Confirms successful USDC transfers with retry mechanisms in place.
- **Reconciliation System**: Tracks all deposits and transfers to ensure accurate mapping of fiat-to-USDC transactions.
- **Audit Logging**: Maintains a detailed audit log for each transaction to promote transparency and regulatory compliance.

## System Components
- **Fiat Bank**: Receives fiat deposits from users.
- **Deposit Detection Module**: Monitors and detects fiat deposits in the Fiat Bank.
- **Liquidity Manager**: Checks USDC availability in the Treasury or retrieves additional funds from the Liquidity Pool if needed.
- **USDC Treasury**: Holds USDC for distribution to users.
- **Transfer Service**: Initiates the blockchain transfer of USDC to the user’s wallet.
- **Transaction Monitor**: Monitors the status of the blockchain transaction to confirm successful delivery.
- **Reconciliation Ledger**: Tracks all fiat deposits and USDC transfers to ensure proper matching.
- **Audit Log**: Stores records of every transaction for auditing and transparency purposes.

## How It Works
1. **User Deposits Fiat**: The user sends fiat money to the Fiat Bank. The system waits for confirmation of the deposit.
2. **Fiat Deposit Detection**: Once the deposit is detected, the system verifies the amount and prepares to initiate the USDC transfer.
3. **Liquidity Check**: The Liquidity Manager checks if there’s enough USDC in the Treasury. If needed, it pulls from the Liquidity Pool.
4. **USDC Transfer**: The USDC is transferred to the user’s wallet via the Transfer Service.
5. **Transaction Confirmation**: The Transaction Monitor ensures that the USDC transfer is completed successfully on the blockchain.
6. **Reconciliation**: The system reconciles fiat deposits with the USDC transferred to ensure there are no discrepancies.
7. **Audit Logging**: All transaction data is stored in the Audit Log for future reference and auditing purposes.

## Installation

### Prerequisites
- Node.js (version 14 or higher)
- MongoDB or PostgreSQL (or preferred database) for storing transaction data
- Web3.js or ethers.js for interacting with Ethereum-based blockchain
- API or webhook integration with the Fiat Bank for detecting deposits
- Docker (optional for containerization)

### Steps
1. Clone the repository:
    ```bash
    git clone https://github.com/kashish281/fiat-to-usdc-conversion.git
    cd fiat-to-usdc-conversion

2. Install dependencies:
    ```bash
    npm install

3. Set up environment variables for database connection and API keys in a .env file.

4. Run the application:
    ```bash
    npm start


### Error Handling and Recovery
- **Transaction Failures:** If the USDC transfer fails, the Transaction Monitor will retry the transfer up to three times. After that, the transaction will be flagged for review.
- **Liquidity Shortage:** If there is not enough USDC in the Treasury, the Liquidity Manager will automatically pull from the Liquidity Pool to fulfill the transaction.
- **Deposit Mismatch:** If the fiat deposit amount does not match the USDC distribution, it will be flagged in the Reconciliation Ledger for review.


### Security Considerations
- Multi-Signature Treasury: The USDC Treasury is protected with multi-signature authorization for large transfers to ensure maximum security.
- Blockchain Transaction Monitoring: The system continuously monitors blockchain transactions to ensure that all transfers are successfully executed.
- API Security: The system securely communicates with the Fiat Bank API using encryption and secure authentication mechanisms.

### Future Enhancements
- Integration with more Fiat Banks: Expand support for additional banks to provide greater user access.
- Support for Other Stablecoins: Allow users to convert fiat into other stablecoins, such as USDT or DAI.
- Automated Tax Reporting: Implement tax reporting features for users to easily track their fiat-to-crypto transactions.


--------------------------------------------------------------------------------------------------
 
## Special Thanks

I would like to extend my gratitude to **CharterLabs** for giving me the opportunity to work on this project as a part of their Qualifier Round assignment-2. I appreciate the time and effort they took to evaluate my skills and provide me with a chance to showcase my abilities. Thank you for the experience.
<br>
**contact-kashishsin28@gmail.com**
