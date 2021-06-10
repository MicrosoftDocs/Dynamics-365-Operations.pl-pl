---
title: Modyfikowanie relacji zależności służbowych
description: W tej procedurze pokazano sposób zmiany relacji zależności służbowej dla pracownika.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 78410347e7e6cf67f692c7e9193419ffd87e3057
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057099"
---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="db430-103">Modyfikowanie relacji zależności służbowych</span><span class="sxs-lookup"><span data-stu-id="db430-103">Modify reporting relationships for a position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="db430-104">W tej procedurze pokazano sposób zmiany relacji zależności służbowej dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="db430-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="db430-105">Relacja zależności służbowej może służyć do kierowania dokumentów przez przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="db430-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="db430-106">W procedurze również pokazano sposób przypisywania pracownika do dodatkowych hierarchii.</span><span class="sxs-lookup"><span data-stu-id="db430-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="db430-107">Na przykład pracownik może być częścią zespołu projektu z nieformalną relacją podlegania kierownikowi projektu.</span><span class="sxs-lookup"><span data-stu-id="db430-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="db430-108">Na stanowisku można zdefiniować dodatkowe relacje służbowe, aby uwzględnić różne scenariusze projektowe lub macierzowe.</span><span class="sxs-lookup"><span data-stu-id="db430-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="db430-109">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="db430-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="db430-110">Wybierz kolejno opcje Zasoby ludzkie > Stanowiska > Stanowiska.</span><span class="sxs-lookup"><span data-stu-id="db430-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="db430-111">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="db430-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="db430-112">Na przykład wyfiltruj według pola Stanowiska z wartością „000091”.</span><span class="sxs-lookup"><span data-stu-id="db430-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="db430-113">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="db430-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="db430-114">Rozwiń sekcję Stanowisko zwierzchnie.</span><span class="sxs-lookup"><span data-stu-id="db430-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="db430-115">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="db430-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="db430-116">W polu Przełożony wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="db430-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="db430-117">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="db430-117">Click Create.</span></span>
8. <span data-ttu-id="db430-118">Rozwiń sekcję Relacje.</span><span class="sxs-lookup"><span data-stu-id="db430-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="db430-119">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="db430-119">Click Add.</span></span>
10. <span data-ttu-id="db430-120">Zaznacz pole wyboru z lewej strony siatki.</span><span class="sxs-lookup"><span data-stu-id="db430-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="db430-121">W polu Nazwa hierarchii wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="db430-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="db430-122">Przykład: Projekt</span><span class="sxs-lookup"><span data-stu-id="db430-122">Example: Project</span></span>  
12. <span data-ttu-id="db430-123">W polu Stanowisko zwierzchnie wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="db430-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="db430-124">Przykład: 000437.</span><span class="sxs-lookup"><span data-stu-id="db430-124">Example:  000437</span></span>
13. <span data-ttu-id="db430-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="db430-125">Click Save.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]