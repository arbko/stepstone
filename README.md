# scrape_stepstone
The purpose of this repo is to scrape search results for some specific job query from stepstone and store them in a word document.

### Installation
You need python 3 installed. Install the required packages:
```
pip install -r requirements.txt
```
Download and unpack geckodriver for your OS from:
https://github.com/mozilla/geckodriver/releases
The script expects geckodriver to be located at:
```
~/.local/bin/geckodriver
```
 But you can store it anywhere and give it as an argument to the script.


### How to use
Go to stepstone.de and search for some job (i.e. what, where, other fileters). Copy the resulting URL of that job search and add it to search_urls.json in the form "search_name": "search_url". You can add multiple entries here.
Run the script with:
```
python3 scrape_stepstone.py
```
There are two arguments. Use the --headless if you don't want the browser GUI to show up:
```
python3 scrape_stepstone.py --headless
```
Use  --geckodriver_path to specify where geckodriver is located (if it's not in the default path):
```
python3 scrape_stepstone.py --geckodriver_path <absolute_geckodriver_path>
```
### Output
For each entry in search_urls.json a word document will be created that lists all the jobs that were found for that specific query. If the script is executed again and new jobs were found they will be appended to the word documents.
