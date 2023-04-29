# Docstrings de pacotes, módulos e funções

## Pacotes

Em um pacote, a docstring deve ser posicionada no arquivo `__init__.py` e deve listar seus módulos e subpacotes exportáveis.

Exemplos sem os resumos dos módulos e subpacotes:
- `mysklearn/__init__.py` (Package)
```python
"""
Linear regression for Python
============================

mysklearn is a complete package for implmentin linear regression in python.
"""
```

- `mysklearn/preprocessing/__init__.py` (Subpackage)
```python
"""
A subpackage for standard preprocessing operations.
"""
```

## Módulos

Em um módulo:
- a docstring deve apresentar uma breve descrição do módulo e seu propósito;
- lista de todas as classes, exceções, funções e quaisquer outros objetos exportados pelo módulo.

Exemplos sem os objetos do módulo:
- `mysklearn/preprocessing/normalize.py` (Module)
```python
"""
A module for normalizing data.
"""
```

## Funções

As docstrings de funções devem conter os mesmos itens das de métodos de classes:
- Uma breve descrição do que é a função e o que ela faz;
- Os parâmetros (obrigatórios e opcionais);
- Rotular parâmetros que são considerados opcionais ou têm valores padrões;
- Qualquer efeito negativo que pode ocorrer quando a função for executada;
- Exceções que podem ser levantadas;
- Restrições de quando a função pode ser chamada.