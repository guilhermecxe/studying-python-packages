# Distribuição

- **Distribution package**: versão empacotada do pacote pronta para ser instalada.
- **Source distritution**: é basicamente o código fonte do pacote.
- **Wheel distribution**: É uma versão processada do pacote feita para ser instalada mais rapidamente.

---

## Construindo os arquivos de distribuição

Uma boa prática é construir os dois métodos de distribuição, Source e Wheel. E é possível fazer isso usando `setup.py` com o comando abaixo.

`$ python setup.py sdist bdist_wheel`

Isso vai criar uma pasta na raíz do repositório chamada `dist` com os arquivos de distribuição. E, fora de `dist`, vai criar as pastas `build` e `<package-name>.egg-info` que podem ser ignorados.

---

## Distribuindo o pacote no PyPI

Para distribuir o pacote usando `pip` é necessário criar uma conta no PyPI e subir o pacote lá.

## MANIFEST.in

O `MANIFEST.in` do pacote deve vir na pasta raíz, junto com `setup.py`.

Por padrão, a distribuição do pacote não inclui a lincença e nem o README. E em `MANIFEST.IN` é possível incluir arquivos que devem ser distruídos também. Exemplo:

`MANIFEST.IN`
```
include LICENSE
include README.md
```