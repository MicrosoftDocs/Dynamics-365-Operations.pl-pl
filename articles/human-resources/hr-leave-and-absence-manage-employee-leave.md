---
title: Zarządzanie urlopem pracownika etatowego
description: Zarządzanie urlopami pracownika etatowego w Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 627c8959b1845fbad761a85bdca7dc93bfc6a105
ms.sourcegitcommit: ffb5998e611b83c2e4f98323f39e3e8f6419c652
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "4420156"
---
# <a name="manage-employee-leave"></a><span data-ttu-id="2a1f1-103">Zarządzanie urlopem pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="2a1f1-103">Manage employee leave</span></span>

<span data-ttu-id="2a1f1-104">Urlopem pracownika etatowego można zarządzać według typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-104">You can manage an employee's leave by leave type.</span></span> <span data-ttu-id="2a1f1-105">Obejmuje to wygasanie rejestracji urlopu i korygowanie sald typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-105">This includes expiring leave enrollment and adjusting leave type balances.</span></span> 

## <a name="adjust-leave-balances"></a><span data-ttu-id="2a1f1-106">Korygowanie sald urlopu</span><span class="sxs-lookup"><span data-stu-id="2a1f1-106">Adjust leave balances</span></span>

1. <span data-ttu-id="2a1f1-107">W rekordzie pracownika wybierz pozycję **Urlop**.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-107">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="2a1f1-108">Wybierz pozycję **Konfiguracja urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-108">Select **Leave and absence setup**.</span></span>

3. <span data-ttu-id="2a1f1-109">Wybierz pozycję **Koryguj saldo**.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-109">Select **Adjust balance**.</span></span>

4. <span data-ttu-id="2a1f1-110">Wybierz **typ urlopu**.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-110">Select the **Leave type**.</span></span>

5. <span data-ttu-id="2a1f1-111">Wprowadź **kwotę korekty**.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-111">Enter an **Adjustment amount**.</span></span> 

6. <span data-ttu-id="2a1f1-112">Opcjonalnie możesz wybrać **datę**.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-112">Optionally, you can select a **Date**.</span></span> 

<span data-ttu-id="2a1f1-113">Możesz uwzględnić kod przyczyny i komentarz podczas korygowania salda urlopu pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-113">You can include a reason code and comment when adjusting an employee's leave balance.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="2a1f1-114">Opcja wyświetlania dodatkowych informacji o saldach urlopowych jest dostępna w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-114">Viewing additional information about leave balances is in preview.</span></span> <span data-ttu-id="2a1f1-115">Należy ją włączyć w środowisku **piaskownicy**.</span><span class="sxs-lookup"><span data-stu-id="2a1f1-115">You'll need to enable it in your **Sandbox** environment.</span></span> <span data-ttu-id="2a1f1-116">Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="2a1f1-116">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br>
><span data-ttu-id="2a1f1-117">Po umieszczeniu kursora na saldzie urlopowym zostaną wyświetlone następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="2a1f1-117">When hovering over any leave balance, you will now see:</span></span><br>
>- <span data-ttu-id="2a1f1-118">**Dostępne** : Łącznie w tym roku — Wykorzystane w tym roku</span><span class="sxs-lookup"><span data-stu-id="2a1f1-118">**Available**: Total this year - Take this year</span></span>
>- <span data-ttu-id="2a1f1-119">**Łącznie w tym roku**: wszystkie naliczone urlopy, korekty i urlopy przeniesione na następny okres dla danego roku</span><span class="sxs-lookup"><span data-stu-id="2a1f1-119">**Total this year**: All accruals, adjustments, and carry forward for the year</span></span>
>- <span data-ttu-id="2a1f1-120">**Wykorzystane w tym roku**: wszystkie zatwierdzone urlopy</span><span class="sxs-lookup"><span data-stu-id="2a1f1-120">**Taken this year**: All approved time off</span></span>

## <a name="see-also"></a><span data-ttu-id="2a1f1-121">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2a1f1-121">See also</span></span>

- [<span data-ttu-id="2a1f1-122">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="2a1f1-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="2a1f1-123">Zarządzanie wnioskami o urlop i nieobecność</span><span class="sxs-lookup"><span data-stu-id="2a1f1-123">Manage leave and absence requests</span></span>](hr-employee-self-service-manage-requests.md)
