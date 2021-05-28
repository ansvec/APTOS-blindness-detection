# Bakalarska praca - Metódy hlbokého učenia v analýze dát v medicínskej oblasti

### Abstrakt ###
Cieľom tejto práce bolo podať teoretický prehľad o metódach hlbokého učenia a jeho využitia v analýze medicínskych dát. Práca popisuje rôzne state-of-the-art prístupy riešenia tejto problematiky ako aj poprednejších metód s využitím (umelých) neurónových sietí. Experimentovalo sa s voľne dostupným datasetom medicínskych obrázkov s použitím konvolučných neurónových sieti, pričom sme využívali programovací jazyk python a prostredie Anaconda - Juniper Notebook.

### Prehľad problematiky ###
Diabetická retinopatia je ochorenie sietnice. Označuje sa za sekundárne ochorenie a predstavuje najčastejšiu komplikáciu cukrovky (diabetes mellitus) typu 1. a 2. . Vysoké hodnoty hladiny cukru v krvi poškodzujú jemné krvné cievy v sietnici. Bunky fotoreceptorov sietnice sú týmto nedostatočne zásobené krvou. Bez včasnej liečby môže viesť retinopatia k závažnému poškodeniu oka alebo až k slepote. Rozhodujúca je preto včasná detekcia ochorenia a zabránenie jej progresii.

V súčasnosti sa diagnostika uskutočňuje pomocou fotografie očnej zrenice. Lekársky skríning vyžaduje manuálnu evaluáciu špecialistu a taktiež adekvátne technické vybavenie, čo predstavuje výraznú výzvu v odľahlých častiach sveta. Automatizácia diagnostického procesu založená na hlbokom učení môže dopomôcť k riešeniu tejto problematiky.

### Dataset ###
Kaggle databáza umožnuje prístup k množine desiatok tisíc klinických fotografií sietnice oka. Snímky pozostávajú zo zdravých pacientov a pacientov s ochorením diabetickej retinopatie v rôznych štádiach. Všetky snímky boli evaluované kvalifikovaným oftalmológom a označené príslušnou závažnosťou ochorenia (0 - bez DR, 1 - mierna DR, 2 -mierne pokročilá DR, 3 - pokročilá DR, 4 - proliferatívna DR). 

Dáta sú prístupné pod linkom: https://www.kaggle.com/c/aptos2019-blindness-detection/data

Za pomoci tejto dátovej množiny sme sa pokúsili o predikčný model pre atomatizáciu diagnostického procesu diabetickej retinopatie. 
Experimenty boli implementované v prostedí Anaconda - Jupiter notebook prostredníctvom open-source knižníc pre strojové učenie: Keras a Tensorflow.


### Výsledky ###
Závažným problémom pre úspešné riešenie je problematika overfittingu siete. Vzhľadom na nevyvážený súbor údajov je potrebné zvoliť správne predsprocesovanie dát a určiť veľkosť resp. hĺbku neurónovej siete. Výsledkom našich experimentov je CNN s presnosťou 72% a citlivosťou 73% , čo reprodukuje obdobný výstup ako porovnávané štúdie.   

### Prístup ###
1. Analýza dátovej množiny na účely výskumu
3. Predspracovanie obrazu (konverzia na polia, zmena veľkosti)
4. Rozdelenie datasetu 
5. Vytvorenie modelu CNN 
6. Trénovanie modelu
7. Predikcia modelu
8. Evaluácia modelu

### Analýza dátovej množiny na účely výskumu ###
Prístupná dátova množina vykazuje prvky nevyváženého súboru údajov. Najviac zastúpenou triedou sú snímky bez známok DR, teda zdravých pacientov. Súčet zvyšných štyroch tried nedosahuje rovnaký počet dostupných snímok. Fotografie fundusu sa okrem iného vynímajú aj nekonzistentnou kvalitou, rozlíšením, zvýšeným šumom a rôznou úrovňou saturácie obrazu.

### Predspracovanie obrazu ###
Vykonali sme konverziu snímok na polia a zjednotili veľkosť obrazu na rozmer 244x244. 

### Rozdelenie datasetu ###
Dostupnú trénovaciu množinu z kaggle databázy sme v prvom experimente rozdelili stratifikovaným vorkovaním na podmnožinu v pomeroch 80:20, 70:30 a 90:10. Príslúchajúca testovacia podmnožina bola taktiež rozdelená na validačnú s pomerom X : 15. V druhom experimente sme využili augmentáciu dát.

### CNN ###
V experimentoch sme pracovali so sekvenčným modelom konvolučnej neurónovej siete. 

### Trénovanie modelu ###
Nerónovú sieť sme trénovali so zámerom porovnať výkonnosť modelov s rožnym rozdelením dátovej množiny, transformáciou obrázkov z RGB na Grayscale a využitím Gaussian-ovho filtera. V modeli sme využili ako aktivačnú funkciu RELU, optimalizátor ADAM. Nakoľko sa jedná o multiclass klasifikáciu použili sme kategorickú krížovú entropiu ako chybovú funkciu. Tréning CNN prebiehal s batch size 16, s počtom epoch 20 a model checkpointom pre minimálnu validačnú stratu ako aj maximálnu validačnú presnosť.

### Predikcia a evaluácia modelu ###
Najlepší uložený model si možeme importovať a vypísať pravdepodobnostné výsledky tréningu. Predikčný model na báze neurónovej konvolučnej siete je plne funkčný a predstavuje potenciálne riešenie pre automatizáciu diagnostiky ochorenia DR. Predmetom ďalšieho výskumu predstavuje optimalizácia výkonnosti siete ako aj zvýšenie citlivosti predikovaných tried.

