---
title: Konfigurowanie konsygnacji
description: W tym temacie wyjaśniono sposób korzystania z procesów konsygnacji przychodzącej dla zapasów.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchTablePart, PurchVendorPortalConfirmedOrders, DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 71ec32f821225e69aac586aed47f8a86fa680442
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219396"
---
# <a name="set-up-consignment"></a>Konfigurowanie konsygnacji

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób korzystania z procesów konsygnacji przychodzącej dla zapasów.

Zapasy konsygnacyjne to zapasy, których właścicielem jest dostawca, ale są one przechowywane Twojej siedzibie. Gdy masz wszystko przygotowane do zużycia lub wykorzystania zapasów, przejmujesz ich własność. Ten temat zawiera informacje o tym, jak fizycznie przyjąć zapasy należące do dostawcy na stan bez tworzenia transakcji księgi głównej, jak uruchomić proces produkcji w sytuacji, gdy zapasy należące do dostawcy można fizycznie zarezerwować, i jak zmienić własność surowca w celu umożliwienia przetwarzania zużycia w ramach przetwarzania zlecenia produkcyjnego. Są tu także pewne informacje o tym, jak dostawcy mogą monitorować zużycie ich zapasów przy użyciu interfejsu współpracy z dostawcami. 

## <a name="overview-of-the-consignment-process"></a>Omówienie procesu konsygnacji
W tym przykładowym scenariuszu firma USMF ma umowę konsygnacyjną z dostawcą US-104 na surowiec M9211CI.

1.  Użytkownika w firmie USMF tworzy ręcznie zamówienie uzupełnienia zapasów konsygnacyjnych na podstawie oczekiwanego zapotrzebowania. Utworzono zamówienie dla dostawcy US-104 i dodano wiersz dla towaru MS9211CI.
2.  Dostawca otrzymuje informację o oczekiwanej dostawie. Może się to stać na jeden z trzech sposobów:
    -   Osoba pracująca w USMF wysyła informacje o zamówieniu do dostawcy.
    -   Dostawca może monitorować obecność oczekiwanych zapasów na stanie, używając do tego interfejsu współpracy z dostawcami.
    -   Osoba pracująca w USMF filtruje dane na stronie **Dostępne zapasy**, aby wyświetlić tylko te rekordy dostawcy US-104, które mają stan przyjęcia **Zamówione**, a następnie wysyła te informacje do dostawcy.
3.  Zapasy są dostarczane od dostawcy US-104 do firmy USMF.
4.  Po przybyciu materiału do USMF zamówienie uzupełnienia zapasów konsygnacyjnych jest aktualizowane o dokument przyjęcia produktów. Rejestrowane są tylko fizycznej ilości zapasów należących do dostawcy. Nie są tworzone żadne transakcje księgi głównej, ponieważ zapasy wciąż są własnością dostawcy.
5.  Dostawca śledzi aktualizacje fizycznie dostępnych zapasów za pośrednictwem strony **Dostępne zapasy konsygnacyjne**.
6.  Teraz gdy fizyczne zapasy są dostępne, proces produkcji rezerwuje zapasy należące do dostawcy i rozpoczyna zlecenie produkcyjne na wyroby gotowe, które zużyją surowiec M9211CI.
7.  Właściciel zarezerwowanych surowców, które mają zostać zużyte w dzisiejszej produkcji, zmienia się z US-104 na USMF. Odbywa się to za pomocą arkusza zmian własności zapasów. Ten proces tworzy zamówienia zakupu, gdzie pole **Źródło** ma wartość **Konsygnacja**.
8.  Dostawca śledzi zużycie (zmianę własności) na stronie **Produkty odebrane z zapasów konsygnacyjnych** i wystawia fakturę na podstawie umów między oboma firmami.
9.  W procesie produkcji jest zużywany surowiec za pomocą listy pobrania do produkcji. Fizyczna rezerwacja jest automatycznie aktualizowana w celu odzwierciedlenia faktu, że dostępne zapasy są własnością firmy USMF.
10. Faktura od dostawcy US-104 jest przetwarzana względem zamówień zakupu, które zostały utworzone automatycznie podczas przetwarzania arkusza zmian własności zapasów. Za zużyte zapasy jest dokonywana płatność do dostawcy US-104.

USMF wykonuje dodatkowe procesy okresowe:

-   Fizyczne przesunięcie zapasów należących do dostawcy między różnymi magazynami jest przetwarzane przy użyciu arkusza przeniesień.
-   Fizyczne zapasy na stanie (dostępne) są aktualizowane przy użyciu arkusza **Zliczanie pozycji**. Inwentaryzacja (zliczanie) może być również używana przez dostawcę do aktualizacji dostępnych zapasów, jeśli ma do tego uprawnienie.

Dostawca US-104 może monitorować aktualizacje za pomocą strony **Dostępne zapasy konsygnacyjne**.

## <a name="consignment-replenishment-orders"></a>Zamówienia uzupełnienia zapasów konsygnacyjnych
Zamówienie uzupełnienia zapasów konsygnacyjnych to dokument używany do wnioskowania o ilości zapasów produktów, które dostawca zamierza dostarczyć w określonym przedziale dat poprzez tworzenie transakcji na zamówione zapasy, oraz do monitorowania tych ilości. Na ogół te ilości opierają się na prognozie i rzeczywistym popycie na wskazane produkty. Zapasy, które mają być przyjmowane na podstawie zamówienia uzupełnienia zapasów konsygnacyjnych, pozostają własnością dostawcy. Rejestrowane jest tylko posiadanie produktów związanych z aktualizacją fizycznego przyjęcia, dlatego nie występują żadne aktualizacje transakcji księgi głównej. 

Wymiar **Właściciel** jest używany do oddzielania informacji o tym, które zapasy są własnością dostawcy, a które własnością przyjmującej firmy. Wiersze zamówienia uzupełnienia zapasów konsygnacyjnych mają stan **Otwarte zamówienie** dotąd, aż zostanie przyjęta lub anulowana pełna ilość określona w wierszach. Gdy pełna ilość zostanie przyjęta lub anulowana, stan zmienia się na **Ukończono**. Fizycznie dostępne zapasy powiązane z zamówieniem uzupełnienia zapasów konsygnacyjnych mogą być rejestrowane za pomocą procesu rejestracji, a także procesu aktualizacji przyjęcia produktów. Rejestracja może się odbywać w ramach procesu przyjęcia towaru lub poprzez ręczną aktualizację wierszy zamówienia. Gdy jest używany proces aktualizacji przyjęcia produktów, w arkuszu przyjęcia produktów jest tworzony rekord, który może służyć do potwierdzania dostawcy, że otrzymano towary.

[![consignment-replenishment-order](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Arkusz zmian własności zapasów
Proces zmiany właściciela zapasów z dostawcy na przyjmującą firmę odbywa się przy użyciu arkusza zmian własności zapasów. Względem arkusza nie są tworzone transakcje dla oczekiwanych zapasów. Jedyne tworzone transakcje magazynowe dotyczą zaksięgowanego arkusza. Po zaksięgowaniu arkusza:

-   Zapasy należące do dostawcy są wydawane przy użyciu odwołania **Zmiana własności** ze stanem **Sprzedane**.
-   Dostępne zapasy są przyjmowane przez firmę, która je zużyje, przy użyciu transakcji magazynowej zaktualizowanej o przyjęcie produktów względem zamówienia zakupu. Powoduje to ustawienie stanu zamówienia na **Otrzymane**. Zamówienia zakupu używane do konsygnacji mają w polu **Źródło** wartość **Konsygnacja**.

Nie jest możliwe aktualizowanie ilości w wierszach zamówienia zakupu konsygnacyjnego po utworzeniu zamówienia.

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Współpraca z dostawcami w procesach konsygnacji
Interfejs współpracy z dostawcami ma trzy strony związane z procesem konsygnacji przychodzącej:

-   **Zamówienia zakupu** **zużywające zapasy konsygnacyjne** — pokazuje szczegółowe informacje zamówienia zakupu związane ze zmianą własności wskutek procesu konsygnacji.
-   **Produkty odebrane z zapasów konsygnacyjnych** — pokazuje informacje o towarach i ilościach, dla których zaktualizowano przyjęcia produktów w trakcie procesu zmiany własności.
-   **Dostępne zapasy konsygnacyjne** — pokazuje informacje o towarach konsygnacyjnych, których dostarczenia oczekuje się od dostawcy, oraz o towarach, które są już fizycznie dostępne w siedzibie odbiorcy.

## <a name="inventory-owners"></a>Właściciele zapasów
Aby zarejestrować fizyczne przychodzące zapasy konsygnacyjne, należy zdefiniować właściciela będącego dostawcą. Służy do tego strona **Właściciel zapasów**. Wybranie opcji **Konto dostawcy** spowoduje wygenerowanie wartości domyślnych dla pól **Nazwa** i **Właściciel**. Wartość w polu **Właściciel** będzie widoczna dla dostawcy, więc warto ją zmienić, jeśli nazwy kont dostawców przechowywane w firmowych systemach są trudne do rozpoznania przez osoby zewnętrzne. Istnieje możliwość edytowania pola **Właściciel**, ale tylko do momentu zapisania rekordu **Właściciel zapasów**. W polu **Nazwa** jest wprowadzana nazwa strony, z którą jest skojarzone konto dostawcy, i nie można jej zmienić.

[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Grupa wymiarów śledzenia
Towary, które mają być używane w procesach konsygnacji, muszą być powiązane z **grupą wymiarów śledzenia**, która w wymiarze **Właściciel** ma ustawioną wartość **Aktywny**. Wymiar Właściciel zawsze ma zaznaczone opcje **Magazyn fizyczny** i **Magazyn finansowy**. Opcja **Plan zapotrzebowania wg wymiaru** nigdy nie jest zaznaczona.

[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Arkusz zmian własności zapasów
Arkusz **Zmiana własności zapasów** służy do rejestrowania przeniesienia własności zapasów konsygnacyjnych z dostawcy na firmę, która je zużyje. Podobnie jak każdy arkusz magazynowy, musi być identyfikowany za pomocą nazwy arkusza magazynowego. Nazwy te są tworzone na stronie **Nazwy arkuszy magazynowych**, a w ustawieniu **Typ arkusza** trzeba zaznaczyć wartość **Zmiana własności**.

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Współpraca z dostawcami w procesach konsygnacji
Jeśli dostawcy używają interfejsu współpracy z dostawcami, mogą w nim monitorować zużywanie zapasów w oddziale Twojej firmy. Aby uzyskać więcej informacji o konfigurowaniu dostawców do używania portalu współpracy z dostawcami, zobacz [Zabezpieczenia użytkowników portalu dostawców](../procurement/configure-security-vendor-portal-users.md).







[!INCLUDE[footer-include](../../includes/footer-banner.md)]