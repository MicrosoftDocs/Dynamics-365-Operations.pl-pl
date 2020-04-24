---
title: Synchronizowanie nagłówków ofert i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales
description: Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b6b4384e1b5f712c08de55195a738295a36b75e7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204477"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a>Synchronizowanie nagłówków ofert i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales

[!include [banner](../includes/banner.md)]

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>Szablon i zadania

Następujący szablon i podstawowe zadania są używane do synchronizowania nagłówków i wierszy ofert sprzedaży bezpośrednio z programu Sales do programu Supply Chain Management:

- **Nazwa szablonu w integracji danych:** Oferty sprzedaży (Sales do Supply Chain Management) — bezpośrednie
- **Nazwy zadań w projekcie integracji danych:**

    - QuoteHeader
    - QuoteLine

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze ofert sprzedaży:

- Produkty (Supply Chain Management do Sales) — bezpośrednie
- Konta (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)
- Kontakty do Odbiorcy (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)

## <a name="entity-set"></a>Zestaw jednostek

| Sprzedaż        | Zarządzanie łańcuchem dostaw     |
|--------------|----------------------------|
| Cytaty       | Nagłówek oferty sprzedaży CDS |
| QuoteDetails | Wiersze oferty sprzedaży CDS  |

## <a name="entity-flow"></a>Przepływ jednostek

Oferty sprzedaży są tworzone w Sales i synchronizowane z programem Supply Chain Management.

Oferty sprzedaży z programu Sales są synchronizowane tylko wtedy, gdy są spełnione następujące warunki:

- Wszystkie oferty produktów w ofercie sprzedaży są obsługiwane zewnętrznie.
- Po kliknięciu opcji **Aktywuj ofertę** oferta sprzedaży jest aktywna.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Pole **Zawiera tylko zewnętrznie obsługiwane produkty** zostało dodane do jednostki **Oferta** w celu umożliwienia ciągłego śledzenia, czy oferta sprzedaży zawiera wyłącznie zewnętrznie obsługiwane produkty. Jeśli oferta sprzedaży ma tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Supply Chain Management. To zachowanie pomaga zagwarantować, że nie będziesz próbować zsynchronizować wierszy oferty sprzedaży zawierających produkty nieznane programowi Supply Chain Management.

Wszystkie produkty z oferty w ofercie sprzedaży są aktualizowane przy użyciu informacji **Zawiera tylko zewnętrznie obsługiwane produkty** z nagłówka oferty sprzedaży. Ta informacja znajduje się w polu **Oferta zawiera tylko zewnętrznie obsługiwane produkty** w jednostce **Szczegóły oferty**.

Rabat można dodać do produktu z oferty i zostanie on zsynchronizowany z programem Supply Chain Management. Pola **Rabat**, **Opłaty** i **Podatek** w nagłówku są kontrolowane przez konfigurację w programie Supply Chain Management. Obecnie ta konfiguracja nie obsługuje mapowanie integracji. W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są obsługiwane w programie Supply Chain Management.

W programie Sales wymienione pola są tylko do odczytu, ponieważ ich wartości nie są synchronizowane z programem Supply Chain Management:

- Pola tylko do odczytu w nagłówku oferty sprzedaży: **% rabatu**, **Rabat** i **Kwota frachtu**
- Pola tylko do odczytu w produktach w ofercie: **Podatek**

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem ofert sprzedaży należy zaktualizować poniższe ustawienia.

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

- Upewnij się, że skonfigurowano uprawienia dla zespołu, do którego przypisany jest użytkownik z połączenia ustawionego w rozwiązaniu Sales. Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora. Jeżeli zespół nie ma dostępu w trybie administratora po uruchomieniu projektu z integracji danych, zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego.

    Aby ustawić uprawnienia dla zespołu, przejdź do okna **Ustawienia** &gt; **Zabezpieczenia** &gt; **Zespoły** i wybierz odpowiedni zespół. Wybierz opcję **Zarządzaj rolami**, a następnie wybierz rolę o odpowiednich uprawnieniach, na przykład **Administrator systemu**.

- Przejdź do okna **Ustawienia** &gt; **Administracja** &gt; **Ustawienia systemu** &gt; **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:

    - Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.
    - Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.

### <a name="setup-in-the-data-integration-project"></a>Konfiguracja w projekcie integracji danych

#### <a name="quoteheader"></a>QuoteHeader

- Sprawdź, czy istnieje wymagane mapowanie dla **Shipto\_country** na **DeliveryAddressCountryRegionISOCode**. Na mapie wartości można zdefiniować wartość domyślną, która jest używana, jeżeli wartość zostanie pozostawiona pusta. Pozostaw lewą stronę pustą i ustaw odpowiedni kraj lub region z prawej strony. Dzięki temu nie trzeba wpisywać kraju ani regionu dla zamówień krajowych.

    Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów, a pusta wartość jest równa wartości **US**.

#### <a name="quoteline"></a>QuoteLine

- Upewnij się, że w rozwiązaniu Supply Chain Management istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.
- Upewnij się, że w rozwiązaniu Sales skonfigurowano wymagane jednostki.

    Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **oumid.name** na **SalesUnitSymbol**.

- Opcjonalnie: Można dodać następujące mapowanie w celu zagwarantowania, że wiersze oferty sprzedaży są importowane do programu Supply Chain Management w razie braku domyślnych informacji o odbiorcy lub produkcie:

    - **SiteId** — Witryna jest konieczna do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management. Nie istnieje domyślna wartość szablonu dla pola **SiteId**.
    - **WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management. Nie istnieje domyślna wartość szablonu dla pola **WarehouseId**.

## <a name="template-mapping-in-data-integrator"></a>Mapowanie szablonu w integratorze danych

> [!NOTE]
> - Pola **Rabat**, **Opłaty** i **Podatek** w nagłówku są kontrolowane przez skomplkowaną konfigurację w programie Supply Chain Management. Obecnie ta konfiguracja nie obsługuje mapowanie integracji. W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są obsługiwane przez program Supply Chain Management.
> - Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

### <a name="quoteheader"></a>QuoteHeader

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Powiązane tematy

[Prospekt na gotówkę](prospect-to-cash.md)

