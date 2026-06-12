
# Raport z Eksperymentu - Sieć Impulsowa (SNN) VGG11

**Data i czas generowania raportu:** 2026-05-11 21:17:17

**Lokalizacja wyników treningu:** C:\Users\Kacper\OneDrive\Desktop\SNN\results\results-real_101-VggNet-Uwaga czasowa
**Lokalizacja wizualizacji:** C:\Users\Kacper\OneDrive\Desktop\SNN\plots\results-real_101-VggNet-Uwaga czasowa

---

## Przegląd Modelu i Treningu

Model: VGG11
Typ sieci: Sieć Impulsowa (SNN) z neuronami LIF (Leaky Integrate-and-Fire)
Zbiór danych: N-Caltech101 (format BIN)
Liczba klas: 101
Liczba epok treningowych (z checkpointu): 78
Urządzenie: cuda

**Parametry neuronu LIF:**
*   Próg (Threshold, `thresh`): 1.35
*   Stała czasowa (Time Constant, `tau`): 0.9
*   Parametr nachylenia funkcji surrogatowej (Slope Parameter, `gamma`): 1.0

**Inne parametry:**
*   Prawdopodobieństwo Dropoutu (`dropout_p`): 0.3
*   Normalizacja wsadowa (Batch Normalization): True
*   Kroki czasowe (Time Steps, `T`): 10
*   Użycie uwagi czasowej (Temporal Attention): True (Reduction: 16)

---

## Wyniki Treningu i Walidacji (z historii)

Poniżej przedstawiono podsumowanie wyników treningu i walidacji w czasie kolejnych epok. Szczegółowe dane liczbowe znajdują się w pliku `metrics.csv`.

### Krzywe Straty i Dokładności
*Plik: loss_accuracy_curves.png*
(Wykresy przedstawiają wartości straty treningowej i walidacyjnej oraz dokładność treningową, Top-1 i Top-5 w zależności od epoki treningu.)

### Średnia Częstość Wyładowań Neuronów LIF
*Plik: mean_firing_rate.png*
(Wykres przedstawia średnią częstość wyładowań dla każdej warstwy LIF w sieci, w funkcji epok. Optymalnie, wartości te powinny mieścić się w rozsądnym zakresie, np. 0.01-0.1, aby zapewnić efektywne uczenie bez nadmiernej aktywności lub 'cichych' neuronów.)

### Metryki Treningowe i Walidacyjne (CSV)
*Plik: metrics.csv*
(Plik CSV zawierający szczegółowe metryki dla każdej epoki, takie jak strata treningowa i walidacyjna, dokładność, Top-1, Top-5 oraz średnia częstość wyładowań dla każdej warstwy LIF.)

---

## Wyniki Ewaluacji na Zbiorze Testowym (Najlepszy Model)

Poniższe wyniki zostały uzyskane na niezależnym zbiorze testowym przy użyciu modelu, który osiągnął najlepszą dokładność walidacyjną podczas treningu.


### Ogólne Metryki
*   **Najlepsza Dokładność Walidacyjna (Val Accuracy z checkpointu):** 73.27% (osiągnięta w epoce 77)
*   **Dokładność na Zbiorze Testowym (Test Accuracy):** 73.27%
*   **Top-1 Accuracy na Zbiorze Testowym:** 73.27%
*   **Top-5 Accuracy na Zbiorze Testowym:** 88.91%
*   **Precyzja (Weighted Average) na Zbiorze Testowym:** 75.64%
*   **Recall (Weighted Average) na Zbiorze Testowym:** 73.27%
*   **F1-Score (Weighted Average) na Zbiorze Testowym:** 71.80%
*   **Precyzja (Macro Average) na Zbiorze Testowym:** 65.31%
*   **Recall (Macro Average) na Zbiorze Testowym:** 68.22%
*   **F1-Score (Macro Average) na Zbiorze Testowym:** 65.10%

### Raport Klasyfikacji
*Plik: classification_report.txt*
(Szczegółowy raport klasyfikacji zawierający precyzję, recall i F1-score dla każdej klasy, a także ogólne średnie. Wartości Macro Average i Weighted Average są podsumowane powyżej.)

### Macierz Pomyłek
*Plik: confusion_matrix.png*
(Wizualizacja macierzy pomyłek przedstawiająca, jak dobrze model klasyfikował każdą klasę na zbiorze testowym. Przekątna macierzy wskazuje liczbę poprawnych klasyfikacji dla każdej klasy.)

---

## Dodatkowe Wizualizacje i Analizy

### Rozkład Częstości Wyładowań w Ostatniej Epoce
*Plik: final_firing_rate_distribution.png*
(Wykres słupkowy pokazujący średnie częstości wyładowań dla każdej warstwy LIF w ostatniej zakończonej epoce treningu. Pomaga to zrozumieć końcowy rozkład aktywności w warstwach sieci.)

### Dokładność per Klasa
*Plik: per_class_accuracy.png*
(Wykres słupkowy prezentujący dokładność modelu dla każdej pojedynczej klasy na zbiorze testowym. Umożliwia identyfikację klas, które są dla modelu łatwiejsze lub trudniejsze do sklasyfikowania.)

### Analiza: Średnia Częstość Wyładowań vs. Dokładność Walidacyjna w Funkcji Epok
*Plik: firing_rate_vs_val_acc_over_epochs.png*
(Wykres liniowy prezentujący trend zmian średniej częstości wyładowań (uśrednionej dla wszystkich warstw LIF) oraz dokładności walidacyjnej w funkcji epok. Pozwala zaobserwować, czy istnieje widoczna zależność między aktywnością sieci a jej wydajnością w trakcie uczenia.)

### Zależność: Średnia Częstość Wyładowań vs. Dokładność Walidacyjna (z epoką)
*Plik: avg_firing_rate_vs_val_acc_scatter.png*
(Wykres rozrzutu przedstawiający bezpośrednią relację między średnią częstością wyładowań a dokładnością walidacyjną. Punkty są kolorowane i rozmiarowane na podstawie numeru epoki, co pozwala śledzić ewolucję tej zależności w czasie. Legenda została usunięta dla lepszej czytelności.)

### Korelacja: Średnia Częstość Wyładowań ↔ Dokładność Walidacyjna
*Plik: correlation_firing_rate_val_acc.png*
(Wykres rozrzutu z linią regresji wizualizujący korelację między średnią częstością wyładowań a dokładnością walidacyjną. Oś Y jest ograniczona do realistycznego zakresu 0-100%. Wartość współczynnika korelacji Pearsona, 0.97 (jeśli obliczona), wskazuje na siłę i kierunek tej liniowej zależności, gdzie:
*   `r > 0` oznacza korelację pozytywną (wzrost jednego prowadzi do wzrostu drugiego)
*   `r < 0` oznacza korelację negatywną (wzrost jednego prowadzenia do spadku drugiego)
*   `r` bliskie `0` oznacza brak liniowej korelacji
Idealnie, sieć powinna uczyć się i osiągać wysoką dokładność przy kontrolowanym (niekoniecznie bardzo niskim) poziomie częstości wyładowań.)

---

## Dalsze Propozycje Wizualizacji / Analiz

*   **Krzywa współczynnika uczenia (Learning Rate Curve):** Jeśli współczynnik uczenia był logowany w historii (np. do historii byłaby dodana lista `lr`), można go wykreślić, aby zobaczyć, jak zmieniał się w trakcie treningu i czy harmonogram uczenia działał zgodnie z oczekiwaniami.
*   **Przykładowe predykcje z wizualizacją danych zdarzeń:** Wizualizacja kilku przykładów wejściowych (np. zrekonstruowanych z danych zdarzeń) wraz z prawdziwą etykietą i przewidywaną etykietą modelu (zwłaszcza dla błędnych predykcji) może dostarczyć cennych informacji jakościowych. Wymaga to jednak dodatkowej logiki do renderowania danych zdarzeń jako obrazów.
*   **Analiza rozkładu potencjałów membranowych (Membrane Potential Distribution):** Wizualizacja rozkładu potencjału membranowego neuronów w różnych warstwach SNN może pomóc w debugowaniu problemów z ich aktywacją (np. zbyt często wyładowują lub są 'ciche').

