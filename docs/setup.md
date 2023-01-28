# Setup

Este projeto assume que você possui a versão mais recente de [Python3](https://www.python.org/), de **PIP** e **GIT**, caso precise instalar por favor visite [https://www.python.org/downloads/](https://www.python.org/downloads/).

Este projeto foi testado e desenvolvido com a versão `Python 3.10.x`


## Clonando o repositório

``` bash
git clone https://github.com/ZRafaF/OpencvPosHold

cd OpencvPosHold
```

## Criando ambiente virtual

> Esse passo não é obrigatório, mas sim **recomendado**

``` bash
python3 -m pip install --user virtualenv

python -m venv venv
```

Com isso um ambiente virtual chamado `venv` será criado no diretório do projeto.

Para ativar:


!!! admonition-windows "Ativação no **Windows**"

    ``` bash title=""
    venv/Scripts/activate
    ```

ou

!!! admonition-linux "Ativação no **Linux**"

    ``` bash title=""
    source venv/bin/activate
    ```
___

## Instalando dependências

Primeiro será necessário instalar o OpenCV, neste caso temos 2 opções de instalação, utilizar um **gerenciador de pacotes** ou compilar da fonte.

Em sistemas embarcados, como a Raspberry PI, é recomendado que este seja **compilado da fonte**

!!! warning

    Devido a evolução do projeto com o tempo a versão do OpenCV que está sendo utilizada é a `opencv_contrib`, entretanto tecnicamente não estamos utilizando nenhum pacote da versão contrib. Logo {==TALVEZ==} seja possível utilizar apenas a versão padrão do OpenCV.

### OpenCV

A versão que estaremos instalando é a `opencv_contrib`, para informações sobre a instalação da versão padrão por favor verificar a [documentação](https://pypi.org/project/opencv-python/).

!!! admonition-pc "Utilizando um gerenciador de pacotes"

    ``` bash title=""
    pip install opencv-contrib-python
    ```
    Caso deseje a opção *headless* pode usar
    ``` bash title=""
    pip install opencv-contrib-python-headless
    ```

ou

!!! admonition-raspi "Compilando da fonte"

    1. Seguir o tutorial de instalação (cerca de 8 horas na RaspberryPi 3 ) [aqui](https://linuxize.com/post/how-to-install-opencv-on-raspberry-pi/)

    2. Linkar o modulo [aqui](https://pyimagesearch.com/2019/09/16/install-opencv-4-on-raspberry-pi-4-and-raspbian-buster/), vá na categoria _Sym-link your OpenCV 4 on the Raspberry Pi_

    Por fim será necessário linkar-lo ao projeto:

    ```bash
    cd /usr/local/lib/python3.9/site-packages/cv2/python-3.9

    sudo mv cv2.cpython-39-arm-linux-gnueabihf.so cv2.so

    cd <OpencvPosHold>

    ln -s /usr/local/lib/python3.9/site-packages/cv2/python-3.9/

    cv2.so cv2.so
    ```
___

### Outros

``` bash
pip install numpy

sudo pip install pupil-apriltags

sudo pip install dronekit

pip install pymavlink

pip install argparse

pip install imutils

pip install picamera
```