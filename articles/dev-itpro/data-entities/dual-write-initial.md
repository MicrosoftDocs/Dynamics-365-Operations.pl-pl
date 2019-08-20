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
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="9e97f-103">Zlecenie wykonania dla wstępnej synchronizacji programów Finance and Operations i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="9e97f-103">Execution order for initial sychronization of Finance and Operations and Common Data Service</span></span>

<span data-ttu-id="9e97f-104">Przed użyciem integracji danych należy utworzyć początkowe dane wymagane dla odbiorców, dostawców i kontaktów.</span><span class="sxs-lookup"><span data-stu-id="9e97f-104">Before you use data integration, you must create the initial data required for customers, vendors and contacts.</span></span> <span data-ttu-id="9e97f-105">Na przykład, jeśli chcesz utworzyć nowy element **Grupa dostawców** i ustawić jego **Warunki płatności** jako **Net30**, przed podjęciem próby utworzenia elementu **Grupy dostawców** należy upewnić się, że **Net30** istnieje zarówno w programie Finance and Operations, jak i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9e97f-105">For example, if you want to create a new **Vendor group** item and set its **Terms of Payment** as **Net30**, then before you attempt to create the **Vendor group** item you need to make sure that **Net30** exists in both Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="9e97f-106">(W przyszłości udostępnimy funkcję platformy podwójnego zapisu o nazwie **Synchronizacja początkowa**. Będzie to jednorazowa synchronizacja danych między programami Finance and Operations i Common Data Service w ramach konfiguracji podwójnego zapisu).</span><span class="sxs-lookup"><span data-stu-id="9e97f-106">(In the future, we will release a  dual-write platform functionality called **Initial Sync**. It will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

<span data-ttu-id="9e97f-107">Wskazówki: udostępniamy mapę podwójnego zapisu dla wszystkich danych referencyjnych, w tym **Warunki płatności**.</span><span class="sxs-lookup"><span data-stu-id="9e97f-107">Tips: We are releasing a dual-write map for all reference data including **Terms of Payment** (Payment Terms).</span></span> <span data-ttu-id="9e97f-108">Jeśli masz już dane początkowe w jednym systemie, operacja małej aktualizacji na rekordzie może wyzwolić podwójny zapisu w tym rekordzie.</span><span class="sxs-lookup"><span data-stu-id="9e97f-108">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span> 

<span data-ttu-id="9e97f-109">Należy postępować zgodnie z poniższą kolejnością pierwszeństwa i upewnić się, że dane początkowe są dostępne zarówno w programie Finance and Operations, jak i w programie Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9e97f-109">You must follow the following order of precedence and make sure that the initial data is available on both Finance and Operations and Common Data Service.</span></span>   

## <a name="vendor"></a><span data-ttu-id="9e97f-110">Dostawca</span><span class="sxs-lookup"><span data-stu-id="9e97f-110">Vendor</span></span>

<span data-ttu-id="9e97f-111">Kolejność wykonywania dla dostawcy to:</span><span class="sxs-lookup"><span data-stu-id="9e97f-111">The order of execution for Vendor is:</span></span>

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a><span data-ttu-id="9e97f-112">Klient (Organizacja)</span><span class="sxs-lookup"><span data-stu-id="9e97f-112">Customer (Organization)</span></span>

<span data-ttu-id="9e97f-113">Kolejność wykonywania dla klienta to:</span><span class="sxs-lookup"><span data-stu-id="9e97f-113">The order of execution for Customer is:</span></span>

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a><span data-ttu-id="9e97f-114">Osoba kontaktowa (Osoba)</span><span class="sxs-lookup"><span data-stu-id="9e97f-114">Contact (Person)</span></span>

<span data-ttu-id="9e97f-115">Kolejność wykonywania dla osoby kontaktowej to:</span><span class="sxs-lookup"><span data-stu-id="9e97f-115">The order of execution for Contact is:</span></span>

```
Customer
Vendor               
```
