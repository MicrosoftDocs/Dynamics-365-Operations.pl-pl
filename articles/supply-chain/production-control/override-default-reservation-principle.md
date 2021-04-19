---
title: Zastępowanie domyślnej zasady rezerwacji materiałów w produkcji
description: W tym temacie opisano sposób ustawienia domyślnej reguły rezerwacji dla każdej grupy modeli towaru, dzięki czemu można automatycznie stosować różne reguły rezerwacji dla każdego towaru, który jest częścią formuły listy składowej (BOM) produkcji lub zamówienia partii.
author: johanhoffmann
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a1b2dd204c9a507dba387b0295f3021253e02dc4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814809"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>Zastępowanie domyślnej zasady rezerwacji materiałów w produkcji

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Funkcja *zastępowania domyślnej rezerwacji produkcji* umożliwia ustawienie reguły domyślnej rezerwacji dla każdej grupy modeli towaru. Dlatego w przypadku każdego towaru, który jest częścią formuły listy składowej (BOM) produkcji lub zamówienia partii, mogą być automatycznie stosowane różne zasady rezerwacji. Można określić, czy każda grupa modeli towaru ma zastępować zasadę domyślną rezerwacji ustawioną dla zamówienia oraz jaką zasadę rezerwacji należy w zamian stosować (*ręcznie*, *szacowanie*, *planowanie*, *zwalnianie* czy *rozpoczynanie*).

Podczas tworzenia nowego zlecenia produkcyjnego lub zamówienia partii wyświetlany jest monit o wybranie reguły rezerwacji, która ma zostać zastosowana dla tego zamówienia oraz wszystkich jego wierszy BOM lub wierszy formuły. Jeśli używana jest funkcja *zastępowania domyślnej rezerwacji produkcji*, niektóre lub wszystkie wiersze BOM lub formuły mogą zastąpić tę zasadę rezerwacji i w zamian użyć reguły rezerwacji ustawionej dla odpowiedniej grupy modeli pozycji.

Jeśli na przykład dla tych produktów są tworzone surowce lub składniki wymagające pracy pobrania, wiersze BOM lub formuły, które są tworzone dla tych produktów, wymagają fizycznej rezerwacji, ponieważ fizyczna rezerwacja jest warunkiem wstępnym generowania pracy magazynowej. Zazwyczaj, jeśli rezerwacja ma być automatyczna, należy wybrać jedną z następujących zasad rezerwacji: *szacowanie*, *planowanie*, *zwalnianie* lub *rozpoczynanie*. Z drugiej strony, jeśli istnieją materiały lub składniki, które nie wymagają pracy związanej z pobraniami, ponieważ są zużywane bezpośrednio z lokalizacji, z reguły wybierana jest zasada rezerwacji *ręcznej*, która nie tworzy żadnych rezerwacji fizycznych ani nie generuje żadnej pracy związanej z pobraniami.

## <a name="turn-on-the-feature"></a>Włączanie funkcji

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Kontrola produkcji*
- **Nazwa funkcji:** *(Wersja zapoznawcza) Zastępowanie domyślnej rezerwacji produkcji*

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Przypisywanie zasad rezerwacji produkcji do grupy modeli pozycji

1. Przejdź do pozycji **Zarządzanie kosztami \> Ustawienia zasad księgowania zapasów \> Grupa modeli pozycji**.
1. Utwórz lub wybierz grupę modeli pozycji.
1. Na skróconej karcie **Zasady zapasów** zaznacz pole wyboru **Zastąp rezerwację produkcji pozycji**.
1. W polu **Rezerwacja** wybierz zasadę rezerwacji dla pozycji należących do wybranej grupy modeli. (Te pozycje obejmują towary, które znajdują się w wierszu BOM lub formuły).

    - **Ręcznie** — towary z grupy modeli nie będą automatycznie rezerwowane na czas produkcji. W razie potrzeby można je jednak zarezerwować ręcznie.
    - **Szacowanie** — towary w grupie modeli zostaną fizycznie zarezerwowane podczas szacowania zlecenia produkcyjnego.
    - **Planowanie** — towary w grupie modeli zostaną fizycznie zarezerwowane podczas planowania zlecenia produkcyjnego.
    - **Zwalnianie** — towary w grupie modeli zostaną fizycznie zarezerwowane po zwolnieniu zlecenia produkcyjnego.
    - **Rozpoczynanie** — towary w grupie modeli zostaną fizycznie zarezerwowane na początku pracy ze zleceniem produkcyjnym.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>Przykład: stosowanie zasad rezerwacji w scenariuszu operacji zbiorczej/pakowania

Smar jest masowo produkowany w mikserze o objętości 1000 litrów. Gdy materiał masowy jest gotowy, jest przenoszony do kilku stacji wypełniania, na których są wypełniane butelki różnych rozmiarów. Po zakończeniu wypełniania butelki należy zapakować do pudełek. Te pudełka są następnie pakowane na palety.

W tym scenariuszu tworzone jest zamówienie partii na 1000 litrów materiału masowego. (To zamówienie jest zamówieniem masowym). Po zakończeniu procesu wypełniania zamówienia partii informacja o tym zamówieniu jest zgłaszana jako gotowa w lokalizacji wprowadzania materiału na stacji wypełniania. Tworzone jest zamówienie partii, które dotyczy wypełnienia i zapakowania różnych rodzajów butelek. (Zamówienia te są zamówieniami pakowania). Zamówienia pakowania mają formułę, która składa się z materiału masowego, pustej butelki, etykiety i innych materiałów do pakowania. Ponieważ materiał masowy przepływa bezpośrednio ze zbiornika miksera do stacji wypełniania, do pobrania tej substancji nie jest wymagana żadna praca magazynowa, a materiał masowy jest zużywany bezpośrednio z lokalizacji wejściowej. Dlatego jako zasadę rezerwacji ustawiono wartość *ręcznie*. Inne materiały są przenoszone etapami do stacji wypełniania w ramach pracy pobrania. Dlatego zasada rezerwacji dla tych wierszy jest ustawiona na *zwalnianie*, aby rezerwacja automatycznie odbywała się w momencie zwolnienia zamówienia pakowania.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]