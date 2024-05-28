# Query Builder - Post Query

## Általános leírás
A lista első Query típusa a Posts Query. Ennek segítségével bármilyen poszt típusból kérhetsz le posztokat. Nem számít, hogy egyedi post, vagy alapértelmezett, az sem hogy a jetengine által van-e létrehozva vagy más bővítménnyel. A lekérdezési paramétereket (másnéven argumentumokr) különöző tabokba kategorizálták. Megnézzük azokat amik a legfontosabbak az általános használatra.

### Tipp

A Query Builder jobb felső sarkában található egy kapcsoló Preview results, ezt kapcsold be. Azért hasznos, mert itt több esetben helyben tudod megnézni az eredményeket, mivel minden változásra reagál. Egyes speciális lekérés esetében nem probléma ha nem ad vissza eredményt. (például specifikus makrós megoldások amik egy bizonyos oldalt igényelnek. De, ha biztosra akarsz menni van preview from page opciója is, amit beállíthatsz a preview modulban.

> [!IMPORTANT]
> WooCommerce esetében ne Posts Query használj, hanem a WC Product Query-t!

### General
Itt a legáltalánosabb beállításokat tudjuk megadni.
> **Post type**
> Itt tudod megadni hogy melyik poszt típusokból kerje le a posztokat. Megadhatsz egyet, többet, vagy üresne is hagyhatod ilyenkor minden elérhető típusból fog dolgozni.
