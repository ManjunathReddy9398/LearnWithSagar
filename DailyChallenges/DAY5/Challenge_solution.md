# ✅ `challenge_solution.md` 

# Season-1: Day 5: Multi-Service Reverse Proxy with Nginx
**Name:** Manjunath K  
**Date:** 11 November 2025  

---

## ✅ Task 1 – create log file as refernce from currnet repo ( Killer coda)

### Result:
```Bash
rw-r--r--  1 root root 2493 Nov 10 16:47 user_activity.log
```
---

## ✅ Task 2 – Create user_extract.sh script

### Commands used:
```Bash
#!/bin/bash

log_file="user_activity.log"

echo "Processing log file: $log_file"

echo "Task 1: Extracting Unique IP Addresses..."
awk '{
    for (i = 1; i <= NF; i++) {
        if ($i ~ /^[0-9]+\.[0-9]+\.[0-9]+\.[0-9]+$/) {
            split($i, octets, ".")
            if (octets[1] <= 255 && octets[2] <= 255 && octets[3] <= 255 && octets[4] <= 255) {
                print $i
            }
        }
else if ($i ~ /^[0-9a-fA-F:]+$/) {
            if (gsub(/:/, ":", $i) >= 2) {
                print $i
            }
        }    
}
}' "$log_file" | sort -u > unique_ips.txt
echo "Unique IPs saved to unique_ips.txt."

# Task 2: Extract Usernames
echo "Task 2: Extracting Usernames..."
awk '{
    for (i = 1; i <= NF; i++) {
        if ($i ~ /^user[0-9]+$/) {
            print $i
        }
    }
}' "$log_file" | sort -u > usernames.txt
echo "Usernames saved to usernames.txt."

# Task 3: Count HTTP Status Codes
echo "Task 3: Counting HTTP Status Codes..."
awk '{
    if ($(NF) ~ /^[0-9]+$/) {
        status[$(NF)]++
    }
} END {
    for (code in status) {
        print code, status[code]
    }
}' "$log_file" | sort -n > http_status_counts.txt
echo "HTTP Status Codes count saved to http_status_counts.txt."

# Task 4: Identify Failed Login Attempts
echo "Task 4: Extracting Failed Login Attempts..."
awk '{
    if ($(NF) == "403") {
        for (i = 1; i <= NF; i++) {
            if ($i ~ /\[.*\]/) {
                timestamp = $i
                break
            }
        }
        print timestamp, $0
    }
}' "$log_file" > failed_logins.txt
echo "Failed login attempts saved to failed_logins.txt."

# Task 5: Generate Summary Report
echo "Task 5: Generating Summary Report..."
awk '
BEGIN {
    successful_requests = 0
    failed_requests = 0
}
{
    # Count users
    for (i = 1; i <= NF; i++) {
        if ($i ~ /^user[0-9]+$/) {
            users[$i]++
        }
    }
    
    # Count status codes
    if ($(NF) == "200") {
        successful_requests++
    }
    if ($(NF) == "404" || $(NF) == "403") {
        failed_requests++
    }
}
END {
    print "Summary Report:"
    print "Total Unique Users: " length(users)
    for (user in users) {
        print "  Requests by " user ": " users[user]
    }
    print "Total Successful Requests (200): " successful_requests
    print "Total Failed Requests (404 and 403): " failed_requests
}' "$log_file" > summary_report.txt
echo "Summary report saved to summary_report.txt."

```

### Result:
Above awk programe is used to extract unique IP's, users, status codes and error code filtering

---

## ✅ Task 3 – Give execute permission for script and run the script
```Bash
chmod 755 user_extract.sh
sh user_extract.sh

```

### Result:
-rwxr-xr-x  1 root root 2493 Nov 10 16:48 user_extract.sh*

---

## ✅ Task 4 – Finally generate 

### Result:
unique_ips.txt
unique_username.txt
http_status_counts.txt
failed_logins.txt
summary_report.txt

## ✅ Submission Checklist

- ✅ Completed all tasks with commands and explanations
- ✅ Inserted screenshots under each command block
- ✅ Pushed code to GitHub
- ✅ Shared on LinkedIn with hashtags: `#getfitwithsagar #DevOpsForAll`

---
