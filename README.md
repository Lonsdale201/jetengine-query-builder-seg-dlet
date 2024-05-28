# jetengine-query-builder-segédlet
JetEngine Query Builder leírások, lekérdezések készítése

## Leírás

Ez a segédlet a JetEngine Query Builder-hez készült, ahol szöveges formában magyar nyelven megtanulhatod a jetengine Query Builder használatát, működését. Az egyes mappákban különböző lekérdezési leírásokat találsz, példákkal. MInden típusok példát nem tudok leírni, de sok alapot, és kiegészítőt készítek amiből tudsz informálódni, tanulni.

## Mi az a Query Builder

A JetEngine egyik legfontosabb alapértelmezett modulja, aminek a segítségével, nem csak a Jet saját egyedi poszt típusait, vagy taxonómiát tudod lekérdezni, hanem WooCommerce termékeket, felhasználókat, kommenteket, más bővítmény egyedi poszt típusait, SQL/AI alapú lekrédezsek, Repeater query, Merged Query, Sub Query stb is készíthetsz. A Query Builder gyors, és rengeteg előre elkészített beállítható paramétere van ami alapján a lekérdezéseket módosíthatod, akár dinamikus értékek alapján, ami a JetEngine saját Makró rendszerével működik, és ami fejlesztői irányból is elég rugalmas ahhoz hogy saját kiegészítéseket írjunk Php segítségével. A Query Builder már restAPi kompatibilis is. Korábban a JetEngine lekérdezéseket egy helyen a Listing grid widgetben lehetett csak alkalmazni, ezt váltotta fel az univerzális Query Builder modul, ami jobb, rugalmasabb, és gyorsabb, a szűrőkkel és más megoldásokkal kompatibilis. 

## Lekérdezések

A **Query** azaz **lekérdezés** arra jó, (univerzális értelemben, nem csak a Query Builder-re értendően), hogy paraméterek alapján vissza adj lekéréseket. Ez lehet post, bejegyzéek, cpt bejegyzések, vagy bármi más egyéb.
A JetEngine Query Builder arra ad lehetőséget, hogy ne natívan php-ba írjuk meg, hanem egy rugalmas felületen keresztül mi magunk tudjuk összekattingatni. Az eredményt többféle képpen felhasználhatod. Beállíthatod a JetEngine Listing Grid widgetbe, a Dynamic Table, vagy Chart moduljukba, de dinamikus címkébe eredményként is kiírhatod az eredményt, ami a szűrők hatására (ajax esetében is) változtatja az értéket. Egy korábbi újításnak köszönhetően egyes elementoros Widgetbe, továbbá a Crocoblock saját pluginjeibe is beépített már a Query Builder-t, így akár a JetTabs tabok, és accordion elemeibe a felépítést akár a Query Builder által is elkészítheted. De a JetFormbuilder-be és a jetSmartfilterbe is beépítették már. (Ezekről mind fogsz tudni olvasni itt)
