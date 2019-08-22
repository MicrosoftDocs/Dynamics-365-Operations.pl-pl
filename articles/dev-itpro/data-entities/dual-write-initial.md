---
title: Zlecenie wykonania dla wstępnej synchronizacji programów Finance and Operations i Common Data Service
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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797305"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a>Zlecenie wykonania dla wstępnej synchronizacji programów Finance and Operations i Common Data Service

Przed użyciem integracji danych należy utworzyć początkowe dane wymagane dla odbiorców, dostawców i kontaktów. Na przykład, jeśli chcesz utworzyć nowy element **Grupa dostawców** i ustawić jego **Warunki płatności** jako **Net30**, przed podjęciem próby utworzenia elementu **Grupy dostawców** należy upewnić się, że **Net30** istnieje zarówno w programie Finance and Operations, jak i Common Data Service. (W przyszłości udostępnimy funkcję platformy podwójnego zapisu o nazwie **Synchronizacja początkowa**. Będzie to jednorazowa synchronizacja danych między programami Finance and Operations i Common Data Service w ramach konfiguracji podwójnego zapisu).

Wskazówki: udostępniamy mapę podwójnego zapisu dla wszystkich danych referencyjnych, w tym **Warunki płatności**. Jeśli masz już dane początkowe w jednym systemie, operacja małej aktualizacji na rekordzie może wyzwolić podwójny zapisu w tym rekordzie. 

Należy postępować zgodnie z poniższą kolejnością pierwszeństwa i upewnić się, że dane początkowe są dostępne zarówno w programie Finance and Operations, jak i w programie Common Data Service.   

## <a name="vendor"></a>Dostawca

Kolejność wykonywania dla dostawcy to:

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a>Klient (Organizacja)

Kolejność wykonywania dla klienta to:

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a>Osoba kontaktowa (Osoba)

Kolejność wykonywania dla osoby kontaktowej to:

```
Customer
Vendor               
```
