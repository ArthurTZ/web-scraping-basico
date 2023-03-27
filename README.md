# Web Scraping básico com Selenium

## Este é um tutorial básico sobre como realizar web scraping utilizando a biblioteca Selenium em Python.

O web scraping é uma técnica utilizada para extrair dados de sites da web. O Selenium é uma biblioteca que permite a automação de ações em um navegador web.

### Pré-requisitos:
- Python 3.x instalado
- Bibliotecas Python: Selenium e BeautifulSoup4
- Navegador web: Chrome ou Firefox
- Driver do navegador: ChromeDriver ou GeckoDriver

## Instalação:
  - Instale o Python 3.x a partir do site oficial https://www.python.org/downloads/
  - Instale as bibliotecas Python executando o seguinte comando no terminal: pip install selenium beautifulsoup4
  - Faça o download do driver do navegador de sua preferência e versão correspondente ao seu navegador: ChromeDriver (https://sites.google.com/a/chromium.org/chromedriver/downloads) ou GeckoDriver (https://github.com/mozilla/geckodriver/releases)
  - Extraia o arquivo baixado e adicione o caminho do driver ao PATH do sistema operacional.

## Primeira Parte: Importar as LIBS

### Biblioteca a serem importadas:
    from time import sleep
    from webdriver_manager.chrome import ChromeDriverManager
    from selenium.webdriver.common.keys import Keys
    from selenium import webdriver
    from selenium.webdriver.chrome.service import Service
    
### Logo em seguida com o driver ja instalado:
    # Proprio selenium faz a busca e ja instala o driver
    servico = Service(ChromeDriverManager().install())
    # faz a pesquisa pelo proprio console
    produto = input('Nome do produto:  ')
    # abre o chrome juntamente do link do site a ser raspado
    navegador = webdriver.Chrome(service=servico)
    navegador.get('https://www.mercadolivre.com.br')
    
### Finalizando, o proprio selenium e suas libs possuem metodos para usar o mouse ou teclado para fazer as ações:
#primeiro: pegar o xpath do navegador (xpath do html) e depois fazer a ação que preferir

    navegador.find_element('xpath', '//*[@id="cb1-edit"]').send_keys(produto)
    sleep(2.1)

    navegador.find_element('xpath','//*[@id="cb1-edit"]').send_keys(Keys.ENTER)
    sleep(2.1)

    navegador.find_element('xpath', '//*[@id="shipping_cost_highlighted"]').send_keys(Keys.ENTER)
