# Issues-to-import-urllib.parse-in-PyCharm
I am trying to run a Python3 code that I learn in a course. However, I'm having issues to run it because the PyCharm is not recognizing url lib.parse. I have already install several packages hoping that I could fix this problem. I am a beginner programmer, so if you have any suggestion what it may be let me know. Thanks

import urllib.request,urllib.parse,urllib.error
from bs4 import BeautifulSoup

# Ignore SSL certificate errors
ctx = ssl.create_default_context()
ctx.check_hostname = False
ctx.verify_mode = ssl.CERT_NONE

url = input('Enter - ')
html = urllib.request.urlopen(url, context=ctx).read()
soup = BeautifulSoup(html, 'html.parser')

# Retrieve all of the anchor tags
tags = soup('a')
for tag in tags:
    print(tag.get('href', None))
