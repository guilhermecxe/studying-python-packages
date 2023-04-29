# Testes

Os testes das funções e classes de um pacote devem ser armazenados em uma pasta chamada `tests` na raíz do pacote e ter a mesma estrutura do pacote em sí, ou seja, os mesmos módulos separados em subpacotes se necessário e até mesmo arquivos `__init__`'s. A única diferença da estrutura é a adição de `test_` no início do nome do pacote, subpacote ou módulo.

Usando `pytest` para criar os testes, basta rodar `$ pytest` no terminal na raíz do pacote que o `pytest` irá entrar na pasta apropriada dos testes, e rodará os testes nos módulos que começam com `test_`.

---

## Testando diferentes versões do Python

`tox` é um pacote usado para rodar diferentes versões de Python e, por tanto, ele é para testar o pacote com as diferentes versões. Mas para isso todas as versões a serem rodadas precisam estar instaladas no computador.

Para configurar o `tox` no nosso pacote, criamos um arquivo chamado `tox.ini` na raíz dele e escrevemos algo como:
```
[tox]
envlist = py27, py35, py36, py37

[testenv]
deps = pytest
commands =
    pytest
```

`envlist` traz as versões a serem usadas, `deps` são as dependências para o `tox` ser rodado. Depois vem os comandos de terminal a serem rodados em cada versão do Python, que é apenas o `pytest` para testar o pacote.

A partir daqui basta rodar `$ tox` na raíz do pacote para testar todas as versões.