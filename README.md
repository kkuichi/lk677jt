# Využitie strojového učenia pre filtrovanie dát z kozmickej fyziky
*Bakalárska práca*
### Lukáš Kostár
*Technická univerzita v Košiciach\
Fakulta elektrotechniky a informatiky\
Študijný program: Hospodárska informatika\
Školiace pracovisko: Katedra kybernetiky a umelej inteligencie
Rok: 2024/2025*

## Popis projektu

Táto bakalárska práca sa venuje automatickej klasifikácii celooblohových snímok nočnej oblohy do troch kategórií podľa úrovne oblačnosti:
- `0_cloudy` – zamračená obloha,  
- `1_partly` – čiastočne zamračená obloha,  
- `2_clear` – jasná obloha.  

Cieľom práce bolo navrhnúť a porovnať viaceré modely strojového učenia, so zameraním na konvolučné neurónové siete, a použiť ich na filtrovanie nevhodných snímok pre ďalšie spracovanie v oblasti kozmickej fyziky.

## Štruktúra repozitára

- [`BP_v2.ipynb`](https://github.com/kkuichi/lk677jt/blob/main/BP_v2.ipynb)  
  Hlavný Jupyter notebook, ktorý obsahuje:
  - načítanie a prípravu datasetu, 
  - rozdelenie dát na trénovaciu, validačnú a testovaciu množinu,  
  - tréning základných referenčných modelov: rozhodovací strom, lineárna regresia a náhodný les,  
  - tréning a vyhodnotenie šiestich modelov konvolučných neurónových sietí (modely A, B, C, D, E, Z),  
  - vizualizáciu priebehu trénovania a maticu zámen pre jednotlivé modely.  

- [`Nasadenie.ipynb`](https://github.com/kkuichi/lk677jt/blob/main/Nasadenie.ipynb)  
  Notebook zameraný na nasadenie najúspešnejšieho modelu (model B) na nové dáta zo stanice v Novom Zélande. Obsahuje:
  - načítanie a spracovanie nových snímok,  
  - klasifikáciu a automatické ukladanie obrázkov podľa kategórie,  
  - vizualizáciu rozdelenia výsledkov klasifikácie pomocou stĺpcového grafu.   

## Dáta a modely

Pre veľkosť súborov sú všetky snímky a natrénované modely uložené na externom úložisku:  
https://mega.nz/folder/krUSnbaI#hgn61KQfOquD--DgjMZoFw

Dostupné priečinky:

- **data**  
  Obsahuje štyri `.zip` súbory:
  - `0_cloudy.zip`, `1_partly.zip`, `2_clear.zip` – snímky zo stanice El Leoncito v Argentíne,  
  - `mt_5727_2019_all (2).zip` – neroztriedené snímky z Nového Zélandu, použité pri nasadení modelu.  

- **Modely**  
  Obsahuje šesť predtrénovaných modelov vo formáte `.keras`:  
  `A32,64.keras`, `B32,64,128.keras`, `C32,64,128,256.keras`,  
  `D16,32,64,128.keras`, `E32,64,128.keras`, `Z32,64,128.keras`

## Požiadavky
- Pred použitím je potrebné všetky `.zip` súbory manuálne rozbaliť do príslušných priečinkov, aby skripty mohli správne pracovať s obrázkami.
- Projekt bol vyvíjaný a testovaný s nasledovnými verziami knižníc:
  - `numpy` – 1.26.4  
  - `albumentations` – 1.4.20  
  - `tensorflow` – 2.10.0  
  - `keras` – 2.10.0
