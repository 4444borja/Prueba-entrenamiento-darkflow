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

En este momento da el siguiete error relativo a cudnn:

2019-07-15 19:29:20.741248: E tensorflow/stream_executor/cuda/cuda_dnn.cc:363] Loaded runtime CuDNN library: 7.0.4 but source was compiled with: 7.1.4.  CuDNN library major and minor version needs to match or have higher minor version in case of CuDNN 7.0 or later version. If using a binary install, upgrade your CuDNN library.  If building from sources, make sure the library loaded at runtime is compatible with the version specified during compile configuration.
