# Analiza Czasu Trwania: Przeżywalność w Niewydolności Serca

Projekt realizowany w ramach przedmiotu **Analiza Czasu Trwania**. Celem jest zbadanie czynników wpływających na czas przeżycia pacjentów z niewydolnością serca przy użyciu metod statystycznych: od estymatorów nieparametrycznych po zaawansowane modele regresji.

## 📊 O zbiorze danych
Wykorzystany zbiór danych to [Heart Failure Clinical Records](https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records) pochodzący z repozytorium UCI Machine Learning.

* **Typ modelu**: Model pojedynczych epizodów – jeden stan wyjścia i jeden stan przeznaczenia.
* **Zmienna celu (`time`)**: Czas oczekiwania na wystąpienie zdarzenia (zgonu) wyrażony w dniach.
* **Zdarzenie (`DEATH_EVENT`)**: Wystąpienie zgonu (1) lub cenzurowanie prawostronne (0).
* **Główne zmienne kliniczne**: wiek, frakcja wyrzutowa (ejection fraction), poziom kreatyniny w surowicy, nadciśnienie tętnicze, palenie tytoniu.

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
