# Prva normalna forma - 1NF
<details>
  <summary> Definicija 1NF </summary>
   
   - Relacija je u prvoj normalnoj formi (1NF) ako svi njeni atributi imaju samo atomicne (nedeljive) vrednosti.
   
   - Šta je to atomična vrednost? Atomična vrednost je vrednost koja se ne može dalje deliti na prostije činioce.
    
</details>
<details>
  
  <summary> Pretpostavka </summary>
  
  </br>

  - Predpostavljamo da **uvek vazi**
  - Uglavnom ne dolaze zadaci koji ne ispunjavaju ovaj uslov, osim ako nije naznaceno da je neko obelezje skup, slog ili tako nesto

</details>

<details>
  
  <summary> Generalno </summary> <br>

Za sve ostale normalne forme (druga,treca,BK) obicno prvo ***gledamo sve funckionalne zavisnosti*** i da li one ispunjavaju neka pravila, ako **sve** ispunjavaju neka pravila onda je zadovoljena normalna forma u suprotnom nije
  
  </details>
  
<details>
  <summary> Potpuna funkcionalna zavisnost </summary> <br>
  
  Funckionalna zavisnost X->A je **POTPUNA** ako ne postoji podskup od X koji isto odredjuje A (odnosno ako se leva strana ne može dalje redukovati)
  
</details> <br>

# Druga normalna forma - 2NF

<details>
  <summary> Definicija 2nf </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/98717036-d45a1880-238c-11eb-8c75-0c0211ccfd71.png)

  
</details>

<details>
  
  <summary> Primarna obelezja </summary> <br>

  - **PRIMARNA** obelezja su obelezja koja pripadaju bilo kom kljucu [mozemo imati vise kljuceva]
  - U literaturi se **primarna** obelezja oznacavaju sa skracenicom **KPR** . 

</details>

<details>
  <summary> Neprimarna obelezja </summary> <br>
  
  - **NEPRIMARNA** obelezja su ona obelezja koja ne pripadaju ni jednom kljucu
  - odnosno, ona obelezja koja se nalaze sa desne strane funkcionalne zavisnosti 
  
</details>

<details>
  <summary> Algoritam odredjivanja vazenja druge normalne forme </summary> <br>
  
### Tumacenje definicije

  - Nadjemo kljuceve i posmatramo sva obelezja koja postoje u kljucu, odnosno sva obelezja podelimo u  **PRIMARNA**(pripadaju barem jednom kljucu) i **NEPRIMARNA** (ne pripadaju ni jednom kljucu)
  - Potom uzmemo bilo koje neprimarno obelezje A ( ne pripada ni jednom kljucu) i uzmemo bilo koji kljuc X
  - Znamo da svaki kljuc sigurno funkcionalno odredjuje svako obelezje a samim tim i svako neprimarno obelezje,
  - Stoga, kljuc X sigurno odredjuje neprimarno obelezje A 
  - Ali ako posmatramo svaki moguci podskup od X-a, recimo podskup Y, znamo sigurno da ne vazi da podskup kljuca odredjuje A

### Ukratko

Iteriramo i proveravamo da li su sve funkcionalne zavisnosti **POTPUNE**, ako nadjemo neku koja nije znaci ne ispunjava uslov Druge normalne forme.
  
</details>

<details>
  <summary> Primer 1 </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/98703503-d9629c00-237b-11eb-9fb1-44dd916a5b56.png)

  - dve funkcionalne zavisnosti: BRI -> PRZ + IME + BPI, OZP -> NAP
  - primarna obelezja su: BRI, OZP
  - neprimarna obelezja su: svi ostali

![image](https://user-images.githubusercontent.com/45834270/98704339-d320ef80-237c-11eb-8bed-1f082b0fc0bf.png)

  - Mozemo primetiti nepotpunu funkcionalnu zavisnost BRI + OZP -> NAP jer podskup skupa BRI + OZP je recimo OZP za kojeg vazi da odredju NAP 
  - Zbog ove nepotpune funkcionalne zavisnosti, mozemo reci da ova sema relacije nije u drugoj normalnoj formi 
  
</details>

<details>
  <summary> Primer 2 </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/98706787-8ee31e80-237f-11eb-91fa-731b5c34c0fd.png)

![image](https://user-images.githubusercontent.com/45834270/98706859-a3bfb200-237f-11eb-8996-efc6b8735df9.png)

 
</details>

<details>
  <summary> Napomena </summary> <br>
  
  - Kada bismo uzeli **svaku funkcionalnu zavisnost** koja postoji u semi relacije ona bi **morala** da bude **POTPUNA** ( od kljuca ka nekom neprimarnom obelezju ). 
  - Ako **nemamo ni jednu funkcionalnu zavisnost** onda je normalna forma **ZADOVOLJENA**
  - Ako imamo situaciju da svaki kljuc ima samo **jedno obelezje**, znamo odma da je druga normalna forma **ZADOVOLJENA**, jer svaki kljuc ce odredjivati svako neprimarno obelezje, a ne postoje podskupovi kljuca, msm jedini podskup kljuca bi bio *prazna skup*
  
</details>

<details>
  <summary> Resavanje zadataka sa normalnim formama </summary> <br>

### Generalno resavanje zadataka sa nf

  - iz seme relacije izvlacimo funkcionalne zavisnosti koje unutra postoje, pa imamo semu relacije, obelezja i funkcionalne zavisnosti 
  - prvo **nadjemo kljuc**
  - **razvajamo primarna i neprimarna obelezja**
  - gledamo koju normalnu formu proveravamo, ako je recimo u drugoj normalnoj formi, moramo dati argumentaciju zasto je u drugoj normalnoj formi
    - U 2nf je jer ne postoje funkcionalne zavisnosti 
    - U 2nf je jer je kljuc prost i ne postoje potskupovi kljuca(a samim tim nije moguce da postoji nepotupna fz)
    - Nije u 2nf ako nadjemo kontra primer zbog kog nije u 2nf
    - U 2nf je jer smo proverili svaki moguci podskup svakog kljuca ka svakom neprimarnom obelezju i sve fz kljuca ka neprimarnom obelezju su potpune
    
</details>

<details>
  <summary> Ceste greske u 2nf </summary> <br>
  
  - Kolege krenu da proveravaju pravila za sva obelezja, dok kod 2nf se kaze da se pravilo odnosi samo na **NEPRIMARNA** obelezja sa desne strane funkcionalnih zavisnosti
  
</details>

<details>
  <summary> Anomalije azuriranja  </summary> <br>
  
  - pre gledanja ovih primera neophodno je bar da poznajete [osnovne stvari](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) o anomalijama azuriranja ( ako niste do sad pogledali, na samom dnu [ovog dela](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) mozete se upoznati sa istim)
  - u ovom delu cemo posmatrati anomalije koje se pojavljuju usled krsenja druge normalne forme

<br>

<details>
  <summary> Primer 1 </summary> <br>
  
  - ako pogledamo primer ispod (dobavljac, proizvod i grad)

![image](https://user-images.githubusercontent.com/45834270/108277044-0f809a80-7179-11eb-8c63-572fc353ef30.png)

<br>

  - anomalije azuriranja koje ovde primecujemo 
  - ono sto bi trebali da mozemo da upisemo a ova sema relacije nam to ne dozvoljava je:
    - da unesemo informaciju o dobavljacu i gradu a da ne unesemo proizvod (sto predstavlja anomaliju upisa)
  - anomalija modifikacije 
    - isti grad za istog dobavljaca ce se ponoviti onoliko koliko ima proizvoda (sto znaci da imamo problem sa modifikacijom, odnosno ako zelimo da promenimo informaciju o gradu, moracemo to uraditi na vise mesta, sto je anomalija modifikacije)
  - anomalija brisanja
    - ako izbrisem poslednji proizod za nekog dobavljaca, izgubicu i informaciju u kom je on gradu (anomalija brisanja)
 
 <br>
  
</details> 

<details>
  <summary> Primer 2 </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/108427435-75365a80-723d-11eb-9153-da1556c224ef.png)

<br>

  - anomalije azuriranja koje ovde mogu da se pojave su anomalija upisa, modifikacije i brisanja
  - anomalija upisa:
    - ne mozemo da unesemo informaciju o novom studentu (BRI, PRZ, IME, BPI) a da izostavimo predmet (OZP), jer je kljuc slozen odnosno kombinacija studenta(BRI) i predmeta(OZP) i to predstavlja anomaliju upisa, takodje vazi da ne mozemo uneti informaciju o novom predmetu a da ne unesemo studenta 
  - anomalija modifikacije(redudanse):
    - oznaku predmeta i naziv predmeta cemo morati ponoviti onoliko puta koliko imamo studenata (BRI), sto znaci da u slucaju da zelimo da promenimo naziv predmeta, to moramo uciniti onoliko puta koliko ima studenata vezanih za taj predmet, sto predstavlja anomaliju modifikacije (redudanse)
  - anomalija brisanja:
    - ako zelimo da izbrisemo recimo studenta (RA10/2010, Peric, Pero, 3) a predmet (AN1, Analiza 1) je predmet kojem je jedini student preostao u tom trenutku bas Pero Peric,
mi imamo anomaliju brisanja, jer brisanjem tog studenta mi gubimo informaciju i o predmetu  
</details> <br>


</details> <br>
  
# Treca normalna forma - 3NF

<details>
  <summary> Definicija tranzitivnosti </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/98717624-99a4b000-238d-11eb-9a70-d3736686416c.png)

### Tumacenje

  - X->A nije tranzitivno ukoliko ne postoji bar jedna od dve grane (X-> Y grana i Y->A grana) ili ukoliko postoji grana Y->X
  
</details>

<details>
  <summary> Definicija 3nf </summary> <br>
  
### Definicija

![image](https://user-images.githubusercontent.com/45834270/98718216-6e6e9080-238e-11eb-92c3-ca73cfbd09c3.png)

### Tumacenje definicije
  - samo za **NEPRIMARNA** obelezja koja ne pripadaju ni jednom kljucu(nalaze se sa desne strane funkcionalne zavisnosti), kada uzmemo bilo koji kljuc, sada ce kljuc sigurno odredjivati to obelezje (znaci sigurno vazi X->A)
  - ukoliko postoji neko Y, tako da Y->A nije trivijalna fz (posto je X kljuc, X ce sigurno odredjivati i Y) onda sigurno mora vaziti da Y odredjuje X (tada je Y neki nadskup kljuca) 
  
</details>

<details>
  <summary> Algoritam odredjivanja vazenja trece normalne forme  </summary> <br>
  
Najlakse se proverava na sledeci nacin:

  - posmatramo sve funckionalne zavisnosti koje imamo  u skupu
  - gledamo da li se desava situacija da je negde sa desne strane neko neprimarno obelezje a sa leve strane nesto sto 
funkcionalno ne odredjuje ni jedan kljuc
  - ako imamo tu situaciju to definitivno znaci da imamo neku tranzitivnu FZ od kljuca ka nekom neprimarnom obelezju

</details>

<details>
  <summary> Primer 1 </summary> <br>

![image](https://user-images.githubusercontent.com/45834270/98723485-bc859300-2392-11eb-9385-f1d933efe99c.png)

  - kljuc seme je: OZN 
  - posto kljuc ima jedno obelezje, zakljucujemo da su sva **neprimarna** obelezja u **potpunoj** fz u odnosu na svaki kljuc (zbog toga je zadovoljena 2nf)
  - a posto postoji **tranzitivna fz** od **kljuca** do **neprimarnog** obelezja, srusili smo 3nf, jer da bi srusili 3nf, dovoljno je samo jedan kontra primer (bas kao ovaj) koji pokazuje **tranzitivnost** od **kljuca** ka **neprimarnom** obelezju

</details>

<details>
  <summary> Napomena </summary> <br>

  - Za 3nf nemamo neku precicu kao kod 2nf gde cim vidimo da kljuc ima jedno obelezje mi zakljucujemo da su sva **neprimarna** obelezja u **potpunoj** fz u odnosu na svaki kljuc
  - Najbolje za 3nf je da nadjemo *kontra primer* koji pokazuje **tranzitivnost** od **kljuca** ka **neprimarnom** obelezju i kazemo da zbog tog kontra primera, 3nf nije zadovoljena 
  - Ako imamo situaciju da nemamo neprimarna obelezja, samim tim nemamo tranzitivnost iz kljuca u neprimarno obelezje jer ga nema, te zakljucujemo da ako **nemamo neprimarno obelezje**, **zadovoljena** je 3nf
  - Ako imamo situaciju da **ne postoje funkcionalne zavisnosti**(trivijalne ne gledamo) onda je sigurno **zadovoljena** 3nf

</details> 

<details>
  <summary> Anomalije azuriranja </summary> <br>
  
  - pre gledanja ovih primera neophodno je bar da poznajete [osnovne stvari](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) o anomalijama azuriranja ( ako niste do sad pogledali, na samom dnu [ovog dela](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) mozete se upoznati sa istim)
  - u ovom delu cemo posmatrati anomalije koje se pojavljuju usled krsenja trece normalne forme

<br>

<details>
  <summary> Primer </summary> <br>

![image](https://user-images.githubusercontent.com/45834270/108437446-a880e580-724d-11eb-83c7-5bde59f79a77.png)

  - anomalije koje se usled krsenja trece normalne forme mogu primetiti su anomalije upisa, modifikacije  i brisanja
  - anomalija upisa:
    - ne mozemo uneti informacije o odseku(SOD-sifra odseka, NAO-naziv odseka) a da pre toga ne unesemo informacije o studentu (BRI, PRZ, IME)
  - anomalija modifikacije(redudanse):
    - ako zelimo recimo da promenimo naziv odseka, primecujemo da se taj odsek pojavljuje na onoliko mesta koliko ima studenata (BRI-a) vezanih za taj odsek,
    - predstavimo to sa Y, sto znaci da jedna promena naziva odseka zahteva da to uradimo na Y mesta, sto predstavlja anomaliju redudanse
  - anomalija brisanja
    - ako izbrisemo studenta koji je recimo bio poslednji student vezan za neki odsek, mi gubimo i informaciju o tom odseku

<br>

</details>
  
  
</details>


<br>

# Bojs Kodova normalna forma - BCNF

<details> 
  <summary> Definicija BCNF </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/98741568-2dd23f80-23ad-11eb-8546-78e05a493934.png)

### Tumacenje definicije

  - uzmemo **bilo koji** atribut
  - posmatramo **bilo koji** skup obelezja Y, tako da Y ne sadrzi A
  - u koliko postoji neka ne trivijalna fz Y->A onda postoji neki kljuc koji je podskup leve strane(podskup Y-a)

U zavisnosti od 3nf, BCNF je strozija bas zbog toga sto je rec o **bilo kom atributu** a ne samo o **neprimarnom atributu**
  
</details>

<details>
  
  <summary> Algoritam odredjivanja vazenja Bojs kodove normalne forme </summary> <br>
  
  - Svaka netrivijalna FZ **bilo kog atributa** mora da sadrzi kljuc sa leve strane

</details>

<details>
  <summary> Primer 1 </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/98748945-04b8ab80-23bb-11eb-8b6c-05afc1820a09.png)

</details>

<details>
  <summary> Primer 2 </summary><br>
  
![image](https://user-images.githubusercontent.com/45834270/98749286-97f1e100-23bb-11eb-9d3f-947caed63861.png)
</details>

<details>
  <summary> Napomena </summary> <br>
  
  - iteriramo kroz svaku fz, i svaka od njih sa leve strane mora da ima bar jedan **CITAV** kljuc(tipa ako je kljuc AC, a imamo fz A->D, bcnf nije zadovoljena jer sa leve strane ove fz se ne nalazi **CITAV** kljuc nego samo njegov deo, tj A)
  
</details>


<details>
  <summary> Anomalije azuriranja </summary> <br>

  - pre gledanja ovih primera neophodno je bar da poznajete [osnovne stvari](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) o anomalijama azuriranja ( ako niste do sad pogledali, na samom dnu [ovog dela](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) mozete se upoznati sa istim)
  - u ovom delu cemo posmatrati anomalije koje se pojavljuju usled krsenja bojs kodove normalne forme

<details>
  <summary> Primer - obelezja "A", "B", "C" </summary> <br>

  - anomalije azuriranja koje se javljaju usled krsenja BCNF posmatramo na primeru ispod

![image](https://user-images.githubusercontent.com/45834270/108510669-17e2ed80-72bf-11eb-85c5-3ae04c81a14b.png)

  - anomalija upisa:
    - ne mozemo da upisemo informaciju o obelezjima "A" i "B" a da ne unesemo informaciju o obelezju "C", sto predstavlja anomaliju upisa
  - anomalija modifikacije(redudanse):
    - ako zelimo da promenimo informaciju o obelezju "A" (ako to sistem uopste dozvoljava,posto je ono primarno obelejze),mi to moramo uraditi na vise mesta (kao sto se vidi na [slici](https://user-images.githubusercontent.com/45834270/108511969-e5d28b00-72c0-11eb-843b-4f7dd72da6e3.png) )
    - sto predstavlja anomaliju redudanse
  - anomalija brisanja:
    - ako pogledamo [ovu](https://user-images.githubusercontent.com/45834270/108512431-832dbf00-72c1-11eb-8790-e31400b3dd3b.png) situaciju, odnosno, ako zelimo da obrisemo informaciju o obelezju "C" (odnosno  ako zelimo da izbrisemo podatak "X")
    - a pri tome je podacima (1,0) obelezja "A" i "B" to poslednja veza sa bilo kojim obelezjem "C"
    - to prouzrokuje da brisanjem podatka "X" obelezja "C" mi gubimo svaki trag i o konkretnim vrednostima (1,0) obelezja "A" i "B"
    - sto predstavlja anomaliju brisanja

<br>

</details>


<details>
  <summary> Primer - Ilustrovaniji </summary> <br>
  
  
![image](https://user-images.githubusercontent.com/45834270/108513492-f8e65a80-72c2-11eb-92e5-a72c1ba1af7c.png)

  - ako vidimo primer iznad, imamo Dobavljaca, NazivDobavljaca i Proizvood
  - K = {Dobavljac + Proizvod, NazivDobavljaca + Proizvod}
  - anomalija upisa:
    - ako predpostavimo da je stanje [ovakvo](https://user-images.githubusercontent.com/45834270/108515927-ec173600-72c5-11eb-93ae-8ef15697ee84.png)
    - odnosno, pokusavamo da dodamo novog dobavljaca, ("AMD","Velja Nevolja")
    - medjutim, to nije moguce ako ne unesemo podatak o "Proizvod"-u 
    - sto znaci da mi ne mozemo uneti novog dobavljaca dokle god ne unesemo i proizvod vezan za njega
    - sto predstavlja anomaliju upisa
  - anomalija modifikacije
    - ako predpostavimo da je stanje [ovakvo](https://user-images.githubusercontent.com/45834270/108514720-7c547b80-72c4-11eb-9f1c-bf68162bf6a8.png)
    - a mi hocemo recimo "Velji Nevolji" obelezja "NazivDobavljaca" da promenimo ime u "Veljko Tehnika", mi to moramo uraditi na vise mesta (sto se da primetiti sa [slike](https://user-images.githubusercontent.com/45834270/108514720-7c547b80-72c4-11eb-9f1c-bf68162bf6a8.png) )
    - a to je anomalija redudanse
  - anomalija brisanja
    - ako sad predpostavimo da je stanje [ovakvo](https://user-images.githubusercontent.com/45834270/108516525-9f802a80-72c6-11eb-8341-9cddc917b190.png)
    - a zelimo da obrisemo recimo proizvod "RX 5500", to znaci da brisanjem tog podatka o proizvodu, mi gubimo i informaciju o dobavljacu (posto mu je to poslednja veza sa bilo kojim proizvodom)
    - sto predstavlja anomaliju brisanja
  
</details>
  
</details>

<br>

# Cetvrta normalna forma - 4NF

<details> 
  <summary> Definicija 4NF </summary> <br>
  
  - skup ogranicenja C je sacinjen od skupa funkionalnih zavisnosti(F) i od skupa viseznacnih zavisnosti(MV)
  
![image](https://user-images.githubusercontent.com/49925421/101392627-4bb89480-38c6-11eb-820a-f8a977d988fa.png)


</details>

<details>
  <summary> Anomalije azuriranja </summary> <br>
  
  - pre gledanja ovih primera neophodno je bar da poznajete [osnovne stvari](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) o anomalijama azuriranja ( ako niste do sad pogledali, na samom dnu [ovog dela](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-3) mozete se upoznati sa istim)
  - u ovom delu cemo posmatrati anomalije koje se pojavljuju usled krsenja cetvrte normalne forme

<details>
  <summary> Primer </summary><br>

![image](https://user-images.githubusercontent.com/45834270/108571251-08d85b80-7310-11eb-890c-07550426a334.png)

  - anomalija upisa:
    - ako zelimo da upisemo (OZP-OznakaPredmeta,OZD-OznakaDepartmana) imamo anomaliju upisa zato sto moramo upisati i OZN(oznaku nastavnika, jer je to obelezje deo kljuca)
    - takodje, ono sto je **SPECIFICNO** kod upisa torke u relaciju koja ima **viseznacne fz** je da ne mozemo samo upisati novu torku, nego moramo proveriti da li je potrebno upisati i neku drugu torku
    - odnosno, ako zelimo da upisemo torku (Predmet,Nastavnik,Departman) zajedno, moze se dogoditi da upis torke izaziva i upis nepotrebnih torki
    - da bi znali koje sve torke jos trebamo dodati u tom slucaju, ono sto je potrebno jeste da znamo sta znaci **zadovoljenje viseznacne zavisnosti**
    - da bi obezbedili to zadovoljenje u jednoj relaciji, trebamo napraviti projekcije i spojiti ih a potom videti da li imamo nove torke u tom spoju
    - ako da, onda treba da **DODAMO I TE NOVE TORKE** da bi se odrzalo zadovoljenje viseznacne zavisnosti, sto predstavlja anomaliju upisa
    - ***napomena***: posto u primeru imamo vz OZP->->OZD, zadovoljene vz moramo proveriti za nju (a tako  bi trebali i za svaku vz koju imamo u skupu ogranicenja C)([podsetnik](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/2020-2021/Predavanja/predavanje-2) kako to najbrze proveriti se nalazi na linkovanom direktorijumu na dnu istog)
    - u nasem slucaju bismo uradili projekciju nad OZP+OZD i projekciju nad OZP+OZN, potom bismo uradili prirodni spoj tih projekcija, a torke koje se ne nalaze u nasoj relaciji a dobijene su ovim spojom, su one torke koje fale da bi vazilo zadovoljenje vz
  - anomalija redudanse
    - ako zelimo da izmenimo informaciju recimo o nastavniku, to moramo uraditi na vise mesta ([ilustrovano](https://user-images.githubusercontent.com/45834270/108572946-b862fd00-7313-11eb-87a3-78127cc1fa88.png) )
  - anomalija brisanja
    - ako u [ovom primeru](https://user-images.githubusercontent.com/45834270/108573050-ffe98900-7313-11eb-98cc-f89dbacc6177.png) recimo zelimo da izbrisemo nastavnika "Rale", izgubicemo informacije i o predmetu Analiza1
    - sto predstavlja anomaliju brisanja
    - takodje, ono sto je **SPECIFICNO** kod brisanja torke u relaciju koja ima **viseznacne fz** je da ne mozemo tek tako obrisati neku torku iz relacije, mora i dalje ostati zadovoljenje vz, odnosno, isti proces kao i kod upisa nove, samo sto u ovom slucaju kada uradimo projekcije i prirodni spoj, saznajemo da li neke torke takodje treba da izbrisemo

</details><br>

</details>

<br>

# Peta normalna forma - 5NF (Normalna forma projekcije i spoja - PJNF)

<details>
  <summary> Uvod </summary><br>

  - znamo da je vz **specijalan** slucaj **zavisnosti spoja** sa samo dve komponente
  - JD je skup zavisnosti spoja
  - ovo(C=F u JD) je samo poopstenje prethodne situacije jer su vz specijalan slucaj **zavisnosti spoja (zs)**
  - dakle, u ovoj formulaciji mi obuhvatamo i sve vz

![image](https://user-images.githubusercontent.com/45834270/108612452-2fb69080-73e9-11eb-8f9d-fd85cb7483af.png)


</details>

<details> 
  <summary> Definicija 5NF/PJNF </summary> <br>
  
  - netrivijalna zavisnost spoja je netrivijalna onda kada je unija svih onih komponenti Xi jednaka R-u
  - a ni jedna od njih posebno nije jednaka bas celom R-u
  - dakle mora biti posledica zavisnosti kljuca iz K 
    - prakticno svaka ta komponenta ce morati biti u vezi sa kljucem
    - i to tako sto uzmemo bilo koju zavisnost spoja i ako uzmemo bilo koju komponentu X (naravno koja je razlicita od R-a, idemo na netrivijalnu)
    - iako je ta zavisnost spoja posledica od naseg C
    - onda za svaku tu komponentu mora postojati neka druga komponenta u zavisnosti spoja
    - pri cemu treba da su one razlicite i da je u preseku kljuc (barem  jedan kljuc)
    - dakle kad uzmemo X1 mora postajati bar jos neki Xi da je u njihovom preseku sadrzan bar jedan kljuc 
  
![image](https://user-images.githubusercontent.com/49925421/101393124-de593380-38c6-11eb-9feb-6a75f51c589c.png)


</details>

<details>
  <summary> Primer </summary><br>
  
  - imamo trokomponentu zavisnost spoja (pri cemu su obelezja: OznakaPredmeta, OznakaNastavnika, OznakaDepartmana)
  - u ovom primeru, nastavnike dodeljujem predmetu nezavisno od departmana i obrnuto(predmetu dodeljujem nastavnike nezavisno od departmana)
  - nastavnike dodeljujem departmanu nezavisno od predmeta
  - predmete dodeljujem departmanu nezavisno od nastavnika   
  - ova zavisnost spoja je takva da nije posledica ni jedne fz (jer ih nema uopste)
  - ono sto takodje vidimo je da ni jedna od ovih komponenata nema da sa jos nekom u preseku sa njom ima kljuc
  - znaci ako uzmemo recimo OZP+OZN komponentu i OZN+OZD komponentu, njihov presek je OZN, ali OZN ne sadrzi kljuc (OZP+OZN+OZD)
  - OZP+OZN i OZP+OZD u preseku ima OZP ali taj presek ne sadrzi kljuc
  - OZN+OZD i OZP+OZD u preseku ima OZD ali taj presek ne sadrzi kljuc
  - te stoga imamo narusen uslov 5NF

![image](https://user-images.githubusercontent.com/45834270/108613416-182fd580-73f2-11eb-8ecc-2e83f0bc6401.png)
  
  - ono sto se lepo vidi ovde je mogucnost dekomponovanja na tri sr (svaka komponenta dobija svoju sr)
  
</details>

<br>

# Sesta normalna forma - 6NF (Normalna forma domena i kljuceva - DKNF)

<details> 
  <summary> Definicija 6NF/DKNF </summary> <br>
  
  - u skupu ogranicenja domena D mi imamo pobrojane sve domene svih obelezja koja su sadrzana u nasoj semi relacije N
  - a **ogranicenjem torke** smo uvodili sva ogranicenja domena
    - svako obelezje iz seme relacije mora za sebe imati uvezano **ogranicenje vrednosti obelezja** (**ogranicenje torke**)
    - a ogranicenje vrednosti obelezja je govorilo da svakom obelezju moramo *pridruziti domen* i moramo specifirati da li za to obelezje u toj semi relaciji *dozvoljeno ili zabranjeno* zadavanje *nula* vrednosti
  - tim ogranicenjem smo uvodili i *skup domena* koji je nama neophodan da bi pridruzili svakom obelezju(iz skupa R) jedan domen i onda sada prakticno govorimo o tom skupu kao o skupu **D**
  
![image](https://user-images.githubusercontent.com/49925421/101393227-08aaf100-38c7-11eb-8a7e-fca0f8da40e7.png)

</details>

<details> 
  <summary> Primer </summary> <br>
  
  - obelezja: StudentID, Prezime,  Ime, SrednjaOcena(avg-prosek), Klasa (opis uspeha studenta)
  - SID->R nam kaze da je SID kljuc
  - a imamo i organicenje torke (takvo da je svakom obelezju dodeljeno ogranicenje vrednosti obelezja)
  
![image](https://user-images.githubusercontent.com/45834270/108639683-16b7e900-7496-11eb-9922-f8c6bcd1b113.png)

  - DKNF je narusen, kada pogledamo logicki  uslov, on povezuje vrednosti obelezja AVG i KLS
    - ali mi ne mozemo reci da je ovaj logicki uslov *posledica* niti **ogranicenja kljuca** niti ogranicenja vrednosti pojedinacnih obelezja tj. **domena**

</details>

<br>

# Odnosni normalnih formi + DOKAZI

<details>
  <summary> Odnos uslova normalnih formi 1NF-BCNF  </summary> <br>
  
  - 1NF je **potreban** uslov za sve vise normalne forme, pri cemu je 1NF **ugradjen u definiciju** uslova svih ostalih normalnih formi

</details>

<details> <summary> [dokaz] 3NF => 2NF  </summary><br> 
  
  - dokaz implikacije koja kaze da cim je zadovoljena treca normalna forma, to implicira da vazi i druga normalna forma
  - ono sto ovde hocemo da dokazemo je da logicki [uslov 3nf](https://user-images.githubusercontent.com/45834270/108538575-3bb62b80-72df-11eb-9b44-b988119c1b37.png
), tj. uslov **netranzitivnosti** bilo koje fz **neprimarnog** atributa od kljuca implicira i uslov da **nemamo** nikada i **nepotpunu**([uslov 2nf](https://user-images.githubusercontent.com/45834270/108538477-1e815d00-72df-11eb-9c50-5ba76647dac6.png)) funkcionalnu zavisnost **neprimarnog** atributa od kljuca  
  - to mozemo postici **kontra pozicijom**, odnosno, dokazujemo da ce **narusenje 2NF implicirati i narusenje 3NF**
  - na ovaj nacin olaksavamo proveru, odnosno umesto da pokazujemo **za svako** zadovoljene 3NF da implicira  2NF, lakse je dokazati **bilo koje** nezadovoljenje 2NF
 
![image](https://user-images.githubusercontent.com/45834270/108545874-a324a900-72e8-11eb-9275-5880de5de09f.png)

  - X->Y jer je X kljuc
  - Y->A zbog nase predpostavke
  - !(Y->X) jer je Y pravi podskup X
  
</details>

<details>
  <summary> Alternativna(ekvivalentna) formulacija uslova 3NF + DOKAZ ekvivalencije </summary> <br>
  
<details>
  <summary> Definicija </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/108551305-0cf48100-72f0-11eb-8cbf-496f29cd7ea6.png)
  
</details>

<details>
  <summary> Dokaz </summary> <br>

## !(alternativna-3NF) => !(standardna-3NF)

 - ako gledamo levu implikaciju
 - prvo sto uradimo je negiranje [ove formule](https://user-images.githubusercontent.com/45834270/108563250-729d3900-7301-11eb-9e39-b12c264a75a0.png)(alternativni uslov 3NF), mi treba onda da dobijemo negaciju [ove formule](https://user-images.githubusercontent.com/45834270/108563208-5d280f00-7301-11eb-85a6-0112e20b28e2.png)(standardni uslov 3NF)(treba da dobijemo **tranzitivnost**)
 - za svaki kljuc X, znamo da on sigurno odredjuje Y
 - takodje znamo da Y->A
 - a Y->X ne vazi, zato sto znamo da Y ne sadrzi ni jedan jedini kljuc sa svoje leve strane, onda Y sigurno ne moze da odredjuje bilo koji kljuc jer bi onda on sam bio kljuc (ili bi sadrzao kljuc sa svoje leve strane)
 - stoga, imamo tranzitivnost, sto znaci da smo dokazali **!(alternativna-3NF) => !(standardna-3NF)**
 
![image](https://user-images.githubusercontent.com/45834270/108562771-aa57b100-7300-11eb-95ef-ee3272b77967.png)

 <br>

## !(standardna-3NF) => !(alternativna-3NF)

  - prvo radimo negaciju [ove formule](https://user-images.githubusercontent.com/45834270/108563208-5d280f00-7301-11eb-85a6-0112e20b28e2.png)(standardni uslov 3NF)(i dobijemo tranzitivnost)  i ocekujemo  da dobijemo negaciju [ove formule](https://user-images.githubusercontent.com/45834270/108563250-729d3900-7301-11eb-9e39-b12c264a75a0.png)(alternativni uslov 3NF)
  - mi onda konstatujemo da [ovde](https://user-images.githubusercontent.com/45834270/108566524-dc6c1180-7306-11eb-82f5-90cdd06d1a3d.png) ne postoji kljuc koji bi bio podskup od Y, inace bi bi prakticno dosli u kontradikciju, jer ako bi postojao kljuc koji bi bio u Y onda bi moralo da  vazi  [ovo gore](https://user-images.githubusercontent.com/45834270/108566722-29e87e80-7307-11eb-8c95-86b754080e31.png), znaci iz cinnjenice da to ne vazi, onda sigurno nema ni jednog kljuca u levoj strani  od Y

![image](https://user-images.githubusercontent.com/45834270/108562851-c8251600-7300-11eb-8a05-c3c29dc3324b.png)

<br>

</details><br>

</details>

<details>
  <summary> [dokaz] BCNF=>3NF </summary> <br>
  
  - posto BCNF kaze da za **svako obelezje** i za svaku netrivijalnu fz, mora postojati kljuc sa leve strane
  - a alternativna definicija 3NF isto to kaze samo za **svako neprimarno obelezje**, a cim za nadskup vazi (sva obelezje), to implicira da vazi i za podskup (neprimarna obelezja)
  
![image](https://user-images.githubusercontent.com/45834270/108552616-db7cb500-72f1-11eb-8ee7-1f8109bd6c29.png)  

</details>

<details>
  <summary> [dokaz] 4NF => BCNF </summary><br>
  
  - mi imamo pravilo da **svaka fz implicira vz** (iz X->Y implicira X->->Y)
  - ako se time vodimo(zbog toga kazemo da je iz Y->a => Y->->A) i odradimo samo negaciju BCNF, treba da dobijemo negiranu 4NF
  - ono sto trenutno dobijemo je skoro naruseni uslov 4NF, ono sto nam fali jos je da umesto **podskupa** imamo **pravi podskup** (negirana 4NF to zahteva)

![image](https://user-images.githubusercontent.com/45834270/108609578-186aa980-73cf-11eb-92af-35c846bece62.png)

<br>

  - stoga, logickim principom iskljucenja treceg imamo 2 slucaja
 
![image](https://user-images.githubusercontent.com/45834270/108609805-cb87d280-73d0-11eb-879d-1bd24e7c1ed9.png)
 
 <br>
 
  - pod a, dobijamo odmah direktno negiranu 4NF

![image](https://user-images.githubusercontent.com/45834270/108609838-038f1580-73d1-11eb-85d6-4d6096bd589c.png)

<br>

  - pod b, imamo kontradikciju
  - ako je **X kljuc i X=R**, a vazi fz R/{A} -> A, onda X nije minimalno jer A moze da se izbaci (iz X-a)
  - znaci X ne moze biti citavo R jer ako je citavo R, onda nije kljuc(jer A moze da se izbaci)
  - sto je kontradikcija sa pocetnom pretpostavkom

![image](https://user-images.githubusercontent.com/45834270/108610767-89628f00-73d8-11eb-81d5-6eadadcff6f8.png)

<br>

  - konacno smo dokazali ono sto smo inicijalno i zeleli (negirana BCNF implicira negiranu 4NF)

![image](https://user-images.githubusercontent.com/45834270/108610775-a13a1300-73d8-11eb-82a5-50530d093a17.png)

<br>
 
</details>

<details>
  <summary> Alternativna(ekvivalentna) formulacija uslova 4NF </summary> <br>
  
<details>
  <summary> Definicija </summary> <br>
  
  - voditi racuna da mora biti zadovoljena **BCNF** !!
  
![image](https://user-images.githubusercontent.com/45834270/108610878-8b791d80-73d9-11eb-8919-cf339432aa56.png)
  
</details>

<details>
  <summary> [dokaz] U desno </summary> <br>
  
  - uzmemo bilo koju vz, takva da je ona posledica od F
  - onda znamo da je F u MV ekvivalentno sa F
  - sto znaci da se nasa sema relacije svodi na sr N(R,F)
  - a cim zadovolja BCNF, onda sigurno zadovoljava i 4NF

![image](https://user-images.githubusercontent.com/45834270/108611146-ead82d00-73db-11eb-91a1-5360a6f1a15f.png)


</details>

<details>
  <summary> [dokaz] U levo </summary> <br>
  
  - ako smo narusili BCNF, narusili smo i 4NF (ranije dokazano)
  - sto znaci da ne mozemo da predpostavimo da vazi 4NF i da je [ovde](https://user-images.githubusercontent.com/45834270/108611501-61c2f500-73df-11eb-99ea-ac56f819b6da.png) narusena, znaci BCNF mora da vazi
 
 
  - onda ostaje ovaj [drugi uslov](https://user-images.githubusercontent.com/45834270/108611517-9040d000-73df-11eb-96a0-4233ce1c6d1f.png)
  - tj. uzmemo vz koja nije posledica skupa fz
  - posto vazi 4NF i posto imamo takvu vz onda mora biti da postoji neki kljuc koji je podskup od ove leve strane Y
  - a ako postoji takav kljuc ,onda vazi X u Z (posto je X kljuc)
  - a ako vazi X u Z, posto je Y nadskup od X, onda vazi Y->Z
  - a to implicira da vazi Y->->Z
  - a poceli smo od predpostavke da Y->->Z ne vazi kao posledica skupa fz F
  - sto nas dovodi do kontradikcije
  
![image](https://user-images.githubusercontent.com/45834270/108611287-8d44e000-73dd-11eb-9708-3134ac1a8393.png)
  
</details>

  
</details>

<details>
  <summary> [dokaz] 5NF=>4NF </summary><br>
  
  - narusavanje 4NF narusava i 5NF zato sto je vz ekvivalentna zavisnosti spoja
  - i cim smo narusili 4NF, tj. da X ne sadrzi kljuc sa svoje leve strane a znamo da je on u preseku onda nece sigurno biti zadovoljen ni uslov 5NF
  
![image](https://user-images.githubusercontent.com/45834270/108613743-ebc98880-73f4-11eb-8d02-543c87cec095.png)
  
</details>

<details>
  <summary> Alternativna(ekvivalentna) formulacija uslova 5NF </summary><br>
  
  - voditi racuna da mora biti zadovoljena **BCNF** !
  - ovo znaci da ako 'doteramo' nasu sr do BCNF i ako mozemo da eliminisemo sve vz i sve zavisnosti spoja kao posledice fz, onda sigurno jesmo u 5NF
  
![image](https://user-images.githubusercontent.com/45834270/108613843-e7519f80-73f5-11eb-9225-c7b089dc69c8.png)
  
  - posledica je da ako nasa sr zadovolji 5NF, onda svaka ta komponenta zavisnosti spoja je takva da sadrzi **bar jedan kljuc**
  
</details>

<br>


# Sve normalne forme

<details>
  <summary> Algoritam za rad sa normalnim formama </summary> <br>
  
  - [0 korak]: Nadjemo kljuceve i posmatramo sva obelezja koja postoje u kljucu, odnosno sva obelezja podelimo u  **PRIMARNA**(pripadaju barem jednom kljucu) i **NEPRIMARNA** (ne pripadaju ni jednom kljucu)
  - [1 korak]:
  - [2 korak]:
  - [3 korak]:
  
</details>
  
<details>
  <summary> Za sve normalne forme vazi </summary> <br>
  
  - **Sema BP** (CELA BAZA PODATAKA) je u nekoj od normalnih formi ako su **sve seme relacija** u nekoj od normalnih formi. 
  - Ako posmatramo 'redosled' normalnih formi [1nf, 2nf, 3nf, bcnf, 4nf, ...] znamo da ako vazi recimo 3nf, mora da vazi 1nf i 2nf, odnosno ako vazi jedna normalna forma, sve one pre nje moraju da vaze
   moze
     
</details> <br>

## Vezbanje

<details>
  <summary> Primer 1 </summary> <br>
  
#### Zadatak

![image](https://user-images.githubusercontent.com/45834270/98749985-29158780-23bd-11eb-9a5f-17b80bcfeb70.png)


#### Resenje

![image](https://user-images.githubusercontent.com/45834270/98750002-33378600-23bd-11eb-9af5-de34b3c63190.png)

  - nije u 2nf jer podskup kljuca moze da izvede neko neprimarno obelezje, npr BRI -> IME
  - nije u 3nf jer imamo tranzitivnost kljuca ka neprimarnom obelezju, npr BRI -> NAZSMER
  - posto je palo vec na 2nf, nije ni bilo potrebe ispitivati 3nf ( to je bilo cisto iz edukativne potrebe)
  - a ostaje nam jedino 1nf, za koju uvek **predpostavljamo da vazi**
  
</details>

<details>
  <summary> Primer 2 </summary> <br>

#### Pitanje

U kojoj je normalnoj formi baza ?

#### Odgovor

Posto se baza sastoji od vise sema, gledamo koja je *najlosija* nf koju sve seme zadovoljavaju. Ako imamo 3 seme koje su u bcnf i jedna u 2nf, nasa baza je u 2nf.

</details>

<details>
  <summary> Primer 3 </summary> <br>

![image](https://user-images.githubusercontent.com/45834270/98754927-eb6a2c00-23c7-11eb-988d-ce671b2007b6.png)

</details>

<details>
  <summary> Primer 4 </summary> <br>

  - fora kada **NEMAMO NEPRIMARNA OBELEZJA**
  - primetili smo da imamo 2 kljuca
  - svako od obelezja se nalazi unutar jednog od kljuceva 
  - to znaci da nemamo neprimarna obelezja 
  - u tom slucaju automatski znaci da 2nf i 3nf vaze 

![image](https://user-images.githubusercontent.com/45834270/98755051-1fdde800-23c8-11eb-98f1-064b2234ef31.png)       

</details>

<br>

## Podsetnik

<details>
  <summary> Odredjivanje svih fz u semi relacije </summary> <br>
  
Npr. da bi odredili koje sve fz postoje u semama relacije na slici ispod:
  - pogledamo polazni skup funkcionalnih zavisnosti F
  - onda uradimo njegovu [projekciju](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/baze2%5B20-21%5D/vezbe/v2) po skupu obelezja seme relacije (Student i Prijava u nasem primeru)
  - tada dobijamo skup funkcionalnih zavisnosti koji vazi unutar te male seme relacije 

![image](https://user-images.githubusercontent.com/45834270/98753326-5a458600-23c4-11eb-9433-a050ec1b1ee2.png)

  
</details>

<br>

## Beleske

Poslednji primer i po formi i po tezini odgovoara nekom tezem zadataku koji moze da dodje na kolokvijumu. 






















