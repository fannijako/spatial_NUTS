# spatial_NUTS
Területi súlymátrixok NUTS 1, 2, 3 szinteken
A tanulmány és a referencia definíciók elérhetőek az alábbi linken.

**Elsőfokú szomszédság**

A 3. definíció által adott szomszédsági mátrix. A közös határ definícióját a régiókat leíró multipoligonok közös pontja mellett a Csalagút, az  Øresund híd és a Messina-híd adja. Abban az esetben, ha a régió területe nem összefüggő, azaz leírásához egynél több poligonra van szükség, minden poligon által alkotott közös határszakasz számít.


**Másodfokú szomszédság**

A 4. definíció által adott szomszédsági mátrix _n = 2_ esetén, ahol a referencia bináris szomszédságmátrixot az előző területi súlymátrix adja.


**Régióközéppont távolság**

Az 5. definíció által adott inverz távolságalapú súlymátrix, ahol a távolságdefiníció a régiókat reprezentáló multipoligonok mértani középpontjainak légvonalbeli távolsága (_km_) alapján definiált, _c = \infty_ és _n = 1_. Abban az esetben, ha a régió területe nem összefüggő, azaz leírásához egynél több poligonra van szükség, a mértani középpontot a legnagyobb területű poligon mértani középpontjaként definiáltam.


**Közúti távolság az elsődleges szomszédok között kilométerben**

Az 5. definíció által adott inverz távolságalapú súlymátrix, ahol a távolságdefiníció a régiók városai között létrejövő összes párosítás átlagos közúti távolsága kilométerben, valamint _n = 1_. A küszöbtávolság ebben az esetben nem egy _c \in **R^+**_ értékkel, hanem az elsőfokú szomszédság mátrix által adott. A közúti távolság mérésére a Google Maps adatai az irányadóak, melynek letöltését a Google Distance Matrix API segítségével értem el. Abban az esetben, ha valamely régióban nem volt jelentősnek tekinthető város az EUROSTAT adatbázisa alapján, a közúti távolságot a régióközéppont távolsággal helyettesítettem.


**Közúti távolság az elsődleges szomszédok között órában**

Az 5. definíció által adott inverz távolságalapú súlymátrix, ahol a távolságdefiníció a régiók városai között létrejövő összes párosítás átlagos közúti távolsága órában, valamint _n = 1_. A küszöbtávolság ebben az esetben nem egy _c \in **R^+**_ értékkel, hanem az elsőfokú szomszédság mátrix által adott. A közúti távolság mérésére a Google Maps adatai az irányadóak, melynek letöltését a Google Distance Matrix API segítségével értem el. Abban az esetben, ha valamely régióban nem volt jelentősnek tekinthető város az EUROSTAT adatbázisa alapján, a közúti távolságot a régióközéppont távolság órára átváltott értékével helyettesítettem. A közúti adatok alapján az átváltási szorzó 0.01103 NUTS 1-es szinten, 0.01152 NUTS 2-es szinten és 0.0124 NUTS 3-as szinten, mely egybeesik egy 90, 87, valamint 80 km/h-s átlagsebességgel.


**Közúti távolság a másodlagos szomszédok között kilométerben**

Az 5. definíció által adott inverz távolságalapú súlymátrix, ahol a távolságdefiníció a régiók városai között létrejövő összes párosítás átlagos közúti távolsága kilométerben, valamint _n = 1_. A küszöbtávolság ebben az esetben nem egy _c \in **R^+**_ értékkel, hanem a másodfokú szomszédság mátrix által adott. A közúti távolság mérésére a Google Maps adatai az irányadóak, melynek letöltését a Google Distance Matrix API segítségével értem el. Abban az esetben, ha valamely régióban nem volt jelentősnek tekinthető város az EUROSTAT adatbázisa alapján, a közúti távolságot a régióközéppont távolsággal helyettesítettem.


**Közúti távolság a másodlagos szomszédok között órában**

Az 5. definíció által adott inverz távolságalapú súlymátrix, ahol a távolságdefiníció a régiók városai között létrejövő összes párosítás átlagos közúti távolsága órában, valamint _n = 1_. A küszöbtávolság ebben az esetben nem egy _c \in **R^+**_ értékkel, hanem a másodfokú szomszédság mátrix által adott. A közúti távolság mérésére a Google Maps adatai az irányadóak, melynek letöltését a Google Distance Matrix API segítségével értem el. Abban az esetben, ha valamely régióban nem volt jelentősnek tekinthető város az EUROSTAT adatbázisa alapján, a közúti távolságot a régióközéppont távolsággal órára átváltott értékével helyettesítettem.


**Poligonok közötti legrövidebb távolság**

Az 5. definíció által adott inverz távolságalapú súlymátrix, ahol a távolságdefiníció a régiókat leíró multipoligonok pont-pont (standard euklideszi értelemben vett) légvonalbeli távolságainak minimuma, valamint _n = 1_. A küszöbtávolság ebben az esetben _c = 500 km_ értékkel adott. Ebben az esetben a közös határral rendelkező területek távolsága definíciószerűen 0, ezért ezen értékeket 0.5-es érték helyettesíti a súlymátrixban (az inverz távolságok maximális értéke 0.4281113, ezért esett a választás a 0.5-es értékre).


**4-legközelebbi szomszéd**


A 6. definíció által adott K legközelebbi szomszéd alapú területi súlymátrix, ahol _k = 4_, valamint a két régió közötti távolságot a mértani középpontjuk légvonalbeli távolsága adja. Abban az esetben, ha a régió területe nem összefüggő, azaz leírásához egynél több poligonra van szükség, a mértani középpontot a legnagyobb területű poligon mértani középpontjaként definiáltam. 
