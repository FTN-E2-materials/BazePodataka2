# Spojivost bez gubitaka

<details>
  <summary> Definicija </summary> <br>
  
  - U: polazni skup obelezja
  - F: polazni skup funkcionalnih zavisnosti 
  - F1: projekcija polaznog skupa funkcionalnih zavisnosti F nad skup obelezja R1
  - F2: projekcija polaznog skupa funkcionalnih zavisnosti F nad skup obelezja R2
  
![image](https://user-images.githubusercontent.com/45834270/98822092-a6c6ab00-2430-11eb-8840-585b13fd78dc.png)

  - kada uradimo uniju R1 i R2, treba da dobijemo polazno U
  - tu je bitno da se ne pojave nove torke ( nove u smislu da se nisu nalazile u polaznoj relaciji U )

</details>

<details>
  <summary> Teorema o spojivosti bez gubitaka </summary> <br>
 
![image](https://user-images.githubusercontent.com/45834270/98823816-d37bc200-2432-11eb-84a9-d4705de76c9d.png)

  - poslednji red je drugi nacin zapisivanja [projekcije](https://github.com/FTN-E2-materials/BazePodataka2/tree/main/baze2%5B20-21%5D/vezbe/v2)
  - gde se samo kaze da je recimo F1 zapravo projekcija F-a nad skupom obelezja R1

![image](https://user-images.githubusercontent.com/45834270/98824005-0cb43200-2433-11eb-9235-d50dfb669602.png)

![image](https://user-images.githubusercontent.com/45834270/98824218-53a22780-2433-11eb-95db-90ca285ddf5b.png)

  - poslednji red je drugi nacin zapisivanja da ***jedna sema relacije*** ima **STRANI KLJUC** ka ***drugoj semi relacije*** 

</details>

<details>
  <summary> Algoritam </summary> <br>
  
  - kada imamo vise sema relacije, **proizvoljnim** redosledom vrsimo spajanje relacija 
  - spajamo tako da u svakom koraku ono sto spajamo, mora da zadovoljava **teoremu o spojivosti bez gubitaka**
  - ako smo **proizvoljnim** redosledom pokusali da spojimo dve relacije (npr R1 i R2 kao u zadataku 1) a one nisu spojive, to ne znaci da nasa SBP ne moze da se spoji **spajanjem drugih** kombinacija (odnosno mozemo sad da probamo R1 sa nekom drugom, pa kada to dobijemo onda mozemo taj spoj da probamo da spojimo sa R2 )
  - tek kada **nikako**(ni preko jedne kombinacije) **ne mozemo da izvrsimo spajanje** sema relacija, tada SBP nema obezbedjenju **spojivost bez gubitaka**
  
  
</details>

<details>
  <summary> Napomena </summary> <br>
  
  - treba spajati seme relacije koje **odmah mogu da se spoje** (jer redosled spajanja nije bitan !)
  
</details> <br>


## Zadaci za vezbu 

<details>
  <summary> Zadatak 1 </summary> <br>
  
## Polazni skup obelezja i funkcionalnih zavisnosti (U,F)

![image](https://user-images.githubusercontent.com/45834270/98825239-8dbff900-2434-11eb-8855-79faf2526a75.png)
  
## Pretpostavka

![image](https://user-images.githubusercontent.com/45834270/98825265-96183400-2434-11eb-8777-cea734d288a3.png)

## Pitanje

Da li je obezbedjena spojivost SBP(seme baze podataka) bez gubitaka ?

## Odgovor

![image](https://user-images.githubusercontent.com/45834270/98829218-40925600-2439-11eb-9dd8-0ba9a8b5f540.png)

  - iako R1 i R2 nisu spojive, to ne znaci da nemamo kombinaciju koju cemo moci da spojimo recimo sa R1, a onda tu kombinaciju da spajamo sa R2, tkd idemo na sledecu kombinaciju

![image](https://user-images.githubusercontent.com/45834270/98829263-4d16ae80-2439-11eb-98d1-5118b1c75962.png)

  - R1 i R3 su spojive jer U1 presek U3 funkcionalno odredjuje U1 razlika U3
  - bitno je napomenuti, da je za spojivost bez gubitaka potrebno da **bar jedan** od ova poslednja dva reda **bude tacan**
  - odnosno R->MSO nije tacno ali posto je R->IP tacno, R1 i R3 su spojive bez gubitaka
  - cim smo utvrdili R->IP i pokazali da imamo **bar jednu ispunjenost** drugu nije ni potrebno proveravati

![image](https://user-images.githubusercontent.com/45834270/98829297-56a01680-2439-11eb-9d08-2ab727246a61.png)

  - sada spojeno R13 spajamo sa R2
  - na slajdu je nacinjena greska jer U13 presek U2 koje fz odredjuje U2 razlika U13 je zapravo M->prazan skup( umesto U13 razlika U2, treba da pise U2 razlika U13 )
  - M -> prazan skup je trivijalna fz(leva strana sadrzi sve ono sto sadrzi i desna), te smo zadovoljili teoremu o spojivosti bez gubitaka 
  - cim smo dobili jednu ispunjenost, znamo da R13 i R2 su spojive bez gubitaka
  
### Zakljucak

Posto smo uspeli da spojimo sve, to znaci da je obezbedjena spojivost bez gubitaka.

</details>

<details>
  <summary> Zadatak 2 </summary> <br>

![image](https://user-images.githubusercontent.com/45834270/98835124-4fc8d200-2440-11eb-880c-9ef93bc39d30.png)

### Odrediti kljuceve

![image](https://user-images.githubusercontent.com/45834270/98835960-628fd680-2441-11eb-9049-99e95dc7736a.png)

### Odrediti koje nf su tu zadovoljene 

![image](https://user-images.githubusercontent.com/45834270/98836050-87844980-2441-11eb-9c56-4b955436cf9f.png) 
  
</details>

<details>
  <summary> Zadatak 3 [tip zadatka za kolokvijum] </summary> <br>
  
![image](https://user-images.githubusercontent.com/45834270/98845483-15fec800-244e-11eb-9316-8b38eb6cc404.png)

## U kojoj nf se nalaze date sr 
  
![image](https://user-images.githubusercontent.com/45834270/98845762-7857c880-244e-11eb-8472-b98947198aac.png)

![image](https://user-images.githubusercontent.com/45834270/98845793-83125d80-244e-11eb-9270-ac9774f72dc5.png)

  - imamo 2 fz, za svaku od njih postoji neki kljuc koji se u potpunosti nalazi sa njihove leve strane tako da je zadovoljena bcnf a samim tim i sve pre nje 
  
![image](https://user-images.githubusercontent.com/45834270/98846166-ffa53c00-244e-11eb-9b71-4ec73a75ac24.png)

  - ovo je najbolja varijanta kad za projekciju dobijemo trivijalne fz, tu odma znamo da vaze sve nf

![image](https://user-images.githubusercontent.com/45834270/98846374-4430d780-244f-11eb-9592-dd349b4cfb76.png)

  - bcnf nije zadovoljena jer imamo A->H i H->A jer sa leve strane neke fz se ne nalazi ceo kljuc    
  
![image](https://user-images.githubusercontent.com/45834270/98847184-34fe5980-2450-11eb-984d-779af8b0f219.png)

  - jedna jedina fz, zadrzi kljuc sa leve strane te odma vazi bcnf i samim tim sve nf pre nje 

## Da li je obezbedjena spojivost sbp bez gubitaka
  
  - ako proverimo sve moguce kombinacije i ne mozemo da dodjemo do citave SBP, tek onda nemamo obezbedjenu spojivost bez gubitaka
  
![image](https://user-images.githubusercontent.com/45834270/98847549-b81faf80-2450-11eb-9095-593e8058c498.png)

![image](https://user-images.githubusercontent.com/45834270/98847759-0af96700-2451-11eb-9aed-2e410df0cdaf.png)

![image](https://user-images.githubusercontent.com/45834270/98848019-64619600-2451-11eb-8459-19e95ae392d8.png)

  
</details> 

<br>

## Kolokvijum

<details>
  <summary> Tipovi zadatka </summary> <br>
  
  - na kolokvijum dolaze 2 laksa zadatka tipa treceg zadatka
  - dobijemo skup obelezja i skup funkcionalnih zavisnosti 
  - prvo pitanje je **u kojoj nf** se nalaze date seme relacije
    - odredimo koji je kljuc 
    - odredimo primarna i neprimarna obelezja 
    - krenemo redom da proveravamo nf 
    - prvo proverimo **PRECICE**: da li **postoje neprimarna obelezja**, jel **kljuc ima samo jedan atribut**, jel odma **zadovoljena bcnf**, jel odma **nije zadovoljena druga**
  - nastavak prvog pitanje je i da na osnovu isprojektovane 2, 3 (koliko god) seme relacije (sa nekim skupovima obelezja) zakljucimo **koje funkcionalne zavisnosti** tu vaze
    - to resavamo tako sto radimo **projekciju skupa fz na taj skup obelezja**
    - kad imamo skup fz onda nadjemo kljuc i vidimo u kojoj su normalnoj formi
  - poslednje pitanje moze da bude **da li vazi spoj bez gubitaka**

</details>

<br>

## Beleske

Poslednji zadatak je veoma slican zadataku koji ce doci na kolokvijum. Tu su samo obelezja, bez znacenja sta koje obelezje predstavlja.
