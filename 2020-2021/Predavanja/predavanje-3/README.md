<!-- Summary snippet

<details>
 <summary> Name of Summary </summary> 
  
Some snippet of text
 
</details>


-->


# Nastavak sa predavanja-1

### Zavisnost spoja

Je nadgradnja viseznacnih zavisnosti. Zavisnost spoja >< (x1, ..., xk)

![image](https://user-images.githubusercontent.com/45834270/97726083-2c606780-1acf-11eb-93bc-9740fee797e2.png)

Cela relacija r ce zadovoljavati zavisnost spoja ><(x1, ... xk)

![image](https://user-images.githubusercontent.com/45834270/97726142-384c2980-1acf-11eb-8b53-32e2fb9b7d9e.png)

ako vazi

![image](https://user-images.githubusercontent.com/45834270/97725849-ee634380-1ace-11eb-8fa8-642a3231cfdc.png)


(grozna formula, bolje je ova **koristna teorema** ispod tj. laksi nacin je taj gde pravimo projekcije i onda te projekcije spajamo, ako za to spajanje dobijemo citav r to znaci da je zadovoljena zavisnost spoja )



## Koristna teorema

Spoj nad projekcijama treba da nam da citav r, ako dobijemo citav r onda vazi zavisnost spoja.
 
 <img src="https://user-images.githubusercontent.com/45834270/97726929-0f786400-1ad0-11eb-920a-9b073ba20415.png">
 
 
 <details>
 
 <summary> Primer </summary>
 
 #### Proveriti da li vazi zavisnost spoja (AB, BC, CD)
 
 Napravili smo projekcije za AB, BC, CD potom ih sve spojili (svejedno je kojim redom, zbog komutativnosti prirodnog spoja), posto smo od tih projekcija dobili r. Zakljucujemo da vazi zavisnosti spoja za (AB, BC, CD).
 
 ![image](https://user-images.githubusercontent.com/45834270/97747301-0ac1a900-1aec-11eb-8b43-31d398967f0b.png)

 
 </details>

## Test pitanja

<details>
 <summary> Pitanje-1 </summary>
 </br>
 
 Kako proveriti da li neka relacija zadovoljava zavisnost spoja x1,x2,x3.
 
 </details>
 
 <details>
 <summary> Odgovor-1 </summary>
 </br>
 
 Tako sto cemo proveriti da li spojevi projekcija daju r. Pogledati koristnu teoremu iznad. Znaci :
  - napravimo projekcije nase polazne relacije na svaku komponentu zavisnosti spoja
  - onda ih spojimo
  - ako dobijemo polaznu relaciju r onda je zavisnost spoja zadovoljena.
 
 </details>

<details>
 <summary> Pitanje-2 </summary>
 </br>
 
 Kako dopuniti nasu relaciju ako ona ne zadovoljava zavisnost spoja da bi je zadovoljavala ?
 
 </details>
 
 <details>
 <summary> Odgovor-2 </summary>
 </br>

Isto kao u odgovoru 1:
 - napraviti projekcije za svaku komponentu spoja
 - spojiti te projekcije 
 - dodati one torke koje fale. 
 
 </details>
 
</br></br></br>



# Novo gradivo

## Osnovni projektantski kriterijumi

 - **K1**: Ne smemo gubiti i dobijati obelezja 'usput'. Obelezja ce postojati i gubiti se, ali u **postupku projektovanja** to ne sme da se dogodi. Sto znaci da projektant sme da zada drugaciji ulaz ali algoritam sam po sebi ne sme biti falican, odnosno, unutar njega se ne smeju menjati obelezja. Tacnije ako je na ulazu jedan skup obelezja i na izlazi mora biti isti skup obelezja.
 
 - **K2**: Prirodnim spojem svih nasih relacija nase relacione baze podataka zelimo da nadoknadimo tacno nasu polaznu univerzalnu relaciju a to u zivotu i nije bas moguce. Ovo je jedan idealizovan kriterijum o kome cemo takodje brinuti.
 
 - **K3**: Onako kako smo ocuvavali nas polazni skup obelezja, tako smo i u obavezi da ocuvamo nas polazni skup ogranicenja. Nasa Sema BP (S, I) u S sadrzi skup sema relacija a u I sadrzi skup medjurelacionih ogranicenja. To znaci da ce nas postupak projektovanja relacione seme baze podataka transformisati nas polazni skup ogranicenja na nacin da nas dovede do lokalnih ogranicenja svih nasih sema relacija to su skupovi Oi, ako svaku semu relacije posmatramo (Ri, Oi) gde je Oi njen skup ogranicenja, onda kada uniramo sva ogranicenja iz lokalnih skupova ogranicenja nasih sema relacija i kada tome pridodamo(uniramo) i nas skup medjurelacionih ogranicenaj I, mi moramo u logickom smislu ocuvati ekvivaletnost sa nasim polaznim skupom ogranicenja.
 ![image](https://user-images.githubusercontent.com/45834270/97714732-d2a57080-1ac1-11eb-83d6-2f2bce5d426d.png) 
 Ocuvati medjusobnu ekvivalentnost znaci samo da sve sto moze da se izvede iz jednog skupa ogranicenja moze da se izvede onda iz drugog i obratno( sve sto moze iz drugog da se izvede onda moze i iz prvog).

- **K4**: Sve anomalije azuriranja trebaju biti uklonjene

### Napomena

Sva cetri kriterijuma u praksi nisu uvek zadovoljena

## Spojivost bez gubitaka

Kada uzmemo jednu relaciju nad nekim skupom obelezja i napravimo projekciju nad jednim podskupom i projekciju nad drugim podskupom(unija ta dva podskupa je orginalni skup), njihov prirodni spoj treba da vrati celu univerzalnu realciju. Ako se to desilo i ako nemamo visak torki, onda imamo **spojivost bez gubitaka**.

