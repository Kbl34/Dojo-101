# Fuzz with ZAP

utilisé en alternative de Burp (cf pentest) car gratuit

## Documentation
https://www.zaproxy.org/docs/desktop/start/
https://www.zaproxy.org/docs/desktop/addons/fuzzer/

## Fuzzing
Click droit sur la requete puis fuzz / generer du bruit


## Fuzzing
Fuzzing is a technique of submitting lots of invalid or unexpected data to a target.

ZAP allows you to fuzz any request still using:

A build in set of payloads
Payloads defined by optional add-ons
Custom scripts
To access the Fuzzer dialog you can either:

Right click a request in one of the ZAP tabs (such as the History or Sites) and select “Attack / Fuzz…”
Highlight a string in the Request tab, right click it and select “Fuzz…”
Select the “Tools / Fuzz…” menu item and then select the request you want to fuzz
Payload Generators 
Payload Generators generate the raw attacks that the fuzzer submits to the target application.

They are managed via the Payloads dialog

### Payload Processors 
Payload Processors can be used to change specific payloads before they are submitted.

They are managed via the Payload Processors dialog

### Fuzz Location Processors 
Fuzz Location Processors can be used to change all of the payloads before they are submitted.

They are managed via the Location Processors dialog

### Message Processors 
Message Processors can access and change the messages being fuzzed, control the fuzzing process and interact with the ZAP UI.

They are managed via the Fuzzer dialog ‘Message Processors’ tab.

This functionality is based on code from the OWASP JBroFuzz project and includes files from the fuzzdb project.
Note that some fuzzdb files have been left out as they cause common anti virus scanners to flag them as containing viruses.
You can replace them (and upgrade fuzzdb) by downloading the latest version of fuzzdb and expanding it in the ‘fuzzers’ library.


## Options Fuzzer screen
This screen allows you to configure the fuzzing options:

### Default Category 
The category that will initially be selected when the Fuzz dialog is displayed.

### Add Custom Fuzz File 
Allows you to add your own files to be used when fuzzing.
These should be text files with one payload per line.
Files are added to the ‘fuzzers’ directory underneath the ZAP home directory.

### Finished Fuzzers in UI 
It defines the numbers of fuzzers (that have completed their execution) visible in the fuzzer tab.

### Retries on IO Error 
The number of retries when an input/output error occurs sending a request to the target.

### Max. Errors Allowed 
If the number of errors exceed this limit, fuzzer will stop its execution.

### Payload Replacement Strategy 
Rules defined to control the order that multiple payload lists are iterated.

### Concurrent Scanning Threads per Scan 
The number of threads the fuzzer will use per scan.
Increasing the number of threads will speed up the scan but may put extra strain on the computer ZAP is running on as well as the target.

### Delay when Fuzzing (in milliseconds) 
The number of milliseconds between requests by the fuzzer to the target host, usually done to avoid getting blocked by the target or if the target implements some sort of throttling requirement.