# Istruzioni

Istruzioni varie per gestire il progetto

## Clonare il progetto da zero

```
git clone git@github.com:diegolandini/diderot.git
cd diderot
git submodule update --init --recursive
```

## Scaricare le ultime modifiche

```
git pull
```

## Aggiungere le modifiche

Nota: vale per qualsiasi modifica, aggiunta o anche cancellazione: in ogni caso bisogna sempre eseguire il comando ```git add```

```
git add pippo.md
git commit -m "ho modificato pippo.md"
git push
```

## Aggiornare hugo

Verificato che il template academic é piuttosto schizzinoso sulle versioni di hugo, é opportuno utilizzare sempre la versione di hugo che il template si aspetta. La maniera piú semplice é *NON* usare il package manager di Linux, ma installarlo direttamente. Fortunatamente hugo é un solo file binario, quindi é molto semplice.

Per esempio, la versione 0.63.1 di hugo si puó scaricare da qui:

https://github.com/gohugoio/hugo/releases/download/v0.63.1/hugo_extended_0.63.1_Linux-64bit.tar.gz

dopodiché si puó decomprimere il file

```
tar xzvf ~/Downloads/hugo_extended_0.63.1_Linux-64bit.tar.gz
```

e poi copiare i binario di hugo in una directory in cui possa essere eseguito (ossia una directory sul PATH, come per esempio /usr/bin)

```
cd /tmp
tar xzvf ~/Downloads/hugo_extended_0.63.1_Linux-64bit.tar.gz
sudo cp hugo /usr/bin
```

dopodiché verificare che la nuova versione di hugo sia disponibile

```
hugo version
Hugo Static Site Generator v0.63.1-CE9ACEB7/extended linux/amd64 BuildDate: 2020-01-23T20:15:47Z
```

## Gestire un conflitto

## Annullare un commit sbagliato

In generale non si dovrebbe mai pushare su repo qualcosa che non funzioni, ma puó succedere per un motivo o per l'altro.

```git log```

o, piú concisamente:

``` git log --oneline```

e si vede la lista degli ultimi commit, identificati da un numero esadecimale.
Annotarsi il numero della commit, per esempio ```2a6741b```, ed uscire premendo ```q``` (quit)

Nota:non serve usare tutto il numero esadecimale, bastano i primi caratteri

A questo punto per ripristinare la situazione cosí com'era dopo quel commit:

```git revert --no-commit 2a6741b..HEAD```
```git push```

NOTA:

se si vuole annullare l'ultimo commit non serve trovare l'identificativo esadecimale del commit.
Questo comando annulla l'ultimo:

```git revert HEAD~1..HEAD```




