---
title: "Synchronizowanie nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
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
ms.openlocfilehash: c8cfc484eed02423dbf0c7caaf8ac2337b6ac38d
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a>Synchronizowanie nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](/common-data-service/entity-reference/dynamics-365-integration). 

Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations). 

## <a name="template-and-tasks"></a>Szablon i zadania

Następujące szablony i podstawowe zadania są używane do synchronizowania nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations:

- **Nazwa szablonu:** Oferty sprzedaży (z Sales do Fin and Ops)
- **Nazwy zadań w projekcie:**

    - QuoteHeader
    - QuoteLine

Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze ofert sprzedaży:

- Produkty (z Fin and Ops do Sales)
- Konta (Sales do Fin and Ops) (jeśli są używane)
- Kontakty z odbiorcami (z Sales do Fin and Ops) (jeśli używane)

## <a name="entity-set"></a>Zestaw jednostek

| Sprzedaż        | CDS           | Finance and Operations    |
|--------------|---------------|---------------------------|
| Cytaty       | Oferta     | Nagłówki ofert sprzedaży   |
| QuoteDetails | QuotationLine | Wiersze oferty sprzedaży CDS |

## <a name="entity-flow"></a>Przepływ jednostek

Oferty sprzedaży są tworzone w programie Sales i synchronizowane z programem Finance and Operations.

Oferty sprzedaży z programu Sales są synchronizowane tylko wtedy, gdy są spełnione następujące warunki:

- Wszystkie produkty w wierszach oferty sprzedaży są obsługiwane zewnętrznie.
- Oferta sprzedaży jest aktywna lub aktywowana.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

Pole **Zawiera tylko zewnętrznie obsługiwane produkty** zostało dodane do jednostki Oferta w celu umożliwienia ciągłego śledzenia, czy oferta sprzedaży zawiera wyłącznie zewnętrznie obsługiwane produkty. Jeśli oferta sprzedaży ma tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Finance and Operations. To zachowanie pomaga zagwarantować, że nie będziesz próbować zsynchronizować wierszy oferty sprzedaży z produktami nieznanymi programowi Finance and Operations.

Wszystkie produkty i wiersze w ofercie są aktualizowane przy użyciu informacji **Zawiera tylko zewnętrznie obsługiwane produkty** z nagłówka oferty. Ta informacja znajduje się w polu **Oferta zawiera tylko zewnętrznie obsługiwane produkty** w jednostce Wiersz oferty.

Pola **Rabat**, **Opłaty** i **Podatek** są kontrolowane przez skomplikowaną konfigurację w programie Finance and Operations. Ta konfiguracja obecnie nie obsługuje mapowanie integracji. W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są zarządzane i obsługiwane przez program Finance and Operations.

W programie Sales wymienione pola są tylko do odczytu, ponieważ ich wartości nie są synchronizowane z programem Finance and Operations:

- **Pola tylko do odczytu w nagłówku oferty sprzedaży:** % rabatu, Rabat, Kwota frachtu
- **Pola tylko do odczytu w wierszach oferty sprzedaży:** Podatek

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować w systemach następujące ustawienie:

### <a name="setup-in-sales"></a>Konfiguracja w programie Sales

- Wybierz kolejno opcje **Ustawienia** &gt; **Administracja** &gt; **Ustawienia systemowe** &gt; **Sprzedaż** i upewnij się, że w polu **Metoda kalkulacji rabatów** jest ustawiona wartość **Na jednostkę**. To ustawienie pomaga zagwarantować, że rabat wiersza w programie Sales jest zgodny z ustawieniem w programie Finance and Operations. W przeciwnym wypadku rabat nie będzie poprawny w programie Finance and Operations, ponieważ program Finance and Operations odczyta rabat jako przyznany na jednostkę, nawet jeśli w programie Sales był on przyznany dla wiersza.

### <a name="setup-in-finance-and-operations"></a>Konfiguracja w programie Finance and Operations

- Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**. Na karcie **Sekwencja numerów** wybierz numerację ofert sprzedaży, a następnie kliknij przycisk **Wyświetl szczegóły**. Następnie w obszarze **Konfiguracja ogólna** w polu **Ręcznie** ustaw wartość **Tak**.
- Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**. Następnie na karcie **Wysyłki** w polu **Kontrola daty dostawy** ustaw wartość **Brak**. To ustawienie pomaga zapobiec niepowodzeniom synchronizacji ofert sprzedaży.

### <a name="setup-in-the-data-integration-project"></a>Konfiguracja w projekcie integracji danych

#### <a name="quoteheader"></a>QuoteHeader

- Pole **Wymagana data dostawy** jest wymagane w programie Finance and Operations i gdy jest puste, synchronizacja nie będzie działać. Aby uniknąć tego problemu, gdy to pole jest puste, domyślna data jest pobierana z ustawienia **Źródło &gt; CDS**. W miejsce tej domyślnej daty należy wpisać preferowaną przez siebie wartość. Obecnie nie można wprowadzić wartości takiej jak **Dzisiaj** w celu reprezentowania dzisiejszej daty. Należy wprowadzić konkretną datę. Domyślną wartością pola **Wymagana data dostawy** w szablonie jest **1/1/2020**.
- Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations. Aby uniknąć błędów synchronizacji, można określić wartość domyślną, która będzie używana, jeśli pole jest puste w programie Sales. Ta wartość domyślna jest również przydatna, ponieważ nie trzeba ręcznie wprowadzać wartości w polu **Kraj/region** w lokalnych adresach. Nie istnieje domyślna wartość szablonu dla ustawienia **DeliveryAddressCountryRegionISOCode**.
- Zaktualizuj mapowanie dla pola **Identyfikator organizacji CDS** w ustawieniu **Źródło &gt; CDS**, tak aby pasowało do ustawienia **Organizacja CDS** w jednostce Organizacja:

    - Domyślna wartość pola **Organization_OrganizationId** w szablonie to **ORG001**.
    - Domyślna wartość pola **Account_Organization_OrganizationId** w szablonie to **ORG001**.
    - Domyślna wartość pola **InvoiceAccount_OrganizationId** w szablonie to **ORG001**.

#### <a name="quoteline"></a>QuoteLine

- Zaktualizuj mapowanie dla pola **Identyfikator organizacji CDS** w ustawieniu **Źródło &gt; CDS**, tak aby pasowało do ustawienia **Organizacja CDS** w jednostce Organizacja:

    - Domyślna wartość pola **Organization_OrganizationId** w szablonie to **ORG001**.
    - Domyślna wartość pola **Product_Organization_Organization_OrganizationId** w szablonie to **ORG001**.
    - Domyślna wartość pola **Quotation_Organization_Organization_OrganizationId** w szablonie to **ORG001**.

- Pole **Wymagana data dostawy** jest wymagane w programie Finance and Operations i gdy jest puste, synchronizacja nie będzie działać. Aby uniknąć tego problemu, gdy to pole jest puste, domyślna data jest pobierana z ustawienia **Źródło &gt; CDS**. W miejsce tej domyślnej daty należy wpisać preferowaną przez siebie wartość. Obecnie nie można wprowadzić wartości takiej jak **Dzisiaj** w celu reprezentowania dzisiejszej daty. Należy wprowadzić konkretną datę. Domyślną wartością pola **Wymagana data dostawy** w szablonie jest **1/1/2020**.
- Można dodać następujące mapowanie z ustawienia **CDS &gt; Miejsce docelowe** w celu zagwarantowania, że wiersze oferty są importowane do programu Finance and Operations w razie braku domyślnych informacji o odbiorcy lub produkcie:

    - **SiteId** — Oddział jest konieczny do generowania ofert i wierszy zamówień sprzedaży w programie Finance and Operations. Nie istnieje domyślna wartość szablonu dla pola **SiteId**.
    - **WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w programie Finance and Operations. Nie istnieje domyślna wartość szablonu dla pola **WarehouseId**.

- Upewnij się, że wymagana mapa wartości dla jednostki miary (JM) sprzedaży w programie Finance and Operations istnieje w mapowaniu **CDS &gt; Miejsce docelowe** między elementem **Quantity_UOM** a elementem **SALESUNITSYMBOL**.

## <a name="template-mapping-in-data-integrator"></a>Mapowanie szablonu w integratorze danych

> [!NOTE]
> - Pola **Rabat**, **Opłaty** i **Podatek** są kontrolowane przez skomplikowaną konfigurację w programie Finance and Operations. Ta konfiguracja obecnie nie obsługuje mapowanie integracji. W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są obsługiwane przez program Finance and Operations.
> - Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań. Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

### <a name="quoteheader"></a>QuoteHeader

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a>QuoteLine

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Powiązane tematy

[Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales](products-template-mapping.md)

[Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping.md)



