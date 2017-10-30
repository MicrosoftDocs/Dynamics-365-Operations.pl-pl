---
title: "Proces wychodzący"
description: "Ten temat zawiera omówienie procesu wychodzącego w module Zarządzanie zapasami."
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 9c09a7bd314bb9005eb0b6c69d7cccad1c30cfdb
ms.openlocfilehash: 7b395cab2184f8f9f3f50a7a595c6ed782645323
ms.contentlocale: pl-pl
ms.lasthandoff: 10/04/2017

---

# <a name="outbound-process"></a>Proces wychodzący

[!include[banner](../includes/banner.md)]

Ten temat zawiera omówienie procesu wychodzącego w module Zarządzanie zapasami.

## <a name="output-orders"></a>Zamówienia wyjścia

Zamówienia wyjścia służą do połączenia wierszy zamówienia sprzedaży i wierszy zamówienia przeniesienia z wychodzącymi procesami pobierania, które używają list pobrania.

Po wygenerowaniu list pobrania z zamówień sprzedaży lub zamówień przeniesienia, zamówienia wyjścia i wysyłki są tworzone automatycznie. Lista pobierania ma relację bezpośrednią z wysyłką. Wysyłkę zamówienia przeniesienia lub dokument dostawy zamówienia sprzedaży można przetworzyć z wysyłki. 

Poniższy schemat przedstawia przegląd procesu dotyczącego zamówień wychodzących. 

[![Przegląd procesu zamówienia wychodzącego](./media/outbound-order.png)](./media/outbound-order.png)

Aby zdefiniować sposób obsługi przez program procesu wychodzącego, można ustawić odpowiednie reguł wychodzące. Tych zasad można użyć do kontroli procesu wysyłki. W szczególności można użyć zasad do kontroli, na jakim etapie procesu ma zostać zrealizowana wysyłka. Poniższe ustawienia określają sposób obsługi procesów wychodzących.

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>Stan marszruty pobrania dla zamówień sprzedaży i przeniesienia 

Przejdź do okna **Rozrachunki z odbiorcami** \> **Konfiguracja** \> **Parametry modułu rozrachunków z odbiorcami**, a następnie na karcie **Aktualizacje** wybierz wartość w polu **Stan marszruty pobrania**.

[![Pole Stan marszruty pobrania dla zamówień sprzedaży](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

Jeżeli pole **Stan marszruty pobrania** jest ustawione na **Ukończono**, proces pobierania następuje automatycznie jako część procesu generowania list pobierania. Jeżeli pole jest ustawione na **Aktywowane**, wiersze list pobierania należy zaktualizować ręcznie.

Ta sama konfiguracja dotyczy zamówień przeniesienia. Przejdź do okna**Zarządzanie zapasami** \> **Konfiguracja** \> **Parametry modułu Zarządzanie zapasami i magazynem**, a następnie na karcie **Transport** wybierz wartość w polu **Stan marszruty pobrania**.

[![Pole Stan marszruty pobrania dla zamówień przeniesienia](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>Koniec zamówień magazynowego wyjścia

Przejdź do okna **Zarządzanie zapasami** \> **Konfiguracja** \> **Parametry modułu Zarządzanie zapasami i magazynem**, a następnie na karcie **Ogólne** ustaw opcję **Koniec zamówienia magazynowego wyjścia**.

[![Opcja Koniec zamówienia magazynowego wyjścia](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

Czasami niektóre towary w zapasach nie mogą zostać pobrane w ramach przetwarzania listy pobierania. Taka sytuacja może mieć miejsce na przykład, jeżeli pracownik magazynu zmniejszy ilości w wierszach pobrania i przetworzy listy pobrania. Jeżeli opcja **Koniec zamówienia magazynowego wyjścia** jest ustawiona na **Tak**, pozostałe niepobrane ilości są zgłaszane z powrotem na poziom zamówienia. Jeżeli opcja jest ustawiona na **Nie**, pozostałe niepobrane ilości są zachowywane jako otwarta ilość zamówienia wyjścia. W takim przypadku ilości pozostają zwolnione do magazynu i muszą zostać dodane do nowej listy pobrania w ramach funkcji **Otwórz zamówienia wyjścia**.

[![Polecenie Otwórz zamówienia wyjścia w menu Funkcje](./media/open-output-order.png)](./media/open-output-order.png)

[![Menu Funkcje na stronie Otwórz zamówienia wyjścia](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>Zmniejsz ilość

Trzeci parametr, którego można użyć w ramach procesu generowania list pobrania to parametr **Zmniejsz ilość**. Ustawienie tego parametru jest powiązane z ustawieniem **Rezerwacja**, które uruchamia proces rezerwacji w ramach zwolnienia do magazynu.

[![Parametr Zmniejsz ilość](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>Przykład procesu wyjścia dla zamówienia sprzedaży

W tym przykładzie występuje zamówienie sprzedaży dla dwóch towarów. Podczas generowania listy pobrania wybierz parametr **Zmniejsz ilość**. Dlatego zwalniasz i tworzysz wiersze pobrania tylko dla dostępnych zapasów. Pobranie musi zostać zgłoszone za pomocą procesu rejestracji dla list pobrania (**Stan marszruty pobrania** = **Aktywowane**).

Podczas generowania listy pobrania rezerwowane są zapasy, które nie zostały już zarezerwowane. Niedostępne zapasy można usunąć z zamówienia sprzedaży lub zwolnione do magazynu do późniejszego przetworzenia wyjściowego, gdy zapasy będą dostępne do pobrania.

[![Aktualizuj listę pobrania](./media/update-picking-list.png)](./media/update-picking-list.png)

Po pobraniu wszystkich wierszy pobrania na stronie **Potwierdzenie listy pobrania** skojarzona wysyłka jest ukończona. Następnie można rozpocząć przetwarzanie dokumentów dostawy zamówienia sprzedaży dla odebranego towaru.

[![Aktualizacja wysyłek wychodzących](./media/outbound-shipments.png)](./media/outbound-shipments.png)
