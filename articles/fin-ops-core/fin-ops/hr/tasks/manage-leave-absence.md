---
title: Zarządzanie nieobecnościami
description: Ta procedura prowadzi przez proces tworzenia rekordów urlopów pracowników.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, HcmEmploymentLeave
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 002700ae7f6474b48fbe09cb3aaa72e9516b8224
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143565"
---
# <a name="manage-leave-of-absence"></a><span data-ttu-id="3d5e8-103">Zarządzanie nieobecnościami</span><span class="sxs-lookup"><span data-stu-id="3d5e8-103">Manage leave of absence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3d5e8-104">Ta procedura prowadzi przez proces tworzenia rekordów urlopów pracowników.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-104">This procedure walks through the creation of employee leave records.</span></span> <span data-ttu-id="3d5e8-105">Można śledzić czas spędzany na urlopach z powodów medycznych, naukowych, na opiekę rodzicielską itd.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-105">You can track leave time for reasons that include medical, educational, or parental activities.</span></span> <span data-ttu-id="3d5e8-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="3d5e8-107">Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-107">Go to Human resources > Workers > Employees.</span></span>
2. <span data-ttu-id="3d5e8-108">Na liście zaznacz pracownika.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-108">In the list, select an employee.</span></span>
3. <span data-ttu-id="3d5e8-109">Wyświetl szczegółowe informacje o wybranym pracowniku, zaznaczając jego imię i nazwisko.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-109">Display detailed information for the selected employee by selecting the employee's name.</span></span>
4. <span data-ttu-id="3d5e8-110">Kliknij kartę Zatrudnienie.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-110">Click the Employment tab.</span></span>
5. <span data-ttu-id="3d5e8-111">Kliknij opcję Urlop.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-111">Click Leave.</span></span>
6. <span data-ttu-id="3d5e8-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-112">Click New.</span></span>
7. <span data-ttu-id="3d5e8-113">W polu Typ urlopu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-113">In the Leave type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="3d5e8-114">W formularzu Typy urlopów można skojarzyć typ urlopu z kodem zarobków.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-114">You can associate a leave type to an earning code in the Leave types form.</span></span> <span data-ttu-id="3d5e8-115">Jeśli typ urlopu jest powiązany z kodem zarobków, dla wprowadzanego okresu urlopowego zostanie wygenerowany wiersz zarobków wraz ze skojarzonym kodem zarobków.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-115">If a leave type is associated with an earning code, an earning line will be generated with the associated earning code during the leave period that you enter.</span></span>  
8. <span data-ttu-id="3d5e8-116">Na liście zaznacz typ urlopu.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-116">In the list, select a leave type.</span></span> 
    * <span data-ttu-id="3d5e8-117">Na przykład: Adopcja</span><span class="sxs-lookup"><span data-stu-id="3d5e8-117">For example: Adoption</span></span>  
9. <span data-ttu-id="3d5e8-118">Wpisz datę rozpoczęcia urlopu.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-118">Enter the date that the leave will start.</span></span> <span data-ttu-id="3d5e8-119">Przykład: „2015-10-26”.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-119">Example: '2015-10-26'</span></span>
    * <span data-ttu-id="3d5e8-120">Na przykład: 2015-10-26</span><span class="sxs-lookup"><span data-stu-id="3d5e8-120">For example:  2015-10-26</span></span>  
10. <span data-ttu-id="3d5e8-121">Wpisz datę rozpoczęcia urlopu.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-121">Enter the date that the leave will start.</span></span> 
    * <span data-ttu-id="3d5e8-122">Na przykład: 2015-11-20</span><span class="sxs-lookup"><span data-stu-id="3d5e8-122">For example:  2015-11-20</span></span>  
11. <span data-ttu-id="3d5e8-123">W polu Notatka wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-123">In the note field, enter a description.</span></span>
    * <span data-ttu-id="3d5e8-124">Na przykład: Urlop w związku z adopcją</span><span class="sxs-lookup"><span data-stu-id="3d5e8-124">For example: Leave for adoption</span></span>  
12. <span data-ttu-id="3d5e8-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3d5e8-125">Click Save.</span></span>

