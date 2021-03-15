---
title: Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów z Dynamics 365 Supply Chain Management do Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: ecee843b6c09c86b4e40ab34cc113e5a7e7c76f8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977695"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).

W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania produktów bezpośrednio z Dynamics 365 Supply Chain Management do Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Przepływ danych w rozwiązaniu Prospekt na gotówkę

Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales. Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales. Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.

[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Szablony i zadania

Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi Power Apps](https://admin.powerapps.com/dataintegration). Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.

Następujący szablon i podstawowe zadanie są używane do synchronizowania kont klientów z usługi Supply Chain Management do Sales:

- **Nazwa szablonu w integracji danych:** Produkty (Supply Chain Management do Sales) — bezpośrednie
- **Nazwa zadania w projekcie integracji danych:** Produkty

Przed zsynchronizowaniem produktu nie jest wymagane wykonanie zadań synchronizacji.

## <a name="entity-set"></a>Zestaw jednostek

| Zarządzanie łańcuchem dostaw    | Sprzedaż    |
|----------------------------|----------|
| Zwolnione produkty możliwe do sprzedaży | Produkty |

## <a name="entity-flow"></a>Przepływ jednostek

Produlty są zarządzane w usłudze Supply Chain Management i synchronizowane z usługą Sales. Jednostka danych **Zwolnione produkty możliwe do sprzedaży** w rozwiązaniu Supply Chain Management eksportuje tylko produkty, które są *możliwe do sprzedaży*. Produkty możliwe do sprzedaży to takie, które zawierają informacje wymagane w celu użycia w zamówieniu sprzedaży. Te same reguły mają zastosowanie podczas weryfikowania produktu przy użyciu funkcji **Sprawdzanie poprawności** na stronie **Zwolniony produkt**.

Numer produktu jest używany jako klucz. Dlatego po zsynchronizowaniu wariantów produktu z rozwiązaniem Sales każdy wariant produktu ma indywidualny identyfikator produktu.

## <a name="prospect-to-cash-solution-for-sales"></a>Rozwiązanie Prospekt na gotówkę dla aplikacji Sales

W rozwiązaniu Sales dodano nowe pole **Obsługiwane zewnętrznie** w produktach, co wskazuje, że dany produkt jest obsługiwany zewnętrznie. Domyślnie wartość jest ustawiana na **Tak** podczas importowania do rozwiązania Sales. Dostępne są następujące wartości:

- **Tak** — Produkt pochodził z rozwiązania Supply Chain Management i nie będzie można edytować w rozwiązaniu Sales.
- **Nie**— produkt wprowadzono bezpośrednio w rozwiązaniu Sales.
- **(Puste)** — produkt istniał w rozwiązaniu Sales przed włączeniem rozwiązania Prospekt na gotówkę.

Pole **Obsługiwane zewnętrznie** pomaga zagwarantować, że z rozwiązaniem Supply Chain Management zostaną zsynchronizowane tylko oferty i zamówienia sprzedaży zawierające produkty obsługiwane zewnętrznie.

Zewnętrznie obsługiwane produkty są automatycznie dodawane do pierwszego prawidłowego cennika o tej samej walucie. Cenniki są ułożone alfabetycznie według nazwy. Cena sprzedaży produktu z rozwiązania Supply Chain Management jest używana jako cena w cenniku. Dlatego w rozwiązaniu Sales musi istnieć cennik dla każdej waluty sprzedaży produktów w rozwiązaniu Supply Chain Management. Jako waluta w zwalnianych produktach możliwych do sprzedaży jest ustawiana waluta rozliczeniowa firmy, z której produkty zostały wyeksportowane.

> [!NOTE]
> - Synchronizacja produktów nie powiedzie się, jeżeli nie będzie istniał cennik zawierający pasująca walutę.
> - Cennikami używanymi w integracji można sterować poprzez zamapowanie elementu pricelevelid.name [Cennik domyślny (nazwa)] w projekcie narzędzia Integracja danych. Dane wejściowe muszą zostać wprowadzone tylko małymi literami. Na przykład w module Sales wartość domyślna cennika o nazwie „Standardowy” byłaby następująca: Pole docelowe: pricelevelid.name [Cennik domyślny (nazwa)] i typ mapowania: [ { "transformType": "Domyślnie", "defaultValue": "standardowy" } ].

## <a name="preconditions-and-mapping-setup"></a>Warunki wstępne i ustawienia mapowania

- Przed uruchomieniem pierwszej synchronizacji należy wypełnić tabelę odrębnych produktów dla istniejących produktów w rozwiązaniu Supply Chain Management. Istniejące produkty będą synchronizowane dopiero po zakończeniu tego zadania.

    1. W programie Supply Chain Management za pomocą funkcji wyszukiwania poszukaj opcji **Wypełnij tabelę odrębnych produktów**.
    2. Wybierz opcję **Wypełnij tabelę odrębnych produktów**, aby uruchomić zadanie. To zadanie należy uruchomić tylko raz.

- Upewnij się, że wymagana mapa wartości dla jednostki miary (JM) sprzedaży między rozwiązaniem Supply Chain Management a rozwiązaniem Sales istnieje w mapowaniu wartości **SalesUnitSymbol** na **DefaultUnit (Nazwa)**.
- Zaktualizuj mapę wartości dla **grupy jednostek** (**defaultuomscheduleid.name**) tak, aby pasowała do **grupy jednostek** w rozwiązaniu Sales.

    Domyślna wartość szablonu to **Jednostka domyślna**.

- Upewnij się, że jednostki miar sprzedaży wszystkich produktów z rozwiązania Supply Chain Management istnieją w rozwiązaniu Sales.
- Upewnij się, że cenniki istnieją w rozwiązaniu Sales dla każdej waluty sprzedaży produktów w rozwiązaniu Supply Chain Management.
- Po utworzeniu produktów w rozwiązaniu Sales mogą mieć stan **Robocza** lub **Aktywne**. Zachowanie można kontrolować w oknie **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** w rozwiązaniu Sales.

    Produkty mają stan **Robocza** po utworzeniu i należy je uaktywnić przed dodaniem do ofert lub zamówień sprzedaży.

## <a name="template-mapping-in-data-integration"></a>Mapowanie szablonu w integracji danych

Poniższa ilustracja przedstawia przykład mapowania szablonu w integracji danych. 

> [!NOTE]
> Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.

![Mapowanie szablonu w integratorze danych](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Powiązane tematy

[Od prospekta do gotówki](prospect-to-cash.md)

[Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management](accounts-template-mapping-direct.md)

[Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management](contacts-template-mapping-direct.md)

[Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]