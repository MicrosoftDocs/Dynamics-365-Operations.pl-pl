---
title: Korzystanie z funkcji śledzenia rozłożenia
description: W tym artykule wyjaśniono, jak za pomocą funkcji śledzenia można badać przyczyny stojące za wynikiem rozłożenia zamówienia.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19231
ms.assetid: 9bc9bfbe-a7a9-437b-a947-826229b0585a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 677b62055d71ee7ba1419fc2d7e6738b9438cb16
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216160"
---
# <a name="use-tracing-for-explosion"></a><span data-ttu-id="ed4b9-103">Korzystanie z funkcji śledzenia rozłożenia</span><span class="sxs-lookup"><span data-stu-id="ed4b9-103">Use tracing for explosion</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed4b9-104">W tym artykule wyjaśniono, jak za pomocą funkcji śledzenia można badać przyczyny stojące za wynikiem rozłożenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-104">This article explains how you can use tracing to explore the causes behind the outcome of an order explosion.</span></span>

<span data-ttu-id="ed4b9-105">Po włączeniu śledzenia można wyświetlać informacje o czynnikach, które wpływają na wynik rozbicia danego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-105">By enabling tracing, you can view information about the factors that contributed to the outcome of the explosion of a particular order.</span></span> <span data-ttu-id="ed4b9-106">W przykładach poniżej pokazano, jak używać informacji uzyskiwanych w drodze śledzenia:</span><span class="sxs-lookup"><span data-stu-id="ed4b9-106">The following examples show how you can use the tracing information:</span></span>

-   <span data-ttu-id="ed4b9-107">Wyświetlanie relacji między działaniami na zamówieniach planowanych w celu zoptymalizowania rezerwacji zapasów i łańcucha dostaw.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-107">View relations between the actions on planned orders to optimize the supply chain and inventory reservations.</span></span>
-   <span data-ttu-id="ed4b9-108">Wyświetlanie relacji do zamówień, które zostały już zatwierdzone.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-108">View relations to orders that are already approved.</span></span> <span data-ttu-id="ed4b9-109">Można też skoncentrować się na automatycznym ustalaniu pochodnych zapotrzebowań i dokładnym określaniu priorytetu zleceń.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-109">You can focus on automatically firming derived requirements and then prioritize orders more accurately.</span></span>
-   <span data-ttu-id="ed4b9-110">Symulowanie wyników planowania pod kątem optymalizacji parametrów planowania.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-110">Simulate planning results to determine whether the planning parameters are optimal.</span></span>
-   <span data-ttu-id="ed4b9-111">Identyfikacja źródła informacji, takich jak daty produkcji, oferty i priorytety dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-111">Identify how information such as production dates, quantities, and priorities for an order were determined.</span></span>

<span data-ttu-id="ed4b9-112">Można wyświetlić szczegółowe informacje o prognozach i działaniach dla wybranego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-112">You can view details about futures and actions for a selected order.</span></span> <span data-ttu-id="ed4b9-113">Na stronie **Rozłożenie** dane śledzenia są dostępne na karcie **Wyjaśnienie** w górnym panelu.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-113">On the **Explosion** page, tracing information is available on the **Explanation** tab in the upper pane.</span></span> <span data-ttu-id="ed4b9-114">Śledzenie włącza się w chwili rozłożenia zamówienia.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-114">Tracing occurs when you explode an order.</span></span> <span data-ttu-id="ed4b9-115">Aby uruchomić śledzenie zamówienia, kliknij **Aktualizacja**, a następnie zaznacz pole wyboru **Włącz śledzenie**.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-115">To start tracing for the order, click **Update**, and then select the **Enable trace** check box.</span></span> <span data-ttu-id="ed4b9-116">Za pomocą **Znajdź tekst** możesz szukać w dzienniku konkretnych informacji.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-116">You can use the **Find text** field to search the log for specific information.</span></span> <span data-ttu-id="ed4b9-117">Wyniki wyszukiwania zostaną wyróżnione w drzewie.</span><span class="sxs-lookup"><span data-stu-id="ed4b9-117">Search results are highlighted in the tree.</span></span>

<a name="additional-resources"></a><span data-ttu-id="ed4b9-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ed4b9-118">Additional resources</span></span>
--------

[<span data-ttu-id="ed4b9-119">Omówienie planów głównych</span><span class="sxs-lookup"><span data-stu-id="ed4b9-119">Master plans overview</span></span>](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]