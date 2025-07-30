A **Cron expression** is a string used to define a **time-based schedule** for running recurring tasks or jobs, commonly used in UNIX/Linux systems, cloud platforms (like AWS, Azure), and job schedulers.

### Format:

A standard Cron expression has **5 or 6 fields**, depending on the system:

```
# 5-field format (used in Unix crontab):
* * * * *  command-to-run
| | | | |
| | | | +----- Day of the week (0 - 6) (Sunday=0 or 7)
| | | +------- Month (1 - 12)
| | +--------- Day of month (1 - 31)
| +----------- Hour (0 - 23)
+------------- Minute (0 - 59)
```

Or:

```
# 6-field format (used in Quartz, AWS, etc.):
Seconds Minutes Hours Day-of-Month Month Day-of-Week [Year]
```

### Examples:

* `0 0 * * *` → Every day at midnight
* `*/15 9-17 * * 1-5` → Every 15 minutes during business hours (9 AM to 5 PM), Monday to Friday
* `0 0 1 1 *` → Every January 1st at midnight

### Special Characters:

* `*` – any value
* `,` – value list separator (e.g. `1,2,3`)
* `-` – range (e.g. `1-5`)
* `/` – step values (e.g. `*/10` means every 10 units)
* `?` – no specific value (used in Quartz)
* `L`, `W`, `#` – advanced modifiers (mainly in Quartz)

### Use Cases:

* Automating backups
* Scheduling reports
* Running periodic system checks
* Triggering Lambda functions or cloud workflows

