# Kalkulator dawek – anestezjologia dziecięca

Jednoplikowa aplikacja webowa (HTML + CSS + JavaScript, bez bibliotek i bez serwera), która na podstawie masy ciała i wieku pacjenta pediatrycznego przelicza dawki leków: anestetyków, opioidów, leków przeciwbólowych, przeciwwymiotnych, ratunkowych oraz maksymalne dawki środków miejscowo znieczulających.

## Ważne

**Narzędzie pomocnicze dla personelu medycznego. Nie zastępuje oceny klinicznej.** Każdą dawkę zweryfikuj w aktualnej ChPL i w kompendium Medycyny Praktycznej (mp.pl). Dawki oparto na ChPL, wytycznych ERC/RCUK 2025, konsensusie PONV (SAMBA) i wytycznych szpitali pediatrycznych. Część wartości wpisano z ogólnej wiedzy klinicznej i wymaga potwierdzenia. Autor nie ponosi odpowiedzialności za skutki użycia.

## Uruchomienie

Plik `index.html` działa lokalnie – wystarczy otworzyć go w przeglądarce (także na telefonie).

### GitHub Pages (hosting za darmo)

1. Utwórz repozytorium na GitHubie i wgraj `index.html` oraz `README.md`.
2. Wejdź w **Settings → Pages**.
3. W **Build and deployment** wybierz **Deploy from a branch**, gałąź `main` i folder `/ (root)`, zapisz.
4. Po chwili strona będzie pod adresem `https://<twoja-nazwa>.github.io/<nazwa-repozytorium>/`.

Uwaga: strona na GitHub Pages w darmowym planie jest publiczna. Jeśli nie ma być ogólnodostępna, użyj hostingu wewnętrznego (np. serwer szpitala).

## Jak zmienić dawki

Wszystkie leki są w tablicy `D` w sekcji `<script>` w `index.html`. Każdy lek to obiekt:

| Pole | Znaczenie |
|---|---|
| `n` | nazwa leku |
| `r` | droga podania |
| `u` | jednostka (`mg`, `µg`, `ml`, `J`) |
| `lo`, `hi` | dawka na kg (liczba lub funkcja masy `w=>...`) |
| `min`, `max` | dolny/górny limit dawki jednorazowej |
| `c` | stężenie (jednostka/ml) do przeliczenia na ml, `null` gdy brak |
| `minW`, `minA` | minimalna masa (kg) i wiek (miesiące); poniżej – „Niezalecany” |
| `t` | uwagi (tekst lub funkcja masy) |

## Wersjonowanie

Po każdej zmianie dawek zapisuj datę i opis w historii commitów, żeby było wiadomo, która wersja jest aktualna.

## Licencja

Wybierz licencję przed upublicznieniem repozytorium (np. MIT) i dodaj plik `LICENSE`.
