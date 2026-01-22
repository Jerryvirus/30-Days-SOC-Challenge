
## Objective
In this lab, you will:
- Learn how to upload and search Zeek connection logs in Splunk.
- Find top clients, top servers, and most common services.
- Identify large traffic and long connections.

## Lab Setup
- **Splunk**: Already installed and accessible.
- **Data Source**: JSON-formatted Zeek-style connection logs.
- **Log File**: Download and upload to Splunk using the steps below.

**[Download Zeek Conn Log File](https://raw.githubusercontent.com/0xrajneesh/30-Days-SOC-Challenge-Beginner/refs/heads/main/zeek_conn_logs.json)**

## Steps to Upload Conn Log into Splunk
1. Go to **Splunk Web → Settings > Add Data**.
2. Choose **Upload** and select `zeek_conn_logs.json`.
3. Set **Source type**: `json` or create a new one like `zeek:conn`.
4. Index: Use `main` or create a new one called `conn_lab`.
5. Complete the upload and check that logs are searchable.

## Lab Tasks
Use the following SPL queries to complete each task:

**Task 1: Find the Top 10 Client IPs (id.orig_h)**
```spl
index=conn_lab sourcetype="json"
| stats count by id.orig_h
| sort -count
| head 10
```

**Task 2: List Most Common Services**
```spl
index=conn_lab sourcetype="json"
| stats count by service
| sort -count
```

**Task 3: Find Connections with Duration > 1 Second**
```spl
index=conn_lab sourcetype="json" duration>1
| table ts id.orig_h id.resp_h service duration
| sort -duration
```

**Task 4: Identify the Most Accessed Internal Servers**
```spl
index=conn_lab sourcetype="json"
| stats count by "id.resp_h"
| sort -count
| head 10
```
