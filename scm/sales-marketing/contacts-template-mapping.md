---
title: "Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kontaktów (kontaktów) i kontaktów (odbiorców) między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 7a856a9460d092925a34a0733f37f89354c2ddf1
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania jednostek Kontakt (kontaktów) i kontaktów (odbiorców) między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations).

## <a name="templates-and-tasks"></a>Szablony i zadania

Następujące szablony i podstawowe zadania są używane do synchronizowania kontaktów (kontaktów) w programie Sales z kontaktami (odbiorcami) w programie Finance and Operations:

- **Nazwy szablonów:**

    - Kontakty z kontaktami (z Sales do Fin and Ops)
    - Kontakty z odbiorcami (z Sales do Fin and Ops)

- **Nazwy zadań w projekcie:**

    - Kontakty
    - ContactToCustomer

Przed rozpoczęciem synchronizowania kontaktów należy wykonać następujące zadanie synchronizacji: Konta (z Sales do Fin and Ops)

## <a name="entity-sets"></a>Zestawy jednostek

| Sprzedaż    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Kontakty | Kontakt | Kontakty w usłudze CDS           |
| Kontakty | Konto | Odbiorcy V2           |

## <a name="entity-flow"></a>Przepływ jednostek

Kontakty są zarządzane w programie Sales oraz synchronizowane z usługą Common Data Service (CDS) i programem Finance and Operations.

Kontakt w programie Sales może stać się kontaktem w usłudze CDS i programie Finance and Operations. Alternatywnie może się stać kontem klienta w usłudze CDS i programie Finance and Operations. Aby ustalić, czy kontakt powinien zostać pobrany w programie Sales w celu synchronizacji z usługą CDS i programem Finance and Operations (na przykład kontakty z okna Sprzedaż &gt; Kontakt do okna CDS &gt; Kontakty i do programu Finance and Operations), system analizuje następujące właściwości kontaktu w programie Sales:

- **Synchronizacja z kontem klienta w usłudze CDS i odbiorcą w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają zaznaczoną wartość **Tak**
- **Synchronizacji z kontaktami w usłudze CDS i kontaktami w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają wartość **Nie**, a ustawienie **Firma** (konto nadrzędne/kontakt) wskazuje konto klienta (nie kontakt)

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales 

Do kontaktu dodano nowe pole **Aktywny odbiorca**. To pole służy do rozróżniania między kontaktami, które mają działania sprzedaży, a kontaktami, które nie mają takich działań. Ustawienie **Aktywny odbiorca** ma wartość **Tak** tylko dla kontaktów, które mają powiązane oferty, zamówienia lub faktury. Tylko te kontakty są synchronizowane z programem Finance and Operations jako odbiorcy.

Do kontaktu dodano nowe pole **IsCompanyAnAccount**. To pole wskazuje, czy kontakt jest połączony z firmą (kontem nadrzędnym/kontaktem) o typie **Konto**. Ta informacja jest używana do identyfikowania kontaktów, które powinny być synchronizowane z programem Finance and Operations jako kontakty.

Do kontaktu dodano nowe pole **Numer osoby kontaktowej** w celu zagwarantowania naturalnego i unikatowego klucza integracji. Podczas tworzenia nowego kontaktu wartość w polu **Numer kontaktowy** jest generowany automatycznie przy użyciu ustalonej numeracji. Wartość składa się z przedrostka **CON**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka. Oto przykład: **CON-01000-BVRCPS**

Gdy rozwiązanie integracji dla programu Sales zostanie dodane do programu Sprzedaż, skrypt uaktualniania ustawia pole **Numer kontaktowy** dla istniejących kontaktów przy użyciu omówionej wcześniej numeracji. Skrypt uaktualniania ustawia również w polu **Aktywny odbiorca** wartość **Tak** dla wszystkich kontaktów mających działania sprzedaży.

## <a name="in-finance-and-operations"></a>W programie Finance and Operations 

Kontakty są oznakowane za pomocą właściwości **IsContactPersonExternallyMaintained**. Ta właściwość wskazuje, że dany kontakt jest obsługiwany zewnętrznie. W takim przypadku zewnętrznie obsługiwane kontakty są prowadzone w aplikacji Sales.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

### <a name="contact-to-contact"></a>Kontakt > kontakt

- Zaktualizuj pole **Identyfikator organizacji CDS** w mapowaniu **Źródło &gt; CDS**.

    - Domyślna wartość pola **Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.
    - Domyślna wartość pola **PrimaryAccount_Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.

- Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations. Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Operacje**. Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales. Domyślną wartością pola **PrimaryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.
- Upewnij się, że w programie Finance and Operations istnieje wartość następującego pola. Jeśli informacja nie jest wymagana w programie Finance and Operations, można usunąć mapowanie z mapowania **CDS &gt; Miejsce docelowe**.

    - **Nazwa pola w programie Finance and Operations:** Decyzja
    - **Mapowanie:** PrimaryAccountRole = DecisionMakingRole

### <a name="contact-to-customer"></a>Kontakt > odbiorca

- Zaktualizuj pole **Identyfikator organizacji CDS** w mapowaniu **Źródło &gt; CDS**. Domyślna wartość pola **Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.
- Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations. Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Miejsce docelowe**. Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales. Domyślną wartością pola **PrimaryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.
- Pole **CustomerGroup** jest wymagane w programie Finance and Operations. Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Miejsce docelowe**. Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales. Domyślną wartością pola **CustomerGroupId** w szablonie jest **10**.
- Dodając następujące mapowania z okna **CDS &gt; Miejsce docelowe**, można ograniczyć liczbę ręcznych aktualizacji wykonywanych w programie Finance and Operations. Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.

    - **SiteId** — W programie Finance and Operations można również określić domyślny oddział. Oddział jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations. Szablon nie ma zdefiniowanej domyślnej wartości pola **SiteID**.
    - **WarehouseId** — W programie Finance and Operations można również określić domyślny magazyn. Magazyn jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations. Szablon nie ma zdefiniowanej domyślnej wartości pola **WarehouseId**.
    - **LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations. Domyślna wartość pola **LanguageId** w szablonie to **en-us**.

## <a name="template-mapping-in-data-integrator"></a>Mapowanie szablonu w integratorze danych

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

### <a name="contact-to-contact"></a>Kontakt > kontakt

![Mapowanie szablonu w integratorze danych](./media/contacts-template-mapping-data-integrator-1.png)

![Mapowanie szablonu dla kontaktów w integratorze danych](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a>Kontakt > odbiorca

![Mapowanie szablonu w integratorze danych](./media/contacts-template-mapping-data-integrator-3.png)

![Mapowanie szablonu dla kontaktów w integratorze danych](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Powiązane tematy

[Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales](products-template-mapping.md)

[Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping.md)

[Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations](sales-quotation-template-mapping.md)

