# Specifikacija zahtev za rešitev programa lojalnosti Maestro

## Kazalo

1. [Kratek opis](#1-kratek-opis)
2. [Funkcionalne zahteve](#2-funkcionalne-zahteve)
3. [Nefunkcionalne zahteve](#3-nefunkcionalne-zahteve)
4. [Podatkovni model](#4-podatkovni-model)
5. [Diagram prehajanja stanj](#5-diagram-prehajanja-stanj)
6. [Odločitvena tabela za točkovanje](#6-odločitvena-tabela-za-točkovanje)
7. [Tehnične zahteve](#7-tehnične-zahteve)
8. [Definicija vmesnikov](#8-definicija-vmesnikov)
9. [API načrt](#9-api-načrt)
10. [Zaslonske maske](#10-zaslonske-maske)
11. [Realizacija primerov uporabe](#11-realizacija-primerov-uporabe)
12. [Slovar izrazov](#12-slovar-izrazov)

---

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

### 2.3 Diagram primerov uporabe

**Akterji:**
- član programa
- administrator
- poslovni informacijski sistem

**Primeri uporabe za člana programa:**
- registracija v program
- prijava v portal
- pregled statusa
- pregled točk
- pregled nakupov
- pregled nagrad
- koriščenje točk
- sprememba jezika

**Primeri uporabe za administratorja:**
- prijava v administracijo
- pregled članov
- pregled statistik
- upravljanje pravil točkovanja
- upravljanje pravil statusov
- upravljanje nagrad
- priprava poročil

**Primeri uporabe za poslovni informacijski sistem:**
- posredovanje podatkov o nakupih
- sinhronizacija podatkov za obračun

![Diagram primerov uporabe](https://vip.lavbic.net/plantuml/png/XPDDRjim48NtFCN0-mIbuv-c20mKMHb5WA123Z2M68SonH4eIeiKlK5rYDv5lLT7iccGheFkzFW-SXvdAADUFNW2f_Tl7WhjLEurMI4mz-HWDlmoQA5sj7TOuGomWKTU2VRNej9MDzuXoycTLeBzJ8sXpchOPfEvpOGOAw3T6mMpZ7Ug2WoLQ2mrNiCJAZwCPl130BIDoh5XxhlQJpLoNI9q8SrquikZZCbdnqWtGUGycXCpJnd5rGjeFFgsmHDoTmtnDFI74x2u1bWyj3Lr9sHv7U6mnObOnSGtSlhFxw5NjbH9gNLCPRLJbQfs2ALwruUGzxEuLcpeUJZdFFSVNPkxgKCn-IccNcg7dIbnZ3H-QdDCHXqlXTfI_cVBiRNd77B-4PyqHrxCG8yWZfFa13hCKYukRzwzyoEggK3FCO6EGz5lWK-cygGQDVJy8cddSEXRcpHU9lFXrqi5xRHNtSLZaMlnKuZnHu2Rcytq22CnZyLTB1QnMCPY5OjrB7ZGqpzrFZnMzudYKIPIfZBTojrE9BTrcmMn56Bi1jpU7YLyWOS7RNFJ5cgp6Rrry5R_UC5QfCvV)

### 2.4 Opisi primerov uporabe

#### PU-1: Registracija uporabnika v program lojalnosti

**Akterji:** stranka (primarni), sistem za pošiljanje e-pošte (sekundarni)

**Predpogoji:**
- Stranka dostopa do spletnega portala Maestro.
- Stranka še nima uporabniškega računa.

**Naknadni pogoji:**
- V sistemu je ustvarjen nov zapis stranke.
- Stranki je dodeljena kartica lojalnosti z začetnim statusom *osnovni*.
- Stranki je poslano potrditveno e-sporočilo.

**Osnovni tok:**
1. Stranka izbere možnost »Registracija« na vstopni strani portala.
2. Sistem prikaže obrazec za registracijo (ime, priimek, e-naslov, telefon, naslov, uporabniško ime, geslo, ponovitev gesla, izbor jezika).
3. Stranka vnese podatke in potrdi obrazec.
4. Sistem preveri popolnost in pravilnost formata podatkov.
5. Sistem preveri, da uporabniško ime in e-naslov v bazi še ne obstajata.
6. Sistem zgosti geslo in shrani podatke stranke.
7. Sistem ustvari kartico lojalnosti s povezavo na stranko in dodeli začetni status *osnovni*.
8. Sistem zapiše začetni status v zgodovino statusov.
9. Sistem pošlje potrditveno e-sporočilo s povezavo za aktivacijo.
10. Sistem prikaže potrditveno sporočilo o uspešni registraciji.

**Alternativni tokovi:**

*A1: E-naslov že obstaja*
- 5a. Sistem ugotovi, da e-naslov že obstaja.
- 5b. Sistem obvesti stranko, da je e-naslov že registriran, in ponudi povezavo do prijave ali obnove gesla.
- 5c. Primer uporabe se zaključi neuspešno.

*A2: Neveljaven format podatkov*
- 4a. Sistem zazna neveljaven format (npr. e-naslov, manjkajoča polja, prekratko geslo).
- 4b. Sistem označi napačna polja in prikaže sporočilo o napaki.
- 4c. Stranka popravi podatke in nadaljuje s korakom 3.

*A3: Gesli se ne ujemata*
- 4d. Sistem zazna, da se polji »geslo« in »ponovitev gesla« ne ujemata.
- 4e. Sistem obvesti stranko in zahteva ponovni vnos.

*A4: Napaka pri pošiljanju e-sporočila*
- 9a. Sistem ne uspe poslati potrditvenega e-sporočila.
- 9b. Sistem vseeno ustvari račun, vendar ga označi kot *neaktiviran*.
- 9c. Sistem obvesti stranko o težavi in ponudi možnost ponovnega pošiljanja.

#### PU-2: Mesečni pripis točk zvestobe

**Akterji:** sistem (sprožitelj — časovnik), poslovni informacijski sistem (sekundarni)

**Predpogoji:**
- Obstajajo veljavna pravila točkovanja za obračunsko obdobje.
- V sistemu obstajajo člani z opravljenimi nakupi v preteklem mesecu.

**Naknadni pogoji:**
- Vsakemu članu so dodeljene točke za nakupe preteklega meseca.
- Po potrebi je posodobljen status članov.
- Vse transakcije so zabeležene v zgodovini točk in zgodovini statusov.

**Osnovni tok:**
1. Časovnik prvi delovni dan v mesecu ob 02:00 sproži postopek obračuna.
2. Sistem od poslovnega informacijskega sistema prevzame podatke o nakupih za pretekli mesec.
3. Sistem preveri, da pri prevzemu ni prišlo do napak in da so podatki popolni.
4. Sistem za vsakega člana z nakupi v preteklem mesecu:
   1. izračuna skupni znesek nakupov,
   2. prebere trenutni status člana,
   3. uporabi veljavno pravilo točkovanja in izračuna število točk,
   4. ustvari transakcijo točk tipa *pripis*,
   5. posodobi stanje točk člana,
   6. preveri pravila za spremembo statusa,
   7. če pogoji za napredovanje (ali nazadovanje) izpolnjeni, posodobi status in zapiše spremembo v zgodovino.
5. Sistem zapiše povzetek obračuna v revizijsko sled.
6. Sistem administratorju pošlje poročilo o opravljenem obračunu.

**Alternativni tokovi:**

*A1: Napaka pri prevzemu podatkov iz poslovnega sistema*
- 3a. Sistem zazna, da povezava do poslovnega sistema ni vzpostavljena ali da podatki niso popolni.
- 3b. Sistem zapiše napako v dnevnik in obvesti administratorja.
- 3c. Obračun se ne izvede; primer uporabe se ponovi po odpravi napake.

*A2: Manjkajoče pravilo točkovanja*
- 4.3a. Sistem ne najde veljavnega pravila točkovanja za kombinacijo statusa in zneskovnega razreda.
- 4.3b. Sistem za tega člana preskoči obračun, ga uvrsti v seznam izjem in obvesti administratorja.

*A3: Član izpolnjuje pogoje za nazadovanje statusa*
- 4.6a. Sistem ugotovi, da član v zadnjih 12 mesecih ne dosega praga za trenutni status.
- 4.6b. Sistem mu zniža status na ustrezno nižjo raven.
- 4.6c. Sprememba se zapiše v zgodovino statusov z razlogom »nazadovanje zaradi premajhne porabe«.

*A4: Delna napaka med obračunom posameznega člana*
- 4.5a. Pri posameznem članu pride do napake (npr. baza ni dostopna).
- 4.5b. Sistem transakcijo zavrne in zavrne tudi sprememb statusa za tega člana, da se ohrani integriteta.
- 4.5c. Član se uvrsti na seznam za ponovni obračun.

---

## 3. Nefunkcionalne zahteve

### 3.1 Zmogljivost
- **NZ-1:** Sistem mora podpirati najmanj 500.000 registriranih uporabnikov.
- **NZ-2:** Odzivni čas tipične spletne strani v portalu ne sme presegati 2 sekundi pri 95 % zahtevkov.
- **NZ-3:** Mesečni obračun točk za celotno bazo članov mora biti dokončan v manj kot 4 urah.
- **NZ-4:** Sistem mora podpirati vsaj 1.000 sočasnih uporabnikov portala.

### 3.2 Razširljivost
- **NZ-5:** Arhitektura mora omogočati horizontalno skaliranje aplikacijske plasti.
- **NZ-6:** Podatkovni model mora omogočati rast nad začetnih 500.000 uporabnikov brez sprememb sheme.

### 3.3 Razpoložljivost
- **NZ-7:** Sistem mora zagotavljati razpoložljivost najmanj 99,5 % na mesečni ravni.
- **NZ-8:** Načrtovani izpadi morajo biti izvedeni izven delovnega časa trgovin.

### 3.4 Varnost
- **NZ-9:** Gesla morajo biti shranjena v zgoščeni obliki z uporabo sodobne algoritmne družine (bcrypt / argon2).
- **NZ-10:** Vsa komunikacija med odjemalcem in strežnikom mora potekati prek HTTPS.
- **NZ-11:** Sistem mora ločevati vloge član, administrator in sistemski uporabnik.
- **NZ-12:** Vsi pomembni dogodki (registracija, sprememba statusa, koriščenje točk, sprememba pravil) morajo biti zabeleženi v revizijski sledi.
- **NZ-13:** Skladnost z GDPR — pravica do vpogleda, popravka in izbrisa osebnih podatkov.

### 3.5 Uporabnost
- **NZ-14:** Vmesnik mora podpirati slovenski in angleški jezik.
- **NZ-15:** Vmesnik mora biti odziven in uporaben na zaslonih od 360 px naprej.
- **NZ-16:** Vmesnik mora upoštevati osnovne smernice dostopnosti (WCAG 2.1, raven AA).

### 3.6 Vzdrževanost
- **NZ-17:** Pravila točkovanja in pravila prehoda med statusi morajo biti konfigurabilna brez sprememb izvorne kode.
- **NZ-18:** Sistem mora podpirati avtomatske varnostne kopije podatkovne baze najmanj enkrat dnevno.
- **NZ-19:** Sistem mora omogočati obnovo iz varnostne kopije v manj kot 4 urah.

### 3.7 Združljivost
- **NZ-20:** Sistem mora uporabljati obstoječo podatkovno bazo Oracle.
- **NZ-21:** Sistem mora podpirati integracijo z obstoječim poslovnim informacijskim sistemom prek standardnega vmesnika (REST ali sporočilna vrsta).
- **NZ-22:** Spletni portal mora delovati v zadnjih dveh različicah brskalnikov Chrome, Firefox, Edge in Safari.

---

## 4. Podatkovni model

### 4.1 Entitete

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

### 4.2 Povezave med entitetami
- Stranka ima eno ali več kartic lojalnosti.
- Stranka ima en trenutni status in zgodovino statusov.
- Stranka opravi nič ali več nakupov.
- Stranka ima nič ali več transakcij točk.
- Pravilo točkovanja določa, koliko točk pripada za kombinacijo statusa in zneskovnega razreda.
- Pravilo statusa določa prehode med statusi.
- Nagrada je povezana s koriščenjem točk preko transakcije točk.

### 4.3 Osnovni relacijski prikaz
- Stranka `1:N` Nakup
- Stranka `1:N` Zgodovina_statusa
- Stranka `1:N` Transakcija_tock
- Stranka `1:N` Kartica_lojalnosti
- Status `1:N` Zgodovina_statusa
- Nagrada `1:N` Transakcija_tock

---

## 5. Diagram prehajanja stanj

Status člana se spreminja na podlagi skupne porabe v zadnjih 12 mesecih.

### 5.1 Stanja
- **Osnovni** — začetno stanje vsakega novega člana.
- **Bronasti** — član s skupno porabo nad 300 € v zadnjih 12 mesecih.
- **Srebrni** — član s skupno porabo nad 1.000 € v zadnjih 12 mesecih.
- **Zlati** — član s skupno porabo nad 3.000 € v zadnjih 12 mesecih.

### 5.2 Prehodi

| Iz stanja | V stanje | Pogoj |
|---|---|---|
| (začetno) | Osnovni | uspešna registracija |
| Osnovni | Bronasti | letna poraba ≥ 300 € |
| Bronasti | Srebrni | letna poraba ≥ 1.000 € |
| Srebrni | Zlati | letna poraba ≥ 3.000 € |
| Zlati | Srebrni | letna poraba pade pod 3.000 € |
| Srebrni | Bronasti | letna poraba pade pod 1.000 € |
| Bronasti | Osnovni | letna poraba pade pod 300 € |
| katerokoli | Deaktiviran | član zahteva izbris ali postane neaktiven > 24 mesecev |

Statusi se preverjajo enkrat mesečno ob obračunu točk. Vir podatkov za pogoj je `nakup` v zadnjih 12 mesecih za danega člana.

![Diagram prehajanja stanj](https://vip.lavbic.net/plantuml/png/dPE_JiCm4CPtFyNDY4Rzmv8E7L1N118IGu7XsXoDazIkR2T3HpQ6F0G36uyHNgHFmZbfcxJPAaMofVlTztrtaPrq6S5SujhW1hQ6OanG9GZMyG43VxhSGbLcg901xK641oJhZ1RYzUOT1eCPF5gb2oLX2hdTqjytmuRMaY5SoGI5Q845LYKvlZRQdSgG3STXU1k6iF_yXOmfBUwDLcYThq-6dWWlYMT3IrCBZ89XZOo37hJ8iDROV_t0fCRQsYc2dwJZvwiyj3QunAQnQMip-ORMliUFZaQdZBxX6AKlVy8FSS_b3-GM8-9xrC6xwftybmrjdBC1sX_GSpZ6wIveJfWwMKY3Ybjs63ig4EHkQQJ5DuMP1DKWf606uplOaAKL5UUkryjqfxrUfTtmzHgYs-gb-3a8eRGZC78TEz0Vn-qAW2T31Hd_llnsrpgX0YonKK4HSPrKQj3LubMfDEWbVuPVIwvoSBegqu2f5scce33Djr1ms4WbCeRHkCaauq2GYi174Fy0)

---

## 6. Odločitvena tabela za točkovanje

Točke se obračunajo glede na **status člana** in **zneskovni razred** mesečnih nakupov. Pravila so konfigurabilna (entiteta `Pravilo_tockovanja`).

### 6.1 Vhodi in izhodi

**Vhodi:**
- C1: status člana (osnovni / bronasti / srebrni / zlati)
- C2: skupni znesek nakupov v mesecu (€)

**Izhod:**
- A: število pripisanih točk

### 6.2 Tabela

| Pravilo | Status (C1) | Mesečni znesek (C2) | Točke (A) |
|---|---|---|---|
| R1  | osnovni  | 0 – 49,99      | 0   |
| R2  | osnovni  | 50 – 199,99    | 1 točka na 1 € |
| R3  | osnovni  | ≥ 200          | 1,2 točke na 1 € |
| R4  | bronasti | 0 – 49,99      | 0   |
| R5  | bronasti | 50 – 199,99    | 1,2 točke na 1 € |
| R6  | bronasti | ≥ 200          | 1,5 točke na 1 € |
| R7  | srebrni  | 0 – 49,99      | 1 točka na 1 € |
| R8  | srebrni  | 50 – 199,99    | 1,5 točke na 1 € |
| R9  | srebrni  | ≥ 200          | 1,8 točke na 1 € |
| R10 | zlati    | 0 – 49,99      | 1,5 točke na 1 € |
| R11 | zlati    | 50 – 199,99    | 2 točki na 1 € |
| R12 | zlati    | ≥ 200          | 2,5 točke na 1 € |

**Primer:** član s srebrnim statusom v marcu opravi nakupov za 320 €. Uporabi se pravilo R9 → 320 × 1,8 = **576 točk**.

---

## 7. Tehnične zahteve

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

## 8. Definicija vmesnikov

### 8.1 Sistemski vmesnik

Sistemski vmesnik predstavlja povezavo med sistemom lojalnosti in poslovnim informacijskim sistemom trgovske verige.

**Namen:**
- prevzem podatkov o nakupih
- prenos podatkov o članstvu
- podpora obračunu točk
- sinhronizacija sprememb

**Vhodni podatki iz poslovnega sistema:**
- identifikator nakupa
- datum nakupa
- znesek nakupa
- identifikator stranke ali kartice
- podatki o računu

**Izhodni podatki v druge sisteme:**
- stanje točk člana
- trenutni status člana
- informacije o koriščenju točk
- poročila in statistike

**Zahteve za sistemski vmesnik:**
- standardiziran format izmenjave podatkov
- preverjanje pravilnosti podatkov
- obravnava napak pri prenosu
- beleženje prenesenih transakcij
- možnost paketne obdelave podatkov

### 8.2 Vmesnik s podatkovno bazo

Sistem bo uporabljal obstoječo podatkovno bazo Oracle.

**Zahteve:**
- dostop do tabel članov, nakupov, točk, statusov in nagrad
- podpora transakcijam pri obračunu in koriščenju točk
- zagotavljanje integritete podatkov
- indeksiranje ključnih atributov za hitro poizvedovanje
- podpora shranjenim proceduram za zahtevnejše obračune, kjer je smiselno
- ločevanje operativnih in poročevalskih poizvedb, kjer je potrebno

**Ključne operacije:**
- vstavljanje novega člana
- posodobitev podatkov člana
- zapis nakupa
- zapis transakcije točk
- sprememba statusa
- poizvedbe za poročila
- poizvedbe za uporabniški portal

### 8.3 Uporabniški vmesnik

Uporabniški vmesnik mora biti dostopen prek spletnega brskalnika.

**Zahteve za članski portal:**
- prijava uporabnika
- registracija novega člana
- pregled statusa
- pregled točk
- pregled zgodovine nakupov
- pregled razpoložljivih nagrad
- koriščenje točk
- nastavitev jezika

**Zahteve za administrativni vmesnik:**
- prijava administratorja
- iskanje in pregled članov
- pregled statistik
- pregled poročil
- upravljanje pravil točkovanja
- upravljanje pravil statusov
- upravljanje nagrad

**Splošne zahteve:**
- intuitivna navigacija
- odziven dizajn
- jasna sporočila o napakah
- enotna grafična podoba
- podpora večjezičnosti

---

## 9. API načrt

Vmesnik je REST, izmenjava v JSON. Avtentikacija prek JWT žetona, razen za javne končne točke.

### 9.1 Avtentikacija

| Metoda | Pot | Opis |
|---|---|---|
| POST | `/api/auth/register` | Registracija novega člana |
| POST | `/api/auth/login` | Prijava (vrne JWT) |
| POST | `/api/auth/logout` | Odjava |
| POST | `/api/auth/password-reset` | Zahteva za ponastavitev gesla |

### 9.2 Član (portal)

| Metoda | Pot | Opis |
|---|---|---|
| GET | `/api/me` | Podatki o prijavljenem članu |
| PUT | `/api/me` | Posodobitev podatkov člana |
| GET | `/api/me/status` | Trenutni status in zgodovina |
| GET | `/api/me/points` | Stanje točk |
| GET | `/api/me/points/history?from=&to=` | Zgodovina transakcij točk |
| GET | `/api/me/purchases?from=&to=` | Zgodovina nakupov |
| GET | `/api/me/language` | Trenutna jezikovna nastavitev |
| PUT | `/api/me/language` | Sprememba jezika |

### 9.3 Nagrade in koriščenje

| Metoda | Pot | Opis |
|---|---|---|
| GET | `/api/rewards` | Seznam nagrad |
| GET | `/api/rewards/{id}` | Podrobnosti nagrade |
| POST | `/api/rewards/{id}/redeem` | Koriščenje točk za nagrado |

### 9.4 Administracija

| Metoda | Pot | Opis |
|---|---|---|
| GET | `/api/admin/members?search=&status=` | Iskanje članov |
| GET | `/api/admin/members/{id}` | Podrobnosti člana |
| PUT | `/api/admin/members/{id}` | Popravek podatkov člana |
| GET | `/api/admin/scoring-rules` | Pravila točkovanja |
| POST | `/api/admin/scoring-rules` | Novo pravilo |
| PUT | `/api/admin/scoring-rules/{id}` | Sprememba pravila |
| DELETE | `/api/admin/scoring-rules/{id}` | Brisanje pravila |
| GET | `/api/admin/status-rules` | Pravila prehoda statusov |
| POST | `/api/admin/status-rules` | Novo pravilo statusa |
| PUT | `/api/admin/status-rules/{id}` | Sprememba |
| DELETE | `/api/admin/status-rules/{id}` | Brisanje |
| GET | `/api/admin/reports/summary?from=&to=` | Povzetek poročila |
| GET | `/api/admin/reports/export?format=csv` | Izvoz poročila |

### 9.5 Integracija s poslovnim sistemom

| Metoda | Pot | Opis |
|---|---|---|
| POST | `/api/integration/purchases` | Paketni prevzem nakupov (poslovni sistem → loyalty) |
| POST | `/api/integration/calculate-points` | Ročni proženje mesečnega obračuna |
| GET | `/api/integration/health` | Status vmesnika |

### 9.6 Standardni odgovori

- `200 OK` — uspešna poizvedba
- `201 Created` — nov vir je nastal
- `400 Bad Request` — napaka v vhodnih podatkih
- `401 Unauthorized` — manjka ali napačen žeton
- `403 Forbidden` — uporabnik nima pravic
- `404 Not Found` — vir ne obstaja
- `409 Conflict` — npr. e-naslov že obstaja, nezadostno število točk
- `500 Internal Server Error` — sistemska napaka

### 9.7 Primer: registracija

```http
POST /api/auth/register
Content-Type: application/json

{
  "ime": "Ana",
  "priimek": "Novak",
  "email": "ana.novak@example.com",
  "telefon": "+38640123456",
  "naslov": "Slovenska 1, Ljubljana",
  "uporabnisko_ime": "ananovak",
  "geslo": "Geslo123!",
  "jezik": "sl"
}
```

Odgovor:

```json
{
  "id_stranka": 10421,
  "stevilka_kartice": "MAESTRO-10421",
  "status": "osnovni",
  "potrditev_email_poslan": true
}
```

---

## 10. Zaslonske maske

### 10.1 Registracija člana
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

### 10.2 Prijava uporabnika
**Namen:** prijava v portal.

**Elementi:**
- uporabniško ime ali e-naslov
- geslo
- gumb za prijavo
- povezava za pozabljeno geslo

### 10.3 Domača stran člana
**Namen:** pregled osnovnih informacij o članu.

**Elementi:**
- ime člana
- trenutni status
- stanje točk
- zadnji nakupi
- hitri dostop do nagrad
- izbira jezika

### 10.4 Pregled točk
**Namen:** prikaz stanja in zgodovine točk.

**Elementi:**
- trenutno stanje točk
- seznam dodeljenih točk
- seznam porabljenih točk
- datum transakcije
- opis transakcije

### 10.5 Pregled nakupov
**Namen:** prikaz nakupov člana.

**Elementi:**
- datum nakupa
- znesek
- številka računa
- pridobljene točke
- filter po obdobju

### 10.6 Pregled nagrad
**Namen:** prikaz razpoložljivih nagrad.

**Elementi:**
- naziv nagrade
- opis nagrade
- potrebno število točk
- razpoložljivost
- gumb za koriščenje

### 10.7 Administrativna maska za člane
**Namen:** iskanje in pregled članov.

**Elementi:**
- iskalnik po imenu, priimku, e-naslovu ali številki kartice
- seznam zadetkov
- osnovni podatki člana
- status
- stanje točk
- zgodovina sprememb

### 10.8 Administrativna maska za pravila točkovanja
**Namen:** upravljanje pravil za dodeljevanje točk.

**Elementi:**
- status člana
- zneskovni razred
- število točk
- datum veljavnosti
- gumb za dodajanje, urejanje, brisanje

### 10.9 Administrativna maska za pravila statusov
**Namen:** upravljanje pravil prehajanja med statusi.

**Elementi:**
- trenutni status
- pogoj
- ciljni status
- datum veljavnosti
- gumb za dodajanje, urejanje, brisanje

### 10.10 Administrativna maska za poročila in statistike
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

## 11. Realizacija primerov uporabe

### 11.1 PU-1: Registracija člana

**Mejni razredi (UI/boundary):**
- `RegistracijaForm` — obrazec za registracijo
- `RegistracijaController` — REST kontroler za `/api/auth/register`

**Kontrolni razredi:**
- `RegistracijaService` — orkestrira postopek registracije
- `ValidatorPodatkov` — validacija formata
- `EmailService` — pošiljanje potrditvenega e-sporočila

**Entitetni razredi:**
- `Stranka`
- `KarticaLojalnosti`
- `Status`
- `ZgodovinaStatusa`

**Razredni diagram (PU-1):**

![Razredni diagram PU-1 registracija](https://vip.lavbic.net/plantuml/png/XLFDRjim3BxxAGJlagnpirnps65TjqCx96ZQ0UibO2p2eQr8XYHxW8S-mjvg3pRPiXixZjURH7uVVpwIbgn0zW2LHYw9SO94mv55RFCKBTa39cIiXfXIO7__290G13d46IJ8mk-OEefkk1IoT_UK7EndKI3x7J0M2p1c4E6hqiV6nTXLhYc3YjPxHyTuDlVModqbRHG7cz5ipbO3_fV7jOEzN8nzewJLIWZKNORDUlkuqmq4zOnRDGhcuvjSIODDu9TUStS-uBZ1doY4-ZNHuXPrIJ5sDVZqcZIaDxLuTHbrrgs3ommQK5GOMu8cRrEj515N70NTWROKlnehoCdGCyHefIE0BKpZEcdo0mGvzPJs8gho93YMgAcU0TYkZhrIOk1-acuiLYfZPtW44XzOaIiDUqacKpiwOezrIdfRGyzQpvKHgHkbrPmibZFZMvwFXBwLrW7iMEXl6b7sT6v5QnD4n7UcBwChpZ_SQhbtvZzD5wtEmqwyCK4ZrEu0vk3_ALRagLVcK2_ZcRv-872lKX2rJDGh9_C-_tTRLvB8eBNYvQBTZ8hZZYeEAVudgn_reFFQuB_ItL4vW3ydYgkI97XUNxAgSqs8E0pjorFyGcbkXAFRZg9FKqUvOlKzieLRu0KKzh3eBZEO89p7QjShk7HjDNQq-9F8RezMhBsyIUHus6zpHjg_JUcVJn1qvONBiF66o-lhz-6ubYdWUG51kpoli8-NOVy0)

**Diagram zaporedja (PU-1):**

![Diagram zaporedja PU-1 registracija](https://vip.lavbic.net/plantuml/png/XPDDRjj038NtSmh2Anc5uIJB0kt6TJSfK2DkkkYcOAM1JMiy53YqWlWElLKFrj7e7qNSbIJoqnlgFKf9dOLFX0V1CronOh752M45k-VLFJpP0mKLp2dM_lnswD4Op9K5zh7iIpGLYb9E5Ng5nPJ_p79U00PeRjx6DknLs3ah2TwekBVXlPMQSfl8xduEVqT71SRvTXml9TS97Qh6UYLzXKKtFMJRPIlMFcy7u36fuXS-eVCSb1BMLGVgnu4BhidZNb4l0HCq5EUZRSz8Rle1gM1CFyhgOt8AtWDTAtQUW7y9NcrkKZcs6szYU_Tr_mtMMD4QBtfSI_B7YadjY7LdHB9j2GcUDarsMQ6yD7q_eeCn4Qx4rbQeEGor9SVsQgRBvNz4dZsLg8rlcMs-ygRKLAlF8NQyVO5t48wnGDdI39tv-rJy3DqcJcIwd5gLR6IMKyKU-aUmx5AU20wPTf8XvVs1W-VQqqnsH6-Pbi9l3EFWJhHZbOBKrba_g6c16sQD2z7_Ykq2Z7lqS7SF6x6ejkXsQ7GuPHL3ki8bLFQ8vYy0)

### 11.2 PU-2: Mesečni pripis točk

**Mejni razredi:**
- `MesecniObracunScheduler` — časovno proženje
- `PoslovniSistemAdapter` — integracija s poslovnim sistemom

**Kontrolni razredi:**
- `ObracunService` — vodi obračun
- `KalkulatorTock` — uporabi pravila točkovanja
- `StatusUpravljavec` — preveri pravila prehoda
- `RevizijskaSled` — beleži dogodke

**Entitetni razredi:**
- `Stranka`
- `Nakup`
- `PraviloTockovanja`
- `PraviloStatusa`
- `TransakcijaTock`
- `ZgodovinaStatusa`

**Razredni diagram (PU-2):**

![Razredni diagram PU-2 obracun](https://vip.lavbic.net/plantuml/png/TLJBRjim4BphAmZtuhHnqFOO107QeYYA96qG9uVcOgobXRqIpHL8IWLKv1FoL_cmhaJPriitYZiSpivovCbhL0zGMKmCgOHWOs6d5kh-QV5PtQ73jrVPpotbv9JdjzSiYdA8CzYWcjrXAaNRdAQPUdTBcwt_gWjK_oAbOWtEDHoneTzh2t5Xbl4MaqAZRH1AVN2vvOhcP_BrSZXppqvpQMX9pkFkImAvFvx8BPOLxkWNP4MESrudl4xnJ5sgMu5VDTlN3TrBH-eD6szPZ-N-GQtvRqVmNYdQacBStqfLAOVQsk7IfhRWi0lfDmq6vivRC1cSArDBeNvhDw2pGeDd-yXnTcHl6UfD50RmXJjNbH7piherChv7ismGJxc5KgTGOjnr1otzDE8XYqWAoACeZTx0FLjOGr_P0vPKKUeoM6fCzdmLoE1fdl264v4oylMxyUI5SkJh3ujeEhOkWu2MTq79gfKKlhqqpgBLfDXJrOopSwZnT9eYk1NMYJIz2s3eFornZ3JNFdCfjnq41S_RTSw9b5OxJFVS6xRz7UTNjURWKeaoXMUO6DoQMKy926CvtEujca9SN7Lbv69w6fOnwRHRFV8zYWCEifXIwBoesXn_h9pmdF9nBy6wDfnRGG_3-ImlWKioq6-X3vOdSYhuYyNr86FH878rOl8NC0Ni1seACShA56XeuwKgd2_1qXIu7vLeaEb6_l2PHUF4Td2jbIT08yUFulQfcdsQDT3PnukBzxEGcbF5GQlHVm00)

**Diagram zaporedja (PU-2):**

![Diagram zaporedja PU-2 obracun](https://vip.lavbic.net/plantuml/png/PPEnZjim38PtFmLnKu8cIySE1GxeKXpQ197J8KK7sYPoj1L9a1GNpJlahV9WfMmbSNBQB7xwoP-a8qTDy8rnx_409tJMKzCYB66zNNw67nJeSZOCphFZ0D5UpbrHEFIHQtPe8hoe-fsQeoR_0XX0FGPNbSVwQ1JvdciQYDKJihP1szwmuX3fyDgWYrbhhLuVqJVKtL5ZjBwqTJSmRsL19dBy9q8UUzOsXMoFfiLHv0wK7at0hkOMR-_ByibDn7WCMoTQkiMUwj7LzZdBoEKKwXRTxMrZUpOuZU-U76-evnEteKEbgHcGZIeA1SklqXtu0dpggU7Skvdp5AdJd8PHpulLm4bl19HGVw83_yJkw6XcgyPMBSsB55rUrKmAyky_HQ6jTJ9awAKBj4Uud3KQX5D62f2pcfOn582jagZXdP42kjbyWhsLKomrbMPXSBw0qu2Fj72fvaGxow7cNvIwQspkPXOLO7bLTMFazlnQL8WfpQI6Cj66_ix67LraOWwV8BpBn3cBbnCHEnLGszn9ylpTo3hA22iU1oXkHAB31MYA1jVMOuMZdZmRvd3pzEH53Uco-DqBwWX1iXteK26CpK9HY9ugWmDoLz-fxCt8KeqLVV2LpcwIB7iZqzpAdDXErtc5DkbAVdaElBQoHh9aUULGf3VguTqgPnY__WC0)

---

## 12. Slovar izrazov

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
