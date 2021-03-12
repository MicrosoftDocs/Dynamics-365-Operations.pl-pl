---
title: Omówienie zarządzania zmianami inżynieryjnymi
description: Ten temat zawiera omówienie zarządzania zmianami inżynieryjnymi, które pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b081cd8d56217b8cf76db824c29482d453fc9ea3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001955"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="8fa99-103">Omówienie zarządzania zmianami inżynieryjnymi</span><span class="sxs-lookup"><span data-stu-id="8fa99-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="8fa99-104">Podsumowanie funkcji</span><span class="sxs-lookup"><span data-stu-id="8fa99-104">Feature summary</span></span>

<span data-ttu-id="8fa99-105">Dzisiejsi producenci wymagają silnego zarządzania danymi produktu, kontroli wersji i zarządzania zmianami inżynieryjnymi, aby odnieść sukces w świecie stale kurczących się cykli życia produktów, zwiększonych wymagań dotyczących jakości i niezawodności oraz zwiększonego nacisku na bezpieczeństwo produktu.</span><span class="sxs-lookup"><span data-stu-id="8fa99-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="8fa99-106">Zarządzanie zmianami inżynieryjnymi umożliwia tworzenie struktury i dyscypliny w procesie zarządzania danymi produktów, a ponadto umożliwia definiowanie, zwalnianie i korygowanie produktów w sposób kontrolowany, który jest obsługiwany przez przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="8fa99-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="8fa99-107"> Dzięki wersjom produktów i zarządzaniu zmianami inżynieryjnymi możesz dokumentować, oceniać wpływ i wprowadzać zmiany w całym cyklu życia produktu.</span><span class="sxs-lookup"><span data-stu-id="8fa99-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="8fa99-108">Zarządzanie zmianami inżynieryjnymi pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi.</span><span class="sxs-lookup"><span data-stu-id="8fa99-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="8fa99-109">Poniżej znajduje się lista funkcji głównych:</span><span class="sxs-lookup"><span data-stu-id="8fa99-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="8fa99-110">Przechowywanie wersji produktów</span><span class="sxs-lookup"><span data-stu-id="8fa99-110">Product versioning</span></span>
- <span data-ttu-id="8fa99-111">Ulepszona funkcjonalność wydania produktu, która umożliwia utrzymywanie danych podstawowych produktu w jednej firmie (firmie inżynierskiej) i publikowanie w pełni skonfigurowanego wydanego produktu innym firmom</span><span class="sxs-lookup"><span data-stu-id="8fa99-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="8fa99-112">Zasady sprawdzania, czy wymagane informacje zostały wprowadzone przed aktywacją wersji produktu (kontrola gotowości)</span><span class="sxs-lookup"><span data-stu-id="8fa99-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="8fa99-113">Udoskonalone zarządzanie cyklem życia produktu dzięki kontroli szczegółowej, gdy zwolniony produkt może być używany w konkretnych procesach biznesowych</span><span class="sxs-lookup"><span data-stu-id="8fa99-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="8fa99-114">Żądania zmian inżynieryjnych obsługiwane przez przepływy pracy</span><span class="sxs-lookup"><span data-stu-id="8fa99-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="8fa99-115">Zamówienia zmian inżynieryjnych obsługiwane przez przepływy pracy</span><span class="sxs-lookup"><span data-stu-id="8fa99-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="8fa99-116">Poprzednie wideo ([Możliwości zarządzania zmianami w Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) znajduje się na [liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.</span><span class="sxs-lookup"><span data-stu-id="8fa99-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-engineering-change-management-for-your-system"></a><span data-ttu-id="8fa99-117">Włącz zarządzanie zmianami inżynieryjnymi w systemie</span><span class="sxs-lookup"><span data-stu-id="8fa99-117">Turn on engineering change management for your system</span></span>

<span data-ttu-id="8fa99-118">Najpierw włącz zarządzanie zmianami inżynieryjnymi, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8fa99-118">First, turn on engineering change management by following these steps.</span></span>

1. <span data-ttu-id="8fa99-119">Przejdź do obszaru [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8fa99-119">Go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
1. <span data-ttu-id="8fa99-120">Sprawdź, czy są aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="8fa99-120">Check for updates.</span></span>
1. <span data-ttu-id="8fa99-121">Włącz funkcję o nazwie **Zarządzanie zmianami inżynieryjnymi**.</span><span class="sxs-lookup"><span data-stu-id="8fa99-121">Turn on the feature that is named **Engineering Change Management**.</span></span>

<span data-ttu-id="8fa99-122">Następnie włącz klucz konfiguracji **Zarządzanie zmianami inżynieryjnymi**, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8fa99-122">Next, turn on the **Engineering Change Management** configuration key by following these steps.</span></span>

1. <span data-ttu-id="8fa99-123">Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8fa99-123">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="8fa99-124">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.</span><span class="sxs-lookup"><span data-stu-id="8fa99-124">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="8fa99-125">Rozwiń węzeł **Handel** i zaznacz pole wyboru **Zarządzanie zmianami inżynieryjnymi**.</span><span class="sxs-lookup"><span data-stu-id="8fa99-125">Expand the **Trade** node, and select the **Engineering Change Management** check box.</span></span>
1. <span data-ttu-id="8fa99-126">Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8fa99-126">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
