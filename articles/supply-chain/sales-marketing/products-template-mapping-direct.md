---
title: Synchronizowanie produktów bezpośrednio w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Sales.
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
ms.openlocfilehash: feb9fbc066162e2caa9fc5dbaeec2c063ae23060
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572611"
---
# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a>Synchronizowanie produktów w rozwiązaniu Finance and Operations bezpośrednio z produktami w rozwiązaniu Sales

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania procuktów bezpośrednio z Microsoft Dynamics 365 for Finance and Operations do Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracja danych do synchronizacji danych między wystąpieniami programu Finance and Operations a programem Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między programami Finance and Operations a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujący szablon i podstawowe zadania są używane do synchronizowania produktów z rozwiązania Finance and Operations do rozwiązania Sales.

- **Nazwa szablonu w integracji danych:** Produkty (Fin and Ops do Sales) — bezpośrednie
- **Nazwa zadania w projekcie integracji danych:** Produkty

Przed zsynchronizowaniem produktu nie jest wymagane wykonanie zadań synchronizacji.

## <a name="entity-set"></a>Zestaw jednostek

| Finance and Operations     | Sprzedaż    |
|----------------------------|----------|
| Zwolnione produkty możliwe do sprzedaży | Produkty |

## <a name="entity-flow"></a>Przepływ jednostek

Produkty są zarządzane w programie Finance and Operations i synchronizowane z programem Sales. Jednostka danych **Zwolnione produkty możliwe do sprzedaży** w rozwiązaniu Finance and Operations eksportuje tylko produkty, które są *możliwe do sprzedaży*. Produkty możliwe do sprzedaży to takie, które zawierają informacje wymagane w celu użycia w zamówieniu sprzedaży. Te same reguły mają zastosowanie podczas weryfikowania produktu przy użyciu funkcji **Sprawdzanie poprawności** na stronie **Zwolniony produkt**.

Numer produktu jest używany jako klucz. Dlatego po zsynchronizowaniu wariantów produktu z rozwiązaniem Sales każdy wariant produktu ma indywidualny identyfikator produktu.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

W rozwiązaniu Sales dodano nowe pole **Obsługiwane zewnętrznie** w produktach, co wskazuje, że dany produkt jest obsługiwany zewnętrznie. Domyślnie wartość jest ustawiana na **Tak** podczas importowania do rozwiązania Sales. Dostępne są następujące wartości:

- **Tak** — produkt pochodził z rozwiązania Finance and Operations i nie będzie można edytować w rozwiązaniu Sales.
- **Nie**— produkt wprowadzono bezpośrednio w rozwiązaniu Sales.
- **(Puste)** — produkt istniał w rozwiązaniu Sales przed włączeniem rozwiązania Prospekt na gotówkę.

Pole **Obsługiwane zewnętrznie** pomaga zagwarantować, że z rozwiązaniem Finance and Operations zostaną zsynchronizowane tylko oferty i zamówienia sprzedaży zawierające produkty obsługiwane zewnętrznie.

Zewnętrznie obsługiwane produkty są automatycznie dodawane do pierwszego prawidłowego cennika o tej samej walucie. Cenniki są ułożone alfabetycznie według nazwy. Cena sprzedaży produktu z rozwiązania Finance and Operations jest używana jako cena w cenniku. Dlatego w rozwiązaniu Sales musi istnieć cennik dla każdej waluty sprzedaży produktów w rozwiązaniu Finance and Operations. Jako waluta w zwalnianych produktach możliwych do sprzedaży jest ustawiana waluta rozliczeniowa firmy, z której produkty zostały wyeksportowane.

> [!NOTE]
> - Synchronizacja produktów nie powiedzie się, jeżeli nie będzie istniał cennik zawierający pasująca walutę.
> - Cennikami używanymi w integracji można sterować poprzez zamapowanie elementu pricelevelid.name [Cennik domyślny (nazwa)] w projekcie narzędzia Integracja danych. Dane wejściowe muszą zostać wprowadzone tylko małymi literami. Na przykład w module Sales wartość domyślna cennika o nazwie „Standardowy” byłaby następująca: Pole docelowe: pricelevelid.name [Cennik domyślny (nazwa)] i typ mapowania: [ { "transformType": "Domyślnie", "defaultValue": "standardowy" } ].

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

- Przed uruchomieniem pierwszej synchronizacji należy wypełnić tabelę odrębnych produktów dla istniejących produktów w rozwiązaniu Finance and Operations. Istniejące produkty będą synchronizowane dopiero po zakończeniu tego zadania.

    1. W programie Finance and Operations za pomocą funkcji wyszukiwania poszukaj opcji **Wypełnij tabelę odrębnych produktów**.
    2. Wybierz opcję **Wypełnij tabelę odrębnych produktów**, aby uruchomić zadanie. To zadanie należy uruchomić tylko raz.

- Upewnij się, że wymagana mapa wartości dla jednostki miary (JM) sprzedaży między rozwiązaniem Finance and Operations a rozwiązaniem Sales istnieje w mapowaniu wartości **SalesUnitSymbol** na **DefaultUnit (Nazwa)**.
- Zaktualizuj mapę wartości dla **grupy jednostek** (**defaultuomscheduleid.name**) tak, aby pasowała do **grupy jednostek** w rozwiązaniu Sales.

    Domyślna wartość szablonu to **Jednostka domyślna**.

- Upewnij się, że jednostki miar sprzedaży wszystkich produktów z rozwiązania Finance and Operations istnieją w rozwiązaniu Sales.
- Upewnij się, że cenniki istnieją w rozwiązaniu Sales dla każdej waluty sprzedaży produktów w rozwiązaniu Finance and Operations.
- Po utworzeniu produktów w rozwiązaniu Sales mogą mieć stan **Robocza** lub **Aktywne**. Zachowanie można kontrolować w oknie **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** w rozwiązaniu Sales.

    Produkty mają stan **Robocza** po utworzeniu i należy je uaktywnić przed dodaniem do ofert lub zamówień sprzedaży.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowania szablonu w integracji danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Finance and Operations.

![Mapowanie szablonu w integratorze danych](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Powiązane tematy

[Prospekt na gotówkę](prospect-to-cash.md)

[Synchronizowanie kont bezpośrednio w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations](accounts-template-mapping-direct.md)

[Synchronizowanie kontaktów bezpośrednio w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations](contacts-template-mapping-direct.md)

[Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations bezpośrednio z elementami w rozwiązaniu Sales](sales-order-template-mapping-direct-two-ways.md)

[Synchronizowanie nagłówków i wierszy faktur sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)



