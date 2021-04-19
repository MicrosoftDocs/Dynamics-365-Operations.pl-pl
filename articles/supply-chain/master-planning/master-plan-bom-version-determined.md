---
title: Ustalanie wersji BOM
description: Jeśli jako domyślny typ zamówienia towar ma ustawioną wartość Produkcja, podczas rozłożenia popytu aparat planowania znajduje prawidłową wersję BOM na podstawie oddziału.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4fd5f28d0ee85c267ea6a86a1452fbacc824620
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833624"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="d100d-103">Ustalanie wersji BOM</span><span class="sxs-lookup"><span data-stu-id="d100d-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d100d-104">Jeśli jako domyślny typ zamówienia towar ma ustawioną wartość Produkcja, podczas rozłożenia popytu aparat planowania znajduje prawidłową wersję BOM na podstawie oddziału.</span><span class="sxs-lookup"><span data-stu-id="d100d-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="d100d-105">Wymiar lokalizacji jest zawsze znany i znajduje się w transakcji popytu.</span><span class="sxs-lookup"><span data-stu-id="d100d-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="d100d-106">Proces określania właściwej wersji BOM przebiega następująco:</span><span class="sxs-lookup"><span data-stu-id="d100d-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="d100d-107">Jeśli w oddziale popytu jest zdefiniowana wersja BOM dla towaru, program używa tego BOM związanego z oddziałem.</span><span class="sxs-lookup"><span data-stu-id="d100d-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="d100d-108">Jeśli w oddziale popytu nie została zdefiniowana wersja BOM dla towaru, program używa ogólnego BOM.</span><span class="sxs-lookup"><span data-stu-id="d100d-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="d100d-109">W ogólnym BOM nie jest określony oddział i jest on prawidłowy dla wielu oddziałów.</span><span class="sxs-lookup"><span data-stu-id="d100d-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="d100d-110">Jeśli istnieje ogólny BOM, jest on używany przez program.</span><span class="sxs-lookup"><span data-stu-id="d100d-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="d100d-111">Jeśli nie istnieje ogólna wersja BOM, której można użyć, rozłożenie popytu jest zatrzymywane w tym momencie.</span><span class="sxs-lookup"><span data-stu-id="d100d-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="d100d-112">Prawidłowa wersja BOM, czy to oddziałowa, czy ogólna, musi spełnić wymagane kryteria daty i ilości.</span><span class="sxs-lookup"><span data-stu-id="d100d-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]