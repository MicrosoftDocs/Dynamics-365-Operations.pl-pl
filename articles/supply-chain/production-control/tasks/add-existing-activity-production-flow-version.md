---
title: Dodawanie istniejącego działania do wersji przepływu produkcji
description: Podczas tworzenia nowych wersji przepływów produkcji można dodać działania utworzone dla starszych wersji do nowej wersji.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 04ffbd87dfed3e5764e24c4e4599bd458b5fb767
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255500"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a><span data-ttu-id="85a8b-103">Dodawanie istniejącego działania do wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="85a8b-103">Add an existing activity to a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="85a8b-104">Podczas tworzenia nowych wersji przepływów produkcji można dodać działania utworzone dla starszych wersji do nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-104">When creating new versions of production flows, you can choose to add activities created for the older versions, to the new version.</span></span> <span data-ttu-id="85a8b-105">Ta procedura pokazuje, jak nowa wersja jest tworzona dla istniejącego przepływu produkcji, bez kopiowania działań.</span><span class="sxs-lookup"><span data-stu-id="85a8b-105">This procedure shows how a new version is created for an existing production flow, without copying the activities.</span></span> <span data-ttu-id="85a8b-106">W następnym kroku istniejące działanie jest dodawane do nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-106">In the next step, an existing activity is added to the new version.</span></span> 

<span data-ttu-id="85a8b-107">Zadanie wymaga przepływu produkcji z już utworzoną wersją i działaniami.</span><span class="sxs-lookup"><span data-stu-id="85a8b-107">This task requires production flow with version and activities already created.</span></span>


## <a name="create-a-new-production-flow-version"></a><span data-ttu-id="85a8b-108">Utwórz nową wersję przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="85a8b-108">Create a new production flow version</span></span>
1. <span data-ttu-id="85a8b-109">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="85a8b-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="85a8b-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="85a8b-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="85a8b-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="85a8b-112">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="85a8b-112">Click Edit.</span></span>
5. <span data-ttu-id="85a8b-113">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="85a8b-113">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="85a8b-114">W polu Data wygaśnięcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="85a8b-114">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="85a8b-115">Należy zauważyć, że przed utworzeniem nowej wersji przepływu produkcji trzeba sprawdzić datę i godzinę ważności aktywnej wersji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-115">Note that before you create a new production flow version, make sure to check the expiration date and time of the active version.</span></span> <span data-ttu-id="85a8b-116">Nowa wersja zostanie utworzona z obowiązującą datą rozpoczęcia, która łączy się z datą ważności wybranej wersji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-116">The new version will be created with an effective start date, which connects to the expiry date of the selected version.</span></span>  
7. <span data-ttu-id="85a8b-117">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="85a8b-117">Click Add.</span></span>
8. <span data-ttu-id="85a8b-118">W polu Kopiuj z wersji wybierz opcję Nie.</span><span class="sxs-lookup"><span data-stu-id="85a8b-118">Select No in the Copy from version field.</span></span>
    * <span data-ttu-id="85a8b-119">Wybierz opcję Nie, aby rozpocząć od pustej wersji, jeśli większość działań skopiowanej wersji zostanie zastąpiona nowymi działaniami.</span><span class="sxs-lookup"><span data-stu-id="85a8b-119">Select No to start with an empty version if most of the activities of the copied version will be replaced by new activities.</span></span> <span data-ttu-id="85a8b-120">Niezmienione działania dodaj ręcznie do funkcji Dodawanie istniejących w formularzu działania.</span><span class="sxs-lookup"><span data-stu-id="85a8b-120">Add the unchanged activities to the Add existing function in the activity form manually.</span></span>  
9. <span data-ttu-id="85a8b-121">W polu Duplikuj reguły Kanban wybierz pozycję Nie.</span><span class="sxs-lookup"><span data-stu-id="85a8b-121">Select No in the Duplicate kanban rules field.</span></span>
    * <span data-ttu-id="85a8b-122">Jeżeli działania nie zostaną skopiowane do nowej wersji, nie można skopiować reguł Kanban podczas tworzenia nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-122">When the activities are not copied to the new version, it is not possible to copy the kanban rules at the time of creation of the new version.</span></span>   <span data-ttu-id="85a8b-123">Zamiast tego później użyjesz funkcji Tworzenie zastępczej reguły Kanban w formularzu Reguła Kanban w celu zastąpienia reguł Kanban starej wersji przepływu produkcji regułami Kanban używającymi działań nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-123">Instead you will use the create replacement kanban function later in the kanban rule form, to replace kanban rules of the old production flow version with kanban rules using the activities of the new version.</span></span>  
10. <span data-ttu-id="85a8b-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85a8b-124">Click OK.</span></span>
11. <span data-ttu-id="85a8b-125">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="85a8b-125">In the list, find and select the desired record.</span></span>

## <a name="add-an-existing-activity"></a><span data-ttu-id="85a8b-126">Dodawanie istniejącego działania</span><span class="sxs-lookup"><span data-stu-id="85a8b-126">Add an existing activity</span></span>
1. <span data-ttu-id="85a8b-127">Kliknij opcję Działania.</span><span class="sxs-lookup"><span data-stu-id="85a8b-127">Click Activities.</span></span>
2. <span data-ttu-id="85a8b-128">Kliknij przycisk Dodawanie istniejących, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="85a8b-128">Click Add existing to open the drop dialog.</span></span>
    * <span data-ttu-id="85a8b-129">Znajdź i zaznacz istniejące działanie, które ma zostać dodane do nowej wersji przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="85a8b-129">Find and select an existing activity to be added to the new production flow version.</span></span>  <span data-ttu-id="85a8b-130">Należy zauważyć, że lista zawiera wszystkie działania, które zostały utworzone dla tego przepływu produkcji we wszystkich poprzednich wersjach przepływu.</span><span class="sxs-lookup"><span data-stu-id="85a8b-130">Note that the list shows all activities that have been created for this production flow for all previous versions of the flow.</span></span>  
3. <span data-ttu-id="85a8b-131">Wprowadź lub wybierz wartość w polu Działanie.</span><span class="sxs-lookup"><span data-stu-id="85a8b-131">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="85a8b-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="85a8b-132">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]