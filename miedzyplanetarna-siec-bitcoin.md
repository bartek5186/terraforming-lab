# Solar Mesh Bitcoin — międzyplanetarna optyczna sieć przekaźnikowa dla kryptograficznych danych

## 1. Streszczenie

**Solar Mesh Bitcoin** to koncepcja międzyplanetarnej sieci komunikacyjnej opartej o laserowe łącza optyczne, ruchome przekaźniki heliocentryczne, punkty Lagrange’a, orbitery planetarne, infrastrukturę księżycową oraz protokoły typu Delay/Disruption Tolerant Networking. Celem systemu jest umożliwienie niezależnego, odpornego i kryptograficznie weryfikowalnego przesyłania danych Bitcoina oraz innych protokołów rozliczeniowych pomiędzy Ziemią, Księżycem, Marsem i kolejnymi obszarami Układu Słonecznego.

System nie zakłada przekroczenia prędkości światła. Ograniczenie fizyczne pozostaje fundamentalne: sygnał elektromagnetyczny nie może dotrzeć szybciej niż światło w próżni. Siła tej koncepcji polega na czym innym: na zwiększeniu dostępności, redundancji, przepustowości, odporności na zasłonięcia przez Słońce, awarie i przerwy kontaktowe oraz na zapewnieniu ciągłości przesyłu krytycznych danych finansowych w środowisku międzyplanetarnym.

W tej architekturze Bitcoin pełni rolę globalnej, międzyplanetarnej warstwy finalnego rozliczenia, natomiast lokalne systemy płatności, takie jak Lightning Network, federacje rozliczeniowe lub inne warstwy drugie, mogą obsługiwać szybkie płatności w obrębie jednej planety, księżyca, stacji orbitalnej albo kolonii.

## 2. Główna idea

Zamiast projektować pojedyncze łącze Ziemia–Mars, należy zaprojektować **ruchomy mesh optyczny** obejmujący wiele typów węzłów:

- stacje naziemne na Ziemi,
- stacje naziemne na Marsie,
- stacje księżycowe,
- satelity LEO, MEO i GEO,
- orbitery Księżyca, Marsa i innych ciał niebieskich,
- przekaźniki w punktach Lagrange’a,
- satelity heliocentryczne krążące wokół Słońca na różnych promieniach orbitalnych,
- węzły rozmieszczone między orbitą Ziemi i Marsa,
- przyszłe węzły przy Wenus, pasie asteroid, Jowiszu i jego księżycach.

Każdy węzeł zna swoją pozycję, prędkość, efemerydy innych węzłów, przewidywane okna kontaktowe, stan buforów, dostępność energetyczną oraz jakość możliwych łączy optycznych. Routing nie jest klasycznym routingiem internetowym. Jest to routing czasoprzestrzenny, w którym krawędź grafu istnieje tylko w określonym przedziale czasu.

Najważniejsza zasada:

```text
Najlepsza trasa to nie zawsze trasa z najmniejszą liczbą przeskoków.
Najlepsza trasa to ta, która dostarczy dane najwcześniej przy znanych przyszłych kontaktach.
```

## 3. Ograniczenie prędkości światła

Solar Mesh nie sprawia, że płatność między Ziemią i Marsem staje się natychmiastowa. Jeżeli Mars znajduje się daleko od Ziemi, opóźnienie jednokierunkowe może wynosić wiele minut. Jeżeli planety znajdują się po przeciwnych stronach Słońca, komunikacja bezpośrednia może być utrudniona lub czasowo niedostępna.

Mesh optyczny pomaga w innych aspektach:

- umożliwia trasowanie wokół obszarów zasłoniętych przez Słońce,
- zwiększa dostępność systemu,
- skraca pojedyncze odcinki laserowe, co może poprawiać przepustowość,
- umożliwia przechowanie danych do czasu kolejnego kontaktu,
- pozwala na równoległą dystrybucję bloków i transakcji,
- umożliwia komunikację z wieloma koloniami i stacjami naraz,
- redukuje zależność od jednej stacji naziemnej lub jednego orbitera.

Jeżeli bezpośrednia linia Ziemia–Mars jest dostępna i ma dobrą jakość, to wiele przeskoków nie będzie szybsze od bezpośredniego przesłania sygnału. Wiele przeskoków ma sens wtedy, gdy bezpośredni link jest niedostępny, zasłonięty, przeciążony, energetycznie nieopłacalny albo ma zbyt słaby budżet łącza.

## 4. Topologia systemu

Proponowana architektura składa się z kilku warstw.

### 4.1. Warstwa lokalna Ziemi

Obejmuje:

- naziemne stacje optyczne,
- naziemne stacje radiowe jako fallback,
- satelity LEO,
- satelity MEO,
- satelity GEO,
- bramy do klasycznego Internetu,
- pełne węzły Bitcoina,
- węzły Lightning,
- centra danych obsługujące kopie blockchaina i mempooli.

Warstwa ziemska jest główną bramą do obecnej sieci Bitcoina, ponieważ większość mocy obliczeniowej, giełd, infrastruktury płynnościowej i użytkowników znajduje się początkowo na Ziemi.

### 4.2. Warstwa Ziemia–Księżyc

Obejmuje:

- orbitery księżycowe,
- stacje powierzchniowe na Księżycu,
- punkty Earth-Moon L1 i L2,
- przekaźniki między Ziemią, Księżycem i dalszą siecią heliocentryczną.

Księżyc jest pierwszym naturalnym poligonem testowym dla międzyplanetarnej wersji sieci. Opóźnienie Ziemia–Księżyc jest małe w porównaniu z Marsem, a jednocześnie środowisko operacyjne pozwala testować problemy związane z łącznością optyczną, autonomicznym routingiem, przerwami kontaktowymi i niezależną infrastrukturą energetyczną.

### 4.3. Warstwa punktów Lagrange’a

Punkty Lagrange’a mogą pełnić funkcję strategicznych hubów.

Najważniejsze lokalizacje:

- Earth-Sun L4,
- Earth-Sun L5,
- Mars-Sun L4,
- Mars-Sun L5,
- Earth-Moon L1,
- Earth-Moon L2,
- potencjalnie punkty Lagrange’a innych planet i księżyców.

L4 i L5 są szczególnie atrakcyjne jako długoterminowe regiony infrastrukturalne, ponieważ są stabilniejsze niż L1 i L2. L1 i L2 są użyteczne jako bramy, obserwatoria oraz punkty przejściowe, ale wymagają bardziej aktywnego utrzymania pozycji.

### 4.4. Warstwa heliocentrycznych pierścieni

Najważniejsza część koncepcji to sieć satelitów krążących wokół Słońca na różnych promieniach orbitalnych. Zamiast ustawiać przekaźniki w jednej linii między Ziemią i Marsem, należy zbudować wiele pierścieni między ich orbitami.

Przykładowy układ:

```text
Ring A: 1.05 AU
Ring B: 1.15 AU
Ring C: 1.25 AU
Ring D: 1.35 AU
Ring E: 1.45 AU
Ring F: 1.52 AU, okolice orbity Marsa
```

Każdy pierścień może mieć wiele satelitów rozmieszczonych kątowo wokół Słońca. Węzły nie są statyczne względem Ziemi i Marsa, ale ich ruch jest przewidywalny. System wykorzystuje efemerydy do planowania kontaktów.

Przykładowy schemat logiczny:

```mermaid
graph LR
    Earth[Ziemia] --> EM[Earth-Moon Relay]
    EM --> ES4[Earth-Sun L4/L5]
    ES4 --> R1[Ring 1.15 AU]
    R1 --> R2[Ring 1.25 AU]
    R2 --> R3[Ring 1.35 AU]
    R3 --> MS4[Mars-Sun L4/L5]
    MS4 --> MO[Mars Orbiter]
    MO --> Mars[Mars]
```

## 5. Odległość X między węzłami

Nie powinno istnieć jedno globalne X. Odległość między węzłami powinna zależeć od klasy linku, wymaganej przepustowości, kosztu wyniesienia, dostępnej energii, rozmiaru terminali optycznych i poziomu redundancji.

Proponowane klasy:

| Klasa | Orientacyjna odległość między węzłami | Zastosowanie |
|---|---:|---|
| Lokalna | 1 000–100 000 km | orbitery, księżyce, stacje orbitalne |
| Planetarna | 100 000–1 000 000 km | okolice planet i ich księżyców |
| Regionalna | 1–5 mln km | przejście z orbity planetarnej do heliocentrycznej |
| Gęsty mesh międzyplanetarny | 5–25 mln km | wysoka przepustowość i redundancja |
| Rzadki backbone | 25–100 mln km | tańsza sieć szkieletowa |
| Direct deep-space | 100–400+ mln km | fallback, broadcast, tryb awaryjny |

Dla samego Bitcoina nie potrzeba ogromnej przepustowości. Nagłówki bloków, transakcje, compact block relay i dowody Merkle są małe. Gęsty mesh staje się uzasadniony, gdy ta sama infrastruktura obsługuje również Internet międzyplanetarny, telemetrię, giełdy, dane naukowe, streaming, komunikację kolonii i archiwizację danych.

## 6. Węzeł Solar Mesh

Każdy węzeł powinien działać jako autonomiczny router, magazyn danych i walidator kryptograficzny.

Przykładowa struktura:

```text
SolarMeshNode
├── Optical Terminal A
├── Optical Terminal B
├── Optical Terminal C
├── RF fallback
├── Ephemeris Engine
├── Contact Planner
├── DTN Bundle Protocol Node
├── Contact Graph Routing Engine
├── Bitcoin Relay Module
├── Block/Header Validator
├── Mempool Cache
├── UTXO Snapshot Cache
├── Priority Queue
├── Store-and-Forward Buffer
├── Clock Synchronization Module
├── Energy Management Module
├── Fault Detection Module
└── Autonomous Operations Controller
```

Węzeł powinien obsługiwać co najmniej trzy funkcje:

1. **Komunikacja optyczna** — kierunkowe łącza laserowe o wysokiej przepustowości.
2. **Store-and-forward** — przechowywanie pakietów do czasu dostępności kolejnego kontaktu.
3. **Walidacja kryptograficzna** — odrzucanie niepoprawnych danych Bitcoina i propagowanie tylko poprawnych struktur.

## 7. Routing czasoprzestrzenny

Solar Mesh wymaga routingu opartego o przewidywane kontakty. Każdy link ma czas rozpoczęcia, czas zakończenia, przepustowość, opóźnienie propagacji, ryzyko utraty i koszt energetyczny.

Model grafu:

```text
Node = satelita, stacja, orbiter, punkt Lagrange’a, przekaźnik heliocentryczny
Edge = możliwe połączenie optyczne w czasie [t_start, t_end]
Weight = propagation_delay + scheduled_wait + queue_delay + acquisition_time + risk_penalty
```

Metryka wyboru trasy:

```text
cost =
  light_time
+ scheduled_wait_time
+ pointing_acquisition_time
+ queue_delay
+ retransmission_risk
+ solar_occlusion_penalty
+ energy_penalty
+ priority_adjustment
```

Dla danych krytycznych system powinien wybierać trasę o najwcześniejszym czasie dostarczenia, a niekoniecznie trasę z najmniejszą liczbą hopów. Dla danych niekrytycznych może wybierać trasę energetycznie tańszą lub o niższym koszcie zajętości łącza.

## 8. Protokół transportowy

Podstawowym protokołem powinien być model DTN, zgodny z ideą Bundle Protocol. Klasyczny TCP/IP nie jest wystarczający, ponieważ zakłada względnie stabilne, krótkie opóźnienia i możliwość szybkiego retransmitowania danych. W kosmosie linki są przerywane, opóźnienia są duże, a kontakt między węzłami może być dostępny tylko w konkretnych oknach czasowych.

Zalecany model:

```text
Bitcoin / Lightning / settlement data
        ↓
Priority-aware application adapter
        ↓
DTN Bundle Protocol
        ↓
Contact Graph Routing
        ↓
Optical link layer
        ↓
Laser terminal
```

## 9. Warstwa Bitcoina

Najbezpieczniejsze podejście zakłada brak zmian w protokole Bitcoina L1. Solar Mesh działa jako nowa warstwa transportowa.

System powinien priorytetyzować dane w następującej kolejności:

| Priorytet | Dane | Znaczenie |
|---|---|---|
| P0 | Nagłówki bloków | najszybsza informacja o stanie łańcucha |
| P1 | Transakcje wysokiej opłaty | szybka propagacja wartościowych transakcji |
| P2 | Compact blocks | efektywna rekonstrukcja bloków |
| P3 | Pełne bloki | pełna synchronizacja |
| P4 | Lightning gossip i watchtower data | obsługa warstw płatniczych |
| P5 | Snapshoty UTXO i archiwum | dane niskiego priorytetu |

Dane Bitcoina są kryptograficznie weryfikowalne. Węzły transportowe nie muszą być w pełni zaufane, ponieważ odbiorca może samodzielnie sprawdzić:

- proof-of-work nagłówka bloku,
- poprawność struktury bloku,
- podpisy transakcji,
- dowody Merkle,
- zgodność transakcji z lokalnym stanem UTXO,
- spójność rekonstrukcji compact block.

## 10. Mining i problem opóźnień

Międzyplanetarny mining jest trudny. Bitcoin ma średni czas bloku około 10 minut. Jeżeli Mars otrzymuje informację o ziemskim bloku po kilkunastu minutach, marsjański górnik pracuje przez pewien czas na potencjalnie nieaktualnym szczycie łańcucha. To zwiększa ryzyko bloków stale/orphan.

Dlatego realny model ekonomiczny wygląda następująco:

```text
Ziemia: główna płynność, większość hashpower, globalna infrastruktura giełdowa
Mars: lokalne płatności, lokalne kanały Lightning, lokalne usługi finansowe
Bitcoin L1: finalne rozliczenie międzyplanetarne
Solar Mesh: transport danych kryptograficznych
```

Mars może używać Bitcoina, ale nie powinien zakładać takiej samej pozycji w globalnym miningu jak węzły znajdujące się na Ziemi, dopóki większość hashpower znajduje się w ziemskiej domenie komunikacyjnej.

## 11. Lightning i lokalne domeny płatnicze

Lightning Network albo podobne systemy warstwy drugiej są naturalnym uzupełnieniem Solar Mesh.

Model:

```text
Mars Colony A ↔ Mars Colony B: szybkie lokalne płatności
Mars ↔ Ziemia: wolniejsze settlementy i synchronizacja kanałów
Ziemia ↔ Księżyc: prawie bieżące rozliczenia w porównaniu z Marsem
```

Lokalne domeny mogą działać szybko, ponieważ opóźnienia w obrębie jednej planety lub księżyca są relatywnie małe. Rozliczenia międzyplanetarne są wolniejsze, ale mogą być wykonywane okresowo, podobnie jak finalne rozliczenia między bankami lub giełdami w klasycznych systemach finansowych.

## 12. Scenariusz: transakcja z Marsa na Ziemię

```text
1. Użytkownik na Marsie podpisuje transakcję.
2. Lokalny węzeł marsjański waliduje transakcję.
3. Transakcja trafia do marsjańskiego mempoola.
4. Mars Orbiter odbiera pakiet i nadaje go do najbliższego węzła Solar Mesh.
5. Contact Graph Routing wybiera trasę o najwcześniejszym czasie dostarczenia.
6. Pakiet przechodzi przez jeden lub więcej przekaźników heliocentrycznych.
7. Earth-Sun relay lub GEO relay przekazuje pakiet do stacji ziemskiej.
8. Ziemski Bitcoin Gateway propaguje transakcję do globalnej sieci Bitcoina.
9. Transakcja trafia do mempooli ziemskich górników.
10. Po wydobyciu bloku informacja wraca do Marsa jako nagłówek, compact block i ewentualnie pełny blok.
```

## 13. Scenariusz: blok z Ziemi na Marsa

```text
1. Górnik na Ziemi znajduje nowy blok.
2. Ziemski gateway natychmiast wysyła nagłówek bloku jako P0.
3. Równolegle wysyłany jest compact block jako P2.
4. Węzły Solar Mesh wybierają trasę do Marsa.
5. Marsjański relay odbiera nagłówek i sprawdza proof-of-work.
6. Marsjański węzeł próbuje zrekonstruować blok z lokalnego mempoola.
7. Brakujące transakcje są dociągane jako osobne pakiety.
8. Po pełnej walidacji blok zostaje uznany za część lokalnego widoku łańcucha.
```

## 14. Bezpieczeństwo

Solar Mesh powinien zakładać, że część przekaźników może być zawodna, złośliwa, uszkodzona lub przejęta. Bezpieczeństwo opiera się na kilku warstwach:

- kryptograficznej weryfikowalności danych Bitcoina,
- wielościeżkowej propagacji,
- podpisanych komunikatach kontrolnych,
- reputacji i stanie zdrowia węzłów,
- redundancji tras,
- kontroli integralności pakietów DTN,
- lokalnym odrzucaniu niepoprawnych bloków i transakcji,
- separacji transportu od zaufania finansowego.

Najważniejsza zasada:

```text
Nie trzeba ufać przekaźnikowi, aby zweryfikować dane Bitcoina.
```

Przekaźnik może opóźnić, zgubić lub cenzurować pakiet, ale nie może sfałszować poprawnego bloku lub transakcji bez złamania kryptografii i mechanizmu proof-of-work.

## 15. Fazy budowy

### Faza 1: Ziemia–Księżyc

- test laserowego relayu dla danych Bitcoina,
- pełne węzły na Ziemi i przy Księżycu,
- DTN bundle transfer,
- walidacja nagłówków i compact blocks,
- eksperymentalny kanał Lightning z opóźnieniem kosmicznym.

### Faza 2: Ziemia–Mars przez istniejące orbitery

- brama ziemska,
- orbiter marsjański,
- marsjański pełny node,
- propagacja nagłówków bloków i transakcji,
- analiza opóźnień i zachowania mempooli.

### Faza 3: Punkty Lagrange’a

- huby Earth-Sun L4/L5,
- huby Mars-Sun L4/L5,
- routing z omijaniem Słońca,
- buforowanie danych podczas solar conjunction.

### Faza 4: Heliocentryczne pierścienie relayów

- kilka orbit pomiędzy 1.0 AU a 1.52 AU,
- kilkanaście lub kilkadziesiąt przekaźników na pierścień,
- predykcyjny routing po efemerydach,
- wielościeżkowa propagacja pakietów krytycznych.

### Faza 5: Solar System Internet

- rozszerzenie do Wenus,
- rozszerzenie do pasa asteroid,
- huby przy Jowiszu i jego księżycach,
- pełna międzyplanetarna sieć rozliczeniowa i komunikacyjna.

## 16. Minimalny produkt badawczy

Minimalne MVP nie wymaga od razu setek satelitów. Wystarczy zbudować software’ową i laboratoryjną symulację.

Elementy MVP:

- symulator orbitalny,
- generator efemeryd,
- graf kontaktów,
- routing earliest-arrival,
- moduł DTN,
- adapter Bitcoina,
- priorytetyzacja pakietów,
- symulacja opóźnień Ziemia–Księżyc i Ziemia–Mars,
- porównanie direct link vs mesh,
- analiza stale/orphan risk dla międzyplanetarnego miningu.

Technicznie można zacząć od symulacji w Go, Rust albo Pythonie. Dla backendu produkcyjnego sensowny byłby podział na moduły:

```text
controller: API, konfiguracja symulacji, dashboard
service: routing, contact planning, packet scheduling
store: efemerydy, pakiety, wyniki symulacji, metryki
model: node, edge, contact, bundle, bitcoin_message
```

## 17. Najważniejsze ryzyka

| Ryzyko | Opis | Możliwa redukcja |
|---|---|---|
| Opóźnienie fizyczne | Nie da się ominąć prędkości światła | lokalne warstwy płatnicze, final settlement L1 |
| Solar conjunction | Słońce zasłania bezpośrednią ścieżkę | L4/L5, heliocentryczne pierścienie, DTN |
| Wysoki koszt infrastruktury | Wyniesienie i utrzymanie satelitów jest kosztowne | fazowanie projektu, dual-use dla komunikacji ogólnej |
| Precyzja laserów | Wymaga dokładnego pointing/acquisition/tracking | krótsze hop-y, terminale wielowiązkowe |
| Energetyka | Węzły daleko od Słońca mają mniej energii | optymalizacja tras, baterie, większe panele |
| Bezpieczeństwo przekaźników | Węzły mogą cenzurować lub opóźniać pakiety | wielościeżkowość, weryfikacja kryptograficzna |
| Mining międzyplanetarny | Duże opóźnienia zwiększają stale blocks | lokalne płatności L2, L1 jako settlement |

## 18. Wniosek

Solar Mesh Bitcoin to nie sposób na „natychmiastowy Bitcoin między planetami”. To sposób na stworzenie **odpornej, autonomicznej, optycznej infrastruktury transportu kryptograficznych danych w Układzie Słonecznym**.

Najlepsza interpretacja tej idei:

```text
Bitcoin = międzyplanetarna warstwa finalnego rozliczenia
Lightning / L2 = lokalne szybkie płatności
Solar Mesh = optyczny, predykcyjny, odporny transport danych
DTN = protokół przetrwania w środowisku z opóźnieniami i przerwami
```

W długim horyzoncie taka infrastruktura mogłaby stać się jednym z fundamentów gospodarki międzyplanetarnej: niezależnym systemem rozliczania wartości, działającym ponad planetami, państwami, operatorami telekomunikacyjnymi i lokalnymi awariami infrastruktury.

## 19. Źródła i kierunki techniczne

- NASA — Delay/Disruption Tolerant Networking: https://www.nasa.gov/communicating-with-missions/delay-disruption-tolerant-networking/
- IETF RFC 9171 — Bundle Protocol Version 7: https://datatracker.ietf.org/doc/rfc9171/
- NASA — Deep Space Optical Communications: https://www.nasa.gov/mission/deep-space-optical-communications-dsoc/
- NASA — Laser Communications Relay Demonstration: https://www.nasa.gov/directorates/stmd/tech-demo-missions-program/laser-communications-relay-demonstration-lcrd-overview/
- ESA — Lagrange points: https://www.esa.int/Enabling_Support/Operations/What_are_Lagrange_points
- Bitcoin BIP152 — Compact Block Relay: https://bips.dev/152/
- Blockstream Satellite: https://blockstream.com/satellite/
