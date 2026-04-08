# Specifikacija zahtev za rešitev programa lojalnosti Maestro

## 1. Kratek opis

Trgovska veriga Maestro želi uvesti program lojalnosti za svoje stranke. Namen programa je povečati število nakupov, nagraditi zveste stranke ter omogočiti boljši pregled nad njihovim nakupnim vedenjem. Sistem bo podpiral včlanitev strank v program, dodeljevanje statusov, obračun točk zvestobe, koriščenje ugodnosti in administrativno upravljanje pravil programa.

Rešitev bo sestavljena iz spletne aplikacije za stranke, administrativnega dela za zaposlene oziroma upravljavce programa ter integracije z obstoječim poslovnim informacijskim sistemom in podatkovno bazo Oracle.

Sistem mora biti zasnovan tako, da podpira veliko število uporabnikov, dva jezika, sodoben uporabniški vmesnik ter možnost kasnejšega spreminjanja pravil programa brez večjih posegov v programsko rešitev.

---

## 2. Funkcionalne zahteve

Funkcionalne zahteve določajo, katere funkcije mora sistem zagotavljati za uporabnike in administratorje.

### 2.1 Seznam funkcionalnih zahtev

#### FZ-1: Registracija v program lojalnosti
Sistem mora omogočati registracijo stranke v program lojalnosti preko spleta.

#### FZ-2: Preverjanje unikatnosti uporabnika
Sistem mora ob registraciji preveriti, da posamezna oseba ne more biti registrirana večkrat z istim elektronskim naslovom ali drugimi enoličnimi podatki.

#### FZ-3: Ustvarjanje uporabniškega računa
Sistem mora ob uspešni registraciji ustvariti uporabniški račun za dostop do portala.

#### FZ-4: Dodelitev kartice lojalnosti
Sistem mora vsakemu članu programa dodeliti kartico lojalnosti oziroma zapis o članstvu.

#### FZ-5: Vodenje statusa člana
Sistem mora za vsakega člana voditi status lojalnosti: osnovni, bronasti, srebrni ali zlati.

#### FZ-6: Prevzem podatkov o nakupih
Sistem mora iz poslovnega informacijskega sistema prevzemati podatke o opravljenih nakupih.

#### FZ-7: Mesečni obračun točk zvestobe
Sistem mora enkrat mesečno izračunati točke zvestobe za pretekli mesec.

#### FZ-8: Izračun točk po pravilih
Sistem mora dodeliti točke glede na znesek nakupov in status člana.

#### FZ-9: Sprememba statusa člana
Sistem mora pred dodelitvijo točk preveriti, ali član izpolnjuje pogoje za spremembo statusa.

#### FZ-10: Hramba zgodovine statusov
Sistem mora hraniti zgodovino vseh sprememb statusov posamezne stranke.

#### FZ-11: Hramba zgodovine točk
Sistem mora hraniti zgodovino vseh dodelitev in koriščenj točk.

#### FZ-12: Pregled zbranih točk
Sistem mora članu omogočiti vpogled v trenutno stanje točk.

#### FZ-13: Pregled zgodovine nakupov
Sistem mora članu omogočiti vpogled v zgodovino nakupov, ki vplivajo na obračun točk.

#### FZ-14: Pregled statusa
Sistem mora članu omogočiti vpogled v svoj trenutni status lojalnosti.

#### FZ-15: Pregled nagradnega programa
Sistem mora članu omogočiti pregled razpoložljivih nagrad ali ugodnosti.

#### FZ-16: Koriščenje točk
Sistem mora članu omogočiti koriščenje zbranih točk za izbrane nagrade ali ugodnosti.

#### FZ-17: Večjezičnost
Sistem mora omogočati uporabo najmanj v slovenskem in angleškem jeziku.

#### FZ-18: Administracija pravil programa
Administrator mora imeti možnost upravljanja pravil za dodeljevanje točk.

#### FZ-19: Administracija pravil prehajanja med statusi
Administrator mora imeti možnost upravljanja pravil za prehajanje med statusi.

#### FZ-20: Upravljanje nagrad
Administrator mora imeti možnost upravljanja nagrad, ki so na voljo za koriščenje točk.

#### FZ-21: Pregled statistik
Administrator mora imeti možnost pregleda statistik nakupov, članov, točk in statusov.

#### FZ-22: Poročila za poljubno obdobje
Administrator mora imeti možnost pregleda stanj in poročil za poljubno obdobje.

#### FZ-23: Iskanje in pregled članov
Administrator mora imeti možnost iskanja članov in vpogleda v njihove podatke.

#### FZ-24: Upravljanje uporabniških podatkov
Administrator mora imeti možnost popravljanja določenih podatkov člana skladno s pravicami dostopa.

#### FZ-25: Avtentikacija uporabnikov
Sistem mora omogočati prijavo uporabnikov v portal.

#### FZ-26: Upravljanje dostopnih pravic
Sistem mora ločevati pravice med člani programa in administratorji.

---

### 2.2 Funkcionalna dekompozicija

#### 2.2.1 Upravljanje članstva
- registracija člana
- preverjanje podatkov
- ustvarjanje uporabniškega računa
- dodelitev kartice lojalnosti
- vodenje osnovnih podatkov člana

#### 2.2.2 Upravljanje nakupov
- prevzem podatkov iz poslovnega sistema
- evidenca nakupov
- povezava nakupov s članom
- pregled zgodovine nakupov

#### 2.2.3 Upravljanje točk zvestobe
- mesečni obračun točk
- izračun točk po pravilih
- vodenje stanja točk
- evidenca dodelitev in porabe točk

#### 2.2.4 Upravljanje statusov
- začetna dodelitev statusa
- preverjanje pogojev za napredovanje
- preverjanje pogojev za znižanje statusa
- sprememba statusa
- evidenca zgodovine statusov

#### 2.2.5 Upravljanje nagrad
- pregled kataloga nagrad
- koriščenje točk
- zmanjšanje stanja točk
- evidenca koriščenj

#### 2.2.6 Uporabniški portal
- prijava
- pregled profila
- pregled statusa
- pregled točk
- pregled nakupov
- pregled nagrad
- koriščenje točk
- izbira jezika

#### 2.2.7 Administrativni modul
- pregled članov
- pregled statistik
- upravljanje pravil točkovanja
- upravljanje pravil statusov
- upravljanje nagrad
- priprava poročil

#### 2.2.8 Integracijski modul
- povezava s poslovnim informacijskim sistemom
- povezava s podatkovno bazo Oracle
- izmenjava podatkov o nakupih
- sinhronizacija članov in točk

---

### 2.3 Diagram primerov uporabe

#### Akterji
- član programa
- administrator
- poslovni informacijski sistem

#### Primeri uporabe za člana programa
- registracija v program
- prijava v portal
- pregled statusa
- pregled točk
- pregled nakupov
- pregled nagrad
- koriščenje točk
- sprememba jezika

#### Primeri uporabe za administratorja
- prijava v administracijo
- pregled članov
- pregled statistik
- upravljanje pravil točkovanja
- upravljanje pravil statusov
- upravljanje nagrad
- priprava poročil

#### Primeri uporabe za poslovni informacijski sistem
- posredovanje podatkov o nakupih
- sinhronizacija podatkov za obračun

![Diagram Primerov Uporabe](https://vip.lavbic.net/plantuml/png/XPDDRjim48NtFCN0-mIbuv-c20mKMHb5WA123Z2M68SonH4eIeiKlK5rYDv5lLT7iccGheFkzFW-SXvdAADUFNW2f_Tl7WhjLEurMI4mz-HWDlmoQA5sj7TOuGomWKTU2VRNej9MDzuXoycTLeBzJ8sXpchOPfEvpOGOAw3T6mMpZ7Ug2WoLQ2mrNiCJAZwCPl130BIDoh5XxhlQJpLoNI9q8SrquikZZCbdnqWtGUGycXCpJnd5rGjeFFgsmHDoTmtnDFI74x2u1bWyj3Lr9sHv7U6mnObOnSGtSlhFxw5NjbH9gNLCPRLJbQfs2ALwruUGzxEuLcpeUJZdFFSVNPkxgKCn-IccNcg7dIbnZ3H-QdDCHXqlXTfI_cVBiRNd77B-4PyqHrxCG8yWZfFa13hCKYukRzwzyoEggK3FCO6EGz5lWK-cygGQDVJy8cddSEXRcpHU9lFXrqi5xRHNtSLZaMlnKuZnHu2Rcytq22CnZyLTB1QnMCPY5OjrB7ZGqpzrFZnMzudYKIPIfZBTojrE9BTrcmMn56Bi1jpU7YLyWOS7RNFJ5cgp6Rrry5R_UC5QfCvV)

## 3. Podatkovni model

### 3.1 Entitete

#### Stranka
- `id_stranka`
- `ime`
- `priimek`
- `email`
- `telefon`
- `naslov`
- `datum_registracije`
- `uporabnisko_ime`
- `geslo`
- `jezik`
- `status_aktiven`

#### Kartica_lojalnosti
- `id_kartica`
- `stevilka_kartice`
- `id_stranka`
- `datum_izdaje`
- `stanje_aktivna`

#### Status
- `id_status`
- `naziv_statusa`
- `opis`

#### Zgodovina_statusa
- `id_zgodovina_statusa`
- `id_stranka`
- `id_status`
- `datum_od`
- `datum_do`
- `razlog_spremembe`

#### Nakup
- `id_nakup`
- `id_stranka`
- `datum_nakupa`
- `znesek`
- `vir_podatka`
- `id_racuna`

#### Pravilo_tockovanja
- `id_pravilo`
- `status`
- `spodnja_meja_zneska`
- `zgornja_meja_zneska`
- `st_tock`
- `datum_veljavnosti_od`
- `datum_veljavnosti_do`

#### Pravilo_statusa
- `id_pravilo_statusa`
- `trenutni_status`
- `pogoj`
- `ciljni_status`
- `datum_veljavnosti_od`
- `datum_veljavnosti_do`

#### Transakcija_tock
- `id_transakcija`
- `id_stranka`
- `datum_transakcije`
- `tip_transakcije`
- `st_tock`
- `opis`
- `id_nakup`
- `id_nagrada`

#### Nagrada
- `id_nagrada`
- `naziv`
- `opis`
- `potrebno_tock`
- `aktivna`

#### Uporabnik_sistema
- `id_uporabnik`
- `uporabnisko_ime`
- `geslo`
- `vloga`
- `zadnja_prijava`

### 3.2 Povezave med entitetami
- Stranka ima eno ali več kartic lojalnosti.
- Stranka ima en trenutni status in zgodovino statusov.
- Stranka opravi nič ali več nakupov.
- Stranka ima nič ali več transakcij točk.
- Pravilo točkovanja določa, koliko točk pripada za kombinacijo statusa in zneskovnega razreda.
- Pravilo statusa določa prehode med statusi.
- Nagrada je povezana s koriščenjem točk preko transakcije točk.

### 3.3 Osnovni relacijski prikaz
- Stranka `1:N` Nakup
- Stranka `1:N` Zgodovina_statusa
- Stranka `1:N` Transakcija_tock
- Stranka `1:N` Kartica_lojalnosti
- Status `1:N` Zgodovina_statusa
- Nagrada `1:N` Transakcija_tock

---

## 4. Tehnične zahteve

- Rešitev mora biti zasnovana kot spletna aplikacija.
- Sistem mora podpirati najmanj 500.000 uporabnikov.
- Sistem mora omogočati nadaljnjo rast števila uporabnikov.
- Rešitev mora podpirati slovenski in angleški jezik.
- Sistem mora uporabljati obstoječo podatkovno bazo Oracle.
- Sistem mora omogočati integracijo z obstoječim poslovnim informacijskim sistemom.
- Sistem mora zagotavljati avtentikacijo in avtorizacijo uporabnikov.
- Sistem mora zagotavljati varno hrambo osebnih podatkov in gesel.
- Gesla morajo biti hranjena v zgoščeni obliki.
- Sistem mora omogočati beleženje revizijske sledi pomembnih sprememb.
- Uporabniški vmesnik mora biti sodoben, intuitiven in odziven.
- Sistem mora omogočati konfigurabilnost pravil brez spremembe izvorne kode, kadar je to mogoče.
- Sistem mora zagotavljati visoko razpoložljivost in ustrezno zmogljivost pri mesečnih obračunih.
- Sistem mora omogočati izdelavo varnostnih kopij in obnovo podatkov.
- Sistem mora biti skladen z zahtevami varstva osebnih podatkov.

---

## 5. Definicija vmesnikov

### 5.1 Sistemski vmesnik

Sistemski vmesnik predstavlja povezavo med sistemom lojalnosti in poslovnim informacijskim sistemom trgovske verige.

#### Namen
- prevzem podatkov o nakupih
- prenos podatkov o članstvu
- podpora obračunu točk
- sinhronizacija sprememb

#### Vhodni podatki iz poslovnega sistema
- identifikator nakupa
- datum nakupa
- znesek nakupa
- identifikator stranke ali kartice
- podatki o računu

#### Izhodni podatki v druge sisteme
- stanje točk člana
- trenutni status člana
- informacije o koriščenju točk
- poročila in statistike

#### Zahteve za sistemski vmesnik
- standardiziran format izmenjave podatkov
- preverjanje pravilnosti podatkov
- obravnava napak pri prenosu
- beleženje prenesenih transakcij
- možnost paketne obdelave podatkov

---

### 5.2 Vmesnik s podatkovno bazo

Sistem bo uporabljal obstoječo podatkovno bazo Oracle.

#### Zahteve
- dostop do tabel članov, nakupov, točk, statusov in nagrad
- podpora transakcijam pri obračunu in koriščenju točk
- zagotavljanje integritete podatkov
- indeksiranje ključnih atributov za hitro poizvedovanje
- podpora shranjenim proceduram za zahtevnejše obračune, kjer je smiselno
- ločevanje operativnih in poročevalskih poizvedb, kjer je potrebno

#### Ključne operacije
- vstavljanje novega člana
- posodobitev podatkov člana
- zapis nakupa
- zapis transakcije točk
- sprememba statusa
- poizvedbe za poročila
- poizvedbe za uporabniški portal

---

### 5.3 Uporabniški vmesnik

Uporabniški vmesnik mora biti dostopen prek spletnega brskalnika.

#### Zahteve za članski portal
- prijava uporabnika
- registracija novega člana
- pregled statusa
- pregled točk
- pregled zgodovine nakupov
- pregled razpoložljivih nagrad
- koriščenje točk
- nastavitev jezika

#### Zahteve za administrativni vmesnik
- prijava administratorja
- iskanje in pregled članov
- pregled statistik
- pregled poročil
- upravljanje pravil točkovanja
- upravljanje pravil statusov
- upravljanje nagrad

#### Splošne zahteve
- intuitivna navigacija
- odziven dizajn
- jasna sporočila o napakah
- enotna grafična podoba
- podpora večjezičnosti

---

## 6. Zaslonske maske

### 6.1 Registracija člana
**Namen:** vnos podatkov za včlanitev v program.

**Elementi:**
- ime
- priimek
- elektronski naslov
- telefon
- naslov
- uporabniško ime
- geslo
- ponovitev gesla
- izbor jezika
- gumb za registracijo

### 6.2 Prijava uporabnika
**Namen:** prijava v portal.

**Elementi:**
- uporabniško ime ali e-naslov
- geslo
- gumb za prijavo
- povezava za pozabljeno geslo

### 6.3 Domača stran člana
**Namen:** pregled osnovnih informacij o članu.

**Elementi:**
- ime člana
- trenutni status
- stanje točk
- zadnji nakupi
- hitri dostop do nagrad
- izbira jezika

### 6.4 Pregled točk
**Namen:** prikaz stanja in zgodovine točk.

**Elementi:**
- trenutno stanje točk
- seznam dodeljenih točk
- seznam porabljenih točk
- datum transakcije
- opis transakcije

### 6.5 Pregled nakupov
**Namen:** prikaz nakupov člana.

**Elementi:**
- datum nakupa
- znesek
- številka računa
- pridobljene točke
- filter po obdobju

### 6.6 Pregled nagrad
**Namen:** prikaz razpoložljivih nagrad.

**Elementi:**
- naziv nagrade
- opis nagrade
- potrebno število točk
- razpoložljivost
- gumb za koriščenje

### 6.7 Administrativna maska za člane
**Namen:** iskanje in pregled članov.

**Elementi:**
- iskalnik po imenu, priimku, e-naslovu ali številki kartice
- seznam zadetkov
- osnovni podatki člana
- status
- stanje točk
- zgodovina sprememb

### 6.8 Administrativna maska za pravila točkovanja
**Namen:** upravljanje pravil za dodeljevanje točk.

**Elementi:**
- status člana
- zneskovni razred
- število točk
- datum veljavnosti
- gumb za dodajanje, urejanje, brisanje

### 6.9 Administrativna maska za pravila statusov
**Namen:** upravljanje pravil prehajanja med statusi.

**Elementi:**
- trenutni status
- pogoj
- ciljni status
- datum veljavnosti
- gumb za dodajanje, urejanje, brisanje

### 6.10 Administrativna maska za poročila in statistike
**Namen:** pregled poslovnih kazalnikov programa.

**Elementi:**
- izbor obdobja
- število članov
- število aktivnih članov
- skupno število točk
- porazdelitev po statusih
- grafični prikaz
- izvoz poročila

---

## 8. Slovar izrazov

**Program lojalnosti**  
Sistem ugodnosti, s katerim trgovska veriga nagrajuje zveste stranke.

**Član programa**  
Stranka, ki se je registrirala v program lojalnosti.

**Kartica lojalnosti**  
Identifikator člana programa, s katerim se član povezuje z nakupi in točkami.

**Status člana**  
Raven članstva v programu lojalnosti. V tem sistemu so to osnovni, bronasti, srebrni in zlati status.

**Točke zvestobe**  
Nagradne točke, ki jih član prejme glede na opravljene nakupe in svoj status.

**Koriščenje točk**  
Uporaba zbranih točk za pridobitev nagrade ali ugodnosti.

**Nakup**  
Poslovni dogodek, pri katerem član opravi nakup v trgovski verigi.

**Pravilo točkovanja**  
Pravilo, ki določa število točk glede na status člana in vrednost nakupa.

**Pravilo statusa**  
Pravilo, ki določa pogoje za napredovanje ali nazadovanje člana med statusi.

**Administracija**  
Del sistema, namenjen upravljanju članov, pravil, nagrad in poročil.

**Poslovni informacijski sistem**  
Obstoječi sistem trgovske verige, iz katerega se prevzemajo podatki o nakupih.

**Oracle podatkovna baza**  
Obstoječa baza podatkov podjetja, ki se uporablja tudi za podporo programu lojalnosti.

**Uporabniški portal**  
Spletna aplikacija, namenjena članom programa za pregled podatkov in koriščenje ugodnosti.
