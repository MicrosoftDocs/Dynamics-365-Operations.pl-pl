---
title: Przepływ pracy odbiorcy
description: Ten temat zawiera informacje dotyczące przepływu pracy odbiorcy. Możesz zmienić określone pola dla odbiorcy, a następnie wysłać te zmiany do zatwierdzenia, używając przepływu pracy, zanim zostaną one dodane do danych odbiorcy.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: af66887dda551d3820b744fbb96d7d13c897e71b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236897"
---
# <a name="customer-workflow"></a><span data-ttu-id="ec4c6-104">Przepływ pracy odbiorcy</span><span class="sxs-lookup"><span data-stu-id="ec4c6-104">Customer workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec4c6-105">Przepływ pracy odbiorcy został dodany do wersji 8.0.4.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-105">The customer workflow has been added to version 8.0.4.</span></span> <span data-ttu-id="ec4c6-106">Możesz zmienić określone pola dla odbiorcy, a następnie wysłać te zmiany do zatwierdzenia, używając przepływu pracy, zanim zostaną one dodane do danych odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-106">You can change specific fields for a customer and then send those changes for approval by using the workflow before they are added to the customer.</span></span>

## <a name="set-up-the-customer-workflow"></a><span data-ttu-id="ec4c6-107">Konfigurowanie przepływu pracy odbiorcy</span><span class="sxs-lookup"><span data-stu-id="ec4c6-107">Set up the customer workflow</span></span>

<span data-ttu-id="ec4c6-108">Aby móc używać funkcji przepływu pracy odbiorcy, musisz ją włączyć.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-108">Before you can use the customer workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="ec4c6-109">Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-109">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="ec4c6-110">Na karcie **Ogólne** na skróconej karcie **Zatwierdzenie odbiorcy** ustaw dla opcji **Włącz zatwierdzanie odbiorców** wartość **Tak**, aby włączyć tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-110">On the **General** tab, on the **Customer approval** FastTab, set the **Enable customer approvals** option to **Yes** to enable the feature.</span></span>
3. <span data-ttu-id="ec4c6-111">W polu **Zachowanie jednostki danych** wybierz zachowanie, którego jednostka danych ma używać podczas importowania danych:</span><span class="sxs-lookup"><span data-stu-id="ec4c6-111">In the **Data entity behavior** field, select the behavior that the data entities should use when data is imported:</span></span>

    - <span data-ttu-id="ec4c6-112">**Zezwalaj na zmiany bez zatwierdzenia** — jednostka może zaktualizować rekord odbiorcy bez konieczności przetwarzania go w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-112">**Allow changes without approval** – An entity can update the customer record without processing it through the workflow.</span></span>
    - <span data-ttu-id="ec4c6-113">**Odrzuć zmiany** — Nie można wprowadzić zmian w rekordzie odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-113">**Reject changes** – Changes can't be made to the customer record.</span></span> <span data-ttu-id="ec4c6-114">Import zakończy się niepowodzeniem w przypadku pól, które są skonfigurowane do użycia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-114">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="ec4c6-115">**Utwórz propozycje zmian** — Wszystkie pola zostaną zmienione, z wyjątkiem pól, które są skonfigurowane do użycia w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-115">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="ec4c6-116">Nowe wartości tych pól zostaną dodane do odbiorcy jako proponowane zmiany, a przepływ pracy zostanie uruchomiony automatycznie.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-116">The new values for those fields will be added to the customer as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="ec4c6-117">Następnie na liście pól odbiorcy zaznacz pole wyboru **Włącz** dla każdego pola, które musi zostać zatwierdzone, zanim będzie można wprowadzić w nim zmianę.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-117">In the list of customer fields, select then **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="ec4c6-118">Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Przepływy pracy dla rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-118">Go to **Accounts receivable \> Setup \> Accounts receivable workflows**.</span></span>
6. <span data-ttu-id="ec4c6-119">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-119">Select **New**.</span></span>
7. <span data-ttu-id="ec4c6-120">Wybierz pozycję **Przepływ pracy proponowanej zmiany u odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-120">Select **Proposed customer change workflow**.</span></span> 
8. <span data-ttu-id="ec4c6-121">Skonfiguruj przepływ pracy, tak aby pasował do Twojego procesu zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-121">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="ec4c6-122">Element zatwierdzania przepływu pracy **Zatwierdzenie proponowanej zmiany u odbiorcy w przepływie pracy** zastosuje zmiany do danych odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-122">The **Workflow approval for proposed customer change** workflow approval element will apply the changes to the customer.</span></span>

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="ec4c6-123">Zmienianie informacji dotyczących odbiorcy i przesyłanie zmian do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="ec4c6-123">Change customer information and submit the changes to the workflow</span></span>

<span data-ttu-id="ec4c6-124">Jeśli zmienisz pole, które jest skonfigurowane do użycia w przepływie pracy, zostanie wyświetlona strona **Proponowane zmiany**.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-124">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="ec4c6-125">Na tej stronie jest wyświetlana oryginalna wartość pola oraz nowa wprowadzona przez Ciebie wartość.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-125">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="ec4c6-126">Przywracana jest oryginalna wartość zmienionego przez Ciebie pola.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-126">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="ec4c6-127">Komunikat o stanie na stronie informuje, że Twoje zmiany nie zostały przesłane.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-127">A status message on the page informs you that your changes haven't been submitted.</span></span>

<span data-ttu-id="ec4c6-128">Zawsze, gdy zmienisz pole, które jest skonfigurowane do użycia w przepływie pracy, to pole jest dodawane do listy proponowanych zmian.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-128">Every time that you change a field that is enabled for the workflow, that field is added to the list of proposed changes.</span></span> <span data-ttu-id="ec4c6-129">Aby odrzucić proponowaną wartość pola, użyj przycisku **Odrzuć**, który znajduje się obok pola na liście.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-129">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="ec4c6-130">Aby odrzucić wszystkie zmiany, użyj przycisku **Odrzuć wszystkie zmiany**, który znajduje się u dołu strony.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-130">To discard all changes, use the **Discard all change** button at the bottom of the page.</span></span> <span data-ttu-id="ec4c6-131">Wybierz przycisk **OK**, aby zamknąć stronę.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-131">Select **OK** to close the page.</span></span>

<span data-ttu-id="ec4c6-132">Jeśli będzie dostępna co najmniej jedna proponowana zmiana, w okienku akcji zostaną wyświetlone dwa dodatkowe menu: **Proponowane zmiany** i **Przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-132">After you have at least one proposed change, two additional menus appear on the Action Pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="ec4c6-133">Wybierz pozycję **Proponowane zmiany**, aby otworzyć stronę **Proponowane zmiany** i przejrzeć swoje zmiany.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-133">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="ec4c6-134">Wybierz kolejno pozycje **Przepływ pracy \> Prześlij**, aby przesłać zmiany do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-134">Select **Workflow \> Submit** to submit the changes to the workflow.</span></span>

    <span data-ttu-id="ec4c6-135">Status na stronie zmienia się na **Zmiany oczekują na zatwierdzenie**.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-135">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="ec4c6-136">Przepływ pracy jest zgodny ze standardowym procesem przepływu pracy w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-136">The workflow follows the standard workflow process in the application.</span></span> <span data-ttu-id="ec4c6-137">Osoba zatwierdzająca jest kierowana na stronę **Odbiorca**, gdzie może przejrzeć zmiany na stronie **Proponowane zmiany**, a następnie wybrać **Przepływ pracy \> Zatwierdź**, aby zatwierdzić przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-137">The approver is directed to the **Customer** page where the changes can be reviewed on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="ec4c6-138">Po wykonaniu wszystkich zatwierdzeń pola zostaną zaktualizowane za pomocą proponowanych przez Ciebie wartości.</span><span class="sxs-lookup"><span data-stu-id="ec4c6-138">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]