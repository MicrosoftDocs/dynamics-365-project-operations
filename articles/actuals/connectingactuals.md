The following table shows the records in the Transaction connection entity for the preceding workflow.

| Event                          | Transaction 1                 | Transaction 1 role | Transaction 1 type           | Transaction 2                | Transaction 2 role | Transaction 2 type |
|--------------------------------|-------------------------------|--------------------|------------------------------|------------------------------|--------------------|--------------------|
| Time Entry Submission          | Journal Line (Sales) GUID     | Unbilled Sales     | msdyn_journalline            | Journal Line (cost) GUID     | Cost               | msdyn_journalline  |
| Time Approval                  | Unbilled Actual (Sales) GUID  | Unbilled Sales     | msdyn_actual                 | Cost Actual(cost) GUID       | Cost               | msdyn_actual       |
| Invoice Creation               | Invoice Line Detail GUID      | Billed Sales       | msdyn_invoicelinetransaction | Unbilled Sales Actual GUID   | Unbilled Sales     | msdyn_actual       |
| Invoice Confirmation           | Reversing Actual GUID         | Reversing          | msdyn_actual                 | Original unbilled sales GUID | Original           | msdyn_actual       |
| Billed Sales GUID              | Billed Sales                  | msdyn_actual       | Unbilled Sales Actual GUID   | Unbilled Sales               | msdyn_actual       |                    |
| Draft Invoice Correction       | Invoice Line Transaction GUID | Replacing          | msdyn_invoicelinetransaction | Billed Sales GUID            | Original           | msdyn_actual       |
| Confirm Invoice Correction     | Billed Sales Reversal GUID    | Reversing          | msdyn_actual                 | Billed Sales GUID            | Original           | msdyn_actual       |
| New Unbilled Sales Actual GUID | Replacing                     | msdyn_actual       | Billed Sales GUID            | Original                     | msdyn_actual       |                    |
