# Bakalarska praca - APTOS-blindness-detection

### Abstrakt ###
Cieľom tejto práce bolo podať teoretický prehľad o metódach hlbokého učenia a jeho využitia v analýze medicínskych dát. Práca popisuje rôzne state-of-the-art prístupy riešenia tejto problematiky ako aj poprednejších metód s využitím (umelých) neurónových sietí. Experimentovalo sa s voľne dostupným datasetom medicínskych obrázkov s použitím konvolučných neurónových sieti, pričom sme využívali programovací jazyk python a prostredie Anaconda - Juniper Notebook.

###Prehľad problematiky###
Diabetická retinopatia je ochorenie sietnice. Označuje sa za sekundárne ochorenie a predstavuje najčastejšiu komplikáciu cukrovky (diabetes mellitus) typu 1. a 2. . Vysoké hodnoty hladiny cukru v krvi poškodzujú jemné krvné cievy v sietnici. Bunky fotoreceptorov sietnice sú týmto nedostatočne zásobené krvou. Bez včasnej liečby môže viesť retinopatia k závažnému poškodeniu oka alebo až k slepote. Rozhodujúca je preto včasná detekcia ochorenia a zabránenie jej progresii.

V súčasnosti sa diagnostika uskutočňuje pomocou fotografie očnej zrenice. Lekársky skríning vyžaduje manuálnu evaluáciu špecialistu a taktiež adekvátne technické vybavenie, čo predstavuje výraznú výzvu v odľahlých častiach sveta. Automatizácia diagnostického procesu založená na hlbokom učení môže dopomôcť k riešeniu tejto problematiky.

###Dataset###
Kaggle databáza umožnuje prístup k množine desiatok tisíc klinických fotografií sietnice oka. Snímky pozostávajú zo zdravých pacientov a pacientov s ochorením diabetickej retinopatie v rôznych štádiach. Všetky snímky boli evaluované kvalifikovaným oftalmológom a označené príslušnou závažnosťou ochorenia. 

Dáta sú prístupné pod linkom: https://www.kaggle.com/c/aptos2019-blindness-detection/data and https://www.kaggle.com/c/diabetic-retinopathy-detection

Za pomoci tejto dátovej množiny sme sa pokúsili vytvoriť pravdepodobnostný systém pre automatickú diagnostiku ochorenia diabetickej retinopatie. Pre vykonané experimenty sme využívali programovací jazyk Python a prostredie Anaconda - Jupiter Notebook. 

