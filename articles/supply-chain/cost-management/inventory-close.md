---
title: Zamknięcie zapasów
description: W ramach procesu rozliczania transakcji rozchodu z transakcjami przychodu można również wybrać aktualizowanie księgi głównej, tak aby uwzględniała wprowadzane korekty.
author: AndersGirke
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61973
ms.assetid: c210c882-6849-4704-b78c-a777dd6cfdb6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d25db42351529fafbc68313c992f873918cd5e8638d9dc9417cb04f1ba5698f3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6711936"
---
# <a name="inventory-close"></a>Zamknięcie zapasów

[!include [banner](../includes/banner.md)]

W ramach procesu rozliczania transakcji rozchodu z transakcjami przychodu można również wybrać aktualizowanie księgi głównej, tak aby uwzględniała wprowadzane korekty.

Proces zamknięcia zapasów umożliwia rozliczenie transakcji wydania względem transakcji przyjęcia metodą wyceny zapasów wybranej w grupie modeli pozycji towaru. W ramach procesu rozliczania można określić, że księga główna ma zostać zaktualizowana, tak aby odzwierciedlała wprowadzone korekty. Jednak do czasu wykonania zamknięcia lub ponownego obliczenia zapasów transakcje wydania są księgowane przy użyciu obliczanej średniej kroczącej kosztu własnego. 

Po zamknięciu zapasów nie można już księgować w okresach przypadających przed ustawioną datą zamknięcia zapasów, chyba że zakończony proces zamknięcia zapasów zostanie wycofany. Na przykład jeśli zamknięcie zapasów zostanie wykonane dla okresu, który kończy się 31 stycznia, nie można księgować transakcji z datą wcześniejszą niż 31 stycznia. 

Towary w zapasach są przypisywane do jednego z dwóch typów zapasów: towar lub usługa. Zamknięcie zapasów działa tak samo dla obu typów. Jednak w przypadku usług zamknięcie zapasów nadal rozlicza wydania względem przyjęć. 

Częstotliwość wykonywania procesu zamknięcia zapasów różni się zależnie od firmy. Wolumen transakcji powinien pomóc określić, jak często należy to robić. Na ogół większość firm uruchamia zamknięcie magazynu w ramach procedur zamykania i uzgadniania na zakończenie miesiąca.

## <a name="inventory-recalculation-and-the-general-ledger"></a>Ponowne obliczanie zapasów i księga główna
Jeśli w trakcie miesiąca lub w innym okresie magazynowym zajdzie konieczność wprowadzenia korekt w zapasach lub w księdze głównej, zamiast zamknięcia zapasów można wykonać ponowne obliczanie zapasów. Ponowne obliczenie zapasów powoduje wprowadzenie korekt w transakcjach magazynowych, ale nie ich rozliczenie. 

Podczas ponownego obliczania zapasów następuje korekta zapasów na stanie i transakcji magazynowych, ponowne obliczenie zapasów oraz zamknięcie zapasów. Te zadania mają wpływ na wszystkie konta księgowe powiązane z pierwotną transakcją magazynową. 

**Przykład** 

Podczas tworzenia zamówienia zakupu na podstawie zamówienia sprzedaży następuje aktualizacja kont księgi głównej użytych w oryginalnym zamówieniu sprzedaży. Nawet jeśli konta księgowe grupy towarów przypisanej do towaru zostały zmienione po zaksięgowaniu zamówienia sprzedaży, a ponowne obliczanie zapasów spowodowało wygenerowanie kwoty korekty, kwota korekty jest księgowana na pierwotnych kontach księgowych. Skorygowana kwota nie jest księgowana na nowych kontach księgowych przypisanych do towaru. 

Po ukończeniu aktualizacji można sprawdzić załącznik finansowy, który został zaksięgowany w wyniku wykonania jednego z tych zadań.

1.  Na stronie **Zamknięcie i korekta** na karcie **Przegląd** wybierz aktualizację, którą chcesz obejrzeć.
2.  Kliknij kolejno opcje **Szczegóły** i **Załącznik**.

## <a name="effects-of-the-inventory-close-process-on-the-general-ledger"></a>Wpływ procesu zamknięcia zapasów na księgę główną
Niektóre zadania, które można wykonać na stronie **Zamknięcie i korekta**, powodują aktualizację księgi głównej. Na przykład księga główna jest aktualizowana po skorygowaniu dostępnych zapasów, skorygowaniu transakcji magazynowych, wykonaniu ponownego obliczania zapasów oraz wykonaniu zamknięcia zapasów. 

Konta księgowe aktualizowane wskutek tych zadań są powiązane z pierwotną transakcja magazynową. Na przykład jeśli zamówienie sprzedaży jest rozliczane względem zamówienia zakupu, konta księgi głównej użyte w pierwotnym zamówieniu sprzedaży zostaną skorygowane. To zachowanie występuje nawet wtedy, gdy konta księgowe grupy towarów przypisanej do towaru zostały zmienione po zaksięgowania zamówienia sprzedaży. Gdy zamknięcie zapasów utworzy kwotę rozliczenia, kwota zostanie zaksięgowana na pierwotnych kontach księgowych, a nie na nowych kontach księgowych przypisanych do towaru. Księga główna może także zostać aktualizowana po wycofaniu zamknięcia zapasów. 

> [!NOTE] 
> - Zamknięcie zapasów jest wymaganym krokiem w procedurze zamykania miesiąca dla wszystkich modeli magazynu, poza średnią ruchomą.  W przypadku próby zamknięcia okresu finansowego bez wcześniejszego zamknięcia magazynu w dniu zakończenia okresu zostanie pojawi się ostrzeżenie.
> - Przed uruchomieniem procedury zamknięcia można wyświetlić listę towarów, które nie mogą zostać rozliczone podczas aktualizacji.
> - Zaleca się wykonywanie zamknięcia zapasów poza godzinami szczytu, kiedy zasoby obliczeniowe mogą być bardziej równomiernie rozdzielone.

## <a name="the-inventory-close-log"></a> Dziennik zamknięcia magazynu
Po zamknięciu zapasów w centrum komunikatów może się pojawić komunikat, że jednostkowe koszty własne mogą być błędne ze względu na niemożność kompletnego rozliczenia transakcji. 

Zanim pojawi się ten komunikat, w systemie zostanie wyświetlony numer towaru i odnośna transakcja. Komunikat informuje, że kwota kosztu użyta w tej transakcji nie została zaktualizowana w wyniku zamknięcia magazynu. Komunikat pojawia się, gdy nie można rozliczyć transakcji wydania. 

Podczas procesu zamknięcia zapasów system sprawdza każdy wymiar finansowy w celu ustalenia, czy do określonej daty zamknięcia nastąpiło więcej wydań niż przyjęć. Takie niezbilansowanie może mieć miejsce, gdy transakcja magazynowa z zamówienia zakupu nie została w pełni zaksięgowana finansowo, bo nie otrzymano faktury od dostawcy lub składniki BOM używane w produkcji na wyższym poziomie nie zostały finansowo zaksięgowane. (Dla produkcji podrzędnej koszty nie są obliczane). W takim przypadku następne zamknięcie nie spowoduje korekty wszystkich wydań o poprawny koszt własny, ponieważ informacje o przyjęciach są niekompletne. 

Dla każdej sesji procedury zamknięcia system wskazuje, czy dziennik z ostrzeżeniami jest zapisywany i można go wyświetlić. 

Jeśli komunikat będzie zawierał wiele ostrzeżeń, zalecamy wykonanie następujących czynności:

-   Zaktualizuj finansowo przychody.
-   Przełożenie daty zamknięcia na późniejszy termin.
-   Ponownie oceń procedury biznesowe.

W pewnych sytuacjach nie można nic zrobić w reakcji na ostrzeżenia. Na przykład gdy są używane oznaczenia, a oznaczone zamówienie zakupu ma datę finansową przypadającą po dacie zamknięcia, nie można zmienić daty zamknięcia.

## <a name="reversing-a-completed-inventory-close"></a>Wycofywanie ukończonego zamknięcia zapasów
Czasami może być konieczne wycofanie ukończonego zamknięcia zapasów w celu przywrócenie rozliczeń do stanu sprzed wprowadzenia korekt. Anulowanie ukończonego zamknięcia magazynu powoduje ponowne otwarcie magazynu w celu umożliwienia księgowania we właściwym okresie, który obejmuje to zamknięcie magazynu. Pokrewne zmiany mogą być również dokonane w księdze głównej. Po dokonaniu wszystkich korekt można ponownie wykonać zamknięcie zapasów dla okresu, nad którym pracujesz. 

> [!NOTE] 
> Można ponownie otworzyć tylko ostatni okres zapasów, który został zamknięty. Aby cofnąć wcześniejsze zamknięcie zapasów, należy wycofać jedno po drugim wszystkie kolejne zamknięcie, począwszy od najnowszego.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]