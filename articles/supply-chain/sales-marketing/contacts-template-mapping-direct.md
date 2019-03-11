---
title: Synchronizowanie kontaktów bezpośrednio w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania pozycji Kontakt (Kontakty) i Kontakt (Klienci) kont z Microsoft Dynamics 365 for Sales do Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 5363c64cd1a475f0047c079d9166718ddc765f02
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "356859"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Finance and Operations

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania pozycji Kontakt (Kontakty) i Kontakt (Klienci) kont bezpośrednio z Microsoft Dynamics 365 for Sales do Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracja danych do synchronizacji danych między wystąpieniami programu Finance and Operations a programem Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między programami Finance and Operations a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujące szablony i podstawowe zadania są używane do synchronizowania jednostek kontaktów (kontaktów) w programie Sales z jednostkami kontaktów (odbiorcami) w programie Finance and Operations:

- **Nazwy szablonów w integracji danych:**

    - Kontakty (z Sales do Fin and Ops) — bezpośrednie
    - Kontakty z odbiorcami (z Sales do Fin and Ops) — bezpośrednie

- **Nazwy zadań w projekcie integracji danych:**

    - Kontakty
    - ContactToCustomer

Przed rozpoczęciem synchronizowania kontaktów należy wykonać następujące zadanie synchronizacji: Konta (z Sales do Fin and Ops)

## <a name="entity-sets"></a>Zestawy jednostek

| Sprzedaż    | Finance and Operations |
|----------|------------------------|
| Kontakty | Kontakty w usłudze CDS           |
| Kontakty | Odbiorcy V2           |

## <a name="entity-flow"></a>Przepływ jednostek

Produkty są zarządzane w programie Sales i synchronizowane z programem Finance and Operations.

Kontakt w programie Sales może stać się kontaktem lub odbiorcą w programie Finance and Operations. Aby określić, czy kontakt w programie Sales ma być synchronizowany z programem Finance and Operations jako kontakt lub odbiorca, system sprawdza następujące właściwości kontaktu w programie Sales:

- **Synchronizacja z klientem w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają zaznaczoną wartość **Tak**
- **Synchronizacja z kontaktem w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają wartość **Nie**, a ustawienie **Firma** (konto nadrzędne/kontakt) wskazuje na konto (nie kontakt)

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Do kontaktu dodano nowe pole **Aktywny odbiorca**. To pole służy do rozróżniania między kontaktami, które mają działania sprzedaży, a kontaktami, które nie mają takich działań. Ustawienie **Aktywny odbiorca** ma wartość **Tak** tylko dla kontaktów, które mają powiązane oferty, zamówienia lub faktury. Tylko te kontakty są synchronizowane z programem Finance and Operations jako odbiorcy.

Do kontaktu dodano nowe pole **IsCompanyAnAccount**. To pole wskazuje, czy kontakt jest połączony z firmą (kontem nadrzędnym/kontaktem) o typie **Konto**. Ta informacja jest używana do identyfikowania kontaktów, które powinny być synchronizowane z programem Finance and Operations jako kontakty.

Do kontaktu dodano nowe pole **Numer osoby kontaktowej** w celu zagwarantowania naturalnego i unikatowego klucza integracji. Podczas tworzenia nowego kontaktu wartość w polu **Numer kontaktowy** jest generowany automatycznie przy użyciu ustalonej numeracji. Wartość składa się z przedrostka **CON**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka. Oto przykład: **CON-01000-BVRCPS**

Gdy rozwiązanie integracji dla programu Sales zostanie zastosowane, skrypt uaktualniania ustawia pole **Numer kontaktowy** dla istniejących kontaktów przy użyciu omówionej wcześniej numeracji. Skrypt uaktualniania ustawia również w polu **Aktywny odbiorca** wartość **Tak** dla wszystkich kontaktów mających działania sprzedaży.

## <a name="in-finance-and-operations"></a>W programie Finance and Operations

Kontakty są oznakowane za pomocą właściwości **IsContactPersonExternallyMaintained**. Ta właściwość wskazuje, że dany kontakt jest obsługiwany zewnętrznie. W takim przypadku zewnętrznie obsługiwane kontakty są prowadzone w aplikacji Sales.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

### <a name="contact-to-customer"></a>Kontakt > odbiorca

- Pole **CustomerGroup** jest wymagane w programie Finance and Operations. Aby ułatwić uniknięcie błędów synchronizacji, można określić wartość domyślną w mapowaniu. Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.

    Wartość domyślna w szablonie to **10**.

- Dodając następujące mapowania, można ograniczyć liczbę koniecznych ręcznych aktualizacji wykonywanych w programie Finance and Operations. Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.

    - **SiteId** — W programie Finance and Operations można również określić domyślny oddział. Oddział jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.

        Szablon nie ma zdefiniowanej domyślnej wartości pola **SiteID**.

    - **WarehouseId** — W programie Finance and Operations można również określić domyślny magazyn. Magazyn jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.

        Szablon nie ma zdefiniowanej domyślnej wartości pola **WarehouseId**.

    - **LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.
    
        Domyślna wartość pola w szablonie to **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Finance and Operations.

### <a name="contact-to-contact"></a>Kontakt > kontakt

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Kontakt > odbiorca

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Powiązane tematy

[Prospekt na gotówkę](prospect-to-cash.md)

[Synchronizowanie kont bezpośrednio w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping-direct.md)

[Synchronizowanie produktów bezpośrednio w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales](products-template-mapping-direct.md)

[Synchronizowanie nagłówków i wierszy zamówień sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-order-template-mapping-direct-two-ways.md)

[Synchronizowanie nagłówków i wierszy faktur sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)


