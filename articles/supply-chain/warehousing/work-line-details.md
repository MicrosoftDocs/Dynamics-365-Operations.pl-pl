---
title: Szczegóły wiersza pracy
description: Ten temat zawiera informacje na temat strony Szczegóły dotyczące wiersza pracy, która zawiera wyczerpującą, sortowaną i filtrującą listę poszczególnych wierszy pracy w systemie.
author: mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 34325d2a2d87a4bb84acae53211db36468b7432a016eb24c0473358a40415426
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753778"
---
# <a name="work-line-details"></a>Szczegóły wiersza pracy

[!include [banner](../includes/banner.md)]

Strona **Szczegóły dotyczące wiersza pracy** zawiera wyczerpującą, sortowaną i filtrującą listę poszczególnych wierszy pracy w systemie. Zapewnia ona pełny przegląd pracy, która jest planowana i wykonywana w magazynie. Można łatwo przełączać między wyświetlaniem wszystkich wierszy pracy i wyświetlaniem tylko otwartych wierszy pracy. Szczegóły podane dla każdego wiersza to między innymi stan pracy, numer towaru, lokalizacja, ilość pracy, identyfikator ładunku i identyfikator wysyłki.

## <a name="turn-on-the-work-line-details-feature"></a>Włącz funkcję szczegółów wiersza pracy

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Szczegóły wiersza pracy*

## <a name="open-and-use-the-work-line-details-page"></a>Otwieranie i używanie strony Szczegóły wiersza pracy

Aby wyświetlić listę szczegółów wiersza pracy, przejdź kolejno do **Zarządzanie magazynem \> Praca \> Szczegóły wiersza pracy**. W tym oknie można wykonać następujące czynności:

- Pole **Filtru** umożliwia wyszukiwanie wierszy mających określoną wartość dla dowolnego dostępnego parametru. (Dostępne parametry obejmują wiele parametrów, które nie są widoczne jako kolumny w siatce).
- Aby wyświetlić lub ukryć zamknięte wiersze, należy skorzystać z pola wyboru **Podgląd zamknięty**.
- Wybierz opcję **Wyświetl wymiary**, aby otworzyć okno dialogowe **Wyświetlanie wymiarów**, w którym można wybrać opcję wyświetlania lub ukrywania w siatce różnych kolumn wymiarów.
- Zaznacz dowolny nagłówek kolumny, aby otworzyć menu, w którym można wybrać sortowanie lub filtrowanie listy według wartości w tej kolumnie.
- Wybierz wiersz pracy, a następnie wybierz opcję **Zmień lokalizację**, aby otworzyć okno dialogowe, w którym można zmienić lokalizację tego wiersza pracy. Określona lokalizacja zastąpi ustawienia dyrektywy lokalizacji.
- Wybierz wiersz pracy, a następnie wybierz opcję **Anuluj wiersz pracy**, aby otworzyć okno dialogowe, w którym można częściowo lub w pełni zmniejszyć ilość tego wiersza pracy.
- Skoryguj ilość.
- Wyświetl transakcje dot. każdego wiersza pracy.

## <a name="try-out-the-feature"></a>Wypróbuj tę funkcję

W tej sekcji znajduje się pokaz trzech części, w którym przedstawiono sposób pracy z szczegółami wiersza pracy.

### <a name="make-sample-data-available"></a>Udostępnianie danych pokazowych

Aby pracować z tym scenariuszem pokazowym przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md). Dodatkowo należy również wybrać firmę **USMF** przed rozpoczęciem.

Tego scenariusza można również używać jako wskazówek dotyczących danej funkcji podczas pracy w produkcji. Jednak w takim przypadku trzeba podstawiać własne wartości i w niektórych przypadkach może brakować pewnych typów wymaganych rekordów, które są dostępne w standardowych danych demonstracyjnych.

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a>Sprawdź, czy konfiguracja scenariusza zawiera wystarczające dostępne zapasy

Podczas pracy z danymi demonstracyjnymi **USMF** należy najpierw upewnić się, że system jest skonfigurowany tak, aby było możliwe udostępnienie wystarczającej ilości zapasów dla każdej odpowiedniej lokalizacji pobrania. W przypadku tego scenariusza demonstracyjnego oczekuje się, że dostępne zapasy są następujące:

- **Pozycja M9200:** 45 ea. (lub więcej)
- **Pozycja M9202:** 10 ea. (lub więcej)

Aby sprawdzić, czy dostępna jest wystarczająca ilość zapasów i wprowadzić wymagane korekty, należy wykonać następujące czynności.

1. Przejdź do **Zarządzania magazynem \> Konfiguracji \> Dyrektyw lokalizacji** i określ, które lokalizacje pobrania są używane do pobierania zamówień sprzedaży w magazynie 51. (Aby uzyskać więcej informacji, zobacz [Uzupełnianie zapasów i Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji](control-warehouse-location-directives.md)).
1. Sprawdź poziomy zapasów w odpowiednich lokalizacjach.
1. W razie potrzeby skoryguj zapasy. Jeśli konieczne jest skorygowanie zapasów, można ręcznie tworzyć zmiany, skorzystać z uzupełnienia lub użyć dowolnego innego przepływu.

### <a name="part-1-create-picking-work"></a>Część 1: Tworzenie pracy pobrania

Przed rozpoczęciem tworzenia pracy należy się upewnić, że magazyn został skonfigurowany tak, aby odpowiadał na żądania robocze w oczekiwany sposób.

Aby utworzyć zlecenie pracy pobierania, należy wykonać poniższe kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz opcję **Nowe**, aby otworzyć okno dialogowe **Tworzenie zamówienia sprzedaży**.
1. W wyświetlonym oknie dialogowym **Utwórz zamówienie sprzedaży** można ustawić następujące wartości:

    - Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość _US-001_.
    - Na skróconej karcie **Ogólne** w polu **Magazyn** ustaw wartość _51_.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i utworzyć nowe zamówienie zakupu.
1. Nowe zamówienie zakupu (PO) zostało otwarte. Zawiera pusty nowy wiersz w siatce **Wiersze zamówienia sprzedaży**. Dla tego wiersza zamówienia należy określić następujące wartości:

    - **Numer pozycji:** _M9200_
    - **Ilość:** _20_
    - **Jednostka:** _EA_

1. Wybierz nowy wiersz zamówienia, następnie pozycję **Zapasy**, potem wybierz **Rezerwacja**, aby otworzyć stronę **Rezerwacja**.
1. Na stronie **Rezerwacja** wybierz opcję **Rezerwacja partii**, aby zarezerwować pełną ilość z wybranego wiersza w magazynie.
1. Zamknij stronę **Rezerwacja**, aby powrócić do zamówienia sprzedaży.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**. System tworzy wysyłkę, dodaje ją do nowego ładunku i tworzy wymaganą pracę.
1. Utwórz drugie zamówienie sprzedaży dla tego samego konta odbiorcy i magazynu, które zostało użyte dla pierwszego zamówienia. Dodaj następujące dwa wiersze do tego zamówienia:

    - **Wiersz 1:** Ustaw pole **Kod towaru** na _M9200_, natomiast pole **Ilość** ustaw na _25_, a pole **Jednostka** na _ea_.
    - **Wiersz 2:** Ustaw pole **Kod towaru** na _M9202_, natomiast pole **Ilość** ustaw na _10_, a pole **Jednostka** na _ea_.

1. Powtórz kroki od 6 do 8, aby zarezerwować zapasy dla każdego wiersza zamówienia (jeden na raz), a następnie powtórz krok 9, aby zwolnić zamówienie do magazynu.

### <a name="part-2-change-the-location-for-a-work-line"></a>Część 2: zmiana lokalizacji dla wiersza pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły wiersza pracy**.
1. Znajdź i wybierz jeden z wierszy pracy utworzonych dla tego pokazu.
1. Wybierz opcję **Zmień lokalizację**, aby otworzyć okno dialogowe **Wybierz nową lokalizację**.
1. W oknie dialogowym **Wybierz nową lokalizację** w polu **Lokalizacja** wybierz nową lokalizację dla wiersza pracy.
1. Wybierz przycisk **OK**, aby zastosować zmiany i zamknąć okienko dialogowe.

> [!IMPORTANT]
> Zmiany lokalizacji można przesyłać tylko w przypadku, gdy w nowej lokalizacji jest wystarczająca ilość dostępnych zapasów (do pobrania) lub jeśli jest przejdzie ona poprawnie weryfikację typu lokalizacji (dla umieszczenia).

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a>Część 3: Zmiana ilości w wierszu pracy lub anulowanie wiersza pracy

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca \> Szczegóły wiersza pracy**.
1. Znajdź i wybierz jeden z wierszy pracy utworzonych dla tego pokazu. Należy zauważyć, że można anulować lub zmienić ilości tylko dla tych wierszy pracy, dla których typem pracy jest _pobranie_.
1. Wybierz **Anuluj wiersz pracy**, aby otworzyć okno dialogowe **Ilość do anulowania**.
1. W oknie dialogowym **Ilość do anulowania** zmień wartość w polu **Ilość**, aby określić ilość, która powinna zostać *odjęta od* ilości aktualnie określonej dla wiersza. Domyślnie w polu **Ilość** wyświetlana jest pełna ilość.

    - W przypadku anulowania pełnej ilości wartość **Stanu pracy** zostanie zmieniona na _Anulowane_, ale w polu **Ilość pracy** nadal będzie wyświetlana wartość oryginalna.
    - W przypadku anulowania części ilości pole **Stanu pracy** zostanie zaktualizowane, ale wartość pola **Stan pracy** nie zmieni się.

1. Wybierz przycisk **OK**, aby zastosować zmiany i zamknąć okienko dialogowe.

> [!IMPORTANT]
> W przypadku anulowania tylko części ilości w wierszu pracy należy również usunąć nieaktualną ilość z wiersza ładunku. W przeciwnym razie, jeśli niedobór w dostawie nie będzie skonfigurowany poprawnie, wiersz ładunku nie może być potwierdzony do wysyłki.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]