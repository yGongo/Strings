# Stringhe
#### Il linguaggio utilizzato in questo codice è il C#
>  Questo programma è sviluppato per lo studio delle stringhe
 
  #  **Descrizione:**
  Realizzazione di un app MAUI  per  lo **studio delle stringhe**  ASCII 7 bit (non unicode).
 
  Dobbiamo immaginare di programmare con un linguaggio privo delle facility date dagli oggetti String come ad esempio il linguaggio **C**.
 
  **NON  SI POSSONO** quindi utilizzare le seguenti classi/metodi di **manipolazione delle stringhe** tipiche dei linguaggi C#,C++,Pyton.
 
  Esempi:
 
 StringBuilder, ToUpper(), ToLower(), Count(), Lenght(), Replace(), IsLetter(), IsNumber() etc...
 
 #  **Finalità del programma:**
 
 Questo programma serve per consolidare
 
 *    l'uso dei vettori
 
 *  l'uso dei cicli (for, do, while)
 
 *   l'uso della mascheratura dei bit con operatori logici and, or, xor, not su dati interi
 
 *  l'uso dei metodi
 
 *  la tabella ASCII
 
 *   il pensiero computazionale, gli algoritmi di ordinamento
 
# **Cosa si ottiene da questo programma:**

* Versione **maiuscola** delle stringhe

*  versione   **minusciola** delle stringhe

*  se contiene solo **caratteri alfabetici**

*   Di    **quante lettere** è formata

*  se contiene solo caratteri  **alfanumerici**

*   La sua versione **rovesciata**

# **Metodi utilizzati:**

```
int lunghezza(string s)
    {
        char[] caratteri = s.ToCharArray();
        int lunghezza = 0;

        foreach (char c in caratteri)
        {
            lunghezza++;
        }

        return lunghezza;
    }
```

> Questo metodo è utilizzato per sostituire "**Length()**; utilizzato per contare i caratteri.

```
    char MaiuscolaChar(char input)
    {
        char output = ' ';
            if (input >= 'a' && input <= 'z')
            {
                output = (char)(input - ('a' - 'A'));
            }
            else
            {
                output = input;
            }
        return output;
    }
```

> Questo metodo è utilizzato per sostituire  il "**ToUpper()**", utilizzato per convertire le stringhe in maiuscolo (Esempio: 'ciao' ---> 'CIAO').

```
    string MinuscolaString(string input)
    {
        string output = "";
        char[] caratteri = input.ToCharArray();
        foreach (char c in caratteri)
        {
            if (c >= 'A' && c <= 'Z')
            {
                output += (char)(c - ('A' - 'a'));
            }
            else
            {
                output += c;
            }
        }
        return output;
    }
```

> Questo metodo è utilizzato per sostituire il "**ToLower()**", utilizzato per convertire le stringhe in minuscolo (Esempio: 'cIaO' ---> 'ciao').


```
    string Reverse(string input)
    {
        string output = "";

        for (int i = lunghezza(input) - 1; i >= 0; i--)
        {
            output+=input[i];
        }
        return output;
    }

```
> Questo metodo è utilizzato per **rovesciare** la stringa (Esempio: 'Ciao' ---> 'oaiC').

```
    bool alfabetico(string str)
    {
        foreach (char c in str)
        {
            // se un carattere non è una lettera alfabetica, restituisce false
            if (!LetteraChar(c))
            {
                return false;
            }
        }
        return true;
    }

```
> Questo metodo è utilizzato per controllare se la stringa è formata **SOLO** da caratteri **alfabetici** (Esempio: 'ciaoo' = True ---> 'ciao12' = False).

```
    bool AlfaNumerico(string input)
    {
        foreach (char c in input)
        {
            if (!LetteraONumero(c))
            {
                return false;
            }
        }
        return true;
    }


```
> Questo metodo è utilizzato per controllare se la stringa è formata da caratteri **alfanumerici** (Esempio: 'ciao233' = True ---> 'ciao244!' = False).

```
    bool LetteraONumero(char c)
    {
        return (c >= 'a' && c <= 'z') || (c >= 'A' && c <= 'Z') || (c >= '0' && c <= '9');
    }

    //Funzione .IsAWhiteSpace di una stringa // ✓ FUNZIONA ✓ //
    bool eunospazzio(char c)
    {
        if (c == ' ' || c == '\t' || c == '\n' || c == '\r')
        {
            return true;
        }
        else
        {
            return false;
        }
    }
```
> Questo metodo è utilizzato per sostituire il "**Char.IsLetterOrNumeber()**", utilizzato per controllare se nella stringa è presente una lettere o un numero.
