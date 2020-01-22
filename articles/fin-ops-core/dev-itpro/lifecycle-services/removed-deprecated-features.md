---
title: Usunięte lub przestarzałe funkcje usługi Lifecycle Services (LCS)
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: sericks007
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c792d06e9b0aa42919de924bdcc9118358779b72
ms.sourcegitcommit: 75bbcff474cfb8d2f282be2b9d2d7984d1505fa3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885462"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="605ba-103">Usunięte lub przestarzałe funkcje usługi Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="605ba-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="605ba-104">W tym temacie opisano funkcje, które zostały usunięte lub uznane za przestarzałe w usłudze Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="605ba-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="605ba-105">*Usunięta* funkcja nie jest już dostępna w usłudze.</span><span class="sxs-lookup"><span data-stu-id="605ba-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="605ba-106">*Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="605ba-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="605ba-107">Ta lista jest udostępniana, aby umożliwić Ci uwzględnianie usuniętych i przestarzałych funkcji we własnym planowaniu.</span><span class="sxs-lookup"><span data-stu-id="605ba-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="605ba-108">Ogłoszenia z października 2019 r.</span><span class="sxs-lookup"><span data-stu-id="605ba-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="605ba-109">Diagramy schematów blokowych w Narzędziu do modelowania procesów biznesowych</span><span class="sxs-lookup"><span data-stu-id="605ba-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="605ba-110"><strong>Przyczyna wycofania/usunięcia</strong></span><span class="sxs-lookup"><span data-stu-id="605ba-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="605ba-111">Wycofujemy składnik diagramów schematów blokowych w Narzędziu do modelowania procesów biznesowych (BPM), ponieważ starszy projekt spowodował niewielkie użycie.</span><span class="sxs-lookup"><span data-stu-id="605ba-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="605ba-112"><strong>Zamieniona przez inną funkcję?</strong></span><span class="sxs-lookup"><span data-stu-id="605ba-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="605ba-113">Nie</span><span class="sxs-lookup"><span data-stu-id="605ba-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="605ba-114"><strong>Obszary powiązane</strong></span><span class="sxs-lookup"><span data-stu-id="605ba-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="605ba-115">Narzędzie do modelowania procesów biznesowych</span><span class="sxs-lookup"><span data-stu-id="605ba-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="605ba-116"><strong>Stan</strong></span><span class="sxs-lookup"><span data-stu-id="605ba-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="605ba-117">Przestarzałe: składnik diagramów schematów blokowych w narzędziu BPM powinien zostać usunięty na początku lutego 2020 r.</span><span class="sxs-lookup"><span data-stu-id="605ba-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed by early February 2020.</span></span> <span data-ttu-id="605ba-118">Następujące funkcje zostaną usunięte:</span><span class="sxs-lookup"><span data-stu-id="605ba-118">The following functionality will be removed:</span></span>
<ul>
<li><span data-ttu-id="605ba-119">Istniejące schematy blokowe będą niedostępne do oglądania ani edytowania.</span><span class="sxs-lookup"><span data-stu-id="605ba-119">Existing flowcharts will be unavailable for viewing or editing.</span></span> <span data-ttu-id="605ba-120">Właściwości kształtu, które są skojarzone z działaniami schematu blokowego, również nie będą dostępne, ponieważ cała karta <strong>Schemat blokowy</strong> zostanie usunięta.</span><span class="sxs-lookup"><span data-stu-id="605ba-120">The shape properties that are associated with flowchart activities will also be unavailable, because the whole <strong>Flowchart</strong> tab will be removed.</span></span> <span data-ttu-id="605ba-121">Te schematy blokowe obejmują zarówno domyślne schematy blokowe, które są generowane automatycznie, jak i dostosowane schematy blokowe, które są modyfikowane na podstawie domyślnych schematów blokowych.</span><span class="sxs-lookup"><span data-stu-id="605ba-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="605ba-122">Funkcja analizy dopasowania/lub w starszej wersji będzie niedostępna.</span><span class="sxs-lookup"><span data-stu-id="605ba-122">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="605ba-123">Dlatego żadna lista luk nie zostanie automatycznie utworzona lub udostępniona do eksportu.</span><span class="sxs-lookup"><span data-stu-id="605ba-123">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="605ba-124"><strong>Uwaga:</strong> ta funkcja została wcześniej uznana za przestarzałą i zastąpiona integracjami metodyki Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="605ba-124"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="605ba-125">Historia wersji schematu blokowego będzie niedostępna.</span><span class="sxs-lookup"><span data-stu-id="605ba-125">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
