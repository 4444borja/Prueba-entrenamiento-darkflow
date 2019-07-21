# Prueba-entrenamiento-darkflow

### Instalación de darkflow
Descargar darkflow de su [repositorio](https://github.com/thtrieu/darkflow) y una vez en el directorio instalar mediante `pip install -e .`.
### Acceso al entorno virtual
Con el objetivo de abstraer las despendencias de la máquina, utilizo virtualenv. He creado uno llamado 'entornovirtual' y se activa ejecutando `source entornovirtual/bin/activate`.
### Instalación de tensorflow-gpu 1.12.0
La versión de tensorflow-gpu 1.12.0 es la última que soporta la versión de los drivers cudnn y cuda instalados en socarrat.
Para ello se desinstala la actual (del entrono) ejecutando `pip uninstall tensorflow-gpu`.
Después se instala la antigua versión con `pip install tensorflow-gpu==1.12.0`.
### Ejecución del entrenamiento
Una vez en el directorio de darkflow, ejecuto el siguiente comando para el entrenamiento:
```
python flow --model cfg/yolo-new.cfg --labels one_label.txt --train --trainer adam --dataset "/home/borjaad/images/img" --annotation "/home/borjaad/images/lab" --gpu 1.0
```
Los archivos necesarios listados a continuación se encuentran en este repositorio.
* cfg/yolo-new.cfg
* one_label.txt
* imágenes de /home/borjaad/images/img
* xmls de /home/borjaad/images/lab
