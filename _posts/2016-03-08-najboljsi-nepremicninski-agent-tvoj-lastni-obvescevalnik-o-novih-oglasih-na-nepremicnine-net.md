---
layout: 	post
title:  	"Najboljši nepremičninski agent … tvoj lastni obveščevalnik o novih oglasih na nepremicnine.net"
date:   	2016-03-08 08:01:42 +0100
categories:	blogi davorin
author:		davorin
tags:		programiranje, splet, tehnologija, telefonija, nepremičnine, nepremicnine.net
---

Kako si lahko takoj obveščen o novih stanovanjih na nepremicnine.net? Zadnjič sem videl, da nekdo išče dobrega (ta nekdo je bil ([(@barjanski)](https://twitter.com/barjanski/)), zanesljivega agenta za iskanje nepremičnin. Ker sem (smo) stanovanje tudi sami iskali več kot leto dni in ker mi ga je iskalo tudi nebroj agencij / agentov, vam povem kako sem ga našel: **sam**.

Z malo pomočjo RSS-a in IFTTT-ja.

Kako? Beri dalje.

Največji problem nepremicnine.net je ta, da pošilja sporočila o novih ponudbah enkrat na dan, pozno zvečer. In tako se nam je nekajkrat zgodilo, da smo bili prepozni za tistih nekaj ur, … zato sem se odločil, da si bom pomagal s tehnologijo.

Ker nepremicnine.net nimajo RSS feedov, je bilo treba narediti svoj RSS, ki ga je skupi sešpohtlal feed43.com. Ideja je bila, da ob novih oglasih dobim:

* notification na telefon,
* notification na računalnik,
* mejl na moj in ženin mejl, da si lahko ponudbe ogleda tudi boljša polovica.

Kar se tiče nepremičninskih agencij: v letu niso našli primernega stanovanja, čeprav sem nebroj njim povedal, kaj bi rad, kje bi rad, za koliko denarja bi rad in da bi rad to čimprej. Poizkušali so, tega ne bom rekel, a na žalost je vsaki ponudbi nekaj manjkalo.

## Kako si sam svoja nepremičninska agencija?

Če imaš čas, lahko 24/7 visiš na nepremicnine.net in takoj pokličeš, ko vidiš kakšen zanimiv oglas.

Lahko pa dobivaš obvestila na telefon / emajl. A kako?

Najprej si moraš naredit custom XML feed. Jaz sem za scraper iz nepremicnine.net uporabil servis feed43.com.

## Feed43.com za XML feed

Kako si naštimaš svoj feed v temle pastebinu: http://pastebin.com/VyQ08Ebf

Za obrazložitev: štos je da na nepremicnine.net poiščeš nepremičnino po svoji izbiri in ko končaš (koklsobno stanovanje, katera upravna enota, kolk kvadratov, kolk dnarja, bla bla bla, na koncu dobiš en URL v naslovni vrstici, ki ga uporabiš kot osnova scrapeanja na Feed43.

V mojem primeru:

* [3 do 5-sobna stanovanja v Šiški do 174k €](https://www.nepremicnine.net/oglasi-prodaja/ljubljana-mesto/ljubljana-siska/stanovanje/3-sobno,3.5-sobno,4-sobno,4.5-sobno,5-in-vecsobno,apartma,drugo-36/cena-do-174000-eur,velikost-od-68-m2,letnik-od-68/?s=16)

Držiš se navodilom v  Pastebinu, ko je feed narejen, moraš samo naštimat custom akcijo na IFTTT, da ti bo pošiljal mejle / notificiatione / … ko se objavi nov oglas.

## IFTTT

Zdej pa je treba naštimat, da dobivaš obvestila o novih nepremičninah takoj, ko so oglasi objavljeni … (nč se ustrašt, ne bo bolelo – če si si naštimal/a RSS, bo tole mala mal’ca):

* najprej morš skonektat kanale (greš v https://ifttt.com/channels … in tam v Search Channels poiščeš “Gmail” (vtipkej 
* v polje za iskanje) in tudi “IF Notifications” … sam za tega mensezdi, da morš met IF na telefonu inštaliran. Ta korak lahko tut ignoriraš, ti bo že zatežu program ko boš delal/a feed in boš povezal/a servise sproti.

Pol pa gremo nardit en notification recipe:

* klikneš na https://ifttt.com/myrecipes/personal/new (če si že registrirana in logirana, oz greš My Recipes -> Create a Recipe (velk plau gumb, ne morš falit).
	* napiše ti if this then that, klikneš na this (glej korak0.png)
	* izbereš kanal, ki bo trigeral that (Choose Trigger Channel), tu vpišeš RSS in klikneš na Feed ikonco (glej korak1.png)
	* izbereš triger -> klikneš New feed item (glej korak2.png)
	* v Feed URL vpišeš željen XML feed, zgoraj sta linka s končnico .xml, enga po enga, lepo prosim (glej korak3.png)
	* if … then that -> klikneš that (glej korak4.png)
	* izbereš Send an email -> (glej korak5.png)
	* izbereiš naslovnika (To address), ostalo pustiš pr gmh, al se pa zajebavaš, če misliš da znaš (glej korak6.png)
	* pa si na konc … za notificatione morš še kliknt klukco “Recieve notification when recipe runs” … za konc zabombaš še Create recipe in čakaš na nove oglase. 🙂 (glej korak7.png)

Če bi si sam notificatione naštimal/a pa:

* do 4. koraka isto, pol pa vpišeš “notif” in dobiš IF notifications izbiro (glej korak5a.png)
	* izbereš notification opcijo (glej korak6a.png)
* spremeniš sporočilo oz potrdiš kar je … (glej korak7a.png)

No, … to je to. Izi-pizi, mal kliki-kliki, pa je narjen. In boš vedno na tekočem, ker bodo nova stanovanja sama letela v inbox oz v notificatione.

… no, pa smo.

Srečno pri iskanju nepremičnine.