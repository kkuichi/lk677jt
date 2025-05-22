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
- `0_cloudy` – zamračená obloha  
- `1_partly` – čiastočne zamračená obloha  
- `2_clear` – jasná obloha  

Cieľom práce bolo navrhnúť a porovnať viaceré modely strojového učenia, so zameraním na konvolučné neurónové siete, a použiť ich na filtrovanie nevhodných snímok pre ďalšie spracovanie v oblasti kozmickej fyziky.

## Štruktúra repozitára

- **BP_v2.ipynb**  
  Hlavný Jupyter notebook, ktorý obsahuje:
  - Načítanie a prípravu datasetu  
  - Rozdelenie dát na trénovaciu, validačnú a testovaciu množinu  
  - Tréning základných referenčných modelov: rozhodovací strom, lineárna regresia a náhodný les  
  - Tréning a vyhodnotenie šiestich modelov konvolučných neurónových sietí (modely A, B, C, D, E, Z)  
  - Vizualizáciu priebehu trénovania a maticu zámen pre jednotlivé modely  

- **Nasadenie.ipynb**  
  Skript pre nasadenie najúspešnejšieho modelu (model B) na nové dáta zo stanice v Novom Zélande. Obsahuje:
  - Načítanie a spracovanie nových snímok  
  - Klasifikáciu a ukladanie obrázkov do priečinkov podľa predpovedanej kategórie  
  - Grafické zobrazenie rozdelenia výstupov podľa tried  

## Dáta a modely

Pre veľkosť súborov sú všetky dáta a natrénované modely uložené na externom úložisku:  
🔗 https://mega.nz/folder/krUSnbaI#hgn61KQfOquD--DgjMZoFw

Dostupné priečinky:

- **data**  
  Obsahuje štyri `.zip` archívy:
  - `0_cloudy.zip`, `1_partly.zip`, `2_clear.zip` – trénovacie a testovacie snímky zo stanice Leoncito  
  - `mt_5727_2019_all (2).zip` – neroztriedené snímky z Nového Zélandu, použité pri nasadení modelu  

- **Modely**  
  Obsahuje šesť predtrénovaných modelov vo formáte `.keras`:  
  `A32,64.keras`, `B32,64,128.keras`, `C32,64,128,256.keras`,  
  `D16,32,64,128.keras`, `E32,64,128.keras`, `Z32,64,128.keras`

> ⚠️ **Poznámka:** Pred použitím je potrebné všetky `.zip` súbory manuálne rozbaliť do príslušných priečinkov, aby skripty mohli správne pracovať s dátami a modelmi.
