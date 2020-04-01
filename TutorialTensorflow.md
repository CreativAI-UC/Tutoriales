#TensorFlow
TensorFlow es una librería open source de google que permite crear applicaciónes de machine learning. En este tutorial se mostrará una introducción a la librería y lgunos ejemplos de uso.

Es importante que para hacer uso de [tensorflow_gpu](https://www.tensorflow.org/install/gpu) se necesita instalar [CUDA](https://developer.nvidia.com/cuda-toolkit-archive) y [cuDNN](https://developer.nvidia.com/cudnn), en caso contrario tf seguira utilizando la cpu del equipo para crear y correr los modelos y redes.

##Documentación
TensorFlow tiene APIs para muchos lenguajes de programación, pero cabe mencionar que la API mas completa y con mayor estabilidad y facilidad de uso es la de python. 


Una lista completa de la documentación se puede encontrar [aquí](https://www.tensorflow.org/api_docs/python/).

Es importante decir que a partir de la version 2.0 de TensorFlow, muchas funciones usadas popularmente en estructuras de red comunes ya no estan implementadas, para esto se puede utilizar:

```python
import tensorflow as tf
tf.compat.v1.<funcion_de_la_version_1.0>
```
Para checkear que version esta siendo utilizada:
```python
import tensorflow as tf
tf.version()
```
##Errores
Un error común que suele aparecer al usar tensorflow_gpu, es que no se detecta la gpu del equipo.
Para esto uno debe desinstalar por completo TensorFlow y reinstalar TensorFlow_gpu:
```
pip3 uninstall tensorflow
pip3 uninstall protobuf
pip3 install tensorflow-gpu
```
Otro error que puede suceder es que, tensor flow utiliza la gpu, pero no logra alocar la memoria necesaria, causando un error del tipo:
`from device: CUDA_ERROR_OUT_OF_MEMORY`

Esto se puede deber a muchas cosas. Por un lado, es posible que la gpu usada simplemente no tenga suficiente memoria. Para probar esto puedes usar `nvidia-smi` para ver exactamente cuanta memoria hay disponible, y cuanta está siendo allocada a correr el programa. 
Es posible tambien que tensorflow no tenga activada la opcion de memory_growth, que utiliza toda la memoria necesaria de la GPU. se puede activar con:
```
tf.config.experimental.set_memory_growth(
    device, enable
)
```
Para multiples GPUs
```
gpu_devices = tf.config.experimental.list_physical_devices('GPU')
for device in gpu_devices:
    tf.config.experimental.set_memory_growth(device, True)
    ```

##Ejemplo básico
Primero debemos importar la librería. Le pondremos nombre tf. 
```python
import tensorflow as tf
```
