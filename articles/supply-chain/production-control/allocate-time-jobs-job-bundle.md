---
title: Alokowanie czasu do zadań w pakiecie zadań
description: W module Uruchomienie produkcji można łączyć zadania w pakiety. Następnie można uruchomić wiele zadań jednocześnie na stronie Lista zadań.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgBundleSlize, JmgProdParameters, JmgRegistration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55591
ms.assetid: 358efce7-73c8-4d2a-a7f7-cb99b88ab6ee
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 382cf8d12d9695c80c3b13497886d20f29f3680c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966587"
---
# <a name="allocate-time-to-jobs-in-a-job-bundle"></a>Alokowanie czasu do zadań w pakiecie zadań

[!include [banner](../includes/banner.md)]

W module Uruchomienie produkcji można łączyć zadania w pakiety. Następnie można uruchomić wiele zadań jednocześnie na stronie Lista zadań.

Jeśli zadania są powiązane w pakietach, należy określić, w jaki sposób czas będzie alokowany do każdego z zadań. Alokację definiuje się, wybierając jedną z następujących opcji w polu **Typ pakietu** na stronie **Klucze alokacji**:

-   **Szacowanie** — czas jest dzielony pomiędzy zadania w oparciu o szacowany czas przeznaczony na zadania.
-   **Zadania** — czas jest dzielony zgodnie z liczbą zadań, które zostały powiązane, i ilością czasu poświęconego na wykonanie wszystkich zadań.
-   **Czas netto** — czas jest dzielony równo pomiędzy zadania, które były w danym czasie powiązane.
-   **Czas rzeczywisty** — alokowany jest rzeczywisty czas pracy. Koszt jest obliczany na podstawie rzeczywistego kosztu płacowego. **Uwaga:** klucz alokacji **Czas rzeczywisty** jest dostępny tylko wtedy, gdy firma używa funkcji listy płac w module Czas i frekwencja.

Przykłady poniżej pokazują wyniki różnych kluczy alokacji.

## <a name="example-scenario"></a>Przykładowy scenariusz
Trzy zadania w kolejce zadań muszą być ukończone. Rozpoczęto pierwsze zadanie, a następnie, podczas gdy zadanie było realizowane, rozpoczęto zadanie drugie i trzecie. Powstał pakiet złożony z trzech zadań. W poniższej tabeli przedstawiono szacowany czas produkcji dla każdego zadania.

| Zadanie   | Czas produkcji |
|-------|-----------------|
| Zadanie 1 | 1 godzina          |
| Zadanie 2 | 3 godziny         |
| Zadanie 3 | 4 godziny         |
| Suma | 8 godzin         |

W następującej tabeli pokazano rzeczywiste godziny pracy poświęcone na każdego zadanie.

| Zadanie    | Godzina rozpoczęcia | Godzina zakończenia | Czas w pakiecie |
|--------|------------|----------|-------------|
| Zadanie 1  | 09:00      | 11:00    | 2 godziny     |
| Zadanie 2  | 10:00      | 13:00    | 3 godziny     |
| Zadanie 3  | 10:00      | 15:00    | 5 godzin     |
| Pakiet | 09:00      | 15:00    | 6 godzin     |

W poniższych sekcjach opisano wyniki obliczonego czasu dla każdego klucza alokacji.

## <a name="estimation-allocation-key"></a>Klucz alokacji szacowania
W poniższej tabeli przedstawiono formułę obliczania czasu alokacji. Oto ta formuła: Łączny czas zadania = Łączny czas pakietu × (Szacowany czas zadania ÷ Łączny szacowany czas)

| Zadanie   | Wzór           | Alokowany czas |
|-------|-------------------|----------------|
| Zadanie 1 | 6 × (1 ÷ 8) godz. | 0,75 godziny      |
| Zadanie 2 | 6 × (3 ÷ 8) godz. | 2,25 godziny     |
| Zadanie 3 | 6 × (4 ÷ 8) godz. | 3,00 godziny     |

## <a name="jobs-allocation-key"></a>Klucz alokacji zadań
W poniższej tabeli przedstawiono formułę obliczania czasu alokacji. Oto ta formuła: Łączny czas zadania = Łączny czas pakietu ÷ Liczba zadań

| Zadanie   | Wzór | Alokowany czas |
|-------|---------|----------------|
| Zadanie 1 | 6 ÷ 3   | 2 godziny        |
| Zadanie 2 | 6 ÷ 3   | 2 godziny        |
| Zadanie 3 | 6 ÷ 3   | 2 godziny        |

## <a name="net-time-allocation-key"></a>Klucz alokacji czasu netto
W poniższej tabeli przedstawiono formułę obliczania czasu alokacji. Oto ta formuła: Obliczony czas na raportowanie = Czas pakietu ÷ Liczba zadań

|                              | 09:00–10:00 (1 godz.) | 10:00–11:00 (1 godz.) | 11:00–13:00 (2 godz.) | 13:00–15:00 (2 godz.) | Alokowany czas |
|------------------------------|----------------------|----------------------|-----------------------|-----------------------|----------------|
| Liczba zadań w pakiecie | 1 przypada na wpłatę z zysku na rzecz budżetu państwa                    | 3                    | 2                     | 1 przypada na wpłatę z zysku na rzecz budżetu państwa                     | Nie dotyczy |
| Zadanie 1                        | 1 ÷ 1 = 1 godz.       | 1 ÷ 3 = 0,33 godz.    | Nie dotyczy        | Nie dotyczy        | 1,33 godziny     |
| Zadanie 2                        | Nie dotyczy       | 1 ÷ 3 = 0,33 godz.    | 2 ÷ 2 = 1 godz.        | Nie dotyczy        | 1,33 godziny     |
| Zadanie 3                        | Nie dotyczy       | 1 ÷ 3 = 0,33 godz.    | 2 ÷ 2 = 1 godz.        | 2 ÷ 1 = 2 godz.       | 3,33 godziny     |

## <a name="real-time-allocation-key"></a>Klucz alokacji czasu rzeczywistego
Aby obliczać koszty produkcji w oparciu o rzeczywiste koszt, trzeba wyczyścić opcję **Kategoria kosztu** na stronie **Ustawienia domyślne zlecenia produkcyjnego**. W poniższej tabeli przedstawiono formułę obliczania czasu alokacji. Oto formuła: Rzeczywisty czas na zadanie = Rzeczywisty czas w pakiecie

| Zadanie   | Rzeczywista godzina |
|-------|-------------|
| Zadanie 1 | 2 godziny     |
| Zadanie 2 | 3 godziny     |
| Zadanie 3 | 5 godzin     |

Załóżmy, że masz trzy zadania wykonywane przez pracownika, który ma stawkę godzinową 12,00. Za wykonywanie zadań pracownik nie otrzymał wynagrodzenia za nadgodziny ani dodatkowej premii. Pracownik poświęcił na wykonanie trzech powiązanych zadań łącznie 6 godzin. Dlatego też wynagrodzenie wynosi 6 x 12,00 USD = 72,00 USD. Przy stosowaniu alokacji czasu rzeczywistego koszt na godzinę jest ponownie obliczany za pomocą współczynnika obliczonego z formuły Czas netto. Rzeczywisty czas poświęcony na wykonanie każdego zadania jest następnie księgowany ponownie wraz ze skorygowaną kwotą kosztu własnego na godzinę. W podanym przykładzie pracownik poświęcił na pracę 6 godzin, lecz alokowanych jest 10 godzin. W poniższej tabeli przedstawiono formuły do obliczania kosztu. Oto formuła: Koszt na godzinę = (Łączny koszt pakietu na zadanie (czas netto) ÷ Rzeczywisty czas wykonywania zadania) × standardowy koszt własny na godzinę

| Zadanie   | Obliczanie skorygowanego kosztu na godzinę | Skorygowany koszt na godzinę | Alokowany czas | Łączny koszt zadania |
|-------|----------------------------------------|-------------------------|----------------|-------------------|
| Zadanie 1 | (1,33 ÷ 2) × 12,00 USD                 | 8,00 USD                | 2 godziny        | 16,00 USD         |
| Zadanie 2 | (1,33 ÷ 3) × 12,00 USD                 | 5,33 USD                | 3 godziny        | 16,00 USD         |
| Zadanie 3 | (3,33 ÷ 5) × 12,00 USD                 | 8,00 USD                | 5 godzin        | 40,00 USD         |

Skorygowany koszt na godzinę i czas zadania są księgowane w arkuszu produkcji. **Uwaga:** zaznaczenie opcji **Kategoria kosztu** na karcie **Ogólne** na stronie **Ustawienia domyślne zlecenia produkcyjnego** sprawia, że rzeczywisty czas dla każdego zadania jest przenoszony do arkusza produkcji, w którym koszt jest stosowany do kategorii kosztu danego zadania.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]