---
title: Ilość pobrania nie jest wystarczająca podczas generowania dokumentu dostawy
description: Podczas generowania dowodu pakowania ładunek wychodzący zawiera pobraną ilość, która nie pasuje do utworzonej ilości roboczej na linii ładunkowej.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6febc340f140d0b3a3f08ea32a59d9eb4e6e5204
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920455"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a>Ilość pobrania nie jest wystarczająca podczas generowania dokumentu dostawy

Kod błędu: SYS54073

## <a name="symptoms"></a>Objawy

Podczas generowania dowodu pakowania ładunek wychodzący zawiera pobraną ilość, która nie pasuje do utworzonej ilości roboczej na linii ładunkowej.

Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:

> %1 zostało pobrane, niewystarczający poziom zapasów do aktualizacji %2 - ilość pozostałych musi wynosić %3.

Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.

## <a name="cause"></a>Powód

Dokument dostawy nie może zostać wygenerowany w obecnym stanie, ponieważ może wystąpić jeden z poniższych warunków:

- Powiązana praca nie została jeszcze pobrana i przeniesiona do końcowej lokalizacji wysyłki.
- Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku.
- Ilość wiersza załadunku, utworzona ilość pracy i pobrana ilość nie zgadzają się.

## <a name="resolution"></a>Rozwiązanie

Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się. Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.
- Dostosuj ilość w wierszu ładunku.
- Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają

Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.
1. Zanotuj wartość pola **Ilość stworzonych prac**.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.
1. Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.

### <a name="adjust-the-load-line-quantity"></a>Dostosuj ilość w wierszu ładunku

Do regulacji ilości przewodu ładunkowego należy użyć następującej procedury.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.
1. W okienku akcji na karcie **Wysyłka i odbiór** w grupie **Wycofaj** wybierz pozycję **Wycofaj potwierdzenie wysyłki**.
1. Na karcie **Wiersze ładunku** wybierz wiersz ładunku dla towaru, który powoduje problem.
1. Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.
1. Ustaw pole **Zmniejsz wiersz ładunku**, aby odzwierciedlić dopasowania w linii obciążenia.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację

Problem może wystąpić, ponieważ ktoś użył rejestracji kompletacji do zamknięcia linii ładunkowej bez pracy. W takim przypadku ręczna rejestracja kompletacji musi zostać cofnięta, a kompletacja musi zostać zakończona za pomocą aplikacji mobilnej Warehouse Management.

Aby odwrócić rejestrację frezów, należy postępować w następujący sposób.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia**.
1. Wybierz zlecenie sprzedaży, dla którego nie można wysłać dokumentu pakowania dla ładunku.
1. Na karcie **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży, dla którego została wykonana rejestracja pobrania.
1. Wybierz pozycję **Aktualizuj wiersz \> Pobierz**, aby odebrać elementy.
