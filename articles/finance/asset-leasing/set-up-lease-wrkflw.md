---
title: Konfigurowanie przepływów pracy zatwierdzeń wynajmów
description: W tym temacie opisano sposób konfigurowania przepływu pracy zatwierdzania, który będzie uruchamiany podczas tworzenia nowej umowy wynajmu.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0e7280bbf60901266c81a0c89395c5183f991425
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881669"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="b17e5-103">Konfigurowanie przepływów pracy zatwierdzeń wynajmów</span><span class="sxs-lookup"><span data-stu-id="b17e5-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b17e5-104">W tym temacie opisano sposób konfigurowania przepływu pracy zatwierdzania, który będzie uruchamiany podczas tworzenia nowej umowy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="b17e5-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="b17e5-105">Aby uzyskać więcej informacji o używaniu przepływu pracy, zobacz [Używanie przepływów pracy zatwierdzeń wynajmów](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="b17e5-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="b17e5-106">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Przepływ pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="b17e5-107">Na stronie **Przepływ pracy wynajmu** wybierz opcję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="b17e5-108">W wyświetlonym oknie dialogowym w obszarze **Typ przepływu pracy** kliknij łącze **Przepływ pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="b17e5-109">Zostanie otwarta aplikacja.</span><span class="sxs-lookup"><span data-stu-id="b17e5-109">The application is opened.</span></span> <span data-ttu-id="b17e5-110">Gdy zostanie uruchomiona, zaloguj się w usłudze Azure Active Directory (Azure AD), a nastąpi przekierowanie do aplikacji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="b17e5-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="b17e5-111">Przeciągnij element **Zatwierdzanie przepływu pracy wynajmu** do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="b17e5-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="b17e5-112">Połącz jeden węzeł od elementu **Początek** do elementu **Zatwierdzanie przepływu pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="b17e5-113">Następnie połącz element **Zatwierdzanie przepływu pracy wynajmu** z elementem **Koniec**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="b17e5-114">Kliknij dwukrotnie element **Zatwierdzanie przepływu pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="b17e5-115">Wybierz opcję **Właściwości**, a następnie w obszarze **Ustawienia podstawowe** nadaj nazwę przepływowi pracy.</span><span class="sxs-lookup"><span data-stu-id="b17e5-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="b17e5-116">Na tej stronie można również określić więcej parametrów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="b17e5-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="b17e5-117">Po włączeniu funkcji **Akcje automatyczne** system będzie automatycznie wykonywał określoną akcję.</span><span class="sxs-lookup"><span data-stu-id="b17e5-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="b17e5-118">Powiadomienia mogą być wysyłane, jeśli są określone na karcie **Powiadomienia**. Na karcie **Ustawienia zaawansowane** można określić ostateczną osobę zatwierdzającą, ustawić limit czasu oraz wyznaczyć określone akcje do wykonania.</span><span class="sxs-lookup"><span data-stu-id="b17e5-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="b17e5-119">Po zakończeniu ustawiania parametrów przepływu pracy wybierz opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="b17e5-120">Wybierz kolejno opcje **Krok 1** i **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="b17e5-121">W obszarze **Ustawienia podstawowe** wprowadź nazwę kroku, utwórz wiersz tematu dla zatwierdzenia oraz podaj instrukcje zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="b17e5-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="b17e5-122">Na stronie **Przypisanie** wybierz typ przypisania.</span><span class="sxs-lookup"><span data-stu-id="b17e5-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="b17e5-123">Aby przypisać konkretnych użytkowników do zatwierdzenia, wybierz opcję **Użytkownik**, wybierz użytkowników, którzy zatwierdzają umowy wynajmu, a następnie wybierz opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="b17e5-124">Wybierz opcję **Zapisz i zamknij**, aby utworzyć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="b17e5-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="b17e5-125">Następnie, po wyświetleniu monitu, wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="b17e5-126">Na stronie **Utwórz przepływ pracy** wybierz opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="b17e5-127">Zaznacz nowy przepływ pracy, a następnie wybierz opcję **Wersje**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="b17e5-128">Następnie wybierz opcję **Uaktywnij**, aby się upewnić, że przepływ pracy jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="b17e5-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="b17e5-129">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="b17e5-129">Select **Close**.</span></span> <span data-ttu-id="b17e5-130">Zostanie wyświetlona nowa aktywna wersja.</span><span class="sxs-lookup"><span data-stu-id="b17e5-130">The new active version appears.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
