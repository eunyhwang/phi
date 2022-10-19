from cgitb import text
import re
import os
import requests
import urllib.request
from urllib.request import urlopen
import json
from bs4 import BeautifulSoup

proxy = "your-proxy-information"
os.environ['http_proxy']=proxy
os.environ['HTTP_PROXY'] = proxy
os.environ['https_proxy'] = proxy
os.environ['HTTPS_PROXY'] = proxy

def extract_info(date): # date should be in YEAR-MONTH-DATE e.g., 2021-01-07
    url = 'https://www.rki.de/DE/Content/InfAZ/N/Neuartiges_Coronavirus/Transport/Archiv_Risikogebiete/Risikogebiete_%s.pdf?__blob=publicationFile' % date
    url = url.format(date ='date')
    page = requests.get(url)
    print(page.text).decode('utf-8')

    try:
        with urlopen(url) as data:
            html = data.read() #data_type: bytes
            country_name = html.find("title")
            print(country_name)

    except urllib.error.URLError as e:
        print("Could not request data from server")
        print(e.reason)

extract_info("2021-01-07")
