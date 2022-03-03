# bin-staking-viewer
Macro que realiza un Scraping a la pagina de staking en Binance y saca datos de: " Duración de Stake / APY / Estado " en base a la extencob 

 
Binance Staking Viewer V0.1 (BETA)

Este es un código que permite extraer información sobre " Activo / Duración de Staking / APY / Estado Actual ". 
Esto en las diferentes opciones que nos ofrece Binance para cada activo que tengamos en nuestra "WatchList". 
Esto en base a una extensión de navegador llamada "UI Vision", en este caso con un navegador en base chromium (Google Chrome, Edge, etc)

---------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------

WatchList: (staking-coins-wl.csv)
Es un archivo de tipo CSV que contiene en su primera columna el listado de activos (TICKET) de los cuales requerimos la información.

EJEMPLO


BTC
AXS
MATIC
SAND
...
....
.....

TIP:
Se puede crear un archivo en cualquier editor de texto con esta lista y al momento de guardar se usa la opción "guardar como" 
y se guarda con la extensión CSV (Archivo Separado por comas). Nombrar el archivo como "staking-coins-wl.csv"


---------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------


UI Vision:
https://ui.vision/

Descargar la extensión buscando con el nombre "UI vision extención".
https://chrome.google.com/webstore/detail/uivision-rpa/gcbalfbdmfieckjlnblleoemohcganoc

Es una extensión que nos ayuda con una interfaz sencilla para interactuar con paginas web. 

Se puede importar el archivo JSON o copiar y pegar el codigo detallado mas adelante. 

---------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------

MODO DE USO:

Primeros pasos.

-Instalada la extensión 
-Tener el código importado en dicha extensión.
-Tener creado tu archivo CSV con la lista de activos de interés.


Usando el código.

	-Importando nuestra WatchList 
		Abrir la extensión, en la parte inferior de la interfaz existe una pestañas de nombre "CSV"
		Al dar click ahí cambiará la interfaz, dando paso a un botón en la parte superior derecha de nombre "Import CSV", dar click en ese botón.
		Buscar y abrir el archivo como en cualquier otro programa.



	-Ejecutar el Código
		En la parte superior derecha de la interfaz principal están los botones de "Play Macro" (Ejecuta una vez) y "Play Loop.." (Ejecuta varias veces)
		Determinando el número de activos en la WatchList, ejecutar el loop la misma cantidad de veces.
	
	
	-Obteniendo resultados
		En la misma sección en la que importamos el archivo CSV podremos ver un archivo llamado "staking-coins-det.csv"
			Al lado derecho del nombre existen 3 botones:
				1) Para ver el archivo de forma rápida en un editor de texto nativo de la extensión 
				2) Descargar el Archivo
				3) Eliminar el Archivo (Empezar de cero)


Para ver un video explicativo pasar por el siguiente link:






---------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------


CODIGO:



{
  "Name": "BIN-STAKING-VIEW-2",
  "CreationDate": "2022-3-3",
  "Commands": [
    {
      "Command": "csvRead",
      "Target": "staking-coins-wl.csv",
      "Value": "",
      "Description": ""
    },
    {
      "Command": "open",
      "Target": "https://www.binance.com/en/pos",
      "Value": "",
      "Description": ""
    },
    {
      "Command": "type",
      "Target": "//*[@id=\"savings-search-coin\"]",
      "Value": "${!COL1}",
      "Description": ""
    },
    {
      "Command": "pause",
      "Target": "1000",
      "Value": "",
      "Description": ""
    },
    {
      "Command": "store",
      "Target": "${!COL1}",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "click",
      "Target": "xpath=//*[@class=\"css-1an9uq5\"]/button[1]",
      "Value": "",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-1an9uq5\"]/button[1]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-14ubhgt\"]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-1dmwl4e\"]/button[1]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "click",
      "Target": "xpath=//*[@class=\"css-1an9uq5\"]/button[2]",
      "Value": "",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-1an9uq5\"]/button[2]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-14ubhgt\"]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-1dmwl4e\"]/button[1]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "click",
      "Target": "xpath=//*[@class=\"css-1an9uq5\"]/button[3]",
      "Value": "",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-1an9uq5\"]/button[3]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-14ubhgt\"]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "storeText",
      "Target": "xpath=//*[@class=\"css-1dmwl4e\"]/button[1]",
      "Value": "!csvLine",
      "Description": ""
    },
    {
      "Command": "csvSave",
      "Target": "staking-coins-det.csv",
      "Value": "",
      "Description": ""
    }
  ]
}






 
