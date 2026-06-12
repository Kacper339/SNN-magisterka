
# Raport z Eksperymentu - Sieć Impulsowa (SNN) VGG11

**Data i czas generowania raportu:** 2026-05-11 19:32:16

**Lokalizacja wyników treningu:** C:\Users\Kacper\OneDrive\Desktop\SNN\results\results-real_101- VGG Net
**Lokalizacja wizualizacji:** C:\Users\Kacper\OneDrive\Desktop\SNN\plots\results-real_101- VGG Net

---

## Przegląd Modelu i Treningu

Model: VGG11
Typ sieci: Sieć Impulsowa (SNN) z neuronami LIF (Leaky Integrate-and-Fire)
Zbiór danych: N-Caltech101
Liczba klas: 101
Liczba epok treningowych (z checkpointu): 65
Urządzenie: cuda

**Parametry neuronu LIF:**
*   Próg (Threshold, `thresh`): 1.35
*   Stała czasowa (Time Constant, `tau`): 0.9
*   Parametr nachylenia funkcji surrogatowej (Slope Parameter, `gamma`): 1.0

**Inne parametry:**
*   Prawdopodobieństwo Dropoutu (`dropout_p`): 0.3
*   Normalizacja wsadowa (Batch Normalization): True
*   Kroki czasowe (Time Steps, `T`): 10

---

## Wyniki Treningu i Walidacji (z historii)

Poniżej przedstawiono podsumowanie wyników treningu i walidacji w czasie kolejnych epok. Szczegółowe dane liczbowe znajdują się w pliku `metrics.csv`.

### Krzywe Straty i Dokładności
*Plik: loss_accuracy_curves.png*
(Wykresy przedstawiają wartości straty treningowej i walidacyjnej oraz dokładność treningową, Top-1 i Top-5 w zależności od epoki treningu.)

### Średnia Częstość Wyładowań Neuronów LIF
*Plik: mean_spike_rate.png*
(Wykres przedstawia średnią częstość wyładowań dla każdej warstwy LIF w sieci, w funkcji epok. Optymalnie, wartości te powinny mieścić się w rozsądnym zakresie, np. 0.01-0.1, aby zapewnić efektywne uczenie bez nadmiernej aktywności lub 'cichych' neuronów.)

### Metryki Treningowe i Walidacyjne (CSV)
*Plik: metrics.csv*
(Plik CSV zawierający szczegółowe metryki dla każdej epoki, takie jak strata treningowa i walidacyjna, dokładność, Top-1, Top-5 oraz średnia częstość wyładowań dla każdej warstwy LIF.)

---

## Wyniki Ewaluacji na Zbiorze Testowym (Najlepszy Model)

Poniższe wyniki zostały uzyskane na niezależnym zbiorze testowym przy użyciu modelu, który osiągnął najlepszą dokładność walidacyjną podczas treningu.


### Ogólne Metryki
*   **Najlepsza Dokładność Walidacyjna (Val Accuracy z checkpointu):** 76.70% (osiągnięta w epoce 60)
*   **Dokładność na Zbiorze Testowym (Test Accuracy):** 76.70%
*   **Top-1 Accuracy na Zbiorze Testowym:** 76.70%
*   **Top-5 Accuracy na Zbiorze Testowym:** 90.60%
*   **Precyzja (Precision) na Zbiorze Testowym (Weighted Average):** 78.68%
*   **Recall na Zbiorze Testowym (Weighted Average):** 76.70%
*   **F1-Score na Zbiorze Testowym (Weighted Average):** 75.87%
*   **Precyzja (Precision) na Zbiorze Testowym (Macro Average):** 70.57%
*   **Recall na Zbiorze Testowym (Macro Average):** 71.91%
*   **F1-Score na Zbiorze Testowym (Macro Average):** 69.66%

### Raport Klasyfikacji
*Plik: classification_report.txt*
                   precision    recall  f1-score   support

BACKGROUND_Google       0.83      0.21      0.34        94
       Faces_easy       0.96      1.00      0.98        87
         Leopards       0.82      1.00      0.90        40
       Motorbikes       0.98      1.00      0.99       160
        accordion       0.65      1.00      0.79        11
        airplanes       0.97      0.96      0.97       160
           anchor       0.38      0.56      0.45         9
              ant       0.45      0.56      0.50         9
           barrel       0.73      0.80      0.76        10
             bass       0.50      0.64      0.56        11
           beaver       0.56      0.50      0.53        10
        binocular       0.50      0.43      0.46         7
           bonsai       0.92      0.85      0.88        26
            brain       0.78      0.70      0.74        20
     brontosaurus       0.39      0.78      0.52         9
           buddha       0.94      0.88      0.91        17
        butterfly       0.60      0.47      0.53        19
           camera       0.67      0.80      0.73        10
           cannon       0.57      0.44      0.50         9
         car_side       0.96      1.00      0.98        25
      ceiling_fan       0.75      0.90      0.82        10
        cellphone       0.85      0.92      0.88        12
            chair       0.50      0.77      0.61        13
       chandelier       0.67      0.73      0.70        22
      cougar_body       0.80      0.40      0.53        10
      cougar_face       0.75      0.86      0.80        14
             crab       0.64      0.60      0.62        15
         crayfish       0.78      0.50      0.61        14
        crocodile       0.30      0.30      0.30        10
   crocodile_head       0.62      0.45      0.53        11
              cup       0.60      0.75      0.67        12
        dalmatian       0.62      0.71      0.67        14
      dollar_bill       1.00      0.91      0.95        11
          dolphin       0.60      0.69      0.64        13
        dragonfly       0.89      0.57      0.70        14
  electric_guitar       0.71      0.67      0.69        15
         elephant       0.64      0.54      0.58        13
              emu       0.50      0.55      0.52        11
        euphonium       0.82      0.69      0.75        13
             ewer       0.88      0.88      0.88        17
            ferry       0.71      0.86      0.77        14
         flamingo       0.53      0.57      0.55        14
    flamingo_head       0.60      0.67      0.63         9
         garfield       0.75      0.86      0.80         7
          gerenuk       0.43      0.43      0.43         7
       gramophone       0.83      0.45      0.59        11
      grand_piano       0.89      0.85      0.87        20
        hawksbill       0.56      0.70      0.62        20
        headphone       0.67      0.89      0.76         9
         hedgehog       0.64      0.82      0.72        11
       helicopter       0.67      0.56      0.61        18
             ibis       0.47      0.56      0.51        16
     inline_skate       1.00      0.71      0.83         7
      joshua_tree       0.85      0.85      0.85        13
         kangaroo       0.82      0.50      0.62        18
            ketch       0.90      0.78      0.84        23
             lamp       0.92      0.85      0.88        13
           laptop       0.68      1.00      0.81        17
            llama       0.57      0.81      0.67        16
          lobster       0.56      0.56      0.56         9
            lotus       0.57      0.29      0.38        14
         mandolin       0.71      0.56      0.63         9
           mayfly       0.56      0.62      0.59         8
          menorah       0.94      0.83      0.88        18
        metronome       0.67      0.86      0.75         7
          minaret       0.88      0.94      0.91        16
         nautilus       0.62      0.91      0.74        11
          octopus       0.33      0.29      0.31         7
            okapi       1.00      1.00      1.00         8
           pagoda       0.90      0.90      0.90        10
            panda       0.50      0.75      0.60         8
           pigeon       0.39      0.78      0.52         9
            pizza       0.78      0.64      0.70        11
         platypus       0.33      0.43      0.38         7
          pyramid       0.64      0.58      0.61        12
         revolver       0.93      0.76      0.84        17
            rhino       0.57      0.67      0.62        12
          rooster       0.64      0.90      0.75        10
        saxophone       0.47      1.00      0.64         8
         schooner       0.79      0.85      0.81        13
         scissors       0.70      0.88      0.78         8
         scorpion       0.59      0.59      0.59        17
        sea_horse       0.67      0.50      0.57        12
           snoopy       0.64      1.00      0.78         7
      soccer_ball       1.00      0.77      0.87        13
          stapler       0.78      0.78      0.78         9
         starfish       0.57      0.72      0.63        18
      stegosaurus       0.69      0.75      0.72        12
        stop_sign       0.72      1.00      0.84        13
       strawberry       0.70      1.00      0.82         7
        sunflower       0.93      0.82      0.87        17
             tick       1.00      0.90      0.95        10
        trilobite       0.94      0.94      0.94        18
         umbrella       0.71      0.67      0.69        15
            watch       0.92      0.92      0.92        48
      water_lilly       0.36      0.62      0.45         8
       wheelchair       0.75      0.75      0.75        12
         wild_cat       1.00      0.29      0.44         7
    windsor_chair       0.71      0.83      0.77        12
           wrench       0.75      0.38      0.50         8
         yin_yang       0.82      0.75      0.78        12

         accuracy                           0.77      1777
        macro avg       0.71      0.72      0.70      1777
     weighted avg       0.79      0.77      0.76      1777

### Macierz Pomyłek
*Plik: confusion_matrix.png*
(Wizualizacja macierzy pomyłek przedstawiająca, jak dobrze model klasyfikował każdą klasę na zbiorze testowym. Przekątna macierzy wskazuje liczbę poprawnych klasyfikacji dla każdej klasy.)

---

## Dodatkowe Wizualizacje i Analizy

### Rozkład Częstości Wyładowań w Ostatniej Epoce
*Plik: final_spike_rate_distribution.png*
(Wykres słupkowy pokazujący średnie częstości wyładowań dla każdej warstwy LIF w ostatniej zakończonej epoce treningu. Pomaga to zrozumieć końcowy rozkład aktywności w warstwach sieci.)

### Dokładność per Klasa
*Plik: per_class_accuracy.png*
(Wykres słupkowy prezentujący dokładność modelu dla każdej pojedynczej klasy na zbiorze testowym. Umożliwia identyfikację klas, które są dla modelu łatwiejsze lub trudniejsze do sklasyfikowania.)

### Analiza: Średnia Częstość Wyładowań vs. Dokładność Walidacyjna w Funkcji Epok
*Plik: spike_rate_vs_val_acc_over_epochs.png*
(Wykres liniowy prezentujący trend zmian średniej częstości wyładowań (uśrednionej dla wszystkich warstw LIF) oraz dokładności walidacyjnej w funkcji epok. Pozwala zaobserwować, czy istnieje widoczna zależność między aktywnością sieci a jej wydajnością w trakcie uczenia.)

### Zależność: Średnia Częstość Wyładowań vs. Dokładność Walidacyjna (z epoką)
*Plik: avg_spike_rate_vs_val_acc_scatter.png*
(Wykres rozrzutu przedstawiający bezpośrednią relację między średnią częstością wyładowań a dokładnością walidacyjną. Punkty są kolorowane i rozmiarowane na podstawie numeru epoki, co pozwala śledzić ewolucję tej zależności w czasie.)

### Korelacja: Średnia Częstość Wyładowań ↔ Dokładność Walidacyjna
*Plik: correlation_spike_rate_val_acc.png*
(Wykres rozrzutu z linią regresji wizualizujący korelację między średnią częstością wyładowań a dokładnością walidacyjną. Oś Y jest ograniczona do realistycznego zakresu 0-100%. Wartość współczynnika korelacji Pearsona, 0.91 (jeśli obliczona), wskazuje na siłę i kierunek tej liniowej zależności, gdzie:
*   `r > 0` oznacza korelację pozytywną (wzrost jednego prowadzi do wzrostu drugiego)
*   `r < 0` oznacza korelację negatywną (wzrost jednego prowadzi do spadku drugiego)
*   `r` bliskie `0` oznacza brak liniowej korelacji
Idealnie, sieć powinna uczyć się i osiągać wysoką dokładność przy kontrolowanym (niekoniecznie bardzo niskim) poziomie częstości wyładowań.)

---

## Dalsze Propozycje Wizualizacji / Analiz

*   **Krzywa współczynnika uczenia (Learning Rate Curve):** Jeśli współczynnik uczenia był logowany w historii (np. do historii byłaby dodana lista `lr`), można go wykreślić, aby zobaczyć, jak zmieniał się w trakcie treningu i czy harmonogram uczenia działał zgodnie z oczekiwaniami.
*   **Przykładowe predykcje z wizualizacją danych zdarzeń:** Wizualizacja kilku przykładów wejściowych (np. zrekonstruowanych z danych zdarzeń) wraz z prawdziwą etykietą i przewidywaną etykietą modelu (zwłaszcza dla błędnych predykcji) może dostarczyć cennych informacji jakościowych. Wymaga to jednak dodatkowej logiki do renderowania danych zdarzeń jako obrazów.
*   **Analiza rozkładu potencjałów membranowych (Membrane Potential Distribution):** Wizualizacja rozkładu potencjału membranowego neuronów w różnych warstwach SNN może pomóc w debugowaniu problemów z ich aktywacją (np. zbyt często spikują lub są 'ciche').

