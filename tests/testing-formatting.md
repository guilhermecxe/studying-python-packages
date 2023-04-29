# flake8

`flake8` é um pacote que checa se o estilo do código Python está de acordo com as boas práticas especificadas no PEP8.

`$ flake8 <file>` para rodar o pacote em um arquivo `.py` específico. O resultado é uma linha para cada violação da PEP8 com o nome do arquivo, a linha e a coluna da violação, o código dela e uma descrição da mesma.

É possível adicionar `# noqa` como comentário em uma linha para que qualquer violação presente nela seja ignorada. Ou `# noqa <code>` especificando o código de uma violação que deve ser ignorada naquela linha.

`$ flake8 --ignore <code>,<code> <file>` para ignorar as violações dos códigos no arquivo inteiro.

`$ flake8 --select <code>,<code> <file>` para sinalizar apenas as violações dos códigos especificados.

É possível ainda criar um arquivo chamado `setup.cfg` para armazenar as configurações desejadas para o `flake8` no pacote. O arquivo deve se parecer com isso:

```
[flake8]
ignore = E302
exclude = setup.py
per-file-ignores =
    example_package/example_package.py: E222
```

Se o comando `$ flake8` rodar sem resultados quer dizer que não houveram violações.