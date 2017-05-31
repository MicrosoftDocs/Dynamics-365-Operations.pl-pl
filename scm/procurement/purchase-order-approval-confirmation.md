---
title: "Zatwierdzanie i potwierdzanie zamówień zakupu"
description: "W tym artykule opisano stany, przez które przechodzi zamówienie zakupu po utworzeniu, oraz skutek włączenia funkcji zarządzanie zmianami w zamówieniach zakupu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 346dde3acdaca367c80cc092f0d8faa2dc28c6b6
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="approve-and-confirm-purchase-orders"></a>Zatwierdzanie i potwierdzanie zamówień zakupu

[!include[banner](../includes/banner.md)]


W tym artykule opisano stany, przez które przechodzi zamówienie zakupu po utworzeniu, oraz skutek włączenia funkcji zarządzanie zmianami w zamówieniach zakupu.

Po utworzeniu zamówienia zakupu może być konieczne przejście procesu zatwierdzania. Gdy dostawca wyrazi zgodę na zamówienie zakupu, otrzymuje ono stan **Potwierdzone**.

## <a name="approval-of-purchase-orders"></a>Zatwierdzanie zamówień zakupu
Zamówienia zakupu, które nie korzystają z mechanizmu zarządzania zmianami, mają stan **Zatwierdzone** natychmiast po utworzeniu, podczas gdy zamówienia zakupu używające funkcji zarządzania zmianami mają po utworzeniu stan **Wersja robocza**. Zamówienie zakupu, które zostało utworzone przez akceptację zamówienia planowanego z planowania głównego, jest zawsze ustawiane na stan **Zatwierdzone**, niezależnie od ustawień zarządzania zmianami. Zamówienie zakupu powoduje tworzenie transakcji magazynowych tylko wtedy, gdy osiągnie stan **Zatwierdzone**. W związku z tym te zapasy są wyświetlane jako dostępne do rezerwacji lub oznaczenia dopiero po zaakceptowaniu zamówienia.  

Włączanie zarządzania zmianami dla zamówień zakupu odbywa się przez ustawienie opcji **Uaktywnienie zarządzania zmianami** na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po włączeniu zarządzania zmianami zamówienia zakupu po wypełnieniu muszą przejść przez przepływ pracy zatwierdzania. Program Microsoft Dynamics 365 for Operations zawiera edytora procesów przepływu pracy, gdzie można zdefiniować przepływ pracy reprezentujący proces zatwierdzania. Ten przepływ pracy może zawierać reguły automatycznego zatwierdzania, reguły określające przypisywanie osób do zatwierdzania konkretnych zamówień zakupu oraz reguły eskalacji przepływów pracy oczekujących bardzo długo na zatwierdzenie. Proces zarządzania zmianami można włączyć dla wszystkich dostawców lub dla wybranych dostawców. Ponadto można skonfigurować proces tak, aby można go było zastępować dla poszczególnych zamówień zakupu.  

Po włączeniu zarządzania zmianami zamówienia zakupu przechodzą przez sześć stanów zatwierdzenia: od **Wersja robocza** do **Zakończone**. Po zatwierdzeniu zamówienia użytkownicy, którzy chcą je zmodyfikować, muszą użyć operacji **Zażądaj zmiany**.

| Stan zatwierdzenia | Opis                                                                      | Wnioskowanie o zmiany jest włączone. |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Wersja robocza           | Zamówienie zakupu jest w wersji roboczej i nie zostało przesłane do zatwierdzenia w ramach przepływu pracy zamówienia zakupu.     | Nie                        |
| W trakcie przeglądu       | Zamówienie zakupu zostało przesłane do zatwierdzenia w ramach przepływu pracy zamówienia zakupu. Trwa oczekiwanie na zatwierdzenie.       | Nie                        |
| Odrzucono        | Zamówienie zakupu zostało odrzucone w procesie zatwierdzania.                                 | Nie                        |
| Zatwierdzono        | Zamówienie zakupu zostało zatwierdzone.                                                             | Tak                       |
| Potwierdzono       | Zamówienie zakupu zostało potwierdzone. Zamówienie zakupu można potwierdzić dopiero po jego zatwierdzeniu.        | Tak                       |
| Zakończone       | Zamówienie zakupu zostało sfinalizowane. Teraz jest zamknięte finansowo i nie można go zmienić. | Nie                        |

## <a name="confirming-purchase-orders"></a>Potwierdzanie zamówienia zakupu
Zamówienia zakupu, które mają stan zatwierdzenia **Zatwierdzone**, mogą przejść przez dodatkowe czynności, zanim zostaną potwierdzone. Na przykład może być konieczne wysłanie zapytania dotyczącego zakupu do dostawcy w celu uzyskiwanie informacji o cenach, rabatach lub datach dostaw. W takim przypadku można ustawić zamówieniu zakupu stan **W trakcie analizy zewnętrznej**, używając do tego akcji **Zapytanie dotyczące zakupu**.  

Dostawcy, którym skonfigurowano używanie portalu dostawców, mogą przeglądać zamówienia w portalu oraz je zatwierdzać lub odrzucać. Podczas tego procesu weryfikowania zamówienie zakupu ma stan **W trakcie analizy zewnętrznej**. Portal dostawców można skonfigurować tak, aby potwierdzenie od dostawcy automatycznie potwierdzało zamówienie w programie Dynamics 365 for Operations. Alternatywnie można ręcznie potwierdzić zamówienie zakupu po otrzymaniu potwierdzenia od dostawcy. Jeśli dostawca odrzuci zamówienie zakupu, odrzucenie jest odbierane razem z przyczynę odrzucenia i sugestiami zmian. W takim przypadku zamówienie zakupu pozostaje w stanie **W trakcie analizy zewnętrznej**.  

Istnieje także możliwość wygenerowania potwierdzenia pro forma dla zamówienia, zanim zostanie przetworzone faktyczne potwierdzenie. Ta opcja tylko tworzy raport, który można udostępnić dostawcy. Nie tworzy żadnych informacji w arkuszu.  

Gdy dostawca wyrazi zgodę na zamówienie zakupu, następnym krokiem jest zarejestrowanie zamówienia jako potwierdzonego. Ten krok można wykonać przy użyciu operacji **Potwierdzenie** lub **Potwierdź**. Obie te akcje ustawiają stan zatwierdzenia zamówienia na **Potwierdzone**. Potwierdzenie zamówienia inicjuje dwa dodatkowe procesy:

-   Tworzony jest arkusz do przechowywania dokładnej kopii tego, co zostało potwierdzone w systemie. Czasami zamówienia wymagają zmian i wtedy po potwierdzeniu zaktualizowanego zamówienia są tworzone dodatkowe arkusze. Te arkusze umożliwiają wyświetlenie historii różnych wersji zamówienia, które zostały potwierdzone.
-   Są tworzone zasady podziału księgowań oraz następuje sprawdzanie zamówienia i budżetu, jeśli włączono tę funkcjonalność. Jeśli którakolwiek kontrola się nie powiedzie, zostanie wyświetlony komunikat o błędzie z informacją, że należy wprowadzić zmiany w zamówieniu zakupu, zanim będzie można je ponownie potwierdzić.

Dostawca może wymagać pewnej formy zapewnienia, że otrzyma zapłatę za kupione towary. Istnieją różne metody dostarczania takiej gwarancji w ramach procesów rozrachunków z dostawcami. Na przykład akcja **Przedpłata** powoduje rezerwację funduszy na zamówienie zakupu, a sama przedpłata jest rejestrowana w zamówieniu zakupu.

## <a name="changing-purchase-orders"></a>Modyfikowanie zamówień zakupu
W niektórych sytuacjach może zajść konieczność zmodyfikowania zamówienia zakupu po osiągnięciu stanu zatwierdzenia **Zatwierdzone** lub **Potwierdzone**.  

Jeśli zamówienie zakupu zostało utworzone przy użyciu procesu zarządzania zmianami, można wprowadzić zmiany poprzez odwołanie raportu, a jeśli zamówienie już zostało zatwierdzone, za pomocą czynności **Zażądaj zmiany**. W takim przypadku stan zatwierdzenia zmienia się z powrotem na **Wersja robocza** i wtedy można zmodyfikować zamówienie. Po zakończeniu wprowadzania zmian może być konieczne przesłanie zamówienia zakupu do ponownego zatwierdzenia. Można skonfigurować rodzaje zmian, które wymagają ponownego zatwierdzenia, przy użyciu reguły **Reguła ponownego zatwierdzania zamówień zakupu** na stronie **Zasady zakupów**.  

Jeśli część zamówionej ilości wiersza zamówienia zakupu została dostarczona, nie można zmienić zamawianej ilości. Można jednak zmienić ilość **Pozostałe do dostarczenia** w wierszu. Następnie można użyć akcji **Finalizuj**, aby anulować wiersze i uniemożliwić dalsze przetwarzanie. 

Po potwierdzeniu zamówienia nie można go usunąć. Jednakże można anulować ilości całkowitą lub wszelką pozostałą ilość w zamówieniu, o ile tylko ta ilość nie została odebrana ani zafakturowana.

<a name="see-also"></a>Informacje dodatkowe
--------

[Omówienie zamówień zakupu](purchase-order-overview.md)

[Tworzenie zamówienia zakupu](purchase-order-creation.md)

[Przyjęcie produktów względem zamówień zakupu](product-receipt-against-purchase-orders.md)

[Przegląd faktur od dostawcy](/dynamics365/operations/financials/accounts-payable/vendor-invoices-overview)




