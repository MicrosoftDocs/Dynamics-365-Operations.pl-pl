---
title: Ilość, która próbujesz zaktualizować, przekracza ilość otrzymaną/dostarczoną.
description: Podczas generowania dowodu pakowania ładunek wychodzący zawiera ilość przekraczającą ilość roboczą, która została pobrana i zarezerwowana dla zamówienia sprzedaży.
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
ms.openlocfilehash: 25507a482b2db7c01f56679bf3e8454249de3a6b9965f9c359a2ebe2cc8445ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6711694"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a>Ilość, która próbujesz zaktualizować, przekracza ilość otrzymaną/dostarczoną

Kod błędu: SYS7676

## <a name="symptoms"></a>Objawy

Podczas generowania dowodu pakowania ładunek wychodzący zawiera ilość przekraczającą ilość roboczą, która została pobrana i zarezerwowana dla zamówienia sprzedaży.

Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:

> Ilość, którą próbujesz zaktualizować, przekracza ilość przyjętą/dostarczoną.

Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.

## <a name="cause"></a>Powód

Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku. Na przykład problem ten może wystąpić, gdy ilość linii ładunkowej, ilość utworzona lub ilość pobrana nie jest dokładna.

## <a name="resolution"></a>Rozwiązanie

Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się. Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.
- Dostosuj ilość w wierszu ładunku.
- Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają

Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać wygenerowana.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.
1. Zanotuj wartość pola **Ilość stworzonych prac**.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.
1. Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.

### <a name="adjust-the-load-line-quantity"></a>Dostosuj ilość w wierszu ładunku

Do regulacji ilości przewodu ładunkowego należy użyć następującej procedury.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.
1. Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.
1. Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem.
1. Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.
1. Ustaw pole **Zmniejsz wiersz ładunku**, aby odzwierciedlić dopasowania w linii obciążenia.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Cofnąć wszystkie rejestracje kompletacji i powtórzyć kompletację

Jeśli ktoś użył rejestracji kompletacji do zamknięcia linii ładunkowej bez pracy, może wystąpić rozbieżność między ilością w linii ładunkowej a ilością pobraną. W takim przypadku ręczna rejestracja kompletacji musi zostać cofnięta, a kompletacja musi zostać zakończona za pomocą aplikacji mobilnej Warehouse Management.

Aby odwrócić rejestrację frezów, należy postępować w następujący sposób.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia**.
1. Wybierz zlecenie sprzedaży, dla którego nie można wysłać dokumentu pakowania dla ładunku.
1. Na karcie  **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży, dla których została wykonana rejestracja pobrania.
1. Wybierz pozycję **Aktualizuj wiersz \> Pobierz**, aby odebrać elementy.
