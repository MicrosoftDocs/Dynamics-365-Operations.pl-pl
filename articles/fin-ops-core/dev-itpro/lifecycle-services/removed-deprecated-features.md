---
title: Usunięte lub przestarzałe funkcje usługi Lifecycle Services (LCS)
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z usługi Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e583ec66f24940f44113433042f5e2340cf0f52c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748446"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="fa88b-103">Usunięte lub przestarzałe funkcje usługi Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="fa88b-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fa88b-104">W tym temacie opisano funkcje, które zostały usunięte lub uznane za przestarzałe w usłudze Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fa88b-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="fa88b-105">*Usunięta* funkcja nie jest już dostępna w usłudze.</span><span class="sxs-lookup"><span data-stu-id="fa88b-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="fa88b-106">*Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="fa88b-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="fa88b-107">Ta lista jest udostępniana, aby umożliwić Ci uwzględnianie usuniętych i przestarzałych funkcji we własnym planowaniu.</span><span class="sxs-lookup"><span data-stu-id="fa88b-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="fa88b-108">Ogłoszenia z października 2019 r.</span><span class="sxs-lookup"><span data-stu-id="fa88b-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="fa88b-109">Diagramy schematów blokowych w Narzędziu do modelowania procesów biznesowych</span><span class="sxs-lookup"><span data-stu-id="fa88b-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="fa88b-110"><strong>Przyczyna wycofania/usunięcia</strong></span><span class="sxs-lookup"><span data-stu-id="fa88b-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="fa88b-111">Wycofujemy składnik diagramów schematów blokowych w Narzędziu do modelowania procesów biznesowych (BPM), ponieważ starszy projekt spowodował niewielkie użycie.</span><span class="sxs-lookup"><span data-stu-id="fa88b-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa88b-112"><strong>Zamieniona przez inną funkcję?</strong></span><span class="sxs-lookup"><span data-stu-id="fa88b-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="fa88b-113">Nie</span><span class="sxs-lookup"><span data-stu-id="fa88b-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa88b-114"><strong>Obszary powiązane</strong></span><span class="sxs-lookup"><span data-stu-id="fa88b-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="fa88b-115">Narzędzie do modelowania procesów biznesowych</span><span class="sxs-lookup"><span data-stu-id="fa88b-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fa88b-116"><strong>Stan</strong></span><span class="sxs-lookup"><span data-stu-id="fa88b-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="fa88b-117">Przestarzałe: składnik diagramów schematów blokowych w narzędziu BPM powinien zostać usunięty w 2020 r.</span><span class="sxs-lookup"><span data-stu-id="fa88b-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="fa88b-118">Następujące funkcje będą niedostępne:</span><span class="sxs-lookup"><span data-stu-id="fa88b-118">The following functionality will be unavailable:</span></span>
<ul>
<li><span data-ttu-id="fa88b-119">Wszystkie schematy blokowe będą tylko do odczytu i nie będzie można ich edytować.</span><span class="sxs-lookup"><span data-stu-id="fa88b-119">All flowcharts will be read-only and unavailable for editing.</span></span> <span data-ttu-id="fa88b-120">Właściwości kształtu skojarzone z działaniami dotyczącymi schematów blokowych będą również niedostępne.</span><span class="sxs-lookup"><span data-stu-id="fa88b-120">The shape properties that are associated with flowchart activities will also be unavailable.</span></span> <span data-ttu-id="fa88b-121">Te schematy blokowe obejmują zarówno domyślne schematy blokowe, które są generowane automatycznie, jak i dostosowane schematy blokowe, które są modyfikowane na podstawie domyślnych schematów blokowych.</span><span class="sxs-lookup"><span data-stu-id="fa88b-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="fa88b-122">Kroki procesu będą tylko do odczytu i nie będzie można ich edytować.</span><span class="sxs-lookup"><span data-stu-id="fa88b-122">The process steps will be read-only and unavailable for editing.</span></span></li>     
<li><span data-ttu-id="fa88b-123">Funkcja analizy dopasowania/lub w starszej wersji będzie niedostępna.</span><span class="sxs-lookup"><span data-stu-id="fa88b-123">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="fa88b-124">Dlatego żadna lista luk nie zostanie automatycznie utworzona lub udostępniona do eksportu.</span><span class="sxs-lookup"><span data-stu-id="fa88b-124">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="fa88b-125"><strong>Uwaga:</strong> ta funkcja została wcześniej uznana za przestarzałą i zastąpiona integracjami metodyki Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="fa88b-125"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="fa88b-126">Historia wersji schematu blokowego będzie niedostępna.</span><span class="sxs-lookup"><span data-stu-id="fa88b-126">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]