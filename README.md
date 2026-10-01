# self_osint_tool
This tool was created to utilize a couple OSINT tools and combine them into an all-in-one package that can be interfaces through a CLI.

 self_osint.py - self-OSINT audit runner.

 Runs whichever of these tools are on PATH against your own identifiers,
 parses their output, and writes a concise Markdown report + CSV findings log:

   sherlock, maigret      -> usernames
   holehe                 -> emails (sites with an account registered)
   HIBP API v3            -> emails (breaches; needs --hibp-key or HIBP_API_KEY)
   exiftool               -> local photos (GPS / device / author metadata)
   spiderfoot / sf.py     -> passive correlation (opt-in, slow: --spiderfoot)

 Google dorks and data brokers are listed as manual follow-ups; scraping
 search engines and broker sites trips CAPTCHAs and violates their ToS.
 
Example:
    python3 self_osint.py --name "First Last" -u handle1 -u oldhandle \
        -e me@example.com -e old@example.com -i ./my_photos --spiderfoot
