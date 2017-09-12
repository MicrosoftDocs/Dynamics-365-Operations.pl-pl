---
title: Tworzenie listu przewozowego
description: "W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: b274ff572d2be9a71b91d533023b95be98591e4f
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="create-a-bill-of-lading"></a><span data-ttu-id="af31a-103">Tworzenie listu przewozowego</span><span class="sxs-lookup"><span data-stu-id="af31a-103">Create a bill of lading</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="af31a-104">W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="af31a-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="af31a-105">List przewozowy jest to dokumentem prawnym między firmą wysyłającą towary a przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="af31a-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="af31a-106">Dokument towarzyszy wysyłanym towarom i służy jako potwierdzenie dostawcy, gdy towary są dostarczane do miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="af31a-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="af31a-107">Jeśli używasz zarządzania magazynem, istnieją dwa sposoby generowania listu przewozowego:</span><span class="sxs-lookup"><span data-stu-id="af31a-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="af31a-108">Tworzenie raportu ręcznie za pomocą strony **List przewozowy**.</span><span class="sxs-lookup"><span data-stu-id="af31a-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="af31a-109">Generowanie raportu z **warsztatu planowania wysyłki ładunku**.</span><span class="sxs-lookup"><span data-stu-id="af31a-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="af31a-110">Jeśli generujesz list przewozowy z **warsztatu planowania wysyłki ładunku**, ładunek musi mieć stan **Wysłano**.</span><span class="sxs-lookup"><span data-stu-id="af31a-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="af31a-111">Jeśli występuje więcej niż jedna wysyłka w ładunku, list przewozowy jest tworzony dla każdej wysyłki.</span><span class="sxs-lookup"><span data-stu-id="af31a-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="af31a-112">Po utworzeniu listu przewozowego można wprowadzać w nim zmiany na stronie **List przewozowy**.</span><span class="sxs-lookup"><span data-stu-id="af31a-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="af31a-113">Główny list przewozowy</span><span class="sxs-lookup"><span data-stu-id="af31a-113">Master bill of lading</span></span>
<span data-ttu-id="af31a-114">Jeśli ładunek obejmuje kilka wysyłek, można utworzyć główny list przewozowy.</span><span class="sxs-lookup"><span data-stu-id="af31a-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="af31a-115">Ma on taki sam układ i informacje, jak list przewozowy, ale sumuje zawartość wszystkich wysyłek.</span><span class="sxs-lookup"><span data-stu-id="af31a-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="af31a-116">Jeśli na stronie **Parametry zarządzania transportem** w opcji **Utwórz główny list przewozowy, jeśli ładunek obejmuje kilka wysyłek** jest ustawiona wartość **Tak**, główny list przewozowy jest generowany automatycznie, jeżeli tworzysz list przewozowego z **warsztatu planowania wysyłki ładunku** w warunkach istnienia więcej niż jednej dostawy.</span><span class="sxs-lookup"><span data-stu-id="af31a-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="af31a-117">Można także wyświetlić spis listów przewozowych, klikając kolejno opcje **Informacje pokrewne** &gt; **List przewozowy**.</span><span class="sxs-lookup"><span data-stu-id="af31a-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="af31a-118">Jeśli tworzysz listy przewozowe ręcznie, można utworzyć główny list przewozowy na stronie **List przewozowy**.</span><span class="sxs-lookup"><span data-stu-id="af31a-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>




