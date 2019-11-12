---
title: Zatwierdzanie i potwierdzanie zamówień zakupu
description: W tym temacie opisano stany, przez które przechodzi zamówienie zakupu po utworzeniu, oraz skutek włączenia funkcji zarządzanie zmianami w zamówieniach zakupu.
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.search.industry: ''
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 265e4dd4be63f70a29e46b6acf7db514feb599a4
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652179"
---
# <a name="approve-and-confirm-purchase-orders"></a>Zatwierdzanie i potwierdzanie zamówień zakupu

[!include [banner](../includes/banner.md)]

W tym temacie opisano stany, przez które przechodzi zamówienie zakupu po utworzeniu, oraz skutek włączenia funkcji zarządzanie zmianami w zamówieniach zakupu.

Po utworzeniu zamówienia zakupu może być konieczne przejście procesu zatwierdzania. Gdy dostawca wyrazi zgodę na zamówienie zakupu, otrzymuje ono stan **Potwierdzone**.

## <a name="approval-of-purchase-orders"></a>Zatwierdzanie zamówień zakupu
Zamówienia zakupu, które nie korzystają z mechanizmu zarządzania zmianami, mają stan **Zatwierdzone** natychmiast po utworzeniu, podczas gdy zamówienia zakupu używające funkcji zarządzania zmianami mają po utworzeniu stan **Wersja robocza**. Zamówienie zakupu, które zostało utworzone przez akceptację zamówienia planowanego z planowania głównego, jest zawsze ustawiane na stan **Zatwierdzone**, niezależnie od ustawień zarządzania zmianami. Zamówienie zakupu powoduje tworzenie transakcji magazynowych tylko wtedy, gdy osiągnie stan **Zatwierdzone**. W związku z tym te zapasy są wyświetlane jako dostępne do rezerwacji lub oznaczenia dopiero po zaakceptowaniu zamówienia.

Włączanie zarządzania zmianami dla zamówień zakupu odbywa się przez ustawienie opcji **Uaktywnienie zarządzania zmianami** na stronie **Parametry modułu Zaopatrzenie i sourcing**. Po włączeniu zarządzania zmianami zamówienia zakupu po wypełnieniu muszą przejść przez przepływ pracy zatwierdzania. Program Supply Chain Management zawiera edytora procesów przepływu pracy, gdzie można zdefiniować przepływ pracy reprezentujący proces zatwierdzania. Ten przepływ pracy może zawierać reguły automatycznego zatwierdzania, reguły określające przypisywanie osób do zatwierdzania konkretnych zamówień zakupu oraz reguły eskalacji przepływów pracy oczekujących bardzo długo na zatwierdzenie. Proces zarządzania zmianami można włączyć dla wszystkich dostawców lub dla wybranych dostawców. Ponadto można skonfigurować proces tak, aby można go było zastępować dla poszczególnych zamówień zakupu.

Po włączeniu zarządzania zmianami zamówienia zakupu przechodzą przez sześć stanów zatwierdzenia: od **Wersja robocza** do **Zakończone**. Po zatwierdzeniu zamówienia użytkownicy, którzy chcą je zmodyfikować, muszą użyć operacji **Zażądaj zmiany**.

| Stan zatwierdzenia | Opis                                                                      | Wnioskowanie o zmiany jest włączone. |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Wersje robocze           | Zamówienie zakupu jest w wersji roboczej i nie zostało przesłane do zatwierdzenia w ramach przepływu pracy zamówienia zakupu.     | Nie                        |
| W trakcie przeglądu       | Zamówienie zakupu zostało przesłane do zatwierdzenia w ramach przepływu pracy zamówienia zakupu. Trwa oczekiwanie na zatwierdzenie.       | Nie                        |
| Odrzucono        | Zamówienie zakupu zostało odrzucone w procesie zatwierdzania.                                 | Nie                        |
| Zatwierdzono        | Zamówienie zakupu zostało zatwierdzone.                                                             | Tak                       |
| Potwierdzono       | Zamówienie zakupu zostało potwierdzone. Zamówienie zakupu można potwierdzić dopiero po jego zatwierdzeniu.        | Tak                       |
| Zakończone       | Zamówienie zakupu zostało sfinalizowane. Teraz jest zamknięte finansowo i nie można go zmienić. | Nie                        |

## <a name="confirming-purchase-orders"></a>Potwierdzanie zamówienia zakupu
Zamówienia zakupu, które mają stan zatwierdzenia **Zatwierdzone**, mogą przejść przez dodatkowe czynności, zanim zostaną potwierdzone. Na przykład może być konieczne wysłanie zapytania dotyczącego zakupu do dostawcy w celu uzyskiwanie informacji o cenach, rabatach lub datach dostaw. W takim przypadku można ustawić zamówieniu zakupu stan **W trakcie analizy zewnętrznej**, używając do tego akcji **Zapytanie dotyczące zakupu**.

Dostawcy, którym skonfigurowano używanie portalu dostawców, mogą przeglądać zamówienia w portalu oraz je zatwierdzać lub odrzucać. Podczas tego procesu weryfikowania zamówienie zakupu ma stan **W trakcie analizy zewnętrznej**. Portal dostawców można skonfigurować tak, aby potwierdzenie od dostawcy automatycznie potwierdzało zamówienie w programie Supply Chain Management. Alternatywnie można ręcznie potwierdzić zamówienie zakupu po otrzymaniu potwierdzenia od dostawcy. Jeśli dostawca odrzuci zamówienie zakupu, odrzucenie jest odbierane razem z przyczynę odrzucenia i sugestiami zmian. W takim przypadku zamówienie zakupu pozostaje w stanie **W trakcie analizy zewnętrznej**.

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

## <a name="canceling-purchase-orders"></a>Anulowanie zamówień zakupu

Można anulować zamówienie zakupu, używając akcji **Anuluj** w nagłówku.

Jeśli ilość została częściowo zarejestrowana, odebrana lub zafakturowana, można anulować tylko pozostałą ilość, która nie została zarejestrowana, odebrana lub zafakturowana. Ilość zamówienia zostanie następnie odpowiednio zmniejszona. Gdy ilość w wierszu zostanie zaktualizowana, stan wiersza również zostanie zaktualizowany. Na przykład oryginalna ilość w wierszu wynosi 5, a otrzymana jest ilość 3. W takim przypadku można anulować tylko dwie. Wiersz zostanie następnie zaktualizowany do stanu **Otrzymano**.

Jeśli reszta dostawy zostanie dodana do wiersza zamówienia i przekroczy ilość w wierszu zamówienia, akcja **Anuluj** nie spowoduje anulowania nadmiarowej ilości. W takim przypadku wiersz pozostaje w stanie **Otwarte zamówienie**, ponieważ zawiera pozostałą ilość. Na przykład oryginalna ilość w wierszu wynosi 5, a pozostała do dostarczenia ilość wynosi 7. Jeśli zamówienie zostało anulowane, pięć jest anulowane, a ilość 2 pozostanie, co jest widoczne w transakcjach magazynowych.

Aby anulować całą ilość w wierszu zamówienia zakupu, w wierszu należy usunąć ilość reszty do dostarczenia. Wiersz zostanie wówczas zaktualizowany do stanu **Anulowane**.

Jeśli zamówienie zakupu jest w module zarządzanie zmianami, każda zmiana, taka jak anulowanie zamówienia lub reszty pozostałej do dostawy, musi zostać przesłana do systemu przepływu pracy i zatwierdzona przed zakończeniem procesu, a transakcje magazynowe mogą być aktualizowane jako anulowane.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie zamówień zakupu](purchase-order-overview.md)

[Tworzenie zamówienia zakupu](purchase-order-creation.md)

[Przyjęcie produktów na podstawie zamówień zakupu](product-receipt-against-purchase-orders.md)

[Omówienie faktur od dostawców](../../finance/accounts-payable/vendor-invoices-overview.md)



