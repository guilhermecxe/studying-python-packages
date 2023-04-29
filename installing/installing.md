# Instalando o package

## Configurando

Para instalar um pacote na máquina para que ele seja acessável de qualquer script em Python precisamos que ele esteja dentro de uma pasta, geralmente com o mesmo nome do pacote e com essa pasta contendo também um arquivo chamado `setup.py` que é usado para instalar o package.

O arquivo `setup.py` deve se parecer com isso:
```py
from setuptools import setup, find_packages

setup(
    author="James Fulton",
    description="A complete package for linear regression.",
    name="mysklearn",
    version="0.1.0",
    packages=find_packages(include=["mysklearn", "mysklearn.*"]),
)
```
A função `find_packages` especifica o pacote chamado `mysklearn` e os seus subpacotes.

**Dica para o controle de versão:**

version number = (major number).(minor number).(patch number)
- Correção de bugs e melhorias de funcionalidades já existentes: aumenta patch number
- Novas funcionalidades: aumenta minor number
- Grandes alterações: aumenta major number


## Instalando na máquina

Para instalar o pacote navegamos até onde se encontra `setup.py` e digitamos `pip install -e .` no terminal. `-e` diz que o pacote é editável e que as alterações feitas nele devem ser aplicadas a qualquer script que faça o `import` dele, do contrário seria necessário reinstalar o pacote a cada alteração. E `.` diz para instalar o pacote presente no diretório atual.

## Dependências

## Especificando dependências do pacote

```py
from setuptools import setup, find_packages

setup(
    ...
    install_requires=['pandas', 'scipy', 'matplotlib'],
)
```

## Especificando dependências do pacote com versões específicas

```py
from setuptools import setup, find_packages

setup(
    ...
    install_requires=[
        'pandas>=1.0',
        'scipy==1.1',
        'matplotlib>=2.2.1,<3'
    ],
)
```
O objetivo deve ser sempre permitir a maior quantidade de versões possíveis. Uma dica é procurar na documentação das dependências e verificar quando as funcionalidades usadas pelo meu pacote foram criadas.

## Especificando a versão do Python

```py
from setuptools import setup, find_packages

setup(
    ...
    python_requires='>=2.7, !=3.0.*, !=3.1.*',
    # Python acima ou igual a 2.7 e diferente de 3.0 e 3.1
)
```

## Salvando os pacotes usados no desenvolvimento

`pip freeze > requirements.txt`

Esses requisitos são importantes para que diferentes desenvolvedores trabalhem usando as mesmas versões deles.

## Instalando os pacotes usados no desenvolvimento

`pip install -r requirements.txt`

## Linceça

A lincença do pacote deve vir na pasta raíz, junto com `setup.py`.

[Como escolher uma licença](https://choosealicense.com/)

## README

O README do pacote deve vir na pasta raíz, junto com `setup.py`.

O arquivo `README` deve ter as seguintes seções:

- Title
- Description and Features
- Installation
- Usage examples
- Contributing
- License
