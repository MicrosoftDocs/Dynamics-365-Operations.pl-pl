--- 
title: "Tworzenie szablonu rekordu w celu ułatwienia wprowadzania danych"
description: "Ta procedura przedstawia sposób tworzenia szablonu rekordu, tak aby wartości pól, które są często używane, nie musiały być jawnie wprowadzane dla każdego nowego rekordu."
author: margoc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 36d14c386322adab0cc0ba9b7b47c874aefbe519
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="c93ac-103">Tworzenie szablonu rekordu w celu ułatwienia wprowadzania danych</span><span class="sxs-lookup"><span data-stu-id="c93ac-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c93ac-104">Ta procedura przedstawia sposób tworzenia szablonu rekordu, tak aby wartości pól, które są często używane, nie musiały być jawnie wprowadzane dla każdego nowego rekordu.</span><span class="sxs-lookup"><span data-stu-id="c93ac-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="c93ac-105">W tej procedurze zostanie utworzy nowy rekord dla nowych laptopów, które należy dodać do środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="c93ac-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="c93ac-106">Procedura wykorzystuje przykładową firmę USMF.</span><span class="sxs-lookup"><span data-stu-id="c93ac-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="c93ac-107">Przejdź do Środki trwałe > Środki trwałe > Środki trwałe.</span><span class="sxs-lookup"><span data-stu-id="c93ac-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="c93ac-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c93ac-108">Click New.</span></span>
3. <span data-ttu-id="c93ac-109">W polu Grupa środków trwałych wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c93ac-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="c93ac-110">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c93ac-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c93ac-111">Na przykład wpisz „Laptop dyrektora w firmie”.</span><span class="sxs-lookup"><span data-stu-id="c93ac-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="c93ac-112">W polu Alias wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c93ac-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="c93ac-113">Na przykład wpisz „laptop”.</span><span class="sxs-lookup"><span data-stu-id="c93ac-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="c93ac-114">Rozwiń sekcję Informacje techniczne.</span><span class="sxs-lookup"><span data-stu-id="c93ac-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="c93ac-115">W polu Marka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c93ac-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="c93ac-116">W polu Model wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c93ac-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="c93ac-117">W polu Rok modelu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c93ac-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="c93ac-118">W okienku akcji kliknij pozycję Opcje.</span><span class="sxs-lookup"><span data-stu-id="c93ac-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="c93ac-119">Kliknij opcję Informacje o rekordzie.</span><span class="sxs-lookup"><span data-stu-id="c93ac-119">Click Record info.</span></span>
12. <span data-ttu-id="c93ac-120">Kliknij opcję Szablon użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c93ac-120">Click User template.</span></span>
13. <span data-ttu-id="c93ac-121">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c93ac-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c93ac-122">Na przykład wpisz „Firmowy laptop”.</span><span class="sxs-lookup"><span data-stu-id="c93ac-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="c93ac-123">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c93ac-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="c93ac-124">Na przykład wpisz „Firmowy laptop”.</span><span class="sxs-lookup"><span data-stu-id="c93ac-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="c93ac-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c93ac-125">Click OK.</span></span>
16. <span data-ttu-id="c93ac-126">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="c93ac-126">Click Close.</span></span>


