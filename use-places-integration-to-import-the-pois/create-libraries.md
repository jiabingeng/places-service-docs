# Create Libraries

Library name must be unique per orgID. Add POIs to the library: use the batchCreate API \(link to API docs here.\) Since this is a regular REST API, it’s bound by network timeout rules. Therefore, it cannot handle large amount of POIs at once. We recommend sending POIs in in batches of 1500 or less. The service supports concurrent calls, so it’s acceptable to call batchCreate simultaneously from several threads. This should speed up the import process quite a bit.

