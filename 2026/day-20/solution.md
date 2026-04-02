# Day 20 – Bash Scripting Challenge: Log Analyzer & Report Generator

##  Objective
Automate log analysis using Bash:
- Count errors
- Detect critical events
- Find top error messages
- Generate a summary report

---

## Script: `log_analyzer.sh`

```bash
#!/bin/bash
set -euo pipefail

# Validate input
if [ "$#" -eq 0 ]; then
    echo "Usage: $0 <path of log file>"
    exit 1
fi

if [ ! -f "$1" ]; then
    echo "Error: $1 doesn't exist. Please check log file name"
    exit 1
fi

LOG_FILE="$1"

# Count ERROR
ERROR_COUNT=$(grep -c "ERROR" "$1")
echo "Total Error Count: $ERROR_COUNT"

# Critical events
CRITICAL_SEARCH=$(grep -n "CRITICAL" "$1")
echo "$CRITICAL_SEARCH"

# Top 5 errors
TOP_ERROR=$(grep "ERROR" "$1" | awk -F' ' '{print $2}' | awk -F'-' '{print $1}' | sort | uniq -c | sort -rn | head -5)

echo "--------------------TOP 5 ERROR MESSAGE--------------------"
echo "$TOP_ERROR"

# Report generation
DATE=$(date +%Y-%m-%d)
REPORT_FILE="log_report_$DATE.txt"

echo "Total Lines Processed: $(wc -l < "$LOG_FILE")"

{
    echo "Date of analysis: $DATE"
    echo "Log file name: $LOG_FILE"
    echo "Total lines processed: $(wc -l < "$LOG_FILE")"
    echo "Total error count: $ERROR_COUNT"
    echo "Top 5 error messages:"
    echo "$TOP_ERROR"
    echo ""
    echo "List of critical events with line numbers:"
    echo "$CRITICAL_SEARCH"
} > "$REPORT_FILE"

echo "Report generated successfully: $REPORT_FILE"
```
