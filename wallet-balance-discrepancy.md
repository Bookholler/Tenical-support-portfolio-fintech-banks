# Wallet Balance Discrepancy After Failed Transaction

## Role
Technical Support Engineer (FinTech / Digital Banking)

## Background
A customer reported that their wallet balance increased after a failed transaction, but no reversal record was visible in the mobile banking application. This raised concerns about data integrity and potential duplicate refunds.

## Impact
- Customer confidence affected
- Risk of duplicate transaction disputes
- Escalation to Tier 2 support

## Investigation
- Queried transaction and wallet ledger tables using SQL
- Reviewed backend transaction processing logs
- Verified API responses between transaction switch and wallet service
- Cross-checked reconciliation records

## Root Cause
The transaction reversal was successfully processed at the backend, but a timeout occurred during the UI notification callback. This prevented the mobile application from displaying the reversal record, even though the wallet balance was correctly updated.

## Resolution
- Confirmed balance correctness at the database level
- Communicated findings to customer-facing teams
- Escalated UI synchronization issue to the application team
- Monitored subsequent transactions for consistency

## Tools Used
- SQL Server
- Application Logs
- API Monitoring
- ManageEngine

## Outcome
- Prevented duplicate refund processing
- Restored customer trust
- Improved internal understanding of UI vs backend discrepancies

## Key Takeaway
Backend verification is critical before concluding transaction failures in digital banking systems.
