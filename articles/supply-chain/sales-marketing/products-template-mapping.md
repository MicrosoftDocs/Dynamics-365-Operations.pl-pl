---
title: "Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 063a20f133a00620bdf389b0a52a90bc61e2f7d4
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a>Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](/common-data-service/entity-reference/dynamics-365-integration). 

Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition a programem Microsoft Dynamics 365 for Sales.

## <a name="template-and-task"></a>Szablon i zadanie

Następujące szablony i podstawowe zadania są używane do synchronizowania produktów między programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations) a programem Microsoft Dynamics 365 for Sales (Sales).

-   Nazwa szablonu: Produkty (z Fin and Ops do Sales)

-   Nazwa zadania w projekcie: Produkty

Zadania synchronizacji wymagane przed synchronizacją produktu: brak

## <a name="entity-set"></a>Zestaw jednostek

| **Finance and Operations** | **CDS** | **Sprzedaż**  |
|----------------------------|---------|------------|
| Zwolnione produkty możliwe do sprzedaży | Produkt | Produkty   |

## <a name="entity-flow"></a>Przepływ jednostek

Produkty są zarządzane w programie Finance and Operations i synchronizowane z programem Sales. Jednostka danych **Zwolnione produkty możliwe do sprzedaży** w programie Finance and Operations powoduje eksportowanie tylko produktów, które można sprzedawać, co oznacza, że produkty muszą zawierać wymagane informacje, aby można ich było używać zamówieniach sprzedaży. Te same reguły mają zastosowanie podczas weryfikowania produktu za pomocą funkcji **Sprawdzanie poprawności** na stronie **Zwolniony produkt**.

Pole **Numer produktu** jest używane jako klucz, co oznacza, że warianty produktu są synchronizowane z usługą CDS i aplikacją Sales z osobnymi **identyfikatorami produktów** dla poszczególnych **wariantów produktu**.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

W aplikacji Sales dodano dla produktów nowe pole **Obsługiwane zewnętrznie**, co wskazuje, że dany produkt jest obsługiwany zewnętrznie. Wartość jest ustawiana na **Tak** domyślnie podczas importowania do aplikacji Sales.

-   **Obsługiwane zewnętrznie = Tak**: produkt pochodzi z programu Finance and Operations i nie będzie go można edytować w programie Sales.

-   **Obsługiwane zewnętrznie = Nie**: produkt jest wprowadzany bezpośrednio w aplikacji Sales.

-   **Obsługiwane zewnętrznie = puste**: produkt istnieje w programie Sprzedaż przed włączeniem rozwiązania Prospekt na gotówkę.

Informacja **Obsługiwane zewnętrznie** jest używana do zagwarantowania, że tylko **oferty** i **zamówienia sprzedaży** zawierające **zewnętrznie obsługiwane produkty** będą synchronizowane z programem Finance and Operations.

**Zewnętrznie obsługiwane produkty** są automatycznie dodawane do pierwszego prawidłowego **cennika** o tej samej walucie. Należy zauważyć, że lista jest uporządkowana w kolejności alfabetycznej według parametru **Nazwa**. Cena sprzedaży produktu z programu Finance and Operations jest używana jako cena w **cenniku**. Oznacza to, że trzeba mieć **cennik** w aplikacji Sales dla każdej **waluty sprzedaży produktu** w programie Finance and Operations. Jako waluta w zwalnianych produktach możliwych do sprzedaży jest ustawiana waluta rozliczeniowa firmy, z której produkty zostały wyeksportowane.

> [!NOTE]
> Synchronizacja produktów nie uda się bez **cennika** ze zgodną walutą.

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

-   Przed uruchomieniem pierwszej synchronizacji należy wypełnić **tabelę odrębnych produktów** dla istniejących produktów w programie Finance and Operations. Istniejące produkty będą synchronizowane dopiero po zakończeniu tego zadania.

    -   W programie Finance and Operations za pomocą funkcji wyszukiwania poszukaj opcji **Wypełnij tabelę odrębnych produktów**.

    -   Kliknij opcję **Wypełnij tabelę odrębnych produktów**, aby uruchomić zadanie. To zadanie trzeba wykonać tylko raz.

-   Upewnij się, że niezbędna **mapa wartości** dla **jednostki miary** sprzedaży w programie Finance and Operations istnieje w **mapowaniu Źródło -\> CDS SalesUnitSymbol/DefaultSellingUnitOfMeasure**.

-   Zaktualizuj pole **Identyfikator organizacji CDS Organization_OrganizationId** w mapowaniu **Źródło -\> CDS**.

    -   Wartość domyślna w szablonie to ORG001.

-   Zaktualizuj **mapę wartości** dla **grupy jednostek** (**defaultuomscheduleid.name**) w mapowaniu **CDS -\> Miejsce docelowe**, aby pasowała do **grupy jednostek** w aplikacji Sales.

    -   Wartość domyślna w szablonie to **Jednostka domyślna**.

-   Upewnij się, że jednostki miar wszystkich sprzedawanych produktów z programu Finance and Operations istnieją w aplikacji Sales z wartością **Listy wyboru w usłudze CDS**.

-   Upewnij się, że **cenniki** istnieją w aplikacji Sales dla każdej waluty sprzedaży produktów w programie Finance and Operations.

-   Produkty można tworzyć w aplikacji Sales ze stanem **Wersja robocza** lub **Aktywny**. Można to kontrolować w oknie **Ustawienia systemowe** w obszarze **Sprzedaż** w aplikacji Sales.

    -   Produkty utworzone w stanie Wersja robocza muszą zostać uaktywnione, zanim będzie je można dodać do **oferty** lub **zamówienia sprzedaży**.

## <a name="template-mapping-in-data-integrator"></a>Mapowanie szablonu w integratorze danych

Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.

![mapowanie szablonu w integratorze danych](./media/products-template-mapping-data-integrator-1.png)

![mapowanie szablonu dla produktów w integratorze danych](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Powiązane tematy

[Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping.md)

[Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations](sales-quotation-template-mapping.md)

[Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-order-template-mapping.md)

[Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-invoice-template-mapping.md)


