# 2. GIT Basics

[Link back to readme](../README.md)

## Creating a local repository

### Kysymys 1

Aloitat uuden ohjelmisto-projektin. Miten alustat tyhjän tietovaraston hakemistoon _uusi_projekti_?

- [ ] `git init`
- [x] **`cd uusi_projekti && git init`**
- [x] **`git init uusi_projekti`**
- [ ] `git clone uusi_projekti`
- [ ] `git clone –empty uusi_projekti`

### Kysymys 2

Miten lisäät _origin_-nimisen etätietovaraston uudelle projektillesi?

- [x] **`git remote add origin <url>`**
- [ ] `git remote add <url> origin`
- [ ] `git remote origin set-url <url>`
- [ ] `git remtoe set-url origin <url>`
- [x] **En lisää, kloonasin projektipohjan etätietovarastosta joka toimii originina.**

### Kysymys 3

Miten voit varmistua siitä, että etätietovarastosi on asetettu oikein?

- [x] **Tarkastamalle nimen ja osoitteen: `git remote -v`**
- [x] **Asettamalla osoitteen uudelleen: `git remote set-url <alias> <url>`**
- [x] **Poistamalla vanhan aliaksen ja luomalla uuden: `git remote remove <alias>` ja `git remote add <alias> <url>`**

## Staging and creating commits

### Kysymys 1

Mitä tietoja saat selville komennolla git status?

- [x] **Mihin committiin/haaraan HEAD osoittaa.**
- [x] **Mihin työpuussa on tehty muutoksia, joita olisi mahdollista lisätä indeksiin.**
- [x] **Mitä muutoksia on lisätty työpuuhun.**
- [x] **Jos HEAD osoittaa haaraan, joka seuraa jotain etätietovaraston haaraa. Montako committia paikallinen haara on edellä tai jäljessä seurattua haaraa.**
- [ ] Milloin edellinen commit on tehty?

### Kysymys 2

Milloin tiedosto näkyy sekä indeksissä, että indeksiin lisäämättömänä?

- [x] Olet muokannut tiedostia indeksiin lisäämisen jälkeen.
- [x] Olet lisännyt indeksiin vain osan tiedostoon tehdyistä muutoksista.
- [ ] Git-peikko on päättänyt jekuttaa sinua.

### Kysymys 3

Mitä komentoa käytät, jos haluat poistaa tiedoston commitista, mutta saatat tarvita sitä vielä.

`git rm --cached <polku>`

### Kysymys 4

Mitä tapahtuu, jos käytät --amendia commitin muokkaamiseen pushin jälkeen.

- [ ] Muokkaan committia ja jatkan käyttöä täysin normaalisti.
- [ ] Muokkaan committia ja rikon tietovaraston.
- [x] **Luon uuden commitin. Paikallinen haarani haarautuu erilleen etätietovaraston haarasta.**
- [ ] Luon uuden commitin, jonka jälkeen voin päivittää etätietovaraston samaan tilaan.
- [ ] Git estää komennon suorittamisen.

### Kysymys 5

Mitä tapahtuu, jos suoritat git resetin sen jälkeen kun olet käyttänyt komentoa git rm main.cpp?

- [ ] Git poistaa poiston indeksistä ja palauttaa poistetun tiedoston.
- [ ] Git poistaa poiston indeksistä ja palauttaa poistetun tiedoston version, joka löytyy HEAD:ista
- [x] **Git poistaa poiston indeksistä ja pitää poistetun tiedoston poistettuna.**

## Basic usage of version history

### Kysymys 1

Mitä teet jos olet muokannut versioitua tiedostoa ja haluat peruuttaa kaikki muutokset kyseiseen tiedostoon?

- [ ] `git checkout HEAD -- .`
- [x] **`git checkout HEAD -- <polku>`**
- [ ] `git pull`
- [ ] `git checkout HEAD`

### Kysymys 2

Mitä teet jos haluat peruuttaa kaikki muutokset versioituihin tiedostoihin?

- [x] **`git checkout HEAD -- .`**
- [ ] `git checkout HEAD -- <polku>`
- [ ] `git pull`
- [ ] `git checkout HEAD`

### Kysymys 3

Mitä teet jos haluat palauttaa jonkin tietyn version polusta.

- [ ] `git checkout HEAD -- <polku>`
- [x] **`git log <polku> && git checkout <commit> -- <polku>`**
- [ ] `git pull`
- [ ] `git log <polku> && git checkout <commit>`

## Synchronizing repositories

### Kysymys 1

Millä käskyllä saat katseltua etätietovarastoon origin tulleita muutoksia sotkematta lokaalia tietovarastoasi?

- [ ] `git fetch main`
- [x] **`git fetch origin`**
- [ ] `git fetch --force`
- [ ] `git pull origin`

### Kysymys 2

Millä käskyllä saat etätietovarastoon origin tulleet muutokset lokaaliin tietovarastoosi?

- [ ] `git fetch origin`
- [ ] `git pull main`
- [ ] `git pull --force`
- [x] **`git pull origin`**

### Kysymys 3

Millä käskyllä saat siirrettyä muutokset HEADin osoittamasta haarasta etätietovarastoon origin?

- [ ] `git pull origin`
- [ ] `git push main`
- [x] **`git push origin`**
- [ ] `git fetch origin`

### Kysymys 4

Miten ratkeaa jokainen epäonnistunut push?

- [ ] Älä valitse `git push --force`
- [ ] `git push --force`
- [ ] Älä valitse `git push --force`
- [x] **Selvittämällä mistä ongelma johtuu. Ei ainakaan `git push --force`**

## Basic Exercises

### Initializing a repository

1. Create or clone a repository for this exercise.
2. Create file `hello_world.py` to the root folder. The file will be ran with Python3.9 and it should print out ”Hello World!”.

```shell
touch hello_world.py
printf %b 'print("Hello World!")' >> hello_world.py
git add hello_world.py
git commit -m "Create hello_world.py"
git push
```

### File version return

1. Add a new remote repository [https://course-gitlab.tuni.fi/git-course/basics-materials.git](https://course-gitlab.tuni.fi/git-course/basics-materials.git) for your repository
2. Fetch and merge version history from the remote repository. Because repositories don’t share common ancestor you’ll have to do merge with --allow-unrelated-histories flag. The first time you pull content from a remote, git will ask you

```text
    hint: You have divergent branches and need to specify how to reconcile them.
    hint: You can do so by running one of the following commands sometime before``
    hint: your next pull:
    hint:
    hint:   git config pull.rebase false  # merge
    hint:   git config pull.rebase true   # rebase
    hint:   git config pull.ff only       # fast-forward only
    hint: You can replace "git config" with "git config --global" to set a default
    hint: preference for all repositories. You can also pass --rebase, --no-rebase,
    hint: or --ff-only on the command line to override the configured default per
    hint: invocation.
    fatal: Need to specify how to reconcile divergent branches.
```

Run the command `git config pull.rebase false` to go forward.

3. You can take a look at `mergesort.py` history [from here](https://course-gitlab.tuni.fi/git-course/basics-materials/commits/master/basics/mergesort.py).
4. You’ll have to recover this version of `mergesort.py` to your repository.

```shell
git pull https://course-gitlab.tuni.fi/git-course/basics-materials.git master --allow-unrelated-histories
git checkout dd8c56c -- ./basics/mergesort.py
git commit -m "Return file mergesort.py"
git push
```

### Removing files

1. Remove files from paths `test_inputs` ja `test_outputs`.

```shell
git rm ./basics/*/1.*
git commit -m "Remove files in /test_inputs and /test_outputs"
git push
```

### Create .gitignore

1. Create `.gitignore` to root folder
2. Add rules which filter out files that end with
   - .in, .out ja .pyc

```shell
touch .gitignore
printf %b '*.in\n*.out\n*.pyc\n' >> .gitignore
git add .gitignore
git commit -m "Add .gitignore"
```
