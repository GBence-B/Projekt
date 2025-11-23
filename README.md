                                                                                TrackMate projekt terv


Projektleírás
A TrackMate célja, hogy egy modern, könnyen használható, naptár-alapú követő alkalmazást biztosítson azok számára, akik szeretnék rendszerezni és nyomon követni mindennapi tevékenységeiket.
A rendszer a felhasználók három fő területét támogatja:

pénzügyi kiadások és bevételek rögzítése,

napi rutinok kezelése,

hangulat monitorozása.




A TrackMate Firebase-alapú backendjének köszönhetően az adatok valós időben frissülnek, több eszközön keresztül is azonnal szinkronizálódnak.
A felhasználók saját személyes profiljuk alatt vezethetik naplójukat, statisztikákat tekinthetnek meg, és visszanézhetik az időszakokra lebontott aktivitásokat.



A felület egy naptárszerű főnézetből indul ki, ahol minden napra kattintva megtekinthetők a kapcsolódó adatok: rögzített pénzügyi tételek, elvégzett rutinok és hangulat-bejegyzések.
A TrackMate így egy digitális self-monitoring eszközként működik, amely támogatja a felhasználók személyes fejlődését, önismeretét és pénzügyi tudatosságát.


Frontend: Angular
Backend: Firebase (Firestore, Authentication, Storage, Hosting)
Adatbázis: Firebase Firestore
Weboldal kinézetének megtekintése
GitHub link: (ide kerül majd a repo linkje)









                                                                                    Funkciók
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








                                                                                    Komponensek
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


A fejlesztők:
 Zsitnyák Ádám István (frontend)
Gáspár Bence Bálint(backend)