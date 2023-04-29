# `pyment`

O pacote `pyment` pode ser usado para gerar documentação de diferentes estilos em Python.

## Exemplo:
Criando a estrutura da documentação para cada função, classe ou método no arquivo `textanalysis.py`:
```
pyment -w -o numpydoc textanalysis.py
```

- `-w`: para sobrescrever um arquivo, no caso, o arquivo `.py`.
- `-o numpydoc`: especificando o estilo da documentação