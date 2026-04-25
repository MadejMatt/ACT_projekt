# Analiza Czasu Trwania: Przeżywalność w Niewydolności Serca

Projekt realizowany w ramach przedmiotu **Analiza Czasu Trwania**. Celem jest zbadanie czynników wpływających na czas przeżycia pacjentów z niewydolnością serca przy użyciu metod statystycznych: od estymatorów nieparametrycznych po zaawansowane modele regresji.

## 📊 O zbiorze danych
Wykorzystany zbiór danych to [Heart Failure Clinical Records](https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records) pochodzący z repozytorium UCI Machine Learning. Zbiór zawiera dane kliniczne 299 pacjentów z niewydolnością serca.

### Charakterystyka zmiennych

| Zmienna | Opis merytoryczny | Jednostka / Wartości |
| :--- | :--- | :--- |
| **age** | Wiek pacjenta | lata |
| **anaemia** | Niedokrwistość (anemia) | 0: brak, 1: występuje |
| **creatinine_phosphokinase** | Poziom kinazy fosfokreatynowej (CPK) | mcg/L |
| **diabetes** | Cukrzyca | 0: brak, 1: występuje |
| **ejection_fraction** | Frakcja wyrzutowa (EF) | % |
| **high_blood_pressure** | Nadciśnienie tętnicze | 0: brak, 1: występuje |
| **platelets** | Liczba płytek krwi (trombocytów) | kilopłytki/mL |
| **serum_creatinine** | Poziom kreatyniny w surowicy | mg/dL |
| **serum_sodium** | Poziom sodu w surowicy | mEq/L |
| **sex** | Płeć | 0: Kobieta, 1: Mężczyzna |
| **smoking** | Palenie tytoniu | 0: niepali, 1: pali |
| **time** | Okres obserwacji | dni |
| **DEATH_EVENT** | Status przeżycia (Zmienna celu) | 0: żyje, 1: zgon |

* **Typ modelu**: Model pojedynczych epizodów – jeden stan wyjścia i jeden stan przeznaczenia.
* **Cenzurowanie**: W zbiorze występuje cenzurowanie prawostronne (dla pacjentów, którzy przeżyli okres obserwacji).


## 🛠️ Struktura Projektu (Zgodnie z wymaganiami)
Projekt jest podzielony na następujące etapy merytoryczne :

1. **Temat i cel projektu**: Określenie problematyki badawczej i hipotez dotyczących czynników ryzyka.
2. **Opis danych**: Statystyki opisowe zmiennych oraz analiza specyfiki cenzurowania w próbie.
3. **Model nieparametryczny**:
    * Estymacja funkcji przeżycia metodą **Kaplana-Meiera (PLE)**.
    * Porównanie grup testami istotności: **Log-rank** oraz **Wilcoxon**.
    * Estymacja skumulowanej funkcji hazardu metodą **Nelsona-Aalena**[.
    * Analiza kształtu funkcji hazardu za pomocą wygładzania jądrowego (**Kernel smoothing**).
4. **Model parametryczny**: Dobór rozkładu (np. Weibulla, wykładniczy) na podstawie wykresów diagnostycznych LLS.
5. **Model semiparametryczny**: Model proporcjonalnych hazardów Coxa wraz z weryfikacją założenia proporcjonalności.
6. **Podsumowanie wyników**: Weryfikacja postawionego celu i interpretacja uzyskanych parametrów.

## 🚀 Technologie i Metodyka
Projekt realizowany jest w języku **Python** z wykorzystaniem biblioteki `lifelines`.

## 🚀 Uruchomienie projektu (Środowisko Wirtualne)

Aby zapewnić zgodność wersji pakietów w zespole, zalecamy pracę w środowisku wirtualnym.

### Krok 1: Utworzenie środowiska wirtualnego
```bash
python -m venv .venv
```

### Krok 2: Aktywacja środowiska
* **Windows (Command Prompt / PowerShell)**:
  ```bash
  .venv\Scripts\activate
  ```
* **macOS / Linux**:
  ```bash
  source .venv/bin/activate
  ```

### Krok 3: Instalacja pakietów
Upewnij się, że środowisko jest aktywne (w terminalu pojawi się `(.venv)`), a następnie zainstaluj wymagane biblioteki:
```bash
pip install -r requirements.txt
```

### Krok 4: Dodanie środowiska do Jupyter Notebook
Aby korzystać z nowego środowiska w notatnikach Jupyter, dodaj odpowiedni kernel:
```bash
python -m ipykernel install --user --name=act_projekt_env --display-name="Python (ACT Projekt)"
```
