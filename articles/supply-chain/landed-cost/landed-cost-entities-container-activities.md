---
title: Jednostki działań kontenera
description: Ten artykuł dostarcza informacji o aktywnościach kontenera, które są używane do śledzenia postępu wysyłki kontenerów.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: b69d26ee8abaa403f6a0ef3b03d9015fe507dd5b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873964"
---
# <a name="container-activities-entity"></a>Encja działań kontenerowych

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Aktywności kontenerowe służą do śledzenia postępów w wysyłce kontenerów. Dla każdego etapu tworzony jest rekord, który jest przypisany do szablonu podróży wybranego w czasie tworzenia kontenera wysyłkowego. Rekordy są tworzone także wtedy, gdy pojemnik wysyłkowy jest tworzony przez jednostkę danych.

Informacje o postępach w transporcie kontenera morskiego są często otrzymywane z zewnętrznego źródła. Jednostka aktywności kontenera pozwala zewnętrznemu źródłu, takiemu jak spedytor, na bezpośrednią aktualizację rekordu. Dlatego nie jest wymagana ręczna aktualizacja danych.

## <a name="container-activities-itmcontaineractivityentity"></a>Kontenerowe aktywności (ITMContainerActivityEntity)

Możesz użyć encji aktywności kontenera (`ITMContainerActivityEntity`), aby utworzyć dodatkowe rekordy aktywności. Alternatywnie, spedytor może przekazywać aktualizacje dla potwierdzonej wartości **Faktycznej daty końcowej**.

| Nazwisko | Mapowanie | Typ danych | Klucz | Wymagana |
|---|---|---|---|---|
| Rzeczywista data zakończenia | ITMContainerActivityTable.ActualEndDate | Data/godzina | Nie | Nie |
| Metoda dostawy | ITMContainerActivityTable.DlvModeId | Nvarchar(10) | Nie | Nie |
| Szacowana data końcowa | ITMContainerActivityTable.EsimatedDate | Data/godzina | Nie | Nie |
| Numer wiersza | ITMContainerActivityTable.LineNum | Numeric(32, 16) | **Tak** | Nie |
| Notatki | ITMContainerActivityTable.Notes | nvarchar(MAX) | Nie | Nie |
| Działanie | ITMContainerActivityTable.ShipActivityId | Nvarchar(10) | Nie | **Tak** |
| Kontener wysyłkowy | ITMContainerActivityTable.ShipContainerId | Nvarchar(20) | **Tak** | **Tak** |
| Podróż | ITMContainerActivityTable.ShipId | Nvarchar(20) | **Tak** | **Tak** |
| Etap | ITMContainerActivityTable.ShipLegId | Nvarchar(20) | Nie | **Tak** |
| Dostawca usługi | ITMContainerActivityTable.ShipServiceProvider | Nvarchar(20) | Nie | Nie |
| Temperatura | ITMContainerActivityTable.ShipTemperature | Numeric(32, 6) | Nie | Nie |
| Statek | ITMContainerActivityTable.ShipVesselId | Nvarchar(20) | Nie | Nie |
| Data początkowa | ITMContainerActivityTable.StartDate | Data/godzina | Nie | Nie |

## <a name="tracking-control"></a>Kontrola śledzenia

Centrum kontroli śledzenia umożliwia, by aktualizacja określonego pola źródłowego została wywołana przez aktualizację określonego pola docelowego. Jeśli zarówno wartość pola źródłowego, jak i wartość pola docelowego zostaną zaktualizowane przy użyciu encji aktywności kontenera, pole docelowe będzie zawierało wartość encji. To zachowanie jest związane z rekordami kontroli śledzenia, które mają **Typ tworzenia** o wartości *Czas realizacji*.

Dla obszarów kosztów, które mają **Typ tworzenia** o wartości *Aktualizacja statusu* lub *Puste* (co jest wartością zdefiniowaną przez użytkownika), system zaktualizuje status rejsu lub pole celu zgodnie z konfiguracją kontroli śledzenia.

## <a name="calculated-fields"></a>Pola obliczeniowe

Wartości poniższych pól w rekordzie aktywności kontenera są obliczane na podstawie wartości innych pól. Chociaż te pola obliczeniowe nie są zawarte w encji danych, zostaną ustawione, jeśli zostaną podane pola, na których opierają się obliczenia.

- **Oszacowane dni** = **Szacowana data końcowa** – **Data początkowa**
- **Rzeczywista dni** = **Rzeczywista data zakończenia** – **Data rozpoczęcia**
