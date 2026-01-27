## TrackMate projekt terv


## Projektleírás
A TrackMate célja, hogy egy modern, könnyen használható, naptár-alapú követő alkalmazást biztosítson azok számára, akik szeretnék rendszerezni és nyomon követni mindennapi tevékenységeiket.
A rendszer a felhasználók három fő területét támogatja:

pénzügyi kiadások és bevételek rögzítése,

napi rutinok kezelése,

hangulat monitorozása.




A TrackMate Firebase-alapú backendjének köszönhetően az adatok valós időben frissülnek, több eszközön keresztül is azonnal szinkronizálódnak.
A felhasználók saját személyes profiljuk alatt vezethetik naplójukat, statisztikákat tekinthetnek meg, és visszanézhetik az időszakokra lebontott aktivitásokat.



A felület egy naptárszerű főnézetből indul ki, ahol minden napra kattintva megtekinthetők a kapcsolódó adatok: rögzített pénzügyi tételek, elvégzett rutinok és hangulat-bejegyzések.
A TrackMate így egy digitális self-monitoring eszközként működik, amely támogatja a felhasználók személyes fejlődését, önismeretét és pénzügyi tudatosságát.


## Frontend: Angular
## Backend: Firebase (Firestore, Authentication, Storage, Hosting)
## Adatbázis: Firebase Firestore
## Weboldal kinézetének megtekintése


## GitHub link: https://github.com/GBence-B/Projekt









## Funkciók
Felhasználói funkciók (bejelentkezés után)
Pénzügyi napló vezetése

Kiadás és bevétel rögzítése

Kategóriák használata (pl. Étel, Utazás, Bevétel stb.)

Napi, heti, havi összegzések

Diagramok és statisztikák

Napi rutinok kezelése

Rutinok létrehozása (pl. edzés, olvasás, tanulás)

Napokhoz rendelés

Teljesítések pipálása

Sikerességi statisztikák megjelenítése

Hangulatkövetés

Napi érzelmi állapot rögzítése (1–5)

Jegyzet hozzáadása

Korábbi napok hangulatának visszanézése

Naptár-alapú megjelenítés

Minden nap külön nézet

Egy helyen látható: pénzügy, rutin, hangulat

Profilkezelés

Név, avatar, alapadatok módosítása

Fiók törlése

Adatok valós idejű mentése Firebase-be








## Komponensek
Bejelentkezés nélkül látható komponensek
homeComponent
Kezdőképernyő a TrackMate rövid bemutatásával.

navbarComponent
Navigációs menüsáv vendégeknek.

loginComponent
Bejelentkezés e-mail/jelszó alapon (Firebase Authentication).

registerComponent
Új felhasználók regisztrációja.

aboutComponent
Információk az alkalmazás működéséről, funkcióiról.

Bejelentkezéssel látható komponensek
Pénzügyi modul
financeListComponent
A felhasználó pénzügyi bejegyzései listázva.

financeDetailsComponent
Egy adott pénzügyi bejegyzés részletei.

addFinanceComponent
Új kiadás/bevétel rögzítése.

Rutin modul
routinesComponent
Felhasználó rutinjainak listája + státusz.

addRoutineComponent
Új rutin létrehozása.

routineDetailsComponent
Egy rutin részletes oldala + naplózás.

Hangulat modul
moodTrackerComponent
Hangulat rögzítése napi bontásban.

moodHistoryComponent
Korábbi hangulatbejegyzések listája.

Naptár modul
calendarViewComponent
A teljes havi nézet, ahová minden adat be van integrálva:

pénzügyi adatok,

rutinok,

hangulat.

dayOverviewComponent
Egy napi összefoglaló nézet (összes modul integrálva).

Profil modul
profileComponent
Felhasználói adatok megtekintése és szerkesztése.

settingsComponent
Preferenciák, értesítések, fiók beállítások.




## ADATBÁZIS TERV(Firebase Firestore)
1. users
{
  "id": "userId",
  "name": "Felhasználó neve",
  "email": "email@example.com",
  "avatar": "storage_url",
  "createdAt": "timestamp"
}
2. finance (users/{userId}/finance)
{
  "type": "expense | income",
  "amount": 3000,
  "category": "Food",
  "note": "Ebéd",
  "date": "2025-11-23"
}
3. routines (users/{userId}/routines)
{
  "title": "Reggeli futás",
  "description": "20 perc kocogás",
  "daysCompleted": ["2025-11-01", "2025-11-02"],
  "createdAt": "timestamp"
}
4. mood (users/{userId}/mood)
{
  "mood": 4,
  "note": "Egész jó nap",
  "date": "2025-11-23"
}
CRUD műveletek Firebase-ben
Felhasználók
regisztráció: Firebase Authentication

bejelentkezés / kijelentkezés

profiladatok módosítása Firestore-ban

profilkép feltöltése Storage-ba

Pénzügyi modul
Művelet	Leírás
CREATE	Új kiadás/bevétel rögzítése
READ	Napi/havi pénzügyek lekérése
UPDATE	Összeg, kategória, leírás módosítása
DELETE	Bejegyzés törlése
Rutin modul
Művelet	Leírás
CREATE	Új rutin felvétele
READ	Rutinok listázása
UPDATE	Teljesített napok módosítása
DELETE	Rutin törlése
Hangulat modul
Művelet	Leírás
CREATE	Hangulat rögzítése egy adott napra
READ	Napi/havi hangulat lekérése
UPDATE	Bejegyzés módosítása
DELETE	Bejegyzés törlése
Firebase szolgáltatások
Authentication – email+password alapú beléptetés

Firestore – NoSQL dokumentum alapú adatbázis

Storage – képek és profilképek tárolása

Hosting – Angular app deployolása

Végpontterv helyett (mivel Firebase REST nélkül működik)
A Firestore műveletek AngularFire-rel történnek, nem külön API-n keresztül.

Példa műveletek:

collection("users").doc(userId).set({...})

collection("users").doc(userId).collection("finance").add({...})

collection("users").doc(userId).collection("routines").update({...})

collection("users").doc(userId).collection("mood").delete()

A Firebase ezért kiváltja a backend REST API-t, nincs Laravel-szerver, nincs MySQL.

