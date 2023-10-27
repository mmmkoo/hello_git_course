# 1. Introduction

[Link back to readme](../README.md)

## Basics of Version control

### Kysymys 1

Miksi versionhallintajärjestelmä on parempi vaihtoehto kuin käsin ylläpidettävä versiointi?

- [ ] Ei ole, työkalut ovat liian kalliita hyötyihin nähden
- [x] **Säästetään aikaa**
- [ ] Käsin kopioimalla säästetään aikaa
- [x] **Muutosten jakaminen helpottuu**

### Kysymys 2

Kumpi on suositumpi versionhallinnan tapa ohjelmistokehityksessä?

- [x] **Hajautettu**
- [ ] Keskitetty
- [ ] Manuaalinen

### Kysymys 3

Mitä hyötyjä versionhallinnalla saavutetaan?

- [x] **Komponenttien rinnakkainen kehitys**
- [x] **Lähdekoodin helppo jakelu**
- [x] **Turvallisempi kehitys**
- [x] **Kehityksen seuraaminen**

## Git

### Kysymys 1

Mihin Git tallentaa tietovarastoon liittyvät tiedot?

- [ ] Vain etätietovarastoon
- [x] **Kansioon nimeltään .git**
- [ ] Jokainen tiedosto sisältää sitä koskevan versiohistorian

### Kysymys 2

Mitä tietoja _commit_ sisältää?

- [x] **SHA1**
- [ ] SSH-avaimen
- [x] **Viestin**
- [ ] Edellisen commitin sisältämät muutokset
- [x] **Tiedon edellisestä commitista**
- [x] **Commitin tekijän**

### Kysymys 3

Mitä versionhallintaan kannattaa tallentaa?

- [x] **Konfiguraatiotiedostot**
- [x] **Dokumentaatio**
- [ ] Projektin kuvat
- [ ] Salasanat
- [ ] Projektista käännetyt tiedostot kuten .jar paketit
- [x] **Toimiva lähdekoodi**

## Brief look at how Git works

### Kysymys 1

Mitkä ovat hyvän commitin merkkejä?

- [x] **Koodi kääntyy**
- [ ] Koodi toimii mahdollisimman tehokkaasti
- [ ] Se sisältää vain yhden tiedoston
- [x] **Se ei sisällä turhaa koodia**

### Kysymys 2

Valitse hyvät commit viestit seuraavista vaihtoehdoista?

- [ ] Fixed function parseJSON()
- [x] **Fix function parseJSON()**
- [ ] Make stuff work
- [x] **Create class Student**
- [x] **Refactor component ConfirmationModal**
- [ ] Make new component ConfirmationModal work. Previously the component did not render correctly when toggled. This was due to bad state management. Fixed by using prevState syntax.

Note: Do not use imperfect form in commit messages, e.g. _Fixed_ function parseJSON().
