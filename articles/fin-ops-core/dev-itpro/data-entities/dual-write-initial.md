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
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="4d3b1-103">Zlecenie wykonania dla wstępnej synchronizacji aplikacji Finance and Operations i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="4d3b1-103">Execution order for initial synchronization of Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="4d3b1-104">Przed użyciem integracji danych należy utworzyć początkowe dane, które są wymagane dla odbiorców, dostawców i kontaktów.</span><span class="sxs-lookup"><span data-stu-id="4d3b1-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="4d3b1-105">Na przykład użytkownik chce utworzyć nowy towar **Grupy dostawców** i określić **Warunki płatności** jako **Net30**.</span><span class="sxs-lookup"><span data-stu-id="4d3b1-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="4d3b1-106">W takim przypadku przed próbą utworzenia pozycji **Grupy dostawców** należy upewnić się, że **Net30** istnieje w obu aplikacjach i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4d3b1-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both the application and Common Data Service.</span></span> <span data-ttu-id="4d3b1-107">(W przyszłości Microsoft udostępni funkcję platformy podwójnego zapisu o nazwie Synchronizacja początkowa. Będzie to jednorazowa synchronizacja danych między aplikacjami i Common Data Service w ramach konfiguracji podwójnego zapisu).</span><span class="sxs-lookup"><span data-stu-id="4d3b1-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between the application and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="4d3b1-108">Microsoft udostępnia mapę podwójnego zapisu dla wszystkich danych referencyjnych, w tym **Warunki płatności** (warunki płatności).</span><span class="sxs-lookup"><span data-stu-id="4d3b1-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="4d3b1-109">Jeśli masz już dane początkowe w jednym systemie, operacja małej aktualizacji na rekordzie może wyzwolić podwójny zapisu w tym rekordzie.</span><span class="sxs-lookup"><span data-stu-id="4d3b1-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="4d3b1-110">Należy postępować zgodnie z poniższą kolejnością pierwszeństwa i upewnić się, że dane początkowe są dostępne zarówno w aplikacji, jak i w programie Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4d3b1-110">You must follow the following order of precedence and make sure that the initial data is available in the application and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="4d3b1-111">Dostawca</span><span class="sxs-lookup"><span data-stu-id="4d3b1-111">Vendor</span></span>

<span data-ttu-id="4d3b1-112">Oto kolejność wykonywania jednostki **Dostawca**:</span><span class="sxs-lookup"><span data-stu-id="4d3b1-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="4d3b1-113">Grupa dostawców</span><span class="sxs-lookup"><span data-stu-id="4d3b1-113">Vendor group</span></span>

    1. <span data-ttu-id="4d3b1-114">Warunki płatności</span><span class="sxs-lookup"><span data-stu-id="4d3b1-114">Terms of payment</span></span>

        1. <span data-ttu-id="4d3b1-115">Dzień zapłaty i wiersze</span><span class="sxs-lookup"><span data-stu-id="4d3b1-115">Payment day and lines</span></span>
        2. <span data-ttu-id="4d3b1-116">Harmonogram płatności</span><span class="sxs-lookup"><span data-stu-id="4d3b1-116">Payment schedule</span></span>

2. <span data-ttu-id="4d3b1-117">Metoda płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="4d3b1-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="4d3b1-118">Klient (Organizacja)</span><span class="sxs-lookup"><span data-stu-id="4d3b1-118">Customer (Organization)</span></span>

<span data-ttu-id="4d3b1-119">Oto kolejność wykonywania jednostki **Odbiorca**:</span><span class="sxs-lookup"><span data-stu-id="4d3b1-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="4d3b1-120">Grupa odbiorców</span><span class="sxs-lookup"><span data-stu-id="4d3b1-120">Customer group</span></span>

    1. <span data-ttu-id="4d3b1-121">Warunki płatności</span><span class="sxs-lookup"><span data-stu-id="4d3b1-121">Terms of payment</span></span>

        1. <span data-ttu-id="4d3b1-122">Dzień zapłaty i wiersze</span><span class="sxs-lookup"><span data-stu-id="4d3b1-122">Payment day and lines</span></span>
        2. <span data-ttu-id="4d3b1-123">Płatność</span><span class="sxs-lookup"><span data-stu-id="4d3b1-123">Payment</span></span> 

2. <span data-ttu-id="4d3b1-124">Metoda płatności odbiorcy</span><span class="sxs-lookup"><span data-stu-id="4d3b1-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="4d3b1-125">Osoba kontaktowa (Osoba)</span><span class="sxs-lookup"><span data-stu-id="4d3b1-125">Contact (Person)</span></span>

<span data-ttu-id="4d3b1-126">Oto kolejność wykonywania jednostki **Kontakt**:</span><span class="sxs-lookup"><span data-stu-id="4d3b1-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="4d3b1-127">Odbiorca</span><span class="sxs-lookup"><span data-stu-id="4d3b1-127">Customer</span></span>
2. <span data-ttu-id="4d3b1-128">Dostawca</span><span class="sxs-lookup"><span data-stu-id="4d3b1-128">Vendor</span></span>
