# 3. GIT Intermediate

[Link back to readme](../README.md)

## Teamworking in Git

### Kysymys 1

Mitä tapahtuu jos kaksi kehittäjää puskevat tekemänsä uudet commitit joita edeltää sama commit?

- [x] **Ensimmäinen kehittäjä saa pushattua muutoksensa ongelmitta**
- [ ] Git estää kummankin kehittäjän pushit
- [x] **Git estää toisen kehittäjän pushin**
- [x] **Toisena puskeva kehittäjä joutuu ratkaisemaan ongelman**

### Kysymys 2

Miten edellisen tehtävän tilanne voidaan ratkaista?

- [ ] Puskemalla muutokset --force vivulla
- [x] **Yhdistämällä commitit**
- [x] **Hylkäämällä toinen commit**
- [ ] Git ratkaisee tilanteen automaattisesti
- [ ] Ottamalla yhteyttä GitLabin asiakaspalveluun
- [x] **Muuttamalla myöhäisemmän commitin aloituskohtaa**

## Branches

### Kysymys 1

Mitä haarat ovat versionhallinnassa?

- [x] **Haarautuneita kehityspolkuja.**
- [ ] Eri työasemia, joilla ohjelmistoa kehitetään.
- [ ] Hylättyjä versioita.

### Kysymys 2

Miten haarat on toteutettu Gitissä?

- [ ] Commitit, jotka eivät ole minkään toisen commitin edeltäjiä ovat haaroja.
- [ ] Commiteissa on tunniste, joka kertoo niiden olevan haaran pää.
- [x] **Haarat ovat nimettyjä viitteitä, jotka viittaavat johonkin committiin.**

### Kysymys 3

Mitä tapahtuu, kun suoritat checkout-komennon johonkin toiseen haaraan?

- [x] **HEAD siirtyy osoittamaan määriteltyä haara.**
- [x] **Työpuu muuttuu vastaamaan haaran committia.**
- [ ] Git muuttaa nykyisen haaran sisällön vastaamaan toista haaraa.
- [ ] Git tallentaa tilapäisesti nykyisen työpuun tilan.

### Kysymys 4

Mitä hyötyä on haarojen käytöstä?

- [x] **Julkaisukelpoinen ohjelma voidaan pitää erillään kehitysversioista.**
- [ ] Vähemmän committeja tietovarastossa.
- [x] **Rinnakkain tapahtuva työskentely on helpompaa.**
- [x] **Projektin hallinointi ja seuranta helpottuu.**
- [x] **Paikallista tietovarastoa ei tarvitse päivittää jatkuvasti.**
- [ ] Etätietovarastojen tarve poistuu.

## Branches and remotes

### Kysymys 1

Millä seuraavista komennoista voit luoda uuden haaran benchmark-etätietovaraston haarasta "memory_optimization"? Lokaali tietovarastosi ei vielä sisällä haaraa "memory_optimization".

- [x] **`git checkout -b memory_optimization benchmark/memory_optimization`**
- [ ] `git checkout -b memory_optimization origin/memory_optimization`
- [x] **`git checkout memory_optimization`**
- [x] **`git branch memory_optimization benchmark/memory_optimization`**
- [ ] `git branch --track origin/memory_optimization`

### Kysymys 2

Mitä komentoa käytät, jos haluat siirtää nykyisen työhaarasi "development" origin-etätietovarastoon?

- [x] **`git push origin HEAD`**
- [ ] `git push development origin`
- [x] **`git push origin development`**
- [ ] `git push development origin:development`
- [x] **`git push origin development:development`**
- [ ] `git push origin/development`

### Kysymys 3

Millä komentorimpsulla pärjäät lähes missä tahansa push-tilanteessa?

- [ ] `git push origin main`
- [ ] `git push origin main --force`
- [x] **`git push origin HEAD`**
- [ ] `git push origin HEAD --force`

## Moving and merging branches

### Kysymys 1

Mitä merge-operaatiossa tapahtuu?

- [x] **Yhdistetään kaksi haaraa**
- [ ] Tarkistetaan muiden tekemien muutosten yhtensopivuus
- [x] **Viedään commitit toisesta haarasta toiseen**
- [ ] Varmistetaan main-haaran eheys

### Kysymys 2

Mitä eroa on mergellä ja fast-forwardilla?

- [x] **Merge luo commitin**
- [x] **Fast-forward ei luo committia**
- [ ] Merge ei luo committia
- [ ] Fast-forward luo commitin

### Kysymys 3

Mikä on merge-konflikti?

- [ ] Tiimin jäsenten välinen ristiriita tiedostojen yhdistämisestä
- [ ] Merkki korruptoituneesta versiohistoriasta
- [x] **Tiedostojen välinen ristiriita jota Git ei kykene ratkaisemaan**
- [ ] Gitin ominaisuus työn hidastamiseksi

### Kysymys 4

Kuinka monta edeltäjä-committia merge-commitilla on?

- [ ] 0
- [ ] 1
- [ ] 2
- [x] **2 tai enemmän**

## Better workflow

### Question 1

Which of the following benefit from having a clean commit history?

- [x] **Merging**
- [x] **Comparing versions**
- [x] **Rebasing**
- [x] **Squashing versions**

### Question 2

What benefits does patching bring?

- [x] **You can modify a file before commiting**
- [ ] You can hide who made the changes
- [ ] You’ll get less commits
- [x] **You can see your changes line by line**

### Question 3

Which of the following commands shows commits made by Teppo Testaaja in 2019?

- [ ] `git log --commiter="Teemu Teekkari" --after=<1.1.2019> --before=<31.12.2019>`
- [x] **`git log --commiter="Teppo Testaaja" --after=<1.1.2019> --before=<31.12.2019>`**
- [ ] `git log --commiter="Teppo Testaaja" --after=<31.12.2019> --before=<1.1.2019>`
- [ ] `git log --after=<1.1.2019> --before=<31.12.2019>`

### Question 4

Which of the following commands shows you the difference between index.html in your branch and in release branch?

- [ ] `git diff -- index.html`
- [ ] `git diff release --path index.html`
- [x] **`git diff release -- index.html`**
- [ ] `git diff`

## Submodules

### Question 1

What are Git submodules?

- [ ] Downloadable extensions for Git.
- [x] **Repositories in repositories.**
- [ ] A special kind of a branch for large development teams.
- [ ] Parts of Git source code which can be utilized for free.

### Question 2

What could submodules be used for?

- [x] To add other projects and tools to project.
- [x] To separate the development of tools and project.
- [x] For archieving to separate old repositories from each other.
- [ ] To encrypt your source code.

### Question 3

How do you update a submodule?

- [ ] `git submodule update`
- [ ] `git update`
- [x] **`git submodule update --remote <submoduule>`**
- [x] **`git submodule foreach "git fetch origin && git checkout origin/main"`**

### Question 4

How do you clone a project that contains submodules?

- [ ] `git clone --submodules <repository>`
- [x] **`git clone --recurse-submodules <repository>`**
- [x] **`git clone`**

### Question 5

What commands can you use in a submodule?

- [ ] Only submodule commands.
- [x] **All of Git commands.**
- [ ] Nothing. You can only control submodule from your main repository.

## Tagging (or naming) versions

### Question 1

What are tags?

- [x] **References to commits**
- [ ] Ways of communicating with team
- [ ] A type of release
- [x] **A human readable way of marking commits for later use**

### Question 2

How do you move tags to remote repository?

- [ ] `git push <tag name> <remote repository>`
- [ ] `git tag -a -m <message> <name>`
- [x] **`git push <remote repository> <tag name>`**
- [ ] `git tag --help`

### Question 3

What benefits are there in using tags?

- [ ] It’s part of agile development process
- [x] **It’s easier to return to a certain commit**
- [x] **You can know what code went to a release**
- [ ] You can add more information to bad commit messages
- [x] **Tags can be utilized in test automation**
- [ ] Tags are easy way to waste work time

## Repository exercises

### Branching

#### Initializing a repository

1. Add a new remote repository for your repository [https://course-gitlab.tuni.fi/git-course/intermediate-branches.git](https://course-gitlab.tuni.fi/git-course/intermediate-branches.git) NOTE: We assume your repository has the default ’main’ branch in it like GitHub repositories should
2. Fetch the history from the remote repository and merge it to yours. You might have to use --allow-unrelated-histories flag

#### Exercise

1. Create a new branch _feature/create-awesome_ from main branch
2. In branch _feature/create-awesome_ add a following line to file _hello_world.py_

    `print("Hello from feature")`

3. Add and commit changes in _feature/create-awesome_
4. Push your changes in _feature/create-awesome_
5. Create a new branch _release_ from _feature/create-awesome_ branch
6. In branch _release_ add the following line to file _hello_world.py_

    `print("Hello from release")`

7. Add and commit changes in _release_
8. Push your changes in _release_

```shell
git checkout main
# Spell world with a small 'w' because the Tuni checker expects it
printf %b 'print("Hello world")\n' > hello_world.py
git add hello_world.py
git commit -m "Update hello_world"
git push

git checkout -b feature/create-awesome
printf %b 'print("Hello from feature")\n' >> hello_world.py
git add hello_world.py
git commit -m "Update hello_world"
git push

git checkout -b release
printf %b 'print("Hello from release")\n' >> hello_world.py
git add hello_world.py
git commit -m "Update hello_world"
git push
```

### Normal merge

#### Initializing a repository

1. Add a new remote repository for your repository [https://course-gitlab.tuni.fi/git-course/intermediate-normal-merge.git](https://course-gitlab.tuni.fi/git-course/intermediate-normal-merge.git)
2. Fetch the history from the remote repository and merge it to yours. You might have to use --allow-unrelated-histories flag

#### Exercise

Merge branch _feature/add-logging_ to _main_. Merge message should be:

```text
Merge branch 'feature/add-logging'
```

Push your updated _main_

```shell
git checkout main
git remote add intermediate-normal-merge https://course-gitlab.tuni.fi/git-course/intermediate-normal-merge.git
git fetch intermediate-normal-merge
git merge intermediate-normal-merge/master --allow-unrelated-histories
git merge intermediate-normal-merge/feature/add-logging -m "Merge branch 'feature/add-logging'"
git push
```

#### Optional exercise

We have no special automated tests for the optional exercise. You can check the exercise by using git log. In this optional exercise we’ll do the previous exercise from a scratch. After doing this exercise you’ll have a better understanding of when merge can be done without conflicts.

1. Create a new local repository.
2. In main branch create a file _hello_world.py_.
3. Add following line to the file.

    `print("Hello world!")`

4. Add the changes to staging area `git add .`
5. Create first commit with message "Initial commit"
6. Create a new branch _feature/add-logging_
7. In _feature/add-logging_ branch add following line to _hello_world.py_

    `print("Hello once again")`

8. Add changes to staging and commit with message _Add logging_
9. Checkout to _main_ branch and merge changes from _feature/add-logging_ with `--no-ff` flag
10. Check git log and verify that it looks similar to the actual exercise

```shell
mkdir optional
cd optional
git init
printf %b 'print("Hello world!")\n' > hello_world.py
git add .
git commit -m "Initial commit"
git checkout -b feature/add-logging
printf %b 'print("Hello once again")\n' >> hello_world.py
git add .
git commit -m "Add logging"
git checkout master
git merge feature/add-logging --no-ff
```

### Solving merge conflicts

#### Initializing a repository

1. Add a new remote repository for your repository [https://course-gitlab.tuni.fi/git-course/intermediate-merge-conflict.git](https://course-gitlab.tuni.fi/git-course/intermediate-merge-conflict.git)
2. Fetch the history from the remote repository and merge it to yours. You might have to use --allow-unrelated-histories flag

#### Exercise

The repository contains one file hello_world.py. File has been changed in both main and in feature/modify-print. Changes have affected the same lines so automatic merge is not possible. You have to get both changes to your main:

Change in `main` to hello_world.py line 2

Change in `feature/modify-print` to hello_world.py line 3

Merge commit message should be "Fix merge conflicts"

Finally push your main to your remote repository.

```shell
git remote add intermediate-merge-conflict https://course-gitlab.tuni.fi/git-course/intermediate-merge-conflict.git
git fetch intermediate-merge-conflict
git merge intermediate-merge-conflict/master --allow-unrelated-histories
git commit -m "Fix merge conflicts"
git merge intermediate-merge-conflict/feature/modify-print --allow-unrelated-histories
git commit -m "Fix merge conflicts"
git push
```

Note: Probably should have merged the remotes first and then merge the result into my _main_. -mmmkoo

### Optional exercise

We have no special automated tests for the optional exercise. You can check the exercise by using git log. In this optional exercise we’ll do the previous exercise from a scratch. After doing this exercise you’ll have a better understanding of when merge conflict happens and how you can solve them.

1. Create a new local repository
2. Create a file hello_world.py in _main_
3. Add the following line to hello_world.py

    `print("Hello World!")`

4. Add the new file to the index with `git add .`
5. Create the first commit with message _Initial commit_
6. Create a new branch _feature/modify-print_
7. In _main_ add a new line to hello_world.py

    `print("Hello darkness my old friend")`

8. Add the file to the index and commit the changes with message _Add print in main_
9. In branch _feature/modify-print_ add a line to hello_world.py

    `print("I've come to talk with you again")`

10. Add the file to the index and commit the changes with message _Modify print_
11. Start a merge from _feature/modify-print_ to _main_
12. Fix merge conflicts
13. Create a merge commit with message _Fix merge conflicts_
14. Check git log and verify that it looks similar to the actual exercise

```shell
mkdir optional
cd optional
git init
printf %b 'print("Hello World!")\n' > hello_world.py
git add .
git commit -m "Initial commit"
git branch feature/modify-print
printf %b 'print("Hello darkness my old friend")\n' >> hello_world.py
git add .
git commit -m "Add print in main"
git checkout feature/modify-print
printf %b "print(\"I've come to talk with you again\")\n" >> hello_world.py
git add .
git commit -m "Modify print"
git checkout main
git merge feature/modify-print
git commit -m "Fix merge conflicts"
```
