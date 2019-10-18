---
title: Zlecenie wykonania dla wstępnej synchronizacji aplikacji Finance and Operations i Common Data Service
description: W tym temacie opisano kolejność synchronizacji obowiązującą podczas tworzenia danych początkowych.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 3110cb809558d168e9d97f640701b249caf73f6c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184515"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a>Zlecenie wykonania dla wstępnej synchronizacji aplikacji Finance and Operations i Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Przed użyciem integracji danych należy utworzyć początkowe dane, które są wymagane dla odbiorców, dostawców i kontaktów. Na przykład użytkownik chce utworzyć nowy towar **Grupy dostawców** i określić **Warunki płatności** jako **Net30**. W takim przypadku przed próbą utworzenia pozycji **Grupy dostawców** należy upewnić się, że **Net30** istnieje w obu aplikacjach i Common Data Service. (W przyszłości Microsoft udostępni funkcję platformy podwójnego zapisu o nazwie Synchronizacja początkowa. Będzie to jednorazowa synchronizacja danych między aplikacjami i Common Data Service w ramach konfiguracji podwójnego zapisu).

> [!TIP]
> Microsoft udostępnia mapę podwójnego zapisu dla wszystkich danych referencyjnych, w tym **Warunki płatności** (warunki płatności). Jeśli masz już dane początkowe w jednym systemie, operacja małej aktualizacji na rekordzie może wyzwolić podwójny zapisu w tym rekordzie.

Należy postępować zgodnie z poniższą kolejnością pierwszeństwa i upewnić się, że dane początkowe są dostępne zarówno w aplikacji, jak i w programie Common Data Service.

## <a name="vendor"></a>Dostawca

Oto kolejność wykonywania jednostki **Dostawca**:

1. Grupa dostawców

    1. Warunki płatności

        1. Dzień zapłaty i wiersze
        2. Harmonogram płatności

2. Metoda płatności dostawcy

## <a name="customer-organization"></a>Klient (Organizacja)

Oto kolejność wykonywania jednostki **Odbiorca**:

1. Grupa odbiorców

    1. Warunki płatności

        1. Dzień zapłaty i wiersze
        2. Płatność 

2. Metoda płatności odbiorcy

## <a name="contact-person"></a>Osoba kontaktowa (Osoba)

Oto kolejność wykonywania jednostki **Kontakt**:

1. Odbiorca
2. Dostawca
