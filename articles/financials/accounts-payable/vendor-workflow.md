---
title: "Przepływ pracy obsługi dostawcy"
description: "Można zmodyfikować informacje o dostawcy, a następnie użyć przepływu pracy do ich zatwierdzenia."
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Vendor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 950a1852acf9f3e4747ce2d55738c0eb3a646897
ms.contentlocale: pl-pl
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-workflow"></a><span data-ttu-id="16f01-103">Przepływ pracy obsługi dostawcy</span><span class="sxs-lookup"><span data-stu-id="16f01-103">Vendor workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16f01-104">Jeśli jest używany przepływ pracy obsługi dostawcy, zmiany wprowadzone w określonych polach są wysyłane do przepływu pracy w celu zatwierdzenia, zanim zostaną dodane do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="16f01-104">When the vendor workflow is used, changes that are made to specific fields are sent to the workflow for approval before they are added to the vendor.</span></span>

## <a name="set-up-the-vendor-workflow"></a><span data-ttu-id="16f01-105">Konfigurowanie przepływu pracy obsługi dostawcy</span><span class="sxs-lookup"><span data-stu-id="16f01-105">Set up the vendor workflow</span></span>

<span data-ttu-id="16f01-106">Aby korzystać z funkcji przepływu pracy, należy ją włączyć.</span><span class="sxs-lookup"><span data-stu-id="16f01-106">Before you can use the workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="16f01-107">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="16f01-107">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="16f01-108">Na karcie **Ogólne** na skróconej karcie **Zatwierdzenie dostawcy** dla opcji **Włącz zatwierdzanie dostawców** wybierz ustawienie **Tak**.</span><span class="sxs-lookup"><span data-stu-id="16f01-108">On the **General** tab, on the **Vendor approval** FastTab, set the **Enable vendor approvals** option to **Yes**.</span></span>
3. <span data-ttu-id="16f01-109">W polu **Zachowanie jednostki danych** wybierz zachowanie, które ma być używane podczas importowania danych:</span><span class="sxs-lookup"><span data-stu-id="16f01-109">In the **Data entity behavior** field, select the behavior that should be used when data is imported:</span></span>

    - <span data-ttu-id="16f01-110">**Zezwalaj na zmiany bez zatwierdzenia** — jednostka danych może aktualizować rekord dostawcy bez przetwarzania go za pomocą przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="16f01-110">**Allow changes without approval** – The data entity can update the vendor record without processing it through the workflow.</span></span>
    - <span data-ttu-id="16f01-111">**Odrzuć zmiany** — nie można wprowadzać zmian w rekordzie dostawcy.</span><span class="sxs-lookup"><span data-stu-id="16f01-111">**Reject changes** – Changes can't be made to the vendor record.</span></span> <span data-ttu-id="16f01-112">Import zakończy się niepowodzeniem dla pól objętych przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="16f01-112">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="16f01-113">**Utwórz propozycje zmian** — wszystkie pola zostaną zmodyfikowane, z wyjątkiem pól objętych przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="16f01-113">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="16f01-114">Nowe wartości tych pól zostaną dodane do dostawcy jako proponowane zmiany, a przepływ pracy zostanie uruchomiony automatycznie.</span><span class="sxs-lookup"><span data-stu-id="16f01-114">The new values for those fields will be added to the vendor as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="16f01-115">Na liście pól dostawcy zaznacz pole wyboru **Włącz** dla każdego pola, które musi zostać zatwierdzone, zanim będzie można dokonać zmian.</span><span class="sxs-lookup"><span data-stu-id="16f01-115">In the list of vendor fields, select the **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="16f01-116">Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Przepływy pracy dla rozrachunków z dostawcami**.</span><span class="sxs-lookup"><span data-stu-id="16f01-116">Go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
6. <span data-ttu-id="16f01-117">Wybierz **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="16f01-117">Select **New**.</span></span>
7. <span data-ttu-id="16f01-118">Zaznacz opcję **Przepływ pracy proponowanych zmian u dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="16f01-118">Select **Proposed vendor changes workflow**.</span></span> 
8. <span data-ttu-id="16f01-119">Skonfiguruj przepływ pracy, tak aby pasował do stosowanego procesu zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="16f01-119">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="16f01-120">Zawarty w przepływie pracy element zatwierdzania **Zatwierdzenie proponowanej zmiany u dostawcy w przepływie pracy** spowoduje zastosowanie zmian do dostawcy.</span><span class="sxs-lookup"><span data-stu-id="16f01-120">The **Workflow approval for proposed vendor change** workflow approval element will apply the changes to the vendor.</span></span>

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="16f01-121">Zmiana informacji o dostawcy i przesyłanie zmian do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="16f01-121">Change vendor information and submit the changes to the workflow</span></span>

<span data-ttu-id="16f01-122">Po zmodyfikowaniu pola objętego przepływem pracy zostanie wyświetlona strona **Proponowane zmiany**.</span><span class="sxs-lookup"><span data-stu-id="16f01-122">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="16f01-123">Ta strona pokazuje oryginalną wartość pola i nowo wprowadzoną wartość.</span><span class="sxs-lookup"><span data-stu-id="16f01-123">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="16f01-124">W zmodyfikowanym polu jest przywracana pierwotna wartość.</span><span class="sxs-lookup"><span data-stu-id="16f01-124">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="16f01-125">Dodatkowo komunikat o stanie informuje, że zmiany nie został przesłane.</span><span class="sxs-lookup"><span data-stu-id="16f01-125">A status message also informs you that your changes haven't been submitted.</span></span> 

<span data-ttu-id="16f01-126">Zawsze gdy modyfikujesz pole objęte przepływem pracy, jest ono dodawane do listy na stronie **Proponowane zmiany**.</span><span class="sxs-lookup"><span data-stu-id="16f01-126">Every time that you change a field that is enabled for the workflow, that field is added to the list on the **Proposed changes** page.</span></span> <span data-ttu-id="16f01-127">Aby odrzucić proponowaną wartość pola, należy użyć przycisku **Odrzuć** widocznego obok pola na liście.</span><span class="sxs-lookup"><span data-stu-id="16f01-127">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="16f01-128">Aby odrzucić wszystkie zmiany, należy użyć przycisku **Odrzuć wszystkie zmiany** znajdującego się u dołu strony.</span><span class="sxs-lookup"><span data-stu-id="16f01-128">To discard all changes, use the **Discard all changes** button at the bottom of the page.</span></span> <span data-ttu-id="16f01-129">Kliknij przycisk **OK**, aby zamknąć stronę.</span><span class="sxs-lookup"><span data-stu-id="16f01-129">Select **OK** to close the page.</span></span>

<span data-ttu-id="16f01-130">Gdy istnieje co najmniej jedna proponowana zmiana, w okienku akcji pojawiają się dwie dodatkowe karty: **Proponowane zmiany** i **Przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="16f01-130">After you have at least one proposed change, two additional tabs appear on the action pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="16f01-131">Wybierz opcję **Proponowane zmiany**, aby otworzyć stronę **Proponowane zmiany** i przejrzeć zmiany.</span><span class="sxs-lookup"><span data-stu-id="16f01-131">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="16f01-132">Wybierz kolejno opcje **Przepływ pracy \> Prześlij**, aby przesłać zmiany do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="16f01-132">Select **Workflow \> Submit to submit the changes to workflow**.</span></span>

    <span data-ttu-id="16f01-133">Stan na stronie zmieni się na **Zmiany oczekują na zatwierdzenie**.</span><span class="sxs-lookup"><span data-stu-id="16f01-133">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="16f01-134">Przepływ pracy przebiega w standardowy sposób określony w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="16f01-134">The workflow follows the standard workflow process in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="16f01-135">Osoba zatwierdzająca jest kierowana do strony **Dostawca**, gdzie może przejrzeć zmiany wyświetlane na stronie **Proponowane zmiany**, a następnie wybrać kolejno opcje **Przepływ pracy \> Zatwierdź** w celu zatwierdzenia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="16f01-135">The approver is directed to the **Vendor** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="16f01-136">Po sfinalizowaniu wszystkich zatwierdzeń pola są aktualizowane o zaproponowane wartości.</span><span class="sxs-lookup"><span data-stu-id="16f01-136">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>

