---
title: "Synchronizowanie nagłówków i wierszy zamówień sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synchronizowanie nagłówków i wierszy zamówień sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales

[!include[banner](../includes/banner.md)]

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracja danych do synchronizacji danych między wystąpieniami programu Finance and Operations a programem Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między programami Finance and Operations a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujący szablon i podstawowe zadania są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży z programu Finance and Operations do programu Sales:

- **Nazwa szablonu w integracji danych:** Zamówienia sprzedaży (Fin and Ops do Sales) — bezpośrednie
- **Nazwy zadań w projekcie integracji danych:**

    - OrderHeader
    - OrderLine

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze faktur sprzedaży:

- Produkty (z Fin and Ops do Sales) — bezpośrednie
- Konta (Sales do Fin and Ops) — bezpośrednie (jeśli są używane)
- Kontakty z odbiorcami (z Sales do Fin and Ops) — bezpośrednie (jeśli używane)

## <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations  | Sprzedaż             |
|-------------------------|-------------------|
| Nagłówki zamówień sprzedaży CDS | SalesOrders       |
| Wiersze zamówienia sprzedaży CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Przepływ jednostek

Zamówienia sprzedaży są tworzone w programie Finance and Operations i synchronizowane z programem Sales.

Filtry w szablonie pomagają zagwarantować, że w synchronizacji uwzględniane są tylko odpowiednie zamówienia sprzedaży:

- W zamówieniu sprzedaży klient zamawiający i fakturujący pochodzący z rozwiązania Sales zostaną uwzględnieni w synchronizacji. W rozwiązaniu Finance and Operations pola **OrderingCustomerIsExternallyMaintained** i **InvoiceCustomerIsExternallyMaintained** służą do śledzenia synchronizacji w jednostkach danych.
- Zamówienie sprzedaży w rozwiązaniu Finance and Operations musi zostać potwierdzone. Z rozwiązaniem Sales są synchronizowane tylko potwierdzone zamówienia sprzedaży lub zamówienia sprzedaży o wyższym statusie przetwarzania, takim jak **Wysłano** lub **Zafakturowano**.
- Po utworzeniu lub zmodyfikowaniu zamówienia sprzedaży należy wykonać zadanie wsadowe **Obliczanie sum sprzedaży** w rozwiązaniu Finance and Operations. Z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży.

> [!NOTE]
> Aktualnie podatek dotyczący opłat w nagłówku zamówienia sprzedaży nie jest uwzględniony w synchronizacji między rozwiązaniem Finance and Operations a programem Sales. Program Sales nie obsługuje informacji podatkowych na poziomie nagłówka. Jednakże podatek dotyczący opłat na poziomie wiersza jest uwzględniony w synchronizacji.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Nowe pola zostały dodane do jednostki **Zamówienie** i są wyświetlane na stronie:

- **Jest obsługiwane zewnętrznie**— ustaw tę opcję na **Tak**, gdy zamówienie pochodzi z programu Finance and Operations.
- **Stan przetwarzania** — to pole służy do wyświetlania stanu przetwarzania zamówienia w rozwiązaniu Finance and Operations. Dostępne są następujące wartości:

    - Aktywne
    - Potwierdzone
    - Dokument dostawy
    - Zafakturowano
    - Pobrane
    - Częściowo pobrane
    - Częściowo zapakowano
    - Wysłano
    - Częściowo wysłane
    - Częściowo zafakturowane
    - Anulowane

Ustawienie **Zawiera tylko zewnętrznie obsługiwane produkty** jest używane w innych scenariuszach dotyczących zamówienia sprzedaży (na przykład synchronizacji z rozwiązania Sales do Finance and Operation) do spójnego śledzenia, czy zamówienie sprzedaży składa się całkowicie z produktów obsługiwanych zewnętrznie. Jeśli zamówienie sprzedaży zawiera tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Finance and Operations. To ustawienie pomaga zagwarantować, że nie będziesz próbować zsynchronizować wierszy zamówienia sprzedaży z produktami nieznanymi rozwiązaniu Finance and Operations.

W przypadku zamówień obsługiwanych zewnętrznie przyciski **Utwórz fakturę**, **Anuluj zamówienie**, **Oblicz ponownie**, **Pobierz produkty** i **Wyszukaj adres** na stronie **Zamówienie sprzedaży** są ukryte, ponieważ faktury zostaną utworzone w rozwiązaniu Finance and Operations i zsynchronizowane z rozwiązaniem Sales. Strony zamówienia nie można edytować, ponieważ informacje o zamówieniu sprzedaży zostaną zsynchronizowane z rozwiązania Finance and Operations.

Stan zamówienia sprzedaży pozostanie **Aktywny**, aby zapewnić przepływ zmian z rozwiązania Finance and Operations do zamówienia sprzedaży w programie Sales. Aby kontrolować to zachowanie, ustaw wartość domyślną pola **Kod stanu \[Stan\]** na **Aktywne** w projekcie integracji danych.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować poniższe ustawienia w systemach.

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

- Upewnij się, że skonfigurowano uprawienia dla zespołu, do którego przypisany jest użytkownik z połączenia rozwiązania Sales. Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora. Jeżeli zespół nie ma także dostępu w trybie administratora po uruchomieniu projektu z integracji danych, zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego.

    Przejdź do okna **Ustawienia** > **Zabezpieczenia** > **Zespoły**, wybierz odpowiedni zespół, wybierz opcję **Zarządzaj rolami** i wybierz rolę o odpowiednich uprawnieniach, na przykład **Administrator systemu**.

- Przejdź do okna **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:

    - Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.
    - Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.

### <a name="setup-in-finance-and-operations"></a>Konfiguracja w programie Finance and Operations

Przejdź do okna **Sprzedaż i marketing** > **Zadania okresowe** > **Obliczanie sum sprzedaży** i skonfiguruj zadanie tak, aby było uruchamiane jako zadanie wsadowe. Ustaw opcję **Oblicz sumy dla zamówień sprzedaży** na **Tak**. Ten krok jest ważny, ponieważ z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży. Częstotliwość zadania wsadowego powinna być zgodna z częstotliwością synchronizacji zamówienia sprzedaży.

### <a name="setup-in-the-data-integration-project"></a>Konfiguracja w projekcie integracji danych

#### <a name="salesheader-task"></a>Zadanie SalesHeader

- Upewnij się, że wymagane mapowanie istnieje w parametru **InvoiceCountryRegionId** na **BillingAddress\_Country** i dla parametru **DeliveryCountryRegionId** na **DeliveryAddress\_Country**.

    Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów.

- Cennik jest wymagany do utworzenia zamówień w rozwiązaniu Sales. Zaktualizuj mapę wartości dla parametru **pricelevelid.name \[Nazwa cennika\]** na cennik używany w programie Sales według waluty. Dla jednej waluty można użyć cennika domyślnego. Ponadto, jeżeli masz cenniki w kilku walutach, możesz użyć mapy wartości.

    Wartość szablonu domyślnego dla parametru **pricelevelid.name \[Nazwa cennika\]** to **CRM Service USA (przykład)**.

#### <a name="salesline-task"></a>Zadanie SalesLine

- Sprawdź, czy istnieje wymagane mapowanie dla **DeliveryCountryRegionId** na **DeliveryAddress\_Country**.

    Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów.

- Upewnij się, że w rozwiązaniu Finance and Operations istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.

    Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **SalesUnitSymbol** na **Ilość\_Jednostka miary**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

> [!NOTE]
> Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Finance and Operations.

### <a name="orderheader"></a>OrderHeader

![Mapowanie szablonu w integratorze danych](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a>OrderLine

![Mapowanie szablonu w integratorze danych](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Powiązane tematy

[Prospekt na gotówkę](prospect-to-cash.md)

[Synchronizowanie kont bezpośrednio w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping-direct.md)

[Synchronizowanie produktów bezpośrednio w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales](products-template-mapping-direct.md)

[Synchronizowanie kontaktów bezpośrednio w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping-direct.md)

[Synchronizowanie nagłówków i wierszy faktur sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)




