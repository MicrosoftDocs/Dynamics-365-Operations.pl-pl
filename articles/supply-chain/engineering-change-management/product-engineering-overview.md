---
title: Omówienie zarządzania zmianami inżynieryjnymi
description: Ten temat zawiera omówienie zarządzania zmianami inżynieryjnymi, które pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947527"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="d96a3-103">Omówienie zarządzania zmianami inżynieryjnymi</span><span class="sxs-lookup"><span data-stu-id="d96a3-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="d96a3-104">Podsumowanie funkcji</span><span class="sxs-lookup"><span data-stu-id="d96a3-104">Feature summary</span></span>

<span data-ttu-id="d96a3-105">Dzisiejsi producenci wymagają silnego zarządzania danymi produktu, kontroli wersji i zarządzania zmianami inżynieryjnymi, aby odnieść sukces w świecie stale kurczących się cykli życia produktów, zwiększonych wymagań dotyczących jakości i niezawodności oraz zwiększonego nacisku na bezpieczeństwo produktu.</span><span class="sxs-lookup"><span data-stu-id="d96a3-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="d96a3-106">Zarządzanie zmianami inżynieryjnymi umożliwia tworzenie struktury i dyscypliny w procesie zarządzania danymi produktów, a ponadto umożliwia definiowanie, zwalnianie i korygowanie produktów w sposób kontrolowany, który jest obsługiwany przez przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="d96a3-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="d96a3-107"> Dzięki wersjom produktów i zarządzaniu zmianami inżynieryjnymi możesz dokumentować, oceniać wpływ i wprowadzać zmiany w całym cyklu życia produktu.</span><span class="sxs-lookup"><span data-stu-id="d96a3-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="d96a3-108">Zarządzanie zmianami inżynieryjnymi pomaga w planowaniu i zarządzaniu wersjami produktów oraz zarządzaniu cyklami życia produktu i zmianami inżynieryjnymi.</span><span class="sxs-lookup"><span data-stu-id="d96a3-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="d96a3-109">Poniżej znajduje się lista funkcji głównych:</span><span class="sxs-lookup"><span data-stu-id="d96a3-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="d96a3-110">Przechowywanie wersji produktów</span><span class="sxs-lookup"><span data-stu-id="d96a3-110">Product versioning</span></span>
- <span data-ttu-id="d96a3-111">Ulepszona funkcjonalność wydania produktu, która umożliwia utrzymywanie danych podstawowych produktu w jednej firmie (firmie inżynierskiej) i publikowanie w pełni skonfigurowanego wydanego produktu innym firmom</span><span class="sxs-lookup"><span data-stu-id="d96a3-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="d96a3-112">Zasady sprawdzania, czy wymagane informacje zostały wprowadzone przed aktywacją wersji produktu (kontrola gotowości)</span><span class="sxs-lookup"><span data-stu-id="d96a3-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="d96a3-113">Udoskonalone zarządzanie cyklem życia produktu dzięki kontroli szczegółowej, gdy zwolniony produkt może być używany w konkretnych procesach biznesowych</span><span class="sxs-lookup"><span data-stu-id="d96a3-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="d96a3-114">Żądania zmian inżynieryjnych obsługiwane przez przepływy pracy</span><span class="sxs-lookup"><span data-stu-id="d96a3-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="d96a3-115">Zamówienia zmian inżynieryjnych obsługiwane przez przepływy pracy</span><span class="sxs-lookup"><span data-stu-id="d96a3-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="d96a3-116">Poprzednie wideo ([Możliwości zarządzania zmianami w Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) znajduje się na [liście odtwarzania Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej na platformie YouTube.</span><span class="sxs-lookup"><span data-stu-id="d96a3-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="d96a3-117">Włącz w systemie funkcje zarządzania zmianami technicznymi i wymiarowania wersji</span><span class="sxs-lookup"><span data-stu-id="d96a3-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="d96a3-118">Aby można było używać funkcji zarządzania zmianami inżynieryjnymi, należy włączyć zarówno funkcję *Zarządzania zmianami inżynieryjnymi*, jak i jej klucz konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d96a3-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="d96a3-119">Jeśli chcesz również śledzić wymiar wersji produktów w transakcjach (opcjonalnie), musisz również włączyć funkcję *Wymiar wersji produktu* i jej klucz konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d96a3-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="d96a3-120">Najpierw włącz funkcje, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d96a3-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="d96a3-121">Przejdź do obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d96a3-121">Go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace.</span></span>
1. <span data-ttu-id="d96a3-122">Sprawdź, czy są aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="d96a3-122">Check for updates.</span></span>
1. <span data-ttu-id="d96a3-123">Włącz funkcję o nazwie **Zarządzanie zmianami inżynieryjnymi**.</span><span class="sxs-lookup"><span data-stu-id="d96a3-123">Turn on the feature that is named **Engineering Change Management**.</span></span>
1. <span data-ttu-id="d96a3-124">Jeśli chcesz go użyć, włącz również funkcję o nazwie **Wersja wymiaru produktu**.</span><span class="sxs-lookup"><span data-stu-id="d96a3-124">If you want to use it, then also turn on the feature that is named **Product dimension version**.</span></span>

<span data-ttu-id="d96a3-125">Następnie włącz klucze konfiguracji, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="d96a3-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="d96a3-126">Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d96a3-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="d96a3-127">Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.</span><span class="sxs-lookup"><span data-stu-id="d96a3-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="d96a3-128">Rozwiń węzeł **Handel**.</span><span class="sxs-lookup"><span data-stu-id="d96a3-128">Expand the **Trade** node.</span></span>
1. <span data-ttu-id="d96a3-129">Włącz klucz konfiguracji funkcji głównej, zaznaczając pole wyboru **Zarządzanie zmianami inżynieryjnymi**.</span><span class="sxs-lookup"><span data-stu-id="d96a3-129">Enable the configuration key for the main feature by selecting the **Engineering Change Management** check box.</span></span> <span data-ttu-id="d96a3-130">(Rozwinięcie węzła nie jest konieczne, chyba że trzeba również wyłączyć jedną lub obie jego funkcje podrzędne).</span><span class="sxs-lookup"><span data-stu-id="d96a3-130">(It isn't necessary to expand the node unless you also want to disable one or both of its sub-features.)</span></span>
1. <span data-ttu-id="d96a3-131">Jeśli chcesz także używać wymiaru wersji, zaznacz pole wyboru **Wymiar produktu — wersja**.</span><span class="sxs-lookup"><span data-stu-id="d96a3-131">If you also want to use the version dimension, then select the **Product dimension - Version** check box.</span></span> <span data-ttu-id="d96a3-132">(To pole wyboru jest dalej niż lista, ale nie jest zagnieżdżone w węźle **Zarządzanie zmianami inżynieryjnymi**).</span><span class="sxs-lookup"><span data-stu-id="d96a3-132">(This check box is further down the list, not nested under the **Engineering Change Management** node.)</span></span>
1. <span data-ttu-id="d96a3-133">Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d96a3-133">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d96a3-134">Począwszy od kwietnia 2022 roku klucze licencji do węzłów **Zarządzanie zmianami inżynieryjnych** i **Wymiar produktu — wersja** będą domyślnie włączone dla wszystkich nowych instalacji, ale w razie potrzeby będzie można je wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="d96a3-134">Starting in April 2022, the license keys for both **Engineering Change Management** and **Product dimension - Version** will be enabled by default for all new installations, but you will still be able to disable them if needed.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
