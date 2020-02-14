# sfmc_domain_history_v1

This will capture the performance (opens, clicks, ctor, optouts) on a domain-by-domain basis for your top 10 domains.  The objective is to be able to see trends, or to spot any problems (if a particular domain sees a sudden drop in opens suggesting there might be a spam/inboxing issue to investigate.)

How I Use This
--------------
I have an Automation that runs weekly to get this information and then emails it to me.

Prerequisites
-------------
Requires a list of domains (with counts) in order to come up with the top 10 in a Data Extension named "domain_counts".  I have another repository that describes how to get that data.  (Or you can fake it if you know the domains you want to track.)

How it Works
------------
Data Extension - holds the data.  Nothing special.  6 "slots" for holding 6 historical time periods.
Query 1 - Gets any new top 10 domains.  (Note: Does not remove domains no longer in the top 10)
Query 2 - Adds supplemental data points for any new top 10 domains.
Query 3 - Moves everything down 1 "slot"
Query 4-8 - Gets new data, stores in slot 0.  Change "14" to however many days you want in your historical look-back.

It currently thinks it's being run weekly based on the dates calculated within the content.

History
-------
I built this for a work project, but it's just standard SFMC, so uploading it here (on my own time) in case others can benefit from it.
