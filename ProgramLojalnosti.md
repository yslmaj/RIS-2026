# Specifikacija zahtev za rešitev programa lojalnosti Maestro

## 1. Kratek opis

Trgovska veriga Maestro želi uvesti program lojalnosti za svoje stranke. Namen programa je povečati število nakupov, nagraditi zveste stranke ter omogočiti boljši pregled nad njihovim nakupnim vedenjem. Sistem bo podpiral včlanitev strank v program, dodeljevanje statusov, obračun točk zvestobe, koriščenje ugodnosti in administrativno upravljanje pravil programa.

Rešitev bo sestavljena iz spletne aplikacije za stranke, administrativnega dela za zaposlene oziroma upravljavce programa ter integracije z obstoječim poslovnim informacijskim sistemom in podatkovno bazo Oracle.

Sistem mora biti zasnovan tako, da podpira veliko število uporabnikov, dva jezika, sodoben uporabniški vmesnik ter možnost kasnejšega spreminjanja pravil programa brez večjih posegov v programsko rešitev.

---

## 2. Funkcionalne zahteve

### 2.1 Seznam funkcionalnih zahtev

**FZ-1: Registracija v program lojalnosti**
Sistem mora omogočati registracijo stranke v program lojalnosti preko spleta.

**FZ-2: Preverjanje unikatnosti uporabnika**
Sistem mora ob registraciji preveriti, da posamezna oseba ne more biti registrirana večkrat z istim elektronskim naslovom ali drugimi enoličnimi podatki.

**FZ-3: Preverjanje pristnosti e-naslova**
Sistem mora ob registraciji preveriti, da stranka dejansko poseduje vneseni e-naslov (preko aktivacijske povezave).

**FZ-4: Ustvarjanje uporabniškega računa**
Sistem mora ob uspešni registraciji ustvariti uporabniški račun za dostop do portala.

**FZ-5: Dodelitev kartice lojalnosti**
Sistem mora vsakemu članu programa dodeliti kartico lojalnosti, ki se stranki posreduje po navadni pošti.

**FZ-6: Vodenje statusa člana**
Sistem mora za vsakega člana voditi status lojalnosti: osnovni, bronasti, srebrni ali zlati.

**FZ-7: Prevzem podatkov o nakupih**
Sistem mora iz poslovnega informacijskega sistema prevzemati podatke o opravljenih nakupih.

**FZ-8: Mesečni obračun točk zvestobe**
Sistem mora enkrat mesečno izračunati točke zvestobe za pretekli mesec.

**FZ-9: Izračun točk po pravilih**
Sistem mora dodeliti točke glede na znesek nakupov in status člana.

**FZ-10: Sprememba statusa člana pred točkovanjem**
Sistem mora pred dodelitvijo točk preveriti, ali član izpolnjuje pogoje za spremembo statusa, in po potrebi posodobiti status.

**FZ-11: Hramba zgodovine statusov**
Sistem mora hraniti zgodovino vseh sprememb statusov posamezne stranke.

**FZ-12: Hramba zgodovine točk**
Sistem mora hraniti zgodovino vseh dodelitev in koriščenj točk.

**FZ-13: Pregled zbranih točk**
Sistem mora članu omogočiti vpogled v trenutno stanje točk.

**FZ-14: Pregled zgodovine nakupov**
Sistem mora članu omogočiti vpogled v zgodovino nakupov, ki vplivajo na obračun točk.

**FZ-15: Pregled statusa**
Sistem mora članu omogočiti vpogled v svoj trenutni status lojalnosti.

**FZ-16: Pregled nagradnega programa**
Sistem mora članu omogočiti pregled razpoložljivih nagrad ali ugodnosti.

**FZ-17: Koriščenje točk**
Sistem mora članu omogočiti koriščenje zbranih točk za izbrane nagrade ali ugodnosti.

**FZ-18: Večjezičnost**
Sistem mora omogočati uporabo najmanj v slovenskem in angleškem jeziku.

**FZ-19: Administracija pravil točkovanja**
Administrator mora imeti možnost upravljanja pravil za dodeljevanje točk.

**FZ-20: Administracija pravil prehajanja med statusi**
Administrator mora imeti možnost upravljanja pravil za prehajanje med statusi.

**FZ-21: Upravljanje nagrad**
Administrator mora imeti možnost upravljanja nagrad, ki so na voljo za koriščenje točk.

**FZ-22: Pregled statistik**
Administrator mora imeti možnost pregleda statistik nakupov, članov, točk in statusov.

**FZ-23: Poročila za poljubno obdobje**
Administrator mora imeti možnost pregleda stanj in poročil za poljubno obdobje.

**FZ-24: Poljubne poizvedbe**
Administrator mora imeti možnost izvajanja poljubnih poizvedb po podatkovni bazi.

**FZ-25: Iskanje in pregled članov**
Administrator mora imeti možnost iskanja članov in vpogleda v njihove podatke.

**FZ-26: Upravljanje uporabniških podatkov**
Administrator mora imeti možnost popravljanja določenih podatkov člana skladno s pravicami dostopa.

**FZ-27: Avtentikacija uporabnikov**
Sistem mora omogočati prijavo uporabnikov v portal.

**FZ-28: Upravljanje dostopnih pravic**
Sistem mora ločevati pravice med člani programa in administratorji.

---

### 2.2 Funkcionalna dekompozicija

**Upravljanje članstva**
- registracija člana
- preverjanje podatkov in unikatnosti
- preverjanje pristnosti e-naslova (aktivacijska povezava)
- ustvarjanje uporabniškega računa
- dodelitev kartice lojalnosti (pošiljanje po pošti)
- vodenje osnovnih podatkov člana

**Upravljanje nakupov**
- prevzem podatkov iz poslovnega informacijskega sistema
- evidenca nakupov
- povezava nakupov s članom
- pregled zgodovine nakupov

**Upravljanje točk zvestobe**
- mesečni obračun točk
- izračun točk po pravilih
- vodenje stanja točk
- evidenca dodelitev in porabe točk

**Upravljanje statusov**
- začetna dodelitev statusa
- preverjanje pogojev za napredovanje
- preverjanje pogojev za nazadovanje
- sprememba statusa
- evidenca zgodovine statusov

**Upravljanje nagrad**
- pregled kataloga nagrad
- koriščenje točk
- zmanjšanje stanja točk
- evidenca koriščenj

**Uporabniški portal**
- prijava
- pregled profila
- pregled statusa
- pregled točk
- pregled nakupov
- pregled nagrad
- koriščenje točk
- izbira jezika

**Administrativni modul**
- pregled članov
- pregled statistik
- upravljanje pravil točkovanja
- upravljanje pravil statusov
- upravljanje nagrad
- priprava poročil
- poljubne poizvedbe

**Integracijski modul**
- povezava s poslovnim informacijskim sistemom
- povezava s podatkovno bazo Oracle
- izmenjava podatkov o nakupih
- sinhronizacija članov in točk

---

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

![Diagram primerov uporabe](https://vip.lavbic.net/plantuml/png/ZPLTZXCn3CVVSugexzq385HfjRmii51HzgqIScTCr_EHL4bc44NSW1w2kvHxuMGcCvcsqBurzi-9xRyzhV2haqvBGziN9tCoc3dIIjYIr0uCr787MGbRNBdl5Khl1hMjC04WSzfqRlY6LjSeX2F7npS4st25eHgDRcMpqmOsAEVo2T0wezcb0rBf0YgbhICXmeLoTlnLWLghde2P12iVs1JzztbDYlWMu6Fm1ajqBxMjTAj8Fgw2S_cu4cB8NyvM78frJ02I369oC_b322aRYnbOZlY4s_1SHWMiLHj3m-tF3r_OdT9BmrWBaZbj75GHUw-tdEG4H4uebzQ1Qon4RXMEbq2dZuSoOfzrLk8bIa79xMuZzy4VwJB8LUGZvq-J6zzfGtz-7m-e2fm-xZtMfUngPx36UWEom3sLGpLl_Ia5xqj7RTzAd2lmOWqqEyN5NguL3Afph1u2lFMiiu-s19ypXJ7ggZqUU8J6jlJ8l_JWXwXC5Kd1vvs1jYh24_udLMiLsiELg68ePiakhzArq4x_CJKVzxydfxgnfvFkf6y-0Fm8Sc8q3E5IcmcdgwBPACv5qxx5V8CZIFiJAR3T-xtHEJYkTArqDshqCYQERHhoX1QF1zv4lJ5mF3IgRrFaFx8vQzJbCJhTYfq9FVafXFyMoFby4NSlFNUZa5hwTKfDtUgabdv9fgPk7r9RF_QfgPjl4UOmsfAXdDZZp4sCeQg9PPYRC-ivEwe_XLdc4uENap-5utMibUWwAE_k5ltsoLVozMjIMTNak5Y8eNyH2LMTGw6ZLvYknrUXqFKhLAV35IX-169nWoYNQxo5YyhSojvwxw3YJHVpdznD6ErluVebZAYVYwjGlumdt5y0)

---

### 2.4 Opisi primerov uporabe

#### PU-1: Registracija uporabnika v program lojalnosti

**Akterji:** stranka (primarni), sistem za pošiljanje e-pošte (sekundarni), pošta (zunanji)

**Predpogoji:**
- Stranka dostopa do spletnega portala Maestro.
- Stranka še nima uporabniškega računa.

**Naknadni pogoji:**
- V sistemu je ustvarjen nov zapis stranke z začetnim statusom *osnovni*.
- Stranki je poslano potrditveno e-sporočilo z aktivacijsko povezavo.
- V sistem je vnesena zahteva za izdajo kartice lojalnosti (kartica se stranki posreduje po navadni pošti).

**Osnovni tok:**
1. Stranka izbere možnost »Registracija« na vstopni strani portala.
2. Sistem prikaže obrazec za registracijo (ime, priimek, e-naslov, telefon, poštni naslov, uporabniško ime, geslo, ponovitev gesla, izbor jezika).
3. Stranka vnese podatke in potrdi obrazec.
4. Sistem preveri popolnost in pravilnost formata podatkov.
5. Sistem preveri, da uporabniško ime in e-naslov v bazi še ne obstajata.
6. Sistem zgosti geslo in shrani podatke stranke.
7. Sistem stranki dodeli začetni status *osnovni* in zapiše dogodek v zgodovino statusov.
8. Sistem ustvari zahtevo za izdajo kartice lojalnosti (kartica se stranki pošlje po navadni pošti).
9. Sistem pošlje potrditveno e-sporočilo z aktivacijsko povezavo na e-naslov stranke.
10. Stranka klikne na povezavo v e-sporočilu in s tem potrdi pristnost e-naslova.
11. Sistem aktivira uporabniški račun in prikaže potrditveno sporočilo o uspešni registraciji.

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

*A4: Stranka ne potrdi e-naslova*
- 10a. Stranka v 24 urah ne klikne na aktivacijsko povezavo.
- 10b. Sistem označi račun kot *neaktiviran*; stranka se ne more prijaviti v portal.
- 10c. Sistem ponudi možnost ponovnega pošiljanja aktivacijske povezave.

*A5: Napaka pri pošiljanju e-sporočila*
- 9a. Sistem ne uspe poslati potrditvenega e-sporočila (napaka SMTP).
- 9b. Sistem vseeno ohrani podatke stranke, vendar račun označi kot *neaktiviran*.
- 9c. Sistem obvesti stranko o težavi in ponudi možnost ponovnega pošiljanja.

---

#### PU-2: Mesečni pripis točk zvestobe

**Akterji:** sistem (sprožitelj — časovnik), poslovni informacijski sistem (sekundarni)

**Predpogoji:**
- Obstajajo veljavna pravila točkovanja in pravila prehoda med statusi za obračunsko obdobje.
- V sistemu obstajajo člani z opravljenimi nakupi v preteklem mesecu.

**Naknadni pogoji:**
- Za vsakega člana je najprej posodobljen status (če izpolnjuje pogoje), nato so mu dodeljene točke glede na nov status.
- Vse transakcije so zabeležene v zgodovini točk in zgodovini statusov.

**Osnovni tok:**
1. Časovnik prvi delovni dan v mesecu ob 02:00 sproži postopek obračuna.
2. Sistem od poslovnega informacijskega sistema prevzame podatke o nakupih za pretekli mesec.
3. Sistem preveri, da pri prevzemu ni prišlo do napak in da so podatki popolni.
4. Sistem za vsakega člana z nakupi v preteklem mesecu:
   - 4.1. izračuna skupni znesek nakupov preteklega meseca,
   - 4.2. prebere trenutni status člana in zgodovino prejšnjih mesecev (potrebno za pravila o doseganju in ohranjanju statusa),
   - 4.3. preveri pravila za spremembo statusa in po potrebi posodobi status člana,
   - 4.4. če je status spremenjen, zapiše spremembo v zgodovino statusov,
   - 4.5. uporabi veljavno pravilo točkovanja glede na nov status in zneskovni razred,
   - 4.6. ustvari transakcijo točk tipa *pripis* in posodobi stanje točk člana.
5. Sistem zapiše povzetek obračuna v revizijsko sled.
6. Sistem administratorju pošlje poročilo o opravljenem obračunu.

> Vrstni red 4.3 → 4.5 je predpisan: stranki se najprej spremeni status (če izpolnjuje pogoje), šele nato se dodeli ustrezno število točk.

**Alternativni tokovi:**

*A1: Napaka pri prevzemu podatkov iz poslovnega sistema*
- 3a. Sistem zazna, da povezava do poslovnega sistema ni vzpostavljena ali da so podatki nepopolni.
- 3b. Sistem zapiše napako v dnevnik in obvesti administratorja.
- 3c. Obračun se ne izvede; primer uporabe se ponovi po odpravi napake.

*A2: Manjkajoče pravilo točkovanja*
- 4.5a. Sistem ne najde veljavnega pravila točkovanja za kombinacijo statusa in zneskovnega razreda.
- 4.5b. Sistem za tega člana preskoči obračun, ga uvrsti v seznam izjem in obvesti administratorja.

*A3: Član izpolnjuje pogoje za nazadovanje statusa*
- 4.3a. Sistem ugotovi, da član v preteklem mesecu ni dosegel praga za ohranitev trenutnega statusa (npr. zlati član z manj kot 500 € prometa, ali srebrni član dva meseca zapored z manj kot 200 € prometa).
- 4.3b. Sistem mu zniža status v skladu z veljavnimi pravili (zlati → srebrni, srebrni → bronasti po dveh slabih mesecih, bronasti → osnovni ob mesečnem nakupu pod 50 €).
- 4.3c. Sprememba se zapiše v zgodovino statusov z razlogom »nazadovanje zaradi premajhne porabe«.
- 4.3d. Točke se nato dodelijo glede na nov, nižji status.

*A4: Delna napaka med obračunom posameznega člana*
- 4.6a. Pri posameznem članu pride do napake (npr. baza ni dostopna).
- 4.6b. Sistem transakcijo zavrne (rollback) skupaj s spremembo statusa za tega člana, da se ohrani integriteta.
- 4.6c. Član se uvrsti na seznam za ponovni obračun.

---

## 3. Nefunkcionalne zahteve

### Zmogljivost in obseg
- **NZ-1:** Sistem mora podpirati najmanj 500.000 registriranih uporabnikov (skladno s 70 % strank verige).
- **NZ-2:** Arhitektura mora omogočati rast in podporo bistveno večjemu številu uporabnikov (sistem se bo tržil tudi izven Slovenije).
- **NZ-3:** Odzivni čas tipične spletne strani portala ne sme presegati 2 sekundi pri 95 % zahtevkov.
- **NZ-4:** Mesečni obračun točk za celotno bazo članov mora biti dokončan v manj kot 4 urah.
- **NZ-5:** Sistem mora podpirati vsaj 1.000 sočasnih uporabnikov portala.

### Razširljivost
- **NZ-6:** Arhitektura mora omogočati horizontalno skaliranje aplikacijske plasti.
- **NZ-7:** Podatkovni model mora omogočati rast brez sprememb sheme.

### Razpoložljivost
- **NZ-8:** Sistem mora zagotavljati razpoložljivost najmanj 99,5 % na mesečni ravni.
- **NZ-9:** Načrtovani izpadi morajo biti izvedeni izven delovnega časa trgovin.

### Varnost
- **NZ-10:** Gesla morajo biti shranjena v zgoščeni obliki z uporabo sodobnega algoritma (bcrypt / argon2).
- **NZ-11:** Vsa komunikacija med odjemalcem in strežnikom mora potekati prek HTTPS.
- **NZ-12:** Sistem mora ločevati vloge član, administrator in sistemski uporabnik.
- **NZ-13:** Sistem mora ob registraciji preveriti pristnost e-naslova prek aktivacijske povezave.
- **NZ-14:** Vsi pomembni dogodki (registracija, sprememba statusa, koriščenje točk, sprememba pravil) morajo biti zabeleženi v revizijski sledi.
- **NZ-15:** Skladnost z GDPR — pravica do vpogleda, popravka in izbrisa osebnih podatkov.

### Uporabnost
- **NZ-16:** Vmesnik mora podpirati slovenski in angleški jezik.
- **NZ-17:** Vmesnik mora biti odziven in uporaben na zaslonih od 360 px naprej.
- **NZ-18:** Vmesnik mora biti intuitiven in upoštevati osnovne smernice dostopnosti (WCAG 2.1, raven AA).
- **NZ-19:** Uporabniški vmesnik mora uporabljati sodobne tehnologije.

### Vzdrževanost
- **NZ-20:** Pravila točkovanja in pravila prehoda med statusi morajo biti konfigurabilna brez sprememb izvorne kode.
- **NZ-21:** Sistem mora podpirati avtomatske varnostne kopije podatkovne baze najmanj enkrat dnevno.
- **NZ-22:** Sistem mora omogočati obnovo iz varnostne kopije v manj kot 4 urah.

### Združljivost
- **NZ-23:** Sistem mora uporabljati obstoječo podatkovno bazo Oracle.
- **NZ-24:** Sistem mora podpirati integracijo z obstoječim poslovnim informacijskim sistemom.
- **NZ-25:** Spletni portal mora delovati v zadnjih dveh različicah brskalnikov Chrome, Firefox, Edge in Safari.

---

## 4. Podatkovni model

### 4.1 Entitete

**Stranka**
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

**Kartica_lojalnosti**
- `id_kartica`
- `stevilka_kartice`
- `id_stranka`
- `datum_izdaje`
- `stanje_aktivna`

**Status**
- `id_status`
- `naziv_statusa`
- `opis`

**Zgodovina_statusa**
- `id_zgodovina_statusa`
- `id_stranka`
- `id_status`
- `datum_od`
- `datum_do`
- `razlog_spremembe`

**Nakup**
- `id_nakup`
- `id_stranka`
- `datum_nakupa`
- `znesek`
- `vir_podatka`
- `id_racuna`

**Pravilo_tockovanja**
- `id_pravilo`
- `status`
- `spodnja_meja_zneska`
- `zgornja_meja_zneska`
- `st_tock`
- `datum_veljavnosti_od`
- `datum_veljavnosti_do`

**Pravilo_statusa**
- `id_pravilo_statusa`
- `trenutni_status`
- `pogoj`
- `ciljni_status`
- `datum_veljavnosti_od`
- `datum_veljavnosti_do`

**Transakcija_tock**
- `id_transakcija`
- `id_stranka`
- `datum_transakcije`
- `tip_transakcije`
- `st_tock`
- `opis`
- `id_nakup`
- `id_nagrada`

**Nagrada**
- `id_nagrada`
- `naziv`
- `opis`
- `potrebno_tock`
- `aktivna`

**Uporabnik_sistema**
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

## 5. Diagram prehajanja stanj med statusi

Status člana se preverja in posodablja enkrat mesečno ob obračunu točk, na podlagi zneska nakupov preteklega meseca (oziroma dveh zaporednih mesecev pri nekaterih prehodih).

### Stanja
- **Osnovni** — začetno stanje vsakega novega člana.
- **Srebrni** — član, ki je prvič presegel 499 € mesečnih nakupov.
- **Zlati** — član, ki je še dvakrat presegel 500 € mesečnih nakupov (skupno torej tretjič nad 500 €).
- **Bronasti** — član, ki je padel iz srebrnega ali zlatega zaradi premajhne porabe.

### Prehodi

| Iz stanja | V stanje | Pogoj |
|---|---|---|
| (začetno) | Osnovni | uspešna registracija |
| Osnovni | Srebrni | mesečni nakup > 499 € (prvič) |
| Srebrni | Zlati | mesečni nakup > 500 € še dvakrat (skupno trikrat presežek) |
| Zlati | Srebrni | mesečni nakup < 500 € |
| Srebrni | Bronasti | mesečni nakup < 200 € dva zaporedna meseca |
| Bronasti | Srebrni | mesečni nakup ≥ 200 € dva zaporedna meseca |
| Bronasti | Osnovni | mesečni nakup < 50 € |

![Diagram prehajanja stanj](https://vip.lavbic.net/plantuml/png/XLBBJW914BpFL_GHZ211FM2GWz6ZcaYyA1uQjeLPO7epCxiX_CD-13_YQValUnQMXnfCDfbDghgg-k6rdn7SQnnRd4DYQO8ncXZ1UNcW0NsFFdLGv3CqA0GEH8H79ESjA_L-zW6DHW-UdU7CQBY1r2MqNWdPqbWB2KSwHgL4qDC1ROb5JjxmnecsUD_Iq9PuOZDTvD23gqu77bvVjeIt6Ve0hrS4xON0rwrMW0UcvgPf8dgNYz27e_KNJUlRgZlB1brPQ7294MV1Ss3q4bpfI6EyM8gql4fL8KDV-q1pqIno-JKeHljWKDj4hIjLaKDX5VHNsIvmQ27AS6hHmpvy_KZb8FWFeIwqAo4HaN4cR2cIiGVUIBhO13ZPGxSAezJEw7JJj_-u7idib_s7xyRMi6p7wl740tzM1GggitCKTfcHbGi285FEQYl6m4FvhDnHQjAcu4yO2pikgzXnn4CThak4pWMLSSkf6_GS2157DDCnW-SYdr9JaOaWf57V)

> Konkretne pragove (200 €, 499 €, 500 €, 50 €) hrani tabela `Pravilo_statusa` v bazi, da jih lahko administrator spreminja brez posegov v kodo.

---

## 6. Odločitvena tabela za točkovanje

Točke se obračunajo glede na status člana po morebitni mesečni spremembi in mesečni znesek nakupov. Pravila so konfigurabilna v tabeli `Pravilo_tockovanja`.

### Razlaga vhodov in izhodov

**Vhodi:**
- C1: status člana po posodobitvi (osnovni / bronasti / srebrni / zlati)
- C2: mesečni znesek nakupov (€)

**Izhod:**
- A: število pripisanih točk

### Tabela

| Pravilo | Status (C1) | Mesečni znesek (C2) | Točke (A) |
|---|---|---|---|
| R1  | osnovni  | do 200 €            | 5 |
| R2  | osnovni  | nad 200 € do 1000 € | 10 |
| R3  | osnovni  | nad 1000 €          | 20 |
| R4  | bronasti | do 200 €            | 0 |
| R5  | bronasti | nad 200 € do 1000 € | 5 |
| R6  | bronasti | nad 1000 €          | 10 |
| R7  | srebrni  | do 200 €            | 7,5 |
| R8  | srebrni  | nad 200 € do 1000 € | 15 |
| R9  | srebrni  | nad 1000 €          | 30 |
| R10 | zlati    | do 200 €            | 10 |
| R11 | zlati    | nad 200 € do 1000 € | 20 |
| R12 | zlati    | nad 1000 €          | 40 |

**Primer:** član s srebrnim statusom v marcu opravi nakupov za 320 €. Uporabi se pravilo R8 → **15 točk**.

**Primer s spremembo statusa:** član *osnovni* v marcu opravi nakupov za 600 €. Najprej se preveri prehod — 600 > 499, član postane *srebrni*. Točke se nato dodelijo po pravilu R8 (srebrni, 200–1000 €) → **15 točk** (in ne 10 točk po R2 za osnovni status).

---

## 7. Tehnične zahteve

- Rešitev mora biti zasnovana kot spletna aplikacija.
- Sistem mora podpirati najmanj 500.000 uporabnikov in omogočati nadaljnjo rast.
- Rešitev mora podpirati slovenski in angleški jezik.
- Sistem mora uporabljati obstoječo podatkovno bazo Oracle.
- Sistem mora omogočati integracijo z obstoječim poslovnim informacijskim sistemom.
- Sistem mora zagotavljati avtentikacijo in avtorizacijo uporabnikov.
- Sistem mora zagotavljati varno hrambo osebnih podatkov in gesel.
- Gesla morajo biti hranjena v zgoščeni obliki.
- Sistem mora omogočati beleženje revizijske sledi pomembnih sprememb.
- Uporabniški vmesnik mora biti sodoben, intuitiven in odziven.
- Sistem mora omogočati konfigurabilnost pravil brez spremembe izvorne kode.
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
- podpora shranjenim proceduram za zahtevnejše obračune
- ločevanje operativnih in poročevalskih poizvedb

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

## 9. API načrt (REST)

Vmesnik je REST, izmenjava podatkov v JSON. Avtentikacija prek JWT žetona, razen za javne končne točke.

### Avtentikacija

| Metoda | Pot | Opis |
|---|---|---|
| POST | `/api/auth/register` | Registracija novega člana |
| GET  | `/api/auth/activate?token=...` | Potrditev e-naslova preko aktivacijske povezave |
| POST | `/api/auth/login` | Prijava (vrne JWT) |
| POST | `/api/auth/logout` | Odjava |
| POST | `/api/auth/password-reset` | Zahteva za ponastavitev gesla |

### Član (portal)

| Metoda | Pot | Opis |
|---|---|---|
| GET | `/api/me` | Podatki o prijavljenem članu |
| PUT | `/api/me` | Posodobitev podatkov člana |
| GET | `/api/me/status` | Trenutni status in zgodovina statusov |
| GET | `/api/me/points` | Stanje točk |
| GET | `/api/me/points/history?from=&to=` | Zgodovina transakcij točk |
| GET | `/api/me/purchases?from=&to=` | Zgodovina nakupov |
| GET | `/api/me/language` | Trenutna jezikovna nastavitev |
| PUT | `/api/me/language` | Sprememba jezika (sl/en) |

### Nagrade in koriščenje

| Metoda | Pot | Opis |
|---|---|---|
| GET | `/api/rewards` | Seznam nagrad |
| GET | `/api/rewards/{id}` | Podrobnosti nagrade |
| POST | `/api/rewards/{id}/redeem` | Koriščenje točk za nagrado |

### Administracija

| Metoda | Pot | Opis |
|---|---|---|
| GET | `/api/admin/members?search=&status=` | Iskanje članov |
| GET | `/api/admin/members/{id}` | Podrobnosti člana |
| PUT | `/api/admin/members/{id}` | Popravek podatkov člana |
| GET | `/api/admin/members/{id}/status-history` | Zgodovina statusov člana za poljubno obdobje |
| GET | `/api/admin/scoring-rules` | Pravila točkovanja |
| POST | `/api/admin/scoring-rules` | Novo pravilo |
| PUT | `/api/admin/scoring-rules/{id}` | Sprememba pravila |
| DELETE | `/api/admin/scoring-rules/{id}` | Brisanje pravila |
| GET | `/api/admin/status-rules` | Pravila prehoda statusov |
| POST | `/api/admin/status-rules` | Novo pravilo statusa |
| PUT | `/api/admin/status-rules/{id}` | Sprememba |
| DELETE | `/api/admin/status-rules/{id}` | Brisanje |
| GET | `/api/admin/reports/purchase-stats?from=&to=` | Statistika nakupov |
| GET | `/api/admin/reports/status-stats?from=&to=` | Pregled statusov strank za poljubno obdobje |
| POST | `/api/admin/reports/custom-query` | Poljubna poizvedba po podatkovni bazi |
| GET | `/api/admin/reports/export?format=csv` | Izvoz poročila |

### Integracija s poslovnim sistemom

| Metoda | Pot | Opis |
|---|---|---|
| POST | `/api/integration/purchases` | Paketni prevzem nakupov |
| POST | `/api/integration/calculate-points` | Ročni proženje mesečnega obračuna |
| GET | `/api/integration/health` | Status vmesnika |

### Standardni odgovori

- `200 OK` — uspešna poizvedba
- `201 Created` — nov vir je nastal
- `400 Bad Request` — napaka v vhodnih podatkih
- `401 Unauthorized` — manjka ali napačen žeton
- `403 Forbidden` — uporabnik nima pravic
- `404 Not Found` — vir ne obstaja
- `409 Conflict` — npr. e-naslov že obstaja, nezadostno število točk
- `500 Internal Server Error` — sistemska napaka

### Primer: registracija

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
  "status": "osnovni",
  "kartica_v_pripravi": true,
  "potrditev_email_poslan": true,
  "sporocilo": "Aktivacijska povezava je bila poslana na vaš e-naslov."
}
```

---

## 10. Zaslonske maske

### 10.1 Registracija člana
**Namen:** vnos podatkov za včlanitev v program.

**Elementi:** ime, priimek, elektronski naslov, telefon, naslov, uporabniško ime, geslo, ponovitev gesla, izbor jezika, gumb za registracijo.

### 10.2 Prijava uporabnika
**Namen:** prijava v portal.

**Elementi:** uporabniško ime ali e-naslov, geslo, gumb za prijavo, povezava za pozabljeno geslo.

### 10.3 Domača stran člana
**Namen:** pregled osnovnih informacij o članu.

**Elementi:** ime člana, trenutni status, stanje točk, zadnji nakupi, hitri dostop do nagrad, izbira jezika.

### 10.4 Pregled točk
**Namen:** prikaz stanja in zgodovine točk.

**Elementi:** trenutno stanje točk, seznam dodeljenih točk, seznam porabljenih točk, datum transakcije, opis transakcije.

### 10.5 Pregled nakupov
**Namen:** prikaz nakupov člana.

**Elementi:** datum nakupa, znesek, številka računa, pridobljene točke, filter po obdobju.

### 10.6 Pregled nagrad
**Namen:** prikaz razpoložljivih nagrad.

**Elementi:** naziv nagrade, opis nagrade, potrebno število točk, razpoložljivost, gumb za koriščenje.

### 10.7 Administrativna maska za člane
**Namen:** iskanje in pregled članov.

**Elementi:** iskalnik po imenu, priimku, e-naslovu ali številki kartice, seznam zadetkov, osnovni podatki člana, status, stanje točk, zgodovina sprememb.

### 10.8 Administrativna maska za pravila točkovanja
**Namen:** upravljanje pravil za dodeljevanje točk.

**Elementi:** status člana, zneskovni razred, število točk, datum veljavnosti, gumbi za dodajanje, urejanje, brisanje.

### 10.9 Administrativna maska za pravila statusov
**Namen:** upravljanje pravil prehajanja med statusi.

**Elementi:** trenutni status, pogoj, ciljni status, datum veljavnosti, gumbi za dodajanje, urejanje, brisanje.

### 10.10 Administrativna maska za poročila in statistike
**Namen:** pregled poslovnih kazalnikov programa.

**Elementi:** izbor obdobja, število članov, število aktivnih članov, skupno število točk, porazdelitev po statusih, grafični prikaz, izvoz poročila.

---

## 11. Realizacija primerov uporabe

### 11.1 PU-1: Registracija člana

**Mejni razredi (boundary):**
- `RegistracijaForm` — obrazec za registracijo
- `RegistracijaController` — REST kontroler za `/api/auth/register`

**Kontrolni razredi:**
- `RegistracijaService` — orkestrira postopek registracije
- `ValidatorPodatkov` — validacija formata
- `EmailService` — pošiljanje potrditvenega e-sporočila
- `KarticaService` — proženje zahteve za izdajo fizične kartice

**Entitetni razredi:**
- `Stranka`
- `KarticaLojalnosti`
- `Status`
- `ZgodovinaStatusa`

**Razredni diagram:**

![Razredni diagram PU-1 registracija](https://vip.lavbic.net/plantuml/png/XLJDRjim3BxxAOJiacvrktR3i0P5WIrjTjXFWwRT8PU0iGc7jYCQac9W6Ve8UwizsAJ8pkp4QKwsf8_aH_8Z3PaSnGEi5SQIH4oGA5YAK8oVmWlnW0bfeo2Y5CJVFpb820ATaIp0eQ8SjFuCKPOeNibuo3chw-kv-mVrw-P6lBfxDxeStHurYLWQnRcp68r6LyFtHorG6ZAR4CEFTn-6Lq5GM0WaA7hVCRMPg4rAr1E_0-5zjB8PiLgA5bU74-9DeIY3DTtFhGEC-YV-TcsFaiOSWyceVo86BMUtZ_Sjuqd1YYFA-KaNk83QIVNw0mh8U7Fv77II6_fovAWwAQeD55K_Dhn7n7FJ1KkD7WwHeH8CzWrdA0TYOXJ9P0Vt73mtIlZL4pXUnWcgaY8KpHQsM2fIa0wTS1nR5zI61vb1nIspt1pa0QALz0mTg6IADuXmfKq9YhmLLwKCrr2GfYb4QAHz0xFIkmNz2JdPTh7oNUEoYsIXi4H5JWrWQePpvhpr_2HjuunaRVgu1CfFnKgZah34RdXgKJB5BwWnxoSNfoAvR00R7B-2CXIzLCKg_Iai39Oy1M_1VUshsAXLm-sT8_c2qu9rdj8dLtlNHPtnc4jSGxdrUofyA_QKSUVcpXMzInbLQqLZF7t4aEAPRlGzfAKNPsXdmlvd_h0fRjLsEq8mbsIvpRRW17NEimNeXJ-dkARAL6yqCDle2QLFKo_SqDRJjvNQhb2g9dpZ57BNO-hcdtbO7GvBoZEeRh4xIwkxrN96wnXItDAqml0q9UpHRB3oeZvKIlVcZz9kbBAwgSAodOssisd2CPSamNizqA5rZMgxs-jTcu1FagjnjQh8EPbfEmfBNCwn8qNBQsyJX-7DeGqu4EFxoQCujnD_3YkpEA_NNt30ODTNDGX1rzvosBr5SH1PwtiWgh4yY6mFza7ONb-EUsxETh2pFngH6sh-xpEe4-XTz2pOVixENlVsJGxWTja6bKPhrDjkr3y0)

**Diagram zaporedja:**

![Diagram zaporedja PU-1 registracija](https://vip.lavbic.net/plantuml/png/XLJDRjim3BxxAOJiacvrktR3i0P5WIrjTjXFWwRT8PU0iGc7jYCQac9W6Ve8UwizsAJ8pkp4QKwsf8_aH_8Z3PaSnGEi5SQIH4oGA5YAK8oVmWlnW0bfeo2Y5CJVFpb820ATaIp0eQ8SjFuCKPOeNibuo3chw-kv-mVrw-P6lBfxDxeStHurYLWQnRcp68r6LyFtHorG6ZAR4CEFTn-6Lq5GM0WaA7hVCRMPg4rAr1E_0-5zjB8PiLgA5bU74-9DeIY3DTtFhGEC-YV-TcsFaiOSWyceVo86BMUtZ_Sjuqd1YYFA-KaNk83QIVNw0mh8U7Fv77II6_fovAWwAQeD55K_Dhn7n7FJ1KkD7WwHeH8CzWrdA0TYOXJ9P0Vt73mtIlZL4pXUnWcgaY8KpHQsM2fIa0wTS1nR5zI61vb1nIspt1pa0QALz0mTg6IADuXmfKq9YhmLLwKCrr2GfYb4QAHz0xFIkmNz2JdPTh7oNUEoYsIXi4H5JWrWQePpvhpr_2HjuunaRVgu1CfFnKgZah34RdXgKJB5BwWnxoSNfoAvR00R7B-2CXIzLCKg_Iai39Oy1M_1VUshsAXLm-sT8_c2qu9rdj8dLtlNHPtnc4jSGxdrUofyA_QKSUVcpXMzInbLQqLZF7t4aEAPRlGzfAKNPsXdmlvd_h0fRjLsEq8mbsIvpRRW17NEimNeXJ-dkARAL6yqCDle2QLFKo_SqDRJjvNQhb2g9dpZ57BNO-hcdtbO7GvBoZEeRh4xIwkxrN96wnXItDAqml0q9UpHRB3oeZvKIlVcZz9kbBAwgSAodOssisd2CPSamNizqA5rZMgxs-jTcu1FagjnjQh8EPbfEmfBNCwn8qNBQsyJX-7DeGqu4EFxoQCujnD_3YkpEA_NNt30ODTNDGX1rzvosBr5SH1PwtiWgh4yY6mFza7ONb-EUsxETh2pFngH6sh-xpEe4-XTz2pOVixENlVsJGxWTja6bKPhrDjkr3y0)

### 11.2 PU-2: Mesečni pripis točk

**Mejni razredi:**
- `MesecniObracunScheduler` — časovno proženje (1. v mesecu, 02:00)
- `PoslovniSistemAdapter` — integracija s poslovnim informacijskim sistemom

**Kontrolni razredi:**
- `ObracunService` — vodi celoten obračun
- `StatusUpravljavec` — preverja in posodablja status pred točkovanjem
- `KalkulatorTock` — izračuna točke po posodobljenem statusu
- `RevizijskaSled` — beleži dogodke obračuna

**Entitetni razredi:**
- `Stranka`
- `Nakup`
- `PraviloStatusa`
- `PraviloTockovanja`
- `TransakcijaTock`
- `ZgodovinaStatusa`

**Razredni diagram:**

![Razredni diagram PU-2 obracun](https://vip.lavbic.net/plantuml/png/bLJRRjim37ttLmZPIxejnTODmreK0RQi0OQjMz6qBtq969j8QSkI8Sa6bg6VqB_gXussd8iTfSMUT3ia3myfEd8InJMi32QAH4AmD92BaRYw7Ps8IxJuzCZtXQ62h73wwJ6B8fkHAg36nHAi_GfnjZIwLCb4IstEpnVr7ioVyLYyklWmFPb-Uz4ariePBMkBwNHwEldueWKgHwu9CVbyyMbo6aK5Gs29Od29ANCsJL8q47yZuNqq-SIAVYyCnAMQnVUOb1ADw52kuKAyiONHAneUyUbXu-1AMwahHJEo3lCl2HJkW7bXi5fXJhyWAmiSwaMY5oaUYJFnastFc-jnu_jXX_aFBqEO_PescefY5BkYjK5fLR5DYzl4RDv6sjz2Ef6WO6YT0PL1DxsP0rVQsy909LEeC0u5gJD3GzyLYw4v0dchjSUtOgLOvepN9JzNfA1bK1RQm8Aks3j9FIpywgrxH7w0p4e9JfiR7MVXLDjqQW1oyDhBEdOjCodNSNcD5QqejHdC92OXbolW7gTXefat-zWhpaNTSUZ2nPdvxCLEOtgt8qhchJJ-x0ogahtCFMT_oNkLujnnCctxtRD9l_sQhWc7KFLJEA3NnEyJ3fbxC7GxkrEDS8osOYtnvz8fMCFKRsEIQU_LawYmxZ6bhIEVSdDn1u5QBhIM8RPrxNN5oZrFU2FnLkv29smrpp5TYxJKfdjZtKuv_eFR3Kjl8OifXRPv0ypS5dIWIwZO0U4-fLR5FYRSE7Vhh_XiVJSVjblXFhNctA-cJlo9luRKopbFJymnNuH8yPywD8X7et5lp4MzgLSZWbCu1DoRPo5GTzQ44FsAdedIkWeCXS3TEHFjZzGcWyvlEm3QAzesRcy-xhZSVeaeMi-amVi1GyJWtV7nwu4V8WVUUfaUGFM9HVy0)

**Diagram zaporedja:**

> Vrstni red v zaporedju je najprej `preveriInPosodobiStatus()`, šele nato `izracunajTocke()`.

![Diagram zaporedja PU-2 obracun](https://vip.lavbic.net/plantuml/png/VLJ1Rjim3BtxAxIU7A2vx3XW0mgiXxPR6qJA3Xc6WhQvbB4Z6PBYOVc7_iC-flklKRBiEDcwN0ARvEFZUpGz-GR5HuADXPquG6iiLbiGSx5OpT-Ap-ZmvLcJQ2srv8GtByzrbXLchokmFyM5B9-msZTeBmGumKzPQRItfX4N3uM5SgybsevAZF47EIbT6DUOJfCavt5tLK7h4yn2NXrXf0U_TwlMGjTieSEoxxJAK7lo0OSZr9W-3nB065rlJ6KwqZ2Dh-KH_mwQUj-0DrQPiexXEtKE7aAc0xrD-CS4PK4xg4lQmbYlr15-YHqTQEjga0rMCRoKMSPAYVa75aIy4tJeiA8aLzvQz5Wt5AGlPncKdZhm6BJBE9sBM1wkuhpkW3kwXthVOcwAoXHRd1G45KFgVEYZGoPz_PPLU9AKDSQqxBteU13SW7XvRa23EAIAJF2lRvtuHgQmbHpLjDRCjCvdMSpJXb4jRPwyCDy3QH5_zrUtY-NrhMYDOpyAyjW9rpjocL9-_xh-TCs9wg5ViwWtlebHr5L4pYPSv2gfW9Pkz281zpRdphClDLoAGsJ7_yCUp2B4A00lKdXciAXiW3JaIlg2OTkqIGkGUujwxpKzzgm7u3EqHJyluyoF32D0V7yYV3yBD5uudcA7km86IPW3zoiq96a6Vkje8_x8DOyY4n4BXyPiPcFgs68jntThEPQx9rQ6yjb9R21hwl7rX6i2OXD6hSQT6ecS3yZ2JiowKzF52LyAdWpnJpNvEmpFN1kyKQzwytzBUX0kdmyyNhFas6uOp_b0zJoHUKr6KogPGjNZk7QUslVzpRnC86UqLDzCgH7Yn1Wr8M7-8g32_Qc6Ux0CINowoT72y4tWyv6E2UIJUy1dPobFK2U8otHTmYBmQJeFytVy1m00)

---

## 12. Slovar izrazov

**Program lojalnosti** - Sistem ugodnosti, s katerim trgovska veriga nagrajuje zveste stranke.

**Član programa** - Stranka, ki se je registrirala v program lojalnosti.

**Kartica lojalnosti** - Identifikator člana programa, s katerim se član povezuje z nakupi in točkami.

**Status člana** - Raven članstva v programu lojalnosti. V tem sistemu so to osnovni, bronasti, srebrni in zlati status.

**Točke zvestobe** - Nagradne točke, ki jih član prejme glede na opravljene nakupe in svoj status.

**Koriščenje točk** - Uporaba zbranih točk za pridobitev nagrade ali ugodnosti.

**Nakup** - Poslovni dogodek, pri katerem član opravi nakup v trgovski verigi.

**Pravilo točkovanja** - Pravilo, ki določa število točk glede na status člana in vrednost nakupa.

**Pravilo statusa** - Pravilo, ki določa pogoje za napredovanje ali nazadovanje člana med statusi.

**Administracija** - Del sistema, namenjen upravljanju članov, pravil, nagrad in poročil.

**Poslovni informacijski sistem** - Obstoječi sistem trgovske verige, iz katerega se prevzemajo podatki o nakupih.

**Oracle podatkovna baza** - Obstoječa baza podatkov podjetja, ki se uporablja tudi za podporo programu lojalnosti.

**Uporabniški portal** - Spletna aplikacija, namenjena članom programa za pregled podatkov in koriščenje ugodnosti.
