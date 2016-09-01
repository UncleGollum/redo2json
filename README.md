# redo2json

A small tool what get an oracle redo (or archived redo) log and save changes of selected tables as json.
Each redo record, IUD or commit/rollback translates directly to formatted json.

Usually, change data capture is beginning of long way ETL transformations and data checks. Whats a point to look and check transaction commit in hight-workload process of log parsing? Its a job for ETL and message brokers. Long transactions is a big problem of CDC tools like GoldenGate and IDR. RDBMS writes ALL changes, and rollback them then it required. How much real data rollbacks have you systen on one commit? Yes, this is it.
