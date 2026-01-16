# Root Cause Analysis – Wallet Balance Discrepancy

## Incident Summary
- **Incident Type:** Transaction Reversal Display Issue
- **Severity:** SEV-2
- **Affected Channel:** Mobile Banking Application
- **Detection Method:** Customer Complaint
- **Duration:** ~45 minutes

## Impact
- Customer confusion due to missing reversal record
- Risk of duplicate refund requests
- Escalation to Tier 2 support

## Timeline
| Time (UTC) | Event |
| 10:05 | Customer complaint received |
| 10:10 | Transaction and ledger investigation started |
| 10:25 | Backend balance confirmed correct |
| 10:35 | Root cause identified |
| 10:50 | Customer communication completed |

## Root Cause
The transaction reversal was successfully processed by the backend wallet service. However, a timeout occurred during the UI notification callback, preventing the reversal record from being displayed in the mobile application.

## Contributing Factors
- Callback timeout configuration
- Dependency on asynchronous UI updates
- Lack of immediate alert for callback failures

## Resolution
- Verified wallet balance integrity at database level
- Confirmed no financial loss occurred
- Escalated UI sync issue to application team
- Monitored subsequent transactions

## Preventive Actions
- Improved callback monitoring
- Added alerting for failed UI notifications
- Updated troubleshooting documentation

## Lessons Learned
Backend validation should always precede UI-based conclusions in transaction investigations.
