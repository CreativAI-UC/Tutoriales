# Pytorch
Pytorch es un paquete de python que tiene dos grandes utilidades:

* Calculo y manipulacion de tensores.

* Creacion, manejo y testeo de redes neuronales profundas.

Una de las ventajas de pytorch es que puede guardar tensores y manejarlos desde una GPU, acelerando los calculos de tensores, y a su vez, haciendo de un sistema mas eficiente de manejo de redes profundas. 

En el ambito de las redes neuronales, Pytorch tiene un sistema bastante mas flexible que otros frameworks (como TensorFlow) en el sentido de que permite cambios arbitrarios sobre un modelo ya implementado, sin tener que empezar de cero. El metodo por el cual logran esta flexibilidad se llama reverse-mode auto-differentiation, que es una manera de calcular el gradiente de la funcion de perdida. Esto hace que Pytorch tenga un backend mas flexible, y deja la posibilidad de construir sobre estructuras de redes ya conocidas.

Pytorch tiene la gracia de ser completamente **_Pythonica_**, por lo que es compatible con otros paquetes de python, y se puede usar las funciones otorgadas por pytorch mediante codigo normal de python.

Pytorch es facil de usar. No suele tirar errores asociados al packete en si, y no tiene notables conflictos entre versiones (:angry: TensorFlow :angry:). Es incluso facil de instalar y esta bien explicado en la documentacion. Es un poco limitado con versiones de python superiores a 3.8.


## Documentación
Pytorch esta compuesto por seis sublibrerias:

* [torch](https://pytorch.org/docs/stable/torch.html) : Libreria principal de Pytorch.

* [torch.autograd](https://pytorch.org/docs/stable/autograd.html) : Libreria para computar operaciones de tensores mediante differenciacion automatica.

* [torch.jit](https://pytorch.org/docs/stable/jit.html) : Es el "just in time compiler" de Pytorch, escrito en TorchScript. Permite serializar codigo sin dependencias de python, via LibTorch (un modulo nativo de C++). Ademas Pytorch puede compilar modulos jit sin interpretarlos, mejorando la velocidad de uso de estos modulos.

* [torch.nn](https://pytorch.org/docs/stable/nn.html) : Libreria de redes neuronales con autograd integrado.

* [torch.multiprocessing](https://pytorch.org/docs/stable/multiprocessing.html) : Libreria de multiprocesamiento para python

* [torch.utils](https://pytorch.org/docs/stable/data.html) : Funciones de utilidad, como DataLoader.

Una lista completa de la documentación se puede encontrar [aquí](https://pytorch.org/docs/stable/index.html).


## Ejemplo

Pytorch tiene un procesador de audio integrado, [torchaudio](https://pytorch.org/tutorials/beginner/audio_preprocessing_tutorial.html). Usaremos este procesador para entrenar una red basada en audio.
