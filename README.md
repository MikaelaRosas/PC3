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
  #HACIENDO EL REQUERIMIENTO
import requests
pagina = 1
url_base = "https://www.gob.pe/institucion/presidencia/noticias?filter%5Bterms%5D=&amp;filter%5Btype%5D=&amp;sheet="
<p>
respuesta = requests.get(url_base + str(pagina))
<p>
from bs4 import BeautifulSoup
</p>
 <p>
 def obtiene_links(page):
    response = requests.get(url_base + str(page))
    sopa = BeautifulSoup(response.text)
    anchors = []
    if sopa is not None: #si la lista no es vacia
        anchors = sopa.find_all("a",{"class":"text-primary track-ga-click card__mock hover:no-underline"})
                                       #class="card border relative bg-white flex shadow-cards min-h-350px h-full flex-col"
    hrefs = ["https://www.gob.pe" + a["href"] for a in anchors]
    return hrefs
</p>

<p>
 obtiene_links(1) # links de la pagina 1, en total 19
</p>

<p>
  TODOS_los_links = []
for pg in range(10):
    TODOS_los_links.extend(obtiene_links(pg))
</p>

<p>
  respuesta_articulo = requests.get(TODOS_los_links[0])
respuesta_articulo
TODOS_los_links[4]
</p>
