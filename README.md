# SIEM Learning Journal – Days 9–15
*Platform:* Splunk Enterprise (Kali Linux)  
*Focus:* Search Processing Language (SPL), Data Analysis & Log Investigation

---

# Day 9 – SPL Search Fundamentals

## Objective
Learn how to search data in Splunk using the Search Processing Language (SPL).

## Topics Covered
- Basic SPL syntax
- Searching an index
- Filtering events
- Using keywords
- Understanding search results

## Commands Practiced

spl
index=main


spl
index=main host=kali


spl
index=main source="/var/log/dpkg.log"


spl
index=main host=kali source="/var/log/dpkg.log"


## Key Lessons
- Every search begins with an index.
- Fields can be combined to narrow results.
- SPL is read from left to right.
- The more filters added, the more precise the search becomes.

## Skills Learned
- Performing basic searches
- Filtering logs
- Understanding indexes, hosts and sources

---

# Day 10 – Importing Data into Splunk

## Objective
Learn how Splunk collects and indexes data.

## Topics Covered
- Uploading log files
- Source Type
- Host
- Source
- Index selection

## Practical
Imported Linux log files into Splunk.

Example:


/var/log/dpkg.log


## Key Lessons
- Splunk does not automatically monitor every file.
- Data must be onboarded before it becomes searchable.
- Correct Source Type improves event parsing.
- Indexes organize collected data.

## Skills Learned
- Data onboarding
- Source Type configuration
- Index selection

---

# Day 11 – SPL Statistics Commands

## Objective
Learn to summarize data using statistical commands.

## Commands Practiced

### Count all events

spl
index=main | stats count


### Count events by source

spl
index=main | stats count by source


### Count events by sourcetype

spl
index=main | stats count by sourcetype


### Count events by host

spl
index=main | stats count by host


### Average calculation

spl
index=main | stats avg(bytes)


## Key Lessons
- stats summarizes search results.
- count counts events.
- avg calculates averages.
- Grouping with by compares data.

## Skills Learned
- Event counting
- Statistical analysis
- Aggregating logs

---

# Day 12 – Table and Sort Commands

## Objective
Display results in a clean format.

## Commands Practiced

### Table

spl
index=main | table host source sourcetype


### Sort Ascending

spl
index=main | sort host


### Sort Descending

spl
index=main | sort -host


### Table with Statistics

spl
index=main
| stats count by source
| sort -count


## Key Lessons
- table displays only selected fields.
- sort organizes search results.
- Descending sort uses the minus (-) sign.

## Skills Learned
- Formatting search output
- Sorting results
- Improving readability

---

# Day 13 – Understanding Fields

## Objective
Understand how Splunk stores searchable information.

## Topics Covered
- Fields
- Default fields
- Extracted fields
- Search filters

## Common Fields

- host
- source
- sourcetype
- index
- _time

## Example Searches

spl
index=main host=kali


spl
index=main sourcetype=linux_secure


spl
index=main source="/var/log/dpkg.log"


## Key Lessons
- Fields describe each event.
- Fields make searching faster.
- Splunk automatically extracts many fields.

## Skills Learned
- Field filtering
- Efficient searching
- Understanding event structure

---

# Day 14 – Log Investigation

## Objective
Practice investigating Linux logs.

## Logs Reviewed

- dpkg.log
- journal logs
- system logs

## Searches Practiced

spl
index=main source="/var/log/dpkg.log"


spl
index=main host=kali


spl
index=main


## Investigation Process

1. Search the correct index.
2. Filter by host.
3. Filter by source.
4. Review timestamps.
5. Identify important events.

## Key Lessons
- Investigations begin with narrowing the dataset.
- Proper filtering reduces noise.
- Every event has useful metadata.

## Skills Learned
- Log investigation
- Event analysis
- Search refinement

---

# Day 15 – Practical SPL Review

## Objective
Review everything learned during Week 2.

## Commands Reviewed

spl
index=main


spl
index=main host=kali


spl
index=main source="/var/log/dpkg.log"


spl
index=main | stats count


spl
index=main | stats count by source


spl
index=main | stats count by sourcetype


spl
index=main | table host source sourcetype


spl
index=main | sort -host


## Week 2 Skills Acquired

- Searching indexes
- Filtering events
- Understanding hosts
- Understanding sources
- Understanding Source Types
- Understanding fields
- Importing data
- Using stats
- Using count
- Using avg
- Using table
- Using sort
- Reading Linux logs
- Basic log investigation
- SPL fundamentals

---

# Week 2 Summary

During Days 9–15, I strengthened my understanding of Splunk by learning how to onboard log data, search indexed events using SPL, analyze logs with statistical commands, organize results using table and sort, understand fields and metadata, and perform basic log investigations. By the end of the week, I was able to confidently search, filter, summarize, and interpret Linux log data using Splunk Enterprise.

---
*Status:* ✅ Week 2 Completed
*Next Phase:* Week 3 – Advanced SPL, Field Extraction, and Threat Detection
