# Általános leírás a Lekérdezés típusokról

## Query Types
A JetEngine Query Builder több típusú lekérdezési formát támogat. Egyes típusok csak akkor fognak megjelenni ha a hozzájuk kapcsolódó bővítmény, vagy modul telepítve / aktiválva van. 

### Alapértelmezett lekérdezési típusok

* **Posts query** Bármilyen poszt, és egyedi poszt típust (cpt) lekérhetsz.
* **Terms Query** Kiválasztott egy vagy több taxonómiából kérhetsz le termseket. Támogatja a Meta Query opciót is.
* **Users Query** Felhasználókat tudsz különböző paraméterek alapján lekérni.
* **Comments Query** A WordPress alapértelmezett kommentjeit tudod lekérni többféle paraméter alapján.
* **SQL/AI** Ez egy speciálisabb lekérés, ugyanis lehetőséged van ez által a phpmyadminhoz hasonlóan elérni az adatbázist, azok értékeit és a táblák értékeivel megcisnálni a lekérést, aminek eredményeit utána meg tudod jeleníteni. (pl listing grid stb)
* **Repeater Query** A JetEngine ismétlődő mező rendszeréhez a Repeaterhez készült. Támogatja a post mellett az Options-ban létrehozható Repeater-t is.
* **Current WP Query** Röviden az aktuális WP_Query objektumot örökli, ezért nincs hozzá csak egyetlen beállítási mód. Mivel globális, az oldalon felülírhatják más widgetek lekérését.
* **Merged Query** Ez egy új JetEngine 3.5 megjelent funkció. Azonos típusú lekéréseket tudsz mergelni, azaz lényegében összeadni. (post csak postokkal, CCT csak CCT-el, user csak user el stb).

Más bővítmények általi lekérési típusok:

* **WC Product Query** Amikor termékeket szeretnél listázni ezt használd a Post helyett. Ez specifikus termékekre vonatkozó paraméterekkel rendelkezik.
* 
