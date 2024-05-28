# Query Builder - Posts Query

## Általános leírás
A lista első Query típusa a Posts Query. Ennek segítségével bármilyen poszt típusból kérhetsz le posztokat. Nem számít, hogy egyedi post, vagy alapértelmezett, az sem hogy a jetengine által van-e létrehozva vagy más bővítménnyel. A lekérdezési paramétereket (másnéven argumentumokr) különöző tabokba kategorizálták. Megnézzük azokat amik a legfontosabbak az általános használatra.

### Tipp

A Query Builder jobb felső sarkában található egy kapcsoló Preview results, ezt kapcsold be. Azért hasznos, mert itt több esetben helyben tudod megnézni az eredményeket, mivel minden változásra reagál. Egyes speciális lekérés esetében nem probléma ha nem ad vissza eredményt. (például specifikus makrós megoldások amik egy bizonyos oldalt igényelnek. De, ha biztosra akarsz menni van preview from page opciója is, amit beállíthatsz a preview modulban.

> [!IMPORTANT]
> WooCommerce esetében ne Posts Query használj, hanem a WC Product Query-t!

### Alapvető Query beállítások

* **Name** Itt tudod megadni a lekérdezésed nevét. Ezt fogod tudni használni amikor be akarod kötni, például a Listing Grid widgetbe, dinamikus címkébe stb.
* **Description** Leírás amit csak a Query builder listázóban fogsz látni. Hasznos ha jegyezetlni szerednéd, mire jó az adott lekérdezésed
* **Query Type** Itt tudod kiválasztani milyen típusú lekérdezést akarsz készíteni.
* **Query ID** Kifejezetten a JetSmartfilter esetében van szükség. Alapvetően nem kell megadnod semmilyen értéket sem, ha nem fogod szűrni a lekérésedet a JSF által
* **Cache Query** Alapértelmezetten mindig be van kapcsolva, csak ritka esetben érdemes kikapcsolni, például ha az eredmény nem egyezik meg.
* **Register Rest API Endpoint** Akkor kell bekapcsolni ha regisztrálni akarod a lekérésedet a Wp restapi-ba végpontként

### General
Itt a legáltalánosabb beállításokat tudjuk megadni.

* **Post Type** - Itt tudod megadni hogy melyik poszt típusokból kerje le a posztokat. Megadhatsz egyet, többet, vagy üresen is hagyhatod ilyenkor minden elérhető típusból fog dolgozni.
* **Post Status** - A bejegyzés státusza. Szintén egy vagy többet is megadhatsz, de hagyhatod üresen, hogy az összesre érvényes legyen. Például lekérheted csak a publikus bejegyzéseket.
* **Search keyword** - Csak azokat a bejegyzéseket adja vissza aminek címében (title) kivonatában (excpert), vagy tartalmában (Content) talál egyezést. Ha a beért szó elé - (kötőjelet tesztel) azokat kizárja.
* **Order & Order By** - Itt alapértelmezett sorrendeket tudsz beállítani. Fontos hogy ha a Jetsmartfilter-ben használsz Sorting funkciót akkor ezek össze tudnak akadni!

### Meta Query
Itt tudsz meták alapján módosítani a lekéréseden

Miután rákatitntottál az Add new gombra 5 opció jelenik meg:

* **Field key/name** Ez a meta azonosítója.
* **Compare** itt tudod az operátport megadni hozzá. Például hogy legyen egyenlő, kisebb, Exist(létezik), stb. Néhány speciálisabb operátor
  -  Like: Részleges egyezés
  -  In The List: Több érték megadásából legalább egyel egyeznie kell. Ez az IN-nek felel meg.
  -  Regexp: reguláris kifezések. Hasznos bonyolultabb mint keresésekor. Például ha van egy egyedi mező ami tartalmazhat számot, vagy betűket akkor a RegEXP egy jó megoldás: ^[0-9]+[a-zA-Z]+$
* **Value** Itt kell megadni az értéket amivel az egyezésnek kell történnie.
* **Type** Itt azt határozzuk meg, hogy a tárolt adat amely összehasonlítását végezzük milyen formában van. A leggyakrabban a Char-t használjuk ami a stringet jelenti.

A **Field key/name** és a **Value** esetében is lehetőség van dinamikus értékeket és jetengine makrókat megadni.

