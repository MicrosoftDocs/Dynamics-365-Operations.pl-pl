---
title: Grupy kont konsolidacji i dodatkowe konta konsolidacji
description: Ten temat zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane w Microsoft Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8db7a60656434aafd8114b08c2c0e9493140f27b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446921"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a><span data-ttu-id="01813-103">Grupy kont konsolidacji i dodatkowe konta konsolidacji</span><span class="sxs-lookup"><span data-stu-id="01813-103">Consolidation account groups and additional consolidation accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="01813-104">Ten temat zawiera informacje o grupach kont konsolidacji i dodatkowych kontach konsolidacji oraz wyjaśnia, jak są one używane w Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="01813-104">This topic provides information about consolidation account groups and additional consolidation accounts, and explains how they are used in Microsoft Dynamics 365 Finance.</span></span>

<a name="consolidation-account-groups"></a><span data-ttu-id="01813-105">Grupy kont konsolidacji</span><span class="sxs-lookup"><span data-stu-id="01813-105">Consolidation account groups</span></span>
----------------------------

<span data-ttu-id="01813-106">Grupy kont konsolidacji pozwalają tworzyć grupy kont, które mają użyć do konsolidowania danych.</span><span class="sxs-lookup"><span data-stu-id="01813-106">Consolidation account groups let you create groups of the accounts that you want to use to consolidate data.</span></span> <span data-ttu-id="01813-107">W większości przypadków grupa kont konsolidacji reprezentuje urzędowy plan kont lub mapuje konta na grupę zdefiniowaną przez centralę firmy.</span><span class="sxs-lookup"><span data-stu-id="01813-107">Most often, a consolidation account group represents a government-mandated chart of accounts or maps accounts to a group that is defined by the company's headquarters.</span></span> <span data-ttu-id="01813-108">Grupy kont konsolidacji są podane w module **Konsolidacje** w obszarze **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="01813-108">You can find consolidation account groups in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="01813-109">Podczas dodawania nowej grupy wprowadzasz unikatowy identyfikator i nazwę grupy kont.</span><span class="sxs-lookup"><span data-stu-id="01813-109">When you add a new group, you enter a unique identifier for the account group and a name.</span></span>

## <a name="additional-consolidation-accounts"></a><span data-ttu-id="01813-110">Dodatkowe konta konsolidacji</span><span class="sxs-lookup"><span data-stu-id="01813-110">Additional consolidation accounts</span></span>
<span data-ttu-id="01813-111">Funkcja dodatkowych kont konsolidacji umożliwia przypisanie konta z istniejącego planu kont do grupy kont konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="01813-111">Additional consolidation accounts let you assign an account from an existing chart of accounts to a consolidation account group.</span></span> <span data-ttu-id="01813-112">Następnie można określić wartość i nazwę konta konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="01813-112">You can then specify a consolidation account value and name.</span></span> 

<span data-ttu-id="01813-113">Dodatkowe konta konsolidacji są podane w module **Konsolidacje** w obszarze **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="01813-113">You can find additional consolidation accounts in the **Setup** area of the **Consolidations** module.</span></span> <span data-ttu-id="01813-114">Podczas tworzenia nowego konta konsolidacji należy określić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="01813-114">When you create a new consolidation account, you must specify the following information:</span></span>

-   <span data-ttu-id="01813-115">**Konto główne** — To pole jest odnośnikiem, który pokazuje wszystkie konta główne oparte na plan kont wybranym na stronie.</span><span class="sxs-lookup"><span data-stu-id="01813-115">**Main account** – This field is a lookup that shows all the main accounts that are based on the chart of accounts that you selected on the page.</span></span> <span data-ttu-id="01813-116">Po wybraniu konta nazwa jest automatycznie wprowadzana w polu **Nazwa konta głównego**.</span><span class="sxs-lookup"><span data-stu-id="01813-116">When you select an account, the name is automatically entered in the **Main account name** field.</span></span>
-   <span data-ttu-id="01813-117">**Grupa kont konsolidacji** — To pole służy określaniu grupy, do której ma zostać przypisane konto.</span><span class="sxs-lookup"><span data-stu-id="01813-117">**Consolidation account group** – Use this field to specify the group to assign the account to.</span></span> <span data-ttu-id="01813-118">Jeśli konsolidujesz na dwa różne sposoby, należy dodać to samo konto do wszystkich czterech grup kont konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="01813-118">If you consolidate in two different ways, you must add the same account to all four consolidation account groups.</span></span>
-   <span data-ttu-id="01813-119">**Konto konsolidacji** — Wprowadź wartość konta konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="01813-119">**Consolidation account** – Enter the value of the consolidation account.</span></span> <span data-ttu-id="01813-120">Ta wartość nie musi określać konta z planu kont.</span><span class="sxs-lookup"><span data-stu-id="01813-120">This value doesn't have to be an account from a chart of accounts.</span></span> <span data-ttu-id="01813-121">To może być dowolne inne konto.</span><span class="sxs-lookup"><span data-stu-id="01813-121">It can be any value that you require.</span></span>
-   <span data-ttu-id="01813-122">**Nazwa konta konsolidacji** — Wprowadź nazwę konta w postaci, w jakiej ma być wyświetlana w zapytaniach i raportach.</span><span class="sxs-lookup"><span data-stu-id="01813-122">**Consolidation account name** – Enter the name of account as you want it to appear on inquiries and reports.</span></span>
-   <span data-ttu-id="01813-123">**Poziom SAT** — To pole służy do zgłaszania wyciągów z kont meksykańskiemu urzędowi skarbowemu.</span><span class="sxs-lookup"><span data-stu-id="01813-123">**SAT level** – This field is used to report account statements to the Mexican tax authorities.</span></span> 

<span data-ttu-id="01813-124">Po zakończeniu tworzenia grup kont konsolidacji i dodatkowych kont konsolidacji można wybrać grupę w procesie konsolidacji online.</span><span class="sxs-lookup"><span data-stu-id="01813-124">When you've finished creating your consolidation account groups and additional consolidation accounts, you can select the group in the Consolidate online process.</span></span>


<span data-ttu-id="01813-125">Aby uzyskać więcej informacji, zobacz [Tworzenie grup konsolidacji i dodatkowych kont konsolidacyjnych](../general-ledger/tasks/create-consolidation-groups.md).</span><span class="sxs-lookup"><span data-stu-id="01813-125">For more information, see [Create consolidation groups and additional consolidation accounts](../general-ledger/tasks/create-consolidation-groups.md).</span></span> 



