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
| `hermes_tui_overlay_v3.0_0203.zip` | **0.20.3** | a jelenlegi csomag |

A **v3.0** (0.20.3) változásai a korábbihoz képest:
- a hermes-agent **0.20.3** alá készült, a telepítő ellenőrzi a verziót
- backup készül a régi entry.js-ről: `entry.js.bak-0203` (visszaállítás: átnevezés)
- a Model Favorites (F2) RPC-t a telepítő hozzáfűzi a gateway `methods_config.py`-jához, ha a hermes frissítés felülírta


