---
description: This section explains the Saint Scrubber script.
title: Scripting for the SAINT Scrubber
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
---

# Scripting for the SAINT Scrubber{#scripting-for-the-saint-scrubber}

This section explains the Saint Scrubber script.

## Overview of SAINT Classification {#section-b840a99f10684bb4b58e844a515d0d79}

Classification is also known by the acronym SAINT for SiteCatalyst Attribute Importing and Naming Tool.

When we "classify" a SiteCatalyst variable, you are establishing a relationship between a variable and meta-data related to that variable. Classifications are most frequently used in the Campaigns area so I will use that as a way to explain them. Most clients send campaign traffic to their site using a tracking code. This tracking code is an identifier that may represent a specific keyword purchased on Google, such as "goog123." This identifier is passed into the s.campaigns variable so you can see what site success events take place after visitors come to your site from that campaign code.

But what if, instead of viewing Campaigns just by the tracking code, you want to see campaign results by Search Engine or Keyword or Campaign Channel? Do you have to create a new conversion variable for Search Engine, another for Keyword and yet another for Campaign Channel? If so, you would use up many of your fifty variables on Campaigns alone! Thankfully, you can use Classifications to make your life easier! Since each tracking code could have a Search Engine, Keyword or Campaign Channel, you can simply create three Classifications of the Campaigns variable to represent each. You are essentially telling SiteCatalyst that there is a direct relationship between the Campaigns variable and these three other "meta-data" values. By doing this, SiteCatalyst will allow you to slice and dice site Success Events by all four variables with no additional tagging.

## SAINT scrubber Script in DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

This script is used when you bring in any SAINT Classification data into DWB. The script *SaintScrubber.dat* is normally placed under the *\Scripts\Scripository* folder on the FSU.

The main purpose of this script is to remove the header in the `<discoiqbr>` SAINT Classification files. Also, it counts the number if the column mentioned in the column header line and checks all the data rows. If there are rows with less or more number of columns, then it removes these rows from the file.

The *SaintScrubber.dat* internally calls the *saint_scrubber.pl *script. Below are the details for this script file:

Path: *E:\Scripts\Scripository\Library\Perl*

Script Arguments:

1. Input Folder (Mandatory): source_directory 
1. Output Folder (Mandatory) : destination_directory 
1. Delimiter (Mandatory) : delimiter 
1. Reject Folder (Optional)(Parameter can be left blank or omitted from the command line) 
1. Log Folder (Optional)(Parameter can be left blank or omitted from the command line)

Steps performed in the Perl script:

1. Replace escaped form feeds, newlines, carriage returns, tabs with spaces. 
1. Remove those double bytes that are interpreted as a control character in the UTF-8 BMP (Basic Multilingual Plane) except for:

    * 9 horizontal tab 
    * 10 line feed 
    * 12 form feed 
    * 13 carriage return 
    * Use the pipe keyword, as a delimiter for | eg: delimiter pipe 
    * Remove other troublesome characters 
    * After the above scrubbing drop any lines with a number of columns differing from the first data line (not blank or comment) 
    * Support optional rejection files to hold rejected lines instead of just skipping them 
    * Support recursive input folder; generate output folders of same structure 
    * Move processed input files to processed sub folders so the script does not repeat the effort when run again on the same existing input folder 
    * Recognize date in workbench filenames; sort processing first by date then alpha—regardless of folder name. This will ensure that the sequence is correct no matter the workbench file type (ecom, non-ecom) or report suite ID (if you are processing multiple report suites into a single Insight dataset). 
    * Support email alerts `<discoiqbr>`

