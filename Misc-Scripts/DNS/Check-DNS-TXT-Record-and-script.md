# Check DNS TXT Record And Perform Action

What this script does is that it fetches the txt record of a domain. if the txt record is equal to "down" it'll run a script. Otherwise it'll do nothing if it contains something else or if the record doesnt exist.

```bash
#!/bin/bash

# Define the domain to check
DOMAIN= #Add your domain here

# Get the TXT record using dig
TXT_RECORD=$(dig +short TXT $DOMAIN | tr -d '"' | xargs)

# Check if the TXT record exists
if [[ -n "$TXT_RECORD" ]]; then
    echo "Cleaned TXT Record: $TXT_RECORD"
    
    # Check if the record contains the word "down"
    if [[ "$TXT_RECORD" == "down" ]]; then
        echo "The service is down. Taking necessary actions."
        #Insert Script(s) here
    else
        echo "The record does not indicate downtime. No action taken."
    fi
else
    echo "No TXT record found for $DOMAIN"
fi
```
