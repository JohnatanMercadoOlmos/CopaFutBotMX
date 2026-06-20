README del proyecto 

Esta solución implementa un sistema de monitoreo táctico automatizado para el fútbol de robots que transforma video convencional en analíticas deportivas avanzadas. El enfoque combina filtros de color geométricos (HSV) para la detección rápida y el modelo de inteligencia artificial SAM (Segment Anything Model) para delimitar a los robots con precisión a nivel de píxel. Finalmente, mediante una matriz de homografía, el sistema corrige la perspectiva de la cámara y proyecta la posición exacta de los jugadores y el balón sobre un plano canónico 2D, lo que permite generar mapas tácticos digitales y mapas de calor de ocupación territorial en tiempo real.

Proceso de instalación 
Para poder hacer uso del proyecto se requiere la siguiente instalación previa.
Se opto por utilizar un entorno virtualizado con conda (Anaconda)
1.	Se instala anaconda en el equipo si no se cuenta con el software, se obtiene de: Download Anaconda Distribution | Anaconda.
Una vez descargado se siguen los pasos de instalación en Windows.
2.	 Crear el entorno virtualizado
Se abre un terminal y se ejecuta el comando: conda créate -n supervision python = 3.11 
3.	Activar el entorno
conda actívate supervision después de este comando se entra al entorno de supervision
4.	Instalar librerías necesarias
Se requiere de uso de GPU para un mejor flujo de trabajo con SAM3
conda install pytorch torchvision pytorch-cuda=12.4 -c pytorch -c nvidia
pip install supervison ultralytics trackers
pip install jupyter
 
5.	Decargar el modelo SAM3
Solicitar acceso en la pagina: https://huggingface.co/facebook/sam3
Descargar el archivo sam3.pt y colocarlo en la misma carpeta que el programa 
6.	Abri vs code
Descargar e instalar vs code la pagina https://cod.visualstudio.com/
Instalar la extenciao Python 
Cuando se ejecuta el archivo del programa se abre como notebook de jupiter, en la parte superior derecha se ubica la opción seleccionar kernel, se selleccion al kernel anteriormente creado en el paso 2 y activado en el paso 3 (Python Environments, se elige supervision).
Una vez instalados el programa ya se puede ejecutar el código proyecto. ipynb
Crear una carpeta donde se alojará el código y el archivo sam3.pt, dentro de esta carpeta colocar los archivos futbot-01.jpg y futbot-2s.mp4
Si se requiere el uso de alguna librería que no se encuentre instalada se coloca en la terminal de vs code el comando: pip install nombre de la librería faltante
Hardware y Sistema operativo utilizado en las pruebas:
•	Windows 11
•	8 gb de ram
•	4 gb de gpu nvidia
•	Procesar amd ryzen 5
Se requiere mas ram y gpu para realizar los procesos más rápido, que en este equipo se tardó en hacer las detecciones en video.  

visualizaciones a la salida
detacciones de objetos en imagen estatica para pasarlos a SAM3 y poder realizar la busqueda de los objetos en el video:

<img width="547" height="989" alt="image" src="https://github.com/user-attachments/assets/f7179a5c-db4d-486a-bead-8fa72ac98575" />

mapa tactico de la imagen inicial:

<img width="584" height="790" alt="image" src="https://github.com/user-attachments/assets/721189ab-77c9-4dd4-ad4e-657e6399ed3a" />

mapa de calor:

<img width="790" height="576" alt="image" src="https://github.com/user-attachments/assets/a61894b9-0a31-478d-a011-a3ed1a659b72" />

video de funcionamiento del codigo



https://github.com/user-attachments/assets/e9679056-d1af-431e-a694-c9f700489792



