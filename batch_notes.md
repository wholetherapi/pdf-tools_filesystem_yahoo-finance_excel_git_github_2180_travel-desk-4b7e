# Batch close-out rules

Every monthly travel-claim batch is closed from the documents filed in `intake/`.

1. Include every intake document in the claim summary exactly once.
2. Reconcile each document: TOTAL must equal FARE + TAX + ADDITIONAL SERVICES (treat ADDITIONAL SERVICES as 0 when the line is absent).
3. If every document reconciles, set the batch register status to CLOSED and leave the note blank.
4. If one or more documents do not reconcile, set the status to FLAGGED and put the file name of the first inconsistent document (in file-name order) in the note column.
5. Approved summaries for the batch are committed under `summaries/` on this branch.

Register columns: batch_id,period,documents,status,note. Keep the document count and batch id unchanged.
