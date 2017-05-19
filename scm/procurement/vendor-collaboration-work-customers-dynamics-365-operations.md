---
title: "Współpraca dostawców z odbiorcami"
description: "W tym temacie opisano używanie portalu współpracy z dostawcami w programie Dynamics 365 for Operations do pracy z zamówieniami zakupu i monitorowania zapasów konsygnacyjnych."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d9dafdc211a866aa7d0b2ea139628ec530a2b6d4
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-with-customers"></a>Współpraca dostawców z odbiorcami

[!include[banner](../includes/banner.md)]


W tym temacie opisano używanie portalu współpracy z dostawcami w programie Dynamics 365 for Operations do pracy z zamówieniami zakupu i monitorowania zapasów konsygnacyjnych.

W tym temacie opisano używanie portalu współpracy z dostawcami do zarządzania współpracą z odbiorcami w programie Microsoft Dynamics 365 for Operations. Są tu informacje dotyczące sposobów monitorowania i odpowiadania na zamówienia zakupu oraz monitorowanie zapasów konsygnacyjnych. Można również używać portalu współpracy z dostawcami do pracy z fakturami. Aby uzyskać więcej informacji, zobacz [Obszar roboczy fakturowania w portalu współpracy z dostawcami](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace).

## <a name="working-with-purchase-orders"></a>Praca z zamówieniami zakupu
Obszar roboczy **Potwierdzenie zamówienia zakupu** pozwala odpowiadać na zamówienia zakupu wysłane Ci do przeglądu. Umożliwia także wyświetlanie informacji o zamówieniach oczekujących na interwencję odbiorcy oraz zamówień zakupu, które zostały potwierdzone, ale są nadal otwarte. W obszarze roboczym **Potwierdzenie zamówienia zakupu** istnieją trzy listy:

-   **Zamówienia zakupu do przeglądu** — Na tej liście znajdują się zamówienia sprzedaży, które zostały Ci wysłane i oczekują na Twoją odpowiedź. Po udzieleniu odpowiedzi zamówienia są usuwane z listy. Jeśli odbiorca wyśle Ci nową wersję zamówienia zakupu, zanim udzielisz odpowiedzi na poprzednią, zobaczysz tylko najnowszą wersję.
-   **Oczekiwanie na akcję odbiorcy** — Ta lista zawiera zamówienia sprzedaży, na które jest już Twoja odpowiedź, ale nie zostały one jeszcze potwierdzone przez odbiorcę. Jeśli zaakceptujesz zamówienie zakupu, możesz je monitorować na tej liście, dopóki jego stan nie zmieni się na **Potwierdzone**. Jeśli zamówienie zakupu zostało przez Ciebie odrzucone lub zaakceptowane ze zmianami, możesz je monitorować w tym miejscu, dopóki klient nie wyśle nowej wersji.
-   **Otwarte potwierdzone zamówienia zakupu** — Ta lista zawiera wszystkie zamówienia zakupu dla swojego klienta, które znajdują się w stanie **Potwierdzone**. Kiedy produkty lub usługi zostaną całkowicie przyjęte względem zamówienia zakupu, zamówienia jest usuwane z listy.

Poniższa lista zawiera cztery strony, których można używać do pracy z zamówieniami zakupu. Dwie strony zawierają te same informacje, co listy w obszarze roboczym:

-   **Zamówienia zakupu do przeglądu** (patrz wyżej)
-   **Historia potwierdzeń zamówień zakupu przez dostawcę** — Ta strona zawiera wszystkie zamówienia zakupu i wersje zamówień zakupu, które zostały wysłane do dostawcy, oraz wszystkie odpowiedzi odesłane przez dostawcę.
-   **Otwarte potwierdzone zamówienia zakupu** (patrz wyżej)
-   **Wszystkie potwierdzone zamówienia zakupu** — Ta strona zawiera wszystkie zamówienia zakupu, które zostały potwierdzone, włącznie z tymi, których produkty lub usługi już otrzymano. Ta lista może służyć do monitorowania, za które zamówienia zakupu można wysłać faktury.

### <a name="responding-to-purchase-orders"></a>Odpowiadanie na zamówienia zakupu

Zamówienia zakupu wysłane Ci przez odbiorcę do przeglądu są widoczne w obszarze roboczym **Potwierdzenie zamówienia zakupu** i na stronie **Zamówienia zakupu do przeglądu**. Po otwarciu zamówienia zakupu można je zaakceptować, odrzucić lub zaakceptować ze zmianami. Mogą istnieć załączniki w nagłówku zamówienia zakupu lub w poszczególnych wierszach. Możesz również dołączyć informacje do swojej odpowiedzi w nagłówku zamówienia zakupu lub w poszczególnych wierszach. Na przykład możesz zasugerować użycie towaru zastępczego w jednym z wierszy. Możesz wyświetlić podgląd zamówienia zakupu i wydrukować je jako plik PDF za pomocą opcji **Podgląd/drukuj**. Za pomocą akcji **Wyświetl wymiary** akcji możesz ukryć lub pokazać następujące kolumny wymiarów: Oddział, Magazyn, Kolor, Rozmiar, Styl i Konfiguracja. Jeśli użyjesz opcji **Zaakceptuj ze zmianami**, możesz zaakceptować lub odrzucić poszczególne wiersze. W wierszach można także wprowadzać następujące zmiany:

-   Zmiana dat lub ilości. Jeśli chcesz zaktualizować potwierdzoną datę dostawy we wszystkich wierszach, użyj opcji **Aktualizuj datę dostawy** w nagłówku zamówienia zakupu.
-   Podział wierszy dla różnych dat dostawy lub ilości.
-   Zastąpienie towaru. W tym celu wprowadź opis i numer towaru w polu **Zewnętrzny** w sekcji **Szczegóły wiersza**.

Nie można zmienić informacji o cenach ani opłat, ale za pomocą notatek można zasugerować ich modyfikacje. Jeśli odbiorca wyśle Ci nową wersję zamówienia, będzie ona miała sufiks wersji wskazujący, że jest to zmodyfikowana wersja zamówienia zakupu, które zostało wcześniej przekazane. Na stronie **Historia potwierdzeń zamówień zakupu przez dostawcę** możesz śledzić historię każdego zamówienia.

## <a name="monitoring-consignment-inventory"></a>Monitorowanie zapasów konsygnacyjnych
Jeśli używasz zapasów konsygnacyjnych, możesz w interfejsie współpracy z dostawcami wyświetlać informacje na następujących stronach:

-   **Zamówienia zakupu zużywające zapasy konsygnacyjne** — Zamówienia zakupu dla zapasów konsygnacyjnych są generowane, gdy odbiorca przejmuje własność zapasów. Te zamówienia zakupu konsygnacyjnego są wyświetlane tylko na stronie **Zamówienia zakupu zużywające zapasy konsygnacyjne**. Nie są one umieszczane na stronie **Wszystkie potwierdzone zamówienia zakupu**.
-   **Produkty odebrane z zapasów konsygnacyjnych** — Na tej stronie znajduje się lista wszystkich transakcji, w których własność produktów została przeniesiona na firmę zużywającą zapasy. Możesz używać tych informacji do fakturowania odbiorcy.
-   **Dostępne zapasy konsygnacyjne** — Na tej stronie są pokazane dostępne zapasy konsygnacyjne będące własnością Twojej firmy, które znajdują się na stanie w magazynie odbiorcy.


<a name="see-also"></a>Informacje dodatkowe
--------

[Zarządzanie użytkownikami portalu współpracy z dostawcami](manage-vendor-collaboration-users.md)




