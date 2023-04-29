# Docstrings de classes

Docstrings devem conter as seguintes informações:
- Um breve sumário do seu propósito e funcionamento;
- Métodos públicos, junto com uma breve descrição;
- Atributos de classe;
- Alguma coisa relacionada à interface para subclasses, se a classe tiver esse objetivo de ser herdada.

As docstrings dos métodos das classes devem conter:
- Uma breve descrição do que é o método e o que ele faz;
- Os parâmetros (obrigatórios e opcionais);
- Rotular parâmetros que são considerados opcionais ou têm valores padrões;
- Qualquer efeito negativo que pode ocorrer quando o método for executado;
- Exceções que podem ser levantadas;
- Restrições de quando o método pode ser chamado.

Exemplo:
```py
class Animal:
    """
    A class used to represent an Animal

    ...

    Attributes
    ----------
    says_str : str
        a formatted string to print out what the animal says
    name : str
        the name of the animal
    sound : str
        the sound that the animal makes
    num_legs : int
        the number of legs the animal has (default 4)

    Methods
    -------
    says(sound=None)
        Prints the animals name and what sound it makes
    """

    says_str = "A {name} says {sound}"

    def __init__(self, name, sound, num_legs=4):
        """
        Parameters
        ----------
        name : str
            The name of the animal
        sound : str
            The sound the animal makes
        num_legs : int, optional
            The number of legs the animal (default is 4)
        """

        self.name = name
        self.sound = sound
        self.num_legs = num_legs

    def says(self, sound=None):
        """Prints what the animals name is and what sound it makes.

        If the argument `sound` isn't passed in, the default Animal
        sound is used.

        Parameters
        ----------
        sound : str, optional
            The sound the animal makes (default is None)

        Raises
        ------
        NotImplementedError
            If no sound is set for the animal or passed in as a
            parameter.
        """

        if self.sound is None and sound is None:
            raise NotImplementedError("Silent Animals are not supported!")

        out_sound = self.sound if sound is None else sound
        print(self.says_str.format(name=self.name, sound=out_sound))
```