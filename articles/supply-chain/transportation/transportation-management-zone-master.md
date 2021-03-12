---
title: Strefa główna zarządzania transportem
description: W tym temacie wyjaśniono, w jaki sposób zarządzanie transportem umożliwia dzielenie lokalizacji geograficznych na strefy.
author: Henrikan
manager: ''
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSZoneMaster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6527c4887ccd3085d63dd64c104a94e6354f536b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996471"
---
# <a name="transportation-management-zone-master"></a><span data-ttu-id="1f74f-103">Strefa główna zarządzania transportem</span><span class="sxs-lookup"><span data-stu-id="1f74f-103">Transportation management zone master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f74f-104">Zarządzanie transportem umożliwia dzielenie lokalizacji geograficznych na strefy.</span><span class="sxs-lookup"><span data-stu-id="1f74f-104">Transport management lets you divide geographic locations into zones.</span></span> <span data-ttu-id="1f74f-105">Podział lokalizacji na strefy ułatwia:</span><span class="sxs-lookup"><span data-stu-id="1f74f-105">Dividing locations into zones can help to:</span></span>

- <span data-ttu-id="1f74f-106">**Uproszczenie cennika transportu** — cenniki według stref mogą być prostsze niż wyceny oparte na poszczególnych lokalizacjach, zwłaszcza gdy lokalizacje transportu są rozproszone.</span><span class="sxs-lookup"><span data-stu-id="1f74f-106">**Simplify transportation pricing** – Zone-wise pricing can be simpler than individual location-based pricing, especially when transportation locations are scattered.</span></span>
- <span data-ttu-id="1f74f-107">**Optymalizowanie planowania ładunku** — przez konsolidowanie ładunków według stref.</span><span class="sxs-lookup"><span data-stu-id="1f74f-107">**Optimize load planning** – By consolidating loads by zones.</span></span>
- <span data-ttu-id="1f74f-108">**Optymalizowanie planowania trasy** — przez przypisanie konkretnych planów tras do wybranych stref.</span><span class="sxs-lookup"><span data-stu-id="1f74f-108">**Optimize route planning** – By assigning specific route plans to specific zones.</span></span>

<span data-ttu-id="1f74f-109">Strefy można określać na podstawie wartości pól metadanych (takich jak kraj, zakres kodów pocztowych lub usługa przewoźnika), które kwalifikują każdą strefę.</span><span class="sxs-lookup"><span data-stu-id="1f74f-109">You define zones based on the metadata field values (such as country, zip code range, or carrier service) that qualify each zone.</span></span> <span data-ttu-id="1f74f-110">Definicje stref nie są wymagane, jeśli cenniki transportu nie korzystają z koncepcji strefy.</span><span class="sxs-lookup"><span data-stu-id="1f74f-110">Zone definitions aren't required if your transportation pricing doesn't employ a zone concept.</span></span>
