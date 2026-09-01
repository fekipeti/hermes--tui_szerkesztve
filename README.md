# hermes--tui
hermes -tui kiegészítések


Sajnos már a telepítéséhez is kell sok minden, mert ez csak egy "mod" kezdeti módosítása a hermes --tui -nak, sok új funkcioval, windowson futó programok indításához, de van honnan elindulni, ha a tui -ban szeretnél egy DosNavigátor kinézetü fájlkezelőt.
Legegyszerűbb ha elolvastatod hermes -el a leírásokat, a bat fájl csak átmásolja a fájlokat, de a két skillt telepíteni kell. Amit szintén megold hermes.
Azért nem adtam neki semmilyen licenszt, mert használ kedvedre, módosítsad, írd át, javitsad ki a menüket.... tui nem nagyon kötött, sok mindent enged ha hagyod hogy az agent elolvassa a tui leírását, plusz a modosítások leírását...   De előfordul, hogy az llm -nem képes módosítani benne semmit, mert csak beszélgetésből jó.... Igy elárulom, hogy Deepseek v4 flash free modellel készült sok tokenből napokon keresztül....      De ingyen.... Közben tanultam sokat, arról mit kell mondani az agentnek ha az alsó sor menüjét módosítsa, vagy a felső sor egyik menüjét....  Néhány skill lett telepítve hermes alá a skills.sh oldalról, a kód teszteléséhez, hibakereséshez... Van ott sok... Nekem már 300 felett van... 





<img width="1113" height="624" alt="image" src="https://github.com/user-attachments/assets/ca451e12-468f-4e72-b136-98fbd12726e2" />







A fájlkezelő résznél, próbáltam beilleszteni pár olyan funkciót melyet hiányolok a népszerű fájlkezelőkből:  windows subsystem for linux  fájl elérése, docker fájljainak elérése, wsl alatt futó fájlszerkesztők használata windows alatt. De belekerült a windows jobb klikk menüjében lévő megnyitás más alkalmazással... Lásd a képen. 
<img width="1116" height="621" alt="image" src="https://github.com/user-attachments/assets/59c7c5b2-ba0c-45ad-9678-aa4d1cd8892c" />

## Verziók

| Csomag | hermes-agent | Megjegyzés |
|---|---|---|
| `hermes_tui_overlay_v1.2.zip` | — | a korábbi csomag |
| `hermes_tui_overlay_v3.0_0203.zip` | **0.20.3** | a korábbi 0.20.3-as csomag |
| `hermes_tui_overlay_v3.1_0204.zip` | **0.20.4** | a korábbi 0.20.4-es csomag |
| `hermes_tui_overlay_v3.2_0204.zip` | **0.20.4** | a korábbi 0.20.4-es csomag (2026-08-24, a 24 pont lezárva) |
| `hermes_tui_overlay_v3.3_0204.zip` | **0.20.4** | a jelenlegi csomag (2026-09-01, DN sortávolság javítás H18) |

A **v3.0** (0.20.3) változásai a korábbihoz képest:
- a hermes-agent **0.20.3** alá készült, a telepítő ellenőrzi a verziót
- backup készül a régi entry.js-ről: `entry.js.bak-0203` (visszaállítás: átnevezés)
- a Model Favorites (F2) RPC-t a telepítő hozzáfűzi a gateway `methods_config.py`-jához, ha a hermes frissítés felülírta

A **v3.1** (0.20.4) változásai a v3.0-hoz képest:
- a hermes-agent **0.20.4** alá készült (a telepítő ellenőrzi a verziót, backup: `entry.js.bak-0204`)
- **F4 Memtest javítás (H16):** az "Üzenetek" szám az agent élő transcriptjéből jön (`agent._session_messages`) — modell-fallback/redirect mellett sem marad 0
- **Fájl diff (18. pont):** Alt+D / Compare módban Enter a `[≠]` fájlon / Manager → Fájlok diff — két hasáb (piros = csak balon, zöld = csak jobbon), Tab = eltérés-ugrás; bináris fájlnál (kép...) HEX mód
- **Becsomagolás/Kicsomagolás (19. pont):** Alt+F5 (pack a másik panelre), Alt+F9 (extract), Archívum teszt (7z t) a kontext menüben — a 7z-t a Program Files-ból (Ninite) keresi, fallback PATH + C:\tmp\tools
- a telepítő a fork gateway **`server.py`-t is telepíti** (backup: `server.py.bak-0204`), hogy a memtest/diff RPC-k is meglegyenek

A **v3.2** (0.20.4, 2026-08-24) változásai a v3.1-hez képest — **a 24 pontos DN-lista LECLÁRVA**:
- **Rendszerinfó ablak:** Ctrl+I / Utilities → Hermes & PC → Rendszerinfó — Windows + MINDEN WSL-distró (uname/free/df/uptime), 4 állapot-gomb (LAN/WiFi/BT/Akku), R = frissítés
- **Vágólap lista (26. pont):** File menü → Vágólap... / Ctrl+Shift+V — a vágólap előzményei (max 50 + pin, R = rögzítés, kép is)
- **Kis eszközök (8. pont):** Utilities → Hermes & PC → Kis eszközök — Számológép / Naptár / ASCII tábla (Tab váltás)
- **Gyorsfeljegyzés (22. pont):** Ctrl+Z — a fájl leírása a Desc oszlopba, `descript.ion` (a Total Commander formátuma, megosztott)
- **Fájlkódolás (23. pont):** kontext menü → Kódolás (Base64)... — `.b64` a másik panelre / vágólapra / visszafejtés
- **Kijelölés-mentés (20. pont):** kontext menü — `kijeloles.lst` mentés/visszaállítás
- **Chmod/Link (21. pont):** WSL-útvonalon kontext menü → Jogok (chmod) / Szimbolikus link (wsl.exe)
- **VFS (24. pont):** archívumra Enter = belépés — a zip/7z belülről böngészhető, F5 = kicsomagolás a másik panelre

A **v3.3** (0.20.4, 2026-09-01) változásai a v3.2-höz képest:
- **DN sortávolság javítás (H18):** a fájlkezelő sorai 2-3 karaktercella magasak voltak (a `nameCol = panelW - 16 - descCol` képlet miatt a sor szövege 5 karakterrel túlfolyt, és a hermes-ink wrap-elte — a lista harmadára zsugorodott, a ki nem férő könyvtárak nem voltak elérhetők). Javítva: `nameCol = panelW - 23 - descCol` — újra 1 sor/elem, a teljes lista görgethető. (A Windows-frissítés KB5120998 NEM volt az ok — a hiba a 08-25-i kódból jött.)


