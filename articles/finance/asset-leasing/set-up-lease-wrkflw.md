---
title: Konfigurowanie przepływów pracy zatwierdzeń wynajmów
description: W tym temacie opisano sposób konfigurowania przepływu pracy zatwierdzania, który będzie uruchamiany podczas tworzenia nowej umowy wynajmu.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1eaa2f5cc191ec93c30f4f10a662a87e501a341d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249588"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="ab222-103">Konfigurowanie przepływów pracy zatwierdzeń wynajmów</span><span class="sxs-lookup"><span data-stu-id="ab222-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab222-104">W tym temacie opisano sposób konfigurowania przepływu pracy zatwierdzania, który będzie uruchamiany podczas tworzenia nowej umowy wynajmu.</span><span class="sxs-lookup"><span data-stu-id="ab222-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="ab222-105">Aby uzyskać więcej informacji o używaniu przepływu pracy, zobacz [Używanie przepływów pracy zatwierdzeń wynajmów](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="ab222-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="ab222-106">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Przepływ pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="ab222-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="ab222-107">Na stronie **Przepływ pracy wynajmu** wybierz opcję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="ab222-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="ab222-108">W wyświetlonym oknie dialogowym w obszarze **Typ przepływu pracy** kliknij łącze **Przepływ pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="ab222-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="ab222-109">Zostanie otwarta aplikacja.</span><span class="sxs-lookup"><span data-stu-id="ab222-109">The application is opened.</span></span> <span data-ttu-id="ab222-110">Gdy zostanie uruchomiona, zaloguj się w usłudze Azure Active Directory (Azure AD), a nastąpi przekierowanie do aplikacji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ab222-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="ab222-111">Przeciągnij element **Zatwierdzanie przepływu pracy wynajmu** do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ab222-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="ab222-112">Połącz jeden węzeł od elementu **Początek** do elementu **Zatwierdzanie przepływu pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="ab222-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="ab222-113">Następnie połącz element **Zatwierdzanie przepływu pracy wynajmu** z elementem **Koniec**.</span><span class="sxs-lookup"><span data-stu-id="ab222-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="ab222-114">Kliknij dwukrotnie element **Zatwierdzanie przepływu pracy wynajmu**.</span><span class="sxs-lookup"><span data-stu-id="ab222-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="ab222-115">Wybierz opcję **Właściwości**, a następnie w obszarze **Ustawienia podstawowe** nadaj nazwę przepływowi pracy.</span><span class="sxs-lookup"><span data-stu-id="ab222-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="ab222-116">Na tej stronie można również określić więcej parametrów przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ab222-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="ab222-117">Po włączeniu funkcji **Akcje automatyczne** system będzie automatycznie wykonywał określoną akcję.</span><span class="sxs-lookup"><span data-stu-id="ab222-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="ab222-118">Powiadomienia mogą być wysyłane, jeśli są określone na karcie **Powiadomienia**. Na karcie **Ustawienia zaawansowane** można określić ostateczną osobę zatwierdzającą, ustawić limit czasu oraz wyznaczyć określone akcje do wykonania.</span><span class="sxs-lookup"><span data-stu-id="ab222-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="ab222-119">Po zakończeniu ustawiania parametrów przepływu pracy wybierz opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="ab222-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="ab222-120">Wybierz kolejno opcje **Krok 1** i **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="ab222-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="ab222-121">W obszarze **Ustawienia podstawowe** wprowadź nazwę kroku, utwórz wiersz tematu dla zatwierdzenia oraz podaj instrukcje zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="ab222-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="ab222-122">Na stronie **Przypisanie** wybierz typ przypisania.</span><span class="sxs-lookup"><span data-stu-id="ab222-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="ab222-123">Aby przypisać konkretnych użytkowników do zatwierdzenia, wybierz opcję **Użytkownik**, wybierz użytkowników, którzy zatwierdzają umowy wynajmu, a następnie wybierz opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="ab222-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="ab222-124">Wybierz opcję **Zapisz i zamknij**, aby utworzyć przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="ab222-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="ab222-125">Następnie, po wyświetleniu monitu, wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab222-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="ab222-126">Na stronie **Utwórz przepływ pracy** wybierz opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="ab222-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="ab222-127">Zaznacz nowy przepływ pracy, a następnie wybierz opcję **Wersje**.</span><span class="sxs-lookup"><span data-stu-id="ab222-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="ab222-128">Następnie wybierz opcję **Uaktywnij**, aby się upewnić, że przepływ pracy jest aktywny.</span><span class="sxs-lookup"><span data-stu-id="ab222-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="ab222-129">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="ab222-129">Select **Close**.</span></span> <span data-ttu-id="ab222-130">Zostanie wyświetlona nowa aktywna wersja.</span><span class="sxs-lookup"><span data-stu-id="ab222-130">The new active version appears.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]