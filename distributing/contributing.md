# Versões e Histórico

## CONTRIBUTING.md

Arquivo que convida outros desenvolvedores para trabalharem com o pacote. E diz a eles como começar a contribuir.

## HISTORY.md

Conhecido como *history*, *changelog* or *release notes*. Diz aos usuário o que mudou de uma versão para outra.

## Versão do pacote

Existem dois arquivos que armazenam a versão do pacote:
- `<root>/<package>/__init__.py`
- `<root>/setup.py`

E quando a versão de um pacote muda os valores devem ser alterados no dois arquivos.

`bumpversion` é um pacote que atualiza os dois arquivos de uma vez.

```
$ bumpversion major # para alterar o primeiro valor
$ bumpversion minor # para alterar o segundo
$ bumpversion patch # para alterar o terceiro
```