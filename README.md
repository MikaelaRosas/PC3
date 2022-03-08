# PC 3-WEB SCRAPING 
## https://www.gob.pe
### Integrantes:
-Diaz Guevara, Juan Carlos
-Ramos Ayma,Xiomara
-Rosas Tenorio, Mikaela
-Tenicela Arana, Anthony
<p>
#INSTALANDO PAQUETES 
#!pip install selenium
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By
from selenium.webdriver.support.wait import WebDriverWait
import time
import os
<p>
respuesta = requests.get(url_base + str(pagina))
<p>
from bs4 import BeautifulSoup
