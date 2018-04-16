Valasztas
================
DemocracyGirl
April 11, 2018

Magyar országgyűlési választások elemzése
=========================================

Bevezető
--------

Ez a dokumentum egy elemzés a 2018 április 8-i országgyűlési választások eredményeiről. Az adatokat a <http://valasztasbigdata.tumblr.com> oldalról töltöttem le, és alapvető statisztikai elemzéseket végeztem el rajta.

Adatok beolvasása
-----------------

    ##   MegyeID    Megye OEVK TelepID           Telepules Szavazokor
    ## 2       1 BUDAPEST    1       1 Budapest I. kerület          1
    ## 3       1 BUDAPEST    1       1 Budapest I. kerület          2
    ## 4       1 BUDAPEST    1       1 Budapest I. kerület          3
    ## 5       1 BUDAPEST    1       1 Budapest I. kerület          4
    ## 6       1 BUDAPEST    1       1 Budapest I. kerület          5
    ## 7       1 BUDAPEST    1       1 Budapest I. kerület          6
    ##   egyeni_Nevjegyzekben egyeni_Megjelent egyeni_Atjel..nevj.
    ## 2                 1001              845                  NA
    ## 3                  976              796                  NA
    ## 4                 1030              677                1595
    ## 5                  946              722                  NA
    ## 6                  917              740                  NA
    ## 7                 1007              822                  NA
    ##   egyeni_Atjel..megj. egyeni_Atjel..boritek egyeni_pecset.nelkul
    ## 2                  NA                    NA                    0
    ## 3                  NA                    NA                    0
    ## 4                1513                  1504                    0
    ## 5                  NA                    NA                    0
    ## 6                  NA                    NA                    1
    ## 7                  NA                    NA                    0
    ##   egyeni_pecsettel egyeni_tobblet.hiany egyeni_ervenytelen egyeni_ervenyes
    ## 2              843                   -2                  5             838
    ## 3              793                   -3                  7             786
    ## 4              675                   -2                  5             670
    ## 5              720                   -2                 12             708
    ## 6              739                   -1                  7             732
    ## 7              819                   -3                  6             813
    ##   egyeni_... egyeni_A.HAZA.PARTJA egyeni_AQP egyeni_CIVIL.MOZGALOM
    ## 2         NA                   NA         NA                    NA
    ## 3         NA                   NA         NA                    NA
    ## 4         NA                   NA         NA                    NA
    ## 5         NA                   NA         NA                    NA
    ## 6         NA                   NA         NA                    NA
    ## 7         NA                   NA         NA                    NA
    ##   egyeni_CSP egyeni_DEMOKRATA.PART egyeni_DK egyeni_DMP egyeni_ECDP
    ## 2         NA                    NA        NA         NA          NA
    ## 3         NA                    NA        NA         NA          NA
    ## 4         NA                    NA        NA         NA          NA
    ## 5         NA                    NA        NA         NA          NA
    ## 6         NA                    NA        NA         NA          NA
    ## 7         NA                    NA        NA         NA          NA
    ##   egyeni_EGYUTT egyeni_EMMO egyeni_EP egyeni_ERP egyeni_EU.ALTERNATIVA
    ## 2             0          NA        NA         NA                    NA
    ## 3             0          NA        NA         NA                    NA
    ## 4             0          NA        NA         NA                    NA
    ## 5             0          NA        NA         NA                    NA
    ## 6             0          NA        NA         NA                    NA
    ## 7             0          NA        NA         NA                    NA
    ##   egyeni_EU.ROM egyeni_FIDESZ.KDNP egyeni_FITIP egyeni_FKGP
    ## 2            NA                384           NA          NA
    ## 3            NA                351           NA          NA
    ## 4            NA                323           NA          NA
    ## 5            NA                341           NA          NA
    ## 6            NA                330           NA          NA
    ## 7            NA                361           NA          NA
    ##   egyeni_Fuggetlen.jelolt egyeni_HAJRA.MAGYARORSZAG. egyeni_HAM
    ## 2                      NA                         NA         NA
    ## 3                      NA                         NA         NA
    ## 4                      NA                         NA         NA
    ## 5                      NA                         NA         NA
    ## 6                      NA                         NA         NA
    ## 7                      NA                         NA         NA
    ##   egyeni_HAZA.MINDENKIE egyeni_HHP egyeni_IMA egyeni_IRANYTU egyeni_JMP
    ## 2                    NA         NA         NA             NA         NA
    ## 3                    NA         NA         NA             NA         NA
    ## 4                    NA         NA         NA             NA         NA
    ## 5                    NA         NA         NA             NA         NA
    ## 6                    NA         NA         NA             NA         NA
    ## 7                    NA         NA         NA             NA         NA
    ##   egyeni_JOBBIK egyeni_JO.UT.MPP egyeni_KEDN egyeni_KPP egyeni_KOSSZ
    ## 2            37               NA          NA         NA           NA
    ## 3            43               NA          NA         NA           NA
    ## 4            31               NA          NA         NA           NA
    ## 5            35               NA          NA         NA           NA
    ## 6            31               NA          NA         NA           NA
    ## 7            38               NA          NA         NA           NA
    ##   egyeni_KOZOS.NEVEZO egyeni_LENDULETTEL egyeni_LMP egyeni_MCP
    ## 2                  NA                 NA        392         NA
    ## 3                  NA                 NA        368         NA
    ## 4                  NA                 NA        294         NA
    ## 5                  NA                 NA        308         NA
    ## 6                  NA                 NA        353         NA
    ## 7                  NA                 NA        396         NA
    ##   egyeni_MEDETE.PART egyeni_MINOKP egyeni_MISZEP egyeni_MIEP egyeni_MKKP
    ## 2                 NA            NA            NA          NA          25
    ## 3                 NA            NA            NA          NA          24
    ## 4                 NA            NA            NA          NA          22
    ## 5                 NA            NA            NA          NA          24
    ## 6                 NA            NA            NA          NA          18
    ## 7                 NA            NA            NA          NA          18
    ##   egyeni_MMM egyeni_MODERN.MAGYARORSZAG.MOZGALOM..MOMA. egyeni_MOMENTUM
    ## 2         NA                                         NA               0
    ## 3         NA                                         NA               0
    ## 4         NA                                         NA               0
    ## 5         NA                                         NA               0
    ## 6         NA                                         NA               0
    ## 7         NA                                         NA               0
    ##   egyeni_MSZP.PARBESZED egyeni_MUNKASPART egyeni_MVMP egyeni_NEEM
    ## 2                     0                NA          NA          NA
    ## 3                     0                NA          NA          NA
    ## 4                     0                NA          NA          NA
    ## 5                     0                NA          NA          NA
    ## 6                     0                NA          NA          NA
    ## 7                     0                NA          NA          NA
    ##   egyeni_NEMZET.ES.BEKE egyeni_NEMZETI.ZOLDEK egyeni_NOP egyeni_NP
    ## 2                    NA                    NA         NA        NA
    ## 3                    NA                    NA         NA        NA
    ## 4                    NA                    NA         NA        NA
    ## 5                    NA                    NA         NA        NA
    ## 6                    NA                    NA         NA        NA
    ## 7                    NA                    NA         NA        NA
    ##   egyeni_OCP egyeni_OP egyeni_OPRE.ROMA egyeni_REND.PART egyeni_SEM
    ## 2         NA        NA               NA               NA         NA
    ## 3         NA        NA               NA               NA         NA
    ## 4         NA        NA               NA               NA         NA
    ## 5         NA        NA               NA               NA         NA
    ## 6         NA        NA               NA               NA         NA
    ## 7         NA        NA               NA               NA         NA
    ##   egyeni_SZEM.PART egyeni_SZP egyeni_TAMP egyeni_EBMP
    ## 2               NA         NA          NA          NA
    ## 3               NA         NA          NA          NA
    ## 4               NA         NA          NA          NA
    ## 5               NA         NA          NA          NA
    ## 6               NA         NA          NA          NA
    ## 7               NA         NA          NA          NA
    ##   egyeni_ERTUNK.ERTETEK egyeni_UMF orszagos_nevjegyzekben
    ## 2                    NA         NA                   1000
    ## 3                    NA         NA                    976
    ## 4                    NA         NA                   1028
    ## 5                    NA         NA                    946
    ## 6                    NA         NA                    915
    ## 7                    NA         NA                   1006
    ##   orszagos_megjelent orszagos_pecset.nelkuli.lap orszagos_pecsetelt.lap
    ## 2                844                           0                    843
    ## 3                796                           0                    796
    ## 4                675                           0                    676
    ## 5                722                           0                    721
    ## 6                739                           0                    739
    ## 7                821                           0                    820
    ##   orszagos_tobblet.hiany orszagos_ervenytelen orszagos_ervenyes
    ## 2                     -1                    7               836
    ## 3                      0                    4               792
    ## 4                      1                   16               660
    ## 5                     -1                    8               713
    ## 6                      0                    6               733
    ## 7                     -1                    2               818
    ##   orszagos_CSALADOK.PARTJA orszagos_DEMOKRATIKUS.KOALICIO
    ## 2                        1                             33
    ## 3                        1                             49
    ## 4                        0                             42
    ## 5                        2                             59
    ## 6                        1                             43
    ## 7                        0                             47
    ##   orszagos_EGYUTT...A.KORSZAKVALTOK.PARTJA
    ## 2                                       24
    ## 3                                       15
    ## 4                                       11
    ## 5                                       12
    ## 6                                       28
    ## 7                                       25
    ##   orszagos_EUROPAI.ROMA.KERESZTENYEK.JOBBLETEERT.DEMOKRATIKUS.PART
    ## 2                                                                0
    ## 3                                                                0
    ## 4                                                                0
    ## 5                                                                0
    ## 6                                                                0
    ## 7                                                                0
    ##   orszagos_FIDESZ...KDNP orszagos_IRANYTU.PART
    ## 2                    382                     0
    ## 3                    350                     0
    ## 4                    318                     0
    ## 5                    336                     0
    ## 6                    323                     0
    ## 7                    361                     1
    ##   orszagos_JOBBIK.MAGYARORSZAGERT.MOZGALOM
    ## 2                                       61
    ## 3                                       74
    ## 4                                       44
    ## 5                                       47
    ## 6                                       46
    ## 7                                       66
    ##   orszagos_KELL.AZ.OSSZEFOGAS.PART orszagos_KOZOS.NEVEZO.2018
    ## 2                                0                          0
    ## 3                                0                          0
    ## 4                                1                          0
    ## 5                                0                          0
    ## 6                                0                          1
    ## 7                                0                          0
    ##   orszagos_LEHET.MAS.A.POLITIKA orszagos_MAGYAR.IGAZSAG.ES.ELET.PARTJA
    ## 2                           116                                      0
    ## 3                           117                                      0
    ## 4                            81                                      0
    ## 5                           108                                      0
    ## 6                           104                                      0
    ## 7                           131                                      1
    ##   orszagos_MAGYAR.KETFARKU.KUTYA.PART orszagos_MAGYAR.MUNKASPART
    ## 2                                  27                          2
    ## 3                                  23                          1
    ## 4                                  26                          0
    ## 5                                  21                          3
    ## 6                                  25                          1
    ## 7                                  27                          1
    ##   orszagos_MAGYAR.SZOCIALISTA.PART....PARBESZED.MAGYARORSZAGERT
    ## 2                                                           115
    ## 3                                                           107
    ## 4                                                            96
    ## 5                                                            80
    ## 6                                                            98
    ## 7                                                           103
    ##   orszagos_MAGYARORSZAGI.CIGANYPART
    ## 2                                 0
    ## 3                                 0
    ## 4                                 0
    ## 5                                 0
    ## 6                                 0
    ## 7                                 0
    ##   orszagos_MAGYARORSZAGON.ELO..DOLGOZO.ES.TANULO..EMBEREK.PARTJA
    ## 2                                                              0
    ## 3                                                              0
    ## 4                                                              0
    ## 5                                                              0
    ## 6                                                              0
    ## 7                                                              0
    ##   orszagos_MOMENTUM.MOZGALOM orszagos_NET.PART
    ## 2                         72                 0
    ## 3                         55                 0
    ## 4                         41                 0
    ## 5                         44                 0
    ## 6                         60                 0
    ## 7                         53                 0
    ##   orszagos_REND.ES.ELSZAMOLTATAS.PART
    ## 2                                   1
    ## 3                                   0
    ## 4                                   0
    ## 5                                   1
    ## 6                                   0
    ## 7                                   0
    ##   orszagos_SPORTOS.ES.EGESZSEGES.MAGYARORSZAGERT.PART
    ## 2                                                   2
    ## 3                                                   0
    ## 4                                                   0
    ## 5                                                   0
    ## 6                                                   3
    ## 7                                                   2
    ##   orszagos_SZEGENY.EMBEREK.MAGYARORSZAGERT.PART
    ## 2                                             0
    ## 3                                             0
    ## 4                                             0
    ## 5                                             0
    ## 6                                             0
    ## 7                                             0
    ##   orszagos_TENNI.AKARAS.MOZGALOM orszagos_OSSZEFOGAS.PART
    ## 2                              0                        0
    ## 3                              0                        0
    ## 4                              0                        0
    ## 5                              0                        0
    ## 6                              0                        0
    ## 7                              0                        0
    ##   nemzetisegi_nevjegyzekben nemzetisegi_megjelent
    ## 2                         1                     1
    ## 3                        NA                    NA
    ## 4                         2                     2
    ## 5                        NA                    NA
    ## 6                         2                     1
    ## 7                         1                     1
    ##   nemzetisegi_pecset.nelkuli.lap nemzetisegi_pecsetelt.lap
    ## 2                              0                         1
    ## 3                             NA                        NA
    ## 4                              0                         2
    ## 5                             NA                        NA
    ## 6                              0                         1
    ## 7                              0                         1
    ##   nemzetisegi_tobblet.hiany nemzetisegi_ervenytelen nemzetisegi_ervenyes
    ## 2                        NA                      NA                    1
    ## 3                        NA                      NA                   NA
    ## 4                         0                       0                    2
    ## 5                        NA                      NA                   NA
    ## 6                        NA                      NA                    1
    ## 7                        NA                      NA                    1
    ##   nemzetisegi_Bolgar nemzetisegi_Gorog nemzetisegi_Horvat
    ## 2                 NA                NA                 NA
    ## 3                 NA                NA                 NA
    ## 4                 NA                NA                  1
    ## 5                 NA                NA                 NA
    ## 6                  0                NA                 NA
    ## 7                 NA                NA                 NA
    ##   nemzetisegi_Lengyel nemzetisegi_Nemet nemzetisegi_Roma nemzetisegi_Roman
    ## 2                   1                NA               NA                NA
    ## 3                  NA                NA               NA                NA
    ## 4                  NA                 1               NA                NA
    ## 5                  NA                NA               NA                NA
    ## 6                  NA                NA               NA                NA
    ## 7                  NA                 1               NA                NA
    ##   nemzetisegi_Ruszin nemzetisegi_Szerb nemzetisegi_Szlovak
    ## 2                 NA                NA                  NA
    ## 3                 NA                NA                  NA
    ## 4                 NA                NA                  NA
    ## 5                 NA                NA                  NA
    ## 6                 NA                NA                  NA
    ## 7                 NA                NA                  NA
    ##   nemzetisegi_Szloven nemzetisegi_Ukran nemzetisegi_Ormeny
    ## 2                  NA                NA                 NA
    ## 3                  NA                NA                 NA
    ## 4                  NA                NA                 NA
    ## 5                  NA                NA                 NA
    ## 6                  NA                NA                  1
    ## 7                  NA                NA                 NA

Választókerületen belüli eltérések elemzése
-------------------------------------------

A megye és az OEVK változók kombinációjából létrehozok egy-egy teljesen független választókerületet jelölő változót. Majd létrehozok egy új oszlopot, ami a külön szavaz szavazóköröknek ad egy unique id-t.

``` r
vdata$valker_id<-paste(vdata$Megye,vdata$OEVK)
#Szavazokor ID, kesobb hasznaljuk a bizottsagi tagok tablaval valo egyesitesben
vdata$szavkor_id<-ifelse(vdata$Megye=="BUDAPEST",paste("BUDAPEST",vdata$TelepID,vdata$Szavazokor), paste(iconv(toupper(vdata$Telepules),to='ASCII//TRANSLIT'),vdata$Szavazokor))
```

Ellenőrizzük, hogy tényleg 106 választókerület jött ki.

``` r
table(vdata$valker_id) %>% nrow()
```

    ## [1] 106

A lentebbi grafikonon az látható, hogy egy-egy független választükerületben hány szavazókör van. Ahogy láthatjuk, egyetlen kirívó választókerület van, ahol több, mint 200 db szavazókör van. Ez a kirívóan fregmentált választókerület a Baranya megyei 4-es választókerület, ahova 225 szavazókör tartozik. Országosan átlagosan 97 szavazókör tartozik egy választókerülethez.

![](Valasztas_files/figure-markdown_github/unnamed-chunk-2-1.png)

    ## [1] 97.0283

    ## # A tibble: 1 x 1
    ##   valker_id
    ##       <chr>
    ## 1 BARANYA 4

Érdekes megvizsgálni, hogy egy-egy választókerülethez hány ember tartozik. A lenti hisztogram mutatja az eloszlást, és azt, hogy átlagosan egy választókerülethez 72000 ember tartozik. Ebből kiugró egy 90000 fő felett számláló választókerület, méghozzá PEST 5.

![](Valasztas_files/figure-markdown_github/unnamed-chunk-3-1.png)

    ## [1] 72410.04

    ## # A tibble: 6 x 2
    ##   valker_id count
    ##       <chr> <int>
    ## 1    PEST 2 87203
    ## 2    PEST 3 85287
    ## 3    PEST 5 91122
    ## 4    PEST 6 85531
    ## 5    PEST 7 85943
    ## 6    PEST 8 86549

Vizsgáljuk meg, hogy egy választókerületen belül milyen eltérések vannak az egyes szavazókörök eredményei között. Homogének a szavazókörök? Tételezzük fel, hogy egy választókerületen belül az adott FIDESZ-es politikus minden egyes szavazókörben ugyanannyira szimpatikus. Így minden szavazókörben a szavazatok ugyannyi százalékát kellene kapnia a statisztikai hibahatáron belül mozogva.

Létrehozok egy új változót, ami az adott szavazókörön belüli FIDESZ egyéni szavazatok százalékos arányát mutatja.

Majd létrehozok egy táblázatot, ami az adott teljes választókerületen belül összesíti az érvényes egyéni szavazatok számát, a FIDESZ-re leadott egyéni szavazatok számát, és így a FIDESZ egyéni szavazatok százalékos arányát. Egy külön oszlopban tartom számon a választókerületen belüli szavazókörök FIDESZ-re szavazás arányának szórását (standard deviation).

Csinálok egy új táblát, amiben benne van a választókerület, az adott szavazókörben hány százalékos volt a FIDESZ támogatottsága, és az adott teljes választókerületben átlagosan hány százalékos volt a FIDESZ támogatottság, és mennyi volt ennek a támogatottságnak a választókerületen belüli szórása.

Gyanús esetek és anomáliák
--------------------------

Flageljuk meg azokat a szavazóköröket, amiknél gyanúsan magas a FIDESZ-es egyéni jelöltre szavazók aránya. Ez azt jelenti, hogy olyan szavazóköröket keresünk, ahol legalább három szórásnyival többen szavaztak a FIDESZ-re, mint átlagosan a teljes választókerületben. Ez statisztikailag az esetek 0.1%-ban fordulhatna elő

Mivel 10000 szavazókör van, ha normál eloszlást mutatna a választókerületeken belüli szavazatok megoszlása, akkor körülbelül 10 ilyen esetnek kellene előfordulnia. Ezzel szemben 60 ilyen kerület van. Ez lehet természetesen azért, mert a szavazóköröket szándékosan így alakították ki, de utalhat helyi szinten "abnormális" mértékű FIDESZ szavazó mozgósításra.

    ##                 valker_id           szavkor_id
    ## 1             BUDAPEST 13       BUDAPEST 16 54
    ## 2               BARANYA 2            BERKESD 1
    ## 3               BARANYA 2       KOVAGOSZOLOS 2
    ## 4               BARANYA 2            PEREKED 1
    ## 5               BARANYA 4              PISKO 1
    ## 6                 BÉKÉS 2           SZARVAS 17
    ## 7                 BÉKÉS 4          OROSHAZA 37
    ## 8                 BÉKÉS 4      PUSZTAOTTLAKA 2
    ## 9  BORSOD-ABAÚJ-ZEMPLÉN 1         ALSOZSOLCA 3
    ## 10 BORSOD-ABAÚJ-ZEMPLÉN 1         ALSOZSOLCA 5
    ## 11 BORSOD-ABAÚJ-ZEMPLÉN 3               OZD 29
    ## 12 BORSOD-ABAÚJ-ZEMPLÉN 3       TORNANADASKA 1
    ## 13 BORSOD-ABAÚJ-ZEMPLÉN 4                FAJ 1
    ## 14 BORSOD-ABAÚJ-ZEMPLÉN 5        FELSOREGMEC 1
    ## 15 BORSOD-ABAÚJ-ZEMPLÉN 6           KISCSECS 1
    ## 16             CSONGRÁD 1         KLARAFALVA 1
    ## 17             CSONGRÁD 1        TISZASZIGET 2
    ## 18                FEJÉR 4              ERCSI 6
    ## 19                FEJÉR 4              ERCSI 8
    ## 20    GYOR-MOSON-SOPRON 3            VADOSFA 1
    ## 21    GYOR-MOSON-SOPRON 4             SARROD 1
    ## 22    GYOR-MOSON-SOPRON 5           CAKOHAZA 1
    ## 23    GYOR-MOSON-SOPRON 5          RABCAKAPI 1
    ## 24          HAJDÚ-BIHAR 1         DEBRECEN 115
    ## 25          HAJDÚ-BIHAR 2          DEBRECEN 26
    ## 26          HAJDÚ-BIHAR 3          NYIRADONY 8
    ## 27          HAJDÚ-BIHAR 6     BALMAZUJVAROS 17
    ## 28                HEVES 1          KERECSEND 2
    ## 29                HEVES 1              KOMLO 2
    ## 30                HEVES 2             SZAJLA 1
    ## 31                HEVES 3              HEVES 9
    ## 32 JÁSZ-NAGYKUN-SZOLNOK 1          TISZAJENO 2
    ## 33 JÁSZ-NAGYKUN-SZOLNOK 3            TISZABO 1
    ## 34 JÁSZ-NAGYKUN-SZOLNOK 3            TISZABO 2
    ## 35 JÁSZ-NAGYKUN-SZOLNOK 3          TISZABURA 2
    ## 36 JÁSZ-NAGYKUN-SZOLNOK 4          TISZAKURT 2
    ## 37    KOMÁROM-ESZTERGOM 1          TATABANYA 4
    ## 38    KOMÁROM-ESZTERGOM 1          TATABANYA 5
    ## 39    KOMÁROM-ESZTERGOM 2               EPOL 1
    ## 40                 PEST 7            VECSES 10
    ## 41                 PEST 8          MAJOSHAZA 1
    ## 42                 PEST 9               DANY 4
    ## 43                 PEST 9               TURA 2
    ## 44                PEST 11              BUGYI 6
    ## 45               SOMOGY 1            GALOSFA 1
    ## 46               SOMOGY 1             HAJMAS 1
    ## 47               SOMOGY 1          KAPOSVAR 55
    ## 48               SOMOGY 1 SZILVASSZENTMARTON 1
    ## 49               SOMOGY 3           PALMAJOR 1
    ## 50               SOMOGY 3          SOMOGYVAR 3
    ## 51               SOMOGY 4             ECSENY 1
    ## 52               SOMOGY 4             KAZSOK 1
    ## 53                  VAS 1              BUCSU 1
    ## 54                  VAS 1         HORVATLOVO 1
    ## 55                  VAS 1              NARDA 1
    ## 56                  VAS 1       VASKERESZTES 1
    ## 57                  VAS 2             SARVAR 5
    ## 58             VESZPRÉM 3            HOSZTOT 1
    ## 59             VESZPRÉM 4             ISZKAZ 1
    ## 60             VESZPRÉM 4           KISPIRIT 1

    ## [1] 60

Ezeket a gyanús szavazóköröket rárakva egy grafikonra a választókerületen belüli többi szavazókör eredményeivel együtt:

    ## Warning: Removed 38 rows containing non-finite values (stat_bin).

![](Valasztas_files/figure-markdown_github/unnamed-chunk-7-1.png)

Hasonlóan megvizsgálhatjuk azokat a szavazóköröket, ahol a várhatónál kevesebben szavaztak a FIDESZ-re. Tehát legalább - a választókerületen belüli - három szórásnyival kevesebben szavaztak itt a FIDESZ-re, mint az átlag. Ilyen kerületból 6 db van.

    ## [1] 6

A választási bizottság összetétele
----------------------------------

Vessük össze a fentieket azzal, hogy milyen volt a választási bizottság összetétele.

Ellenőrizzük, hogy egy választási bizottságban átlagosan hány szavazatszámláló, illetve választási bizottsági tag van. (3,4 fő)

    ## [1] 3.356443

Ebből FIDESZ-es kicsivel több, mint másfél.

    ## [1] 1.591355

Azoknak a szavazóköröknek az aránya, ahol csak FIDESZ-es bizottsági tag van 12%:

    ## [1] 0.120912

Vizsgájuk meg, hogy az előbbi, "gyanúsan magas" FIDESZ szavazókörökben mennyi volt a csak FIDESZ-es bizottsági tag által felügyelt körzet. Összesen 23, ami az összes (60 db) gyanús körzet közel 40%-a!

    ## # A tibble: 1 x 1
    ##       n
    ##   <int>
    ## 1    23

A részrehajlást csökkentendő, csak azokat a választókerületeket nézve, ahol volt legalább egy gyanús szavazókör, ez az arány 14.5%. Tehát megállapítható, hogy a gyanúsan magas arányú FIDESZ szavazatot kapó szavazóköröknél szinte háromszor nagyobb aránnyal fordul elő olyan eset, hogy CSAK FIDESZ-es választási bizottsági tag felügyelte a munkát.

    ##           n
    ## 1 0.1450578

Az előbbi adatokat grafikonon ábrázolva:

![](Valasztas_files/figure-markdown_github/unnamed-chunk-15-1.png)![](Valasztas_files/figure-markdown_github/unnamed-chunk-15-2.png)![](Valasztas_files/figure-markdown_github/unnamed-chunk-15-3.png)

TL;DR
-----

Azokban a szavazókörökben, ahol gyanúsan magas volt a FIDESZ szavazók aránya (az azonos választókerületben lévő többi szavazókörhöz viszonyítva) 3-szor nagyobb eséllyel ült csak FIDESZ-es bizottsági tag.

Egyes esetek megvizsgálása
--------------------------

Végigpörgetve a kirívó eseteket:
\* A BUDAPEST XVI. kerület 54-es szavazókörben a FIDESZ-re egyéni-listás szavazatok száma 459-362, tehát az egyéni-listás FIDESZ szavazatok aránya 1.26. Ezzel szemben a teljes XVI. kerületben ez az arány 1.04, minimális szórással. Szinte biztos, hogy rosszul lettek számolva a szavazatok.
\* Berkesden (Baranya 2) a FIDESZ a listásnál az egyéniben 37%-kal nagyobb támogatottságát (262-191) valószínűleg a 76 mozgósított nemzetiséginek köszönheti, akik közül - bár a nemzetiségi névjegyzékben vannak feltűntetve - 27-en nem szavaztak érvényesen a nemzetiségi listára (2-nek nem is volt lepecsételve a szavazólapja). Itt csak FIDESZ-es volt a bizottsag.
\* Hasonló a helyzet szintén Kővágószőlős 2-n, ahol az arányok 14% (152-133), 18 nemzetiségi, ebből 12 érvényes nemzetiségi listás szavazat (12 roma); valamint Perekeden (70-31), ahol 45 nemzetiségi, 39 ervenyes nemzetisegi listas (30 nemet, 9 roma), es csak FIDESZ-es bizottsag volt.
\* Piskón (Baranya 4) a 139 egyéni és listás érvényes szavazatokkal egyéniben 132-et, listán 132-t tudott behozni a FIDESZ. Ez egyéniben 96%-os támogatottság, míg az egész Baranya 4-ben ez az arány átlagosan 54%. Megjegyzem, ez pont egy olyan szavazókör, ahol csak FIDESZ-es bizottsági tag volt.
\* Alsózsolca 1, 2 és 4-es szavazókörökben a BORSOD 1 választókerülethez hasonlóan a FIDESZ egyéni szavazatok aránya 40% körül van. Ezzel szemben, Alsózsolca 3 és 5 szavazókörökben kiemelkedően magas FIDESZ támogatottság van, 67% és 64%, és a szavazatok szinte kizárólag a Jobbiktól lettek "átcsoportosítva". Ezekben a körzetekben a megjelentek aránya is sokkal alacsonyabb, Alsózsolca 1, 2 és 4-ben 74%, 73%, 71,5%-kal szemben Alsózsolca 3, 5-ben 63% és 59%. Az érvénytelen szavazatok aránya elég magas, Alsózsolca 5-ben például 4%. Erre a jelenségre nem találtam választ...volt többféle pártból is delegált. Van valami demográfiai oka ennek? **Azért is érdekes lenne kideríteni, mert pont BORSOD 1-ben 127 szavazatkülönbséggel nyert csak a FIDESZ.**
\* Szajla 1 és 2 (Heves 2) között is hasonló jellegű a különbség, Szajla 1 szavazókörben 89%-os a FIDESZ támogatottság, míg Szajla 2-ben mindössze 63%. Szajla 1-ben és 2-ben is csak FIDESZ-es volt egyébként a szavazatszámláló bizottság tagja.
\* ... Sajnos idő hiányában nem tudom a többi "gyanús" szavazókört átnézni.
