# Query Builder - Posts Query

## Általános leírás
A lista első Query típusa a Posts Query. Ennek segítségével bármilyen poszt típusból kérhetsz le posztokat. Nem számít, hogy egyedi post, vagy alapértelmezett, az sem hogy a jetengine által van-e létrehozva vagy más bővítménnyel. A lekérdezési paramétereket (másnéven argumentumok) különböző tabokba kategorizálták. Megnézzük azokat amik a legfontosabbak az általános használatra.

### Tipp

A Query Builder jobb felső sarkában található egy kapcsoló **Preview results**, ezt kapcsold be. Azért hasznos, mert itt több esetben helyben tudod megnézni az eredményeket, mivel minden változásra reagál. Egyes speciális lekérés esetében nem probléma ha nem ad vissza eredményt. (például specifikus makrós megoldások amik egy bizonyos oldalt igényelnek. De, ha biztosra akarsz menni van preview from page opciója is, amit beállíthatsz a preview modulban.

> [!IMPORTANT]
> WooCommerce esetében ne Posts Query használj, hanem a WC Product Query-t!

### Alapvető Query beállítások

* **Name** Itt tudod megadni a lekérdezésed nevét. Ezt fogod tudni használni amikor be akarod kötni, például a Listing Grid widgetbe, dinamikus címkébe stb.
* **Description** Leírás amit csak a Query builder listázóban fogsz látni. Hasznos ha jegyzetelni szerednéd, mire jó az adott lekérdezésed
* **Query Type** Itt tudod kiválasztani milyen típusú lekérdezést akarsz készíteni.
* **Query ID** Általában a JetSmartfilter esetében javasolt ID megadni, de egyes más esetekben speciális azonosításnál szintén szükséges. Alapvető használatkor nem kell megadni azonosítót.
* **Cache Query** Alapértelmezetten mindig be van kapcsolva, csak ritka esetben érdemes kikapcsolni, például ha az eredmény nem egyezik meg.
* **Register Rest API Endpoint** Akkor kell bekapcsolni ha regisztrálni akarod a lekérésedet a Wp restapi-ba végpontként

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/c07418dd-36e1-43de-9d42-d7740ce04d80)


### General
Itt a legáltalánosabb beállításokat tudjuk megadni.

* **Post Type** - Itt tudod megadni hogy melyik poszt típusokból kerje le a posztokat. Megadhatsz egyet, többet, vagy üresen is hagyhatod, ilyenkor minden elérhető típusból fog dolgozni.
* **Post Status** - A bejegyzés státusza. Szintén egy vagy többet is megadhatsz, de hagyhatod üresen, hogy az összesre érvényes legyen. Például lekérheted csak a publikus bejegyzéseket.
* **Search keyword** - Csak azokat a bejegyzéseket adja vissza aminek címében (title) kivonatában (excerpt), vagy tartalmában (content) talál egyezést. Ha a beírt szó elé - (kötőjelet teszel) azokat kizárja.
* **Order & Order By** - Itt alapértelmezett sorrendeket tudsz beállítani. Fontos hogy ha a Jetsmartfilter-ben használsz Sorting funkciót akkor ezek össze tudnak akadni!

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/3894b691-5181-4f71-bcb6-1362583dafbe)


### Meta Query
Itt tudsz meták alapján módosítani a lekéréseden

Miután rákattintottál az Add new gombra 5 opció jelenik meg:

* **Field key/name** -- Itt kell megadni a meta azonosítót
* **Compare** -- itt tudod az operátort megadni hozzá. Például hogy legyen egyenlő, kissebb, Exist(létezik), stb. Néhány speciálisabb operátor:
  -  Like: Részleges egyezés
  -  In The List: Több érték megadásából legalább egyel egyeznie kell. Ez az IN-nek felel meg.
  -  Regexp: reguláris kifezések. Hasznos bonyolultabb mint keresésekor. Például ha van egy egyedi mező ami tartalmazhat számot, vagy betűket akkor a RegEXP egy jó megoldás: ^[0-9]+[a-zA-Z]+$
* **Value** -- Itt kell megadni az értéket amivel az egyezésnek kell történnie.
* **Type** -- Itt azt határozzuk meg, hogy a tárolt adat amely összehasonlítását végezzük milyen formában van. A leggyakrabban a Char-t használjuk ami a stringet jelenti.

A **Field key/name** és a **Value** esetében is lehetőség van dinamikus értékeket és jetengine makrókat megadni.

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/d4a4b6d4-70a7-4da4-9041-f2467401e777)


### Tax Query
A Posztokat itt tudod különböző Taxonómiák alapján lekérni. 

Miután rákattintottál az Add new gombra 5 opció jelenik meg:

* **Taxonomy** -- Itt tudod kiválasztani melyik Taxonómiából akarod lekérni a posztokat. (itt egyszerre csak egyet választhatsz ki)
* **Field** -- Itt tudod kiválasztani hogy a Terms melyik értékből fogsz adatok megadni. Term ID, Name, Slug, Term Taxonomy ID
* **Terms** -- Itt kell megadni az értékeket. Ha a Field mezőben a SLUG ot állítottad be, úgy a terms keresőbarát nevét kell megadnod, ha ID akkor az azonosító-t. Több érték esetében vesszővel válaszd el. Makrókat is használhatsz.
* **Exclude Childre** -- Alapértelmezetten a child terms ben lévő poszotkat is visszaadja, de ha bekapcsolod, akkor mindig csak a parent terms eket fogja figyelembe enni.
* **Compare operator** -- Itt tudod megadni hogy az összehasonlítási mi legyen, ha kizárni akarsz akkor a listából válaszd a **NOT IN** opciót.

*Extra, ha több Taxonomyból is akarsz dolgozni, miután a másodikat is hozzáadod, alul megjelenik egy Relation opciót, ott tudod megadni hogy több taxonomy esetében mindegyik feltételnek megkell felenie, (AND), vagy valamelyiknek (OR)*

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/cc7bcc41-7c97-4906-b530-889f30a6b362)

### Date Query
Itt a poszthoz tartozó dátum lekéréseket tudjuk megadni amik a létrehozási, módosítási dátumokon alapszik

Miután rákattintottál az Add new gombra 8 opció jelenik meg:

* **Year** -- A megadott évben publikált(/módosított) bejegyzéseket teszi a lekérésbe
* **Month** -- A megadott hónapban (1-12 ig megadható értékkel) publikált(/módosított) bejegyzéseket teszi a lekérésbe
* **Day** -- A hónap megadott napján (1-31 ig megadható értékkel) publikált(/módosított) bejegyzéseket teszi a lekérésbe
* **After** -- Itt megadhatsz fix dátumokat, hogy csak az az utániakat tegye a lekérésbe. Nem csak fix dátumot adhatsz meg hanem relatív értékeket is, például today, tomorrow +1 day stb.
* **Before** -- Az After fordított változata, tehát a megadott dátum előttieket teszi a lekérésbe.
* **Inclusive** -- Ez az After és before paraméterek esetében fontos, ezzel lehet meghatározni, hogy a megadott időszak kezdő dátuma is bele vegye, vagy sem. He be kapcsolod akkor fogja tartalmazni, tehát az érték true lesz.
* **Compare** -- Ez az összehasonolítás amolyan operátor jellegű, hasonlóan ahogy egy Meta Query esetében is van. Ez A Year, Month és Day értékekre értendő.
* **Column** -- Itt tudod kiválasztanmi, hogy a módosítási vagy publikálási dátumot vegye alapul a lekérdezéshez.

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/9b3c943e-c663-4ce7-9c98-33a4ce7d1a74)

### Post & Page
Itt konkrétan tudsz kizárni posztokat is vagy slug alapján, vagy beállítani hogy fixen tartalmazza a lekérés. Az ID és slugokat vessző elválasztással add meg ha többet szeretnél hozzáadni.

Fontosabbak: 

* **Post In** -- Itt ID ket kell megadni, de nem adhatsz meg csak egyetlen egyet. Ha csak egy ID-ről van szó használd a Post ID opciót helyette.
* **Post Not In** -- Az előző fordítottja, tehát olyan posztok amiket ki akarunk zárni. Itt egyet is megadhatsz vagy többet.
* **Post Parent ID** -- Bár hozzá vagyunk szokva ahhoz, hogy a posztokat nem szoktunk az oldalakhoz hasonlóan hierarchikusan kezelni, mivel a CPT ezt támogatja, így lehetőséged van arra, hogy a megadott azonosító alapján a hozzá tartozó összes child posztot is a lekérésbe tegye. Ha 0 értéket írsz be akkor minden olyan poszt, ami parent, de van child eleme, a childek nem kerülnek bele.

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/e7d715e7-0600-4876-b61f-1d7f35e8c0ab)


### Comments
Itt beállíthatod azt, hogy csak olyan posztok kerüljenek be ami például legalább X mennyiségű kommentel rendelkezik.

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/48afcec0-6782-4bce-b049-39db5ff5fd44)

### Pagination
A lapozás a legtöbb query típus esetében elérhető. Itt tudod megadni hogy oldalanként mennyi posztot jelenítsen meg a lekérdezés. Érdekesség, hogy itt tudod a sticky post opciót is kizárni.

* **Posts Per Page** -- A leggyakrabban ezzel a paraméterrel dolgozunk. Itt tudod megadni hogy oldalanként mennyi poszt legyen. Fontos, hogy ennek működéséhez megfelelő widget kell ami ezt támogatja. (például JetSmartFilter). -1 érték esetén az összes posztot vissza adja
* **Offset** -- Ritka esetben használatos. Ha itt adsz meg értéket, annyi posztot ki fog hagyni.

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/34451a0f-4298-430a-86f0-cc65a10b80a8)

### Author
Alap esetben a lekérésünk nem veszi figyelembe, hogy kitől származik a bejegyzés. Ha itt nem adsz meg semmit, akkor a szerzőtől függetlenül meg fognak jelenni a bejegyzések. Ez az Author beállítási rész akkor hasznos, ha a felhasználónak saját profilja van, és ahol szeretnéd visszalistázni csak azokat a posztokat amiket ő töltött fel. A Leggyakrabban az **Author ID** opciót használjuk, és általáb macro-al, például a Queried User ID-el.

![image](https://github.com/Lonsdale201/jetengine-query-builder-segedlet/assets/23199033/3fbe98ec-fecf-433e-a822-17bba5bc05d3)


