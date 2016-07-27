from urllib2 import urlopen
from json import load 
import json, re, os, sys, requests





word = 0

##searches for cyber and cyber* both seem to get 646 results
##got rid of search for 'data security' because i couldn't figure out how to search for phrase

while word < 6:

	url = 'https://www.govtrack.us/api/v2/bill?limit=6000&q='
	
	word = word + 1

##added more words in final searches

	if word == 1:
		wordmeaning = 'cyber'
	if word == 2:
		wordmeaning = 'password'
	if word == 3:
		wordmeaning = 'encryption'
	if word == 4:
		wordmeaning = 'hacker'
	if word == 5:
		wordmeaning = 'malware'
	if word == 6:
		wordmeaning = 'spam'

	print word
	url = url + wordmeaning
	print url


	response = requests.get(url)
	response.raise_for_status()
	w = json.loads(response.text)
	x = wordmeaning + '.txt'

	with open(x, "a" if os.path.exists(x) else "w") as output:
		json.dump(w, output)
		output.write(os.linesep)




print 'done'
