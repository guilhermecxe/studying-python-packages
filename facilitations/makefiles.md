# Makefiles

É um arquivo usado para automatizar partes da construção do pacote. Exemplo:
```Makefile
dist: ## builds source and wheel package
    python3 setup.py sdist bdist_wheel
clean-build: ## remove build artifacts
    rm -fr build/
    rm -fr dist/
    rm -fr .eggs/
test: ## run tests quickly with the default Python
    pytest
release: dist ## package and upload a release
    twine upload dist/*
```

Agora basta que, por exemplo, `$ make dist` seja executado no terminal para que `$ python3 setup.py sdist bdist_wheel` seja executado. Diminuindo a quantidade de códigos a serem sempre lembrados.

`make help` lista as funções dentro de `Makefile`.