---
title: Dokumenty uzasadnienia planowania budżetu
description: Dokumenty uzasadnienia dostarczają osobom wnioskującym o budżet wyjaśnień, dlaczego utworzenie określonego budżetu jest niezbędne.
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 321da6643b421070ddd9f32bddd3e8d72f0adb86
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446922"
---
# <a name="budget-planning-justification-documents"></a><span data-ttu-id="61684-103">Dokumenty uzasadnienia planowania budżetu</span><span class="sxs-lookup"><span data-stu-id="61684-103">Budget planning justification documents</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61684-104">Dokumenty uzasadnienia dostarczają osobom wnioskującym o budżet wyjaśnień, dlaczego utworzenie określonego budżetu jest niezbędne.</span><span class="sxs-lookup"><span data-stu-id="61684-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="61684-105">Menedżera budżetu tworzy szablon planu budżetu w programie Microsoft Word i przypisuje go do bieżącego procesu planowania budżetu.</span><span class="sxs-lookup"><span data-stu-id="61684-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="61684-106">Następnie właściciele budżetów mogą otworzyć szablon i automatycznie wypełnić dane w programie Word na podstawie swoich żądań budżetów.</span><span class="sxs-lookup"><span data-stu-id="61684-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="61684-107">Potem mogą wprowadzić dodatkowy tekst lub dane, a następnie zapisać i dołączyć spersonalizowany dokument uzasadnienia do planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="61684-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="61684-108">Konfigurowanie dodatku Microsoft Dynamics do obsługi programu Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="61684-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="61684-109">Otwórz dokument programu Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="61684-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="61684-110">Na wstążce kliknij przycisk **Wstaw**, a następnie kliknij opcję **Sklep**.</span><span class="sxs-lookup"><span data-stu-id="61684-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="61684-111">Wyszukaj dodatek pakietu Office dla usługi Microsoft Dynamics i kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="61684-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="61684-112">W programie Word w prawym okienku kliknij opcję **Dodaj informacje dotyczące serwera**.</span><span class="sxs-lookup"><span data-stu-id="61684-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="61684-113">Wpisz lub wklej adres URL serwera i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="61684-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="61684-114">Definiowanie szablonu uzasadnienia w programie Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="61684-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="61684-115">Po zalogowaniu w dodatku pakietu Office dla usługi Microsoft Dynamics kliknij opcję **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="61684-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="61684-116">Dla informacji nagłówka użyj przycisku **Dodaj pola**.</span><span class="sxs-lookup"><span data-stu-id="61684-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="61684-117">Zaznacz źródło danych jednostki BudgetPlanJustification, a następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="61684-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="61684-118">**Uwaga:** Ta jednostka jest wymagana dla każdego dokumentu uzasadnienia.</span><span class="sxs-lookup"><span data-stu-id="61684-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="61684-119">Mogą być używane również inne jednostki, ale w razie braku tej jednostki przekazywanie z powrotem do Microsoft Dynamics 365 Finance zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="61684-119">Other entities can be used but the upload back to Microsoft Dynamics 365 Finance will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="61684-120">W dokumencie programu Word dodaj etykiety i wartości BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter i DocumentNumber.</span><span class="sxs-lookup"><span data-stu-id="61684-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="61684-121">**Uwaga:** W razie potrzeby można użyć własnych spersonalizowanych etykiet zamiast standardowych etykiet.</span><span class="sxs-lookup"><span data-stu-id="61684-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="61684-122">Kliknij przycisk **Gotowe**, aby zakończyć konfigurowanie sekcji nagłówka.</span><span class="sxs-lookup"><span data-stu-id="61684-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="61684-123">Dla szczegółów kwot planu budżetu na poziomie wiersza kliknij opcję **Dodaj tabelę**.</span><span class="sxs-lookup"><span data-stu-id="61684-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="61684-124">Ponownie zaznacz źródło danych jednostki BudgetPlanJustification, a następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="61684-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="61684-125">Dodaj pola EffectiveDate, ScenarioName, AccountDisplayValue i AccountingCurrencyExpenseAmount.</span><span class="sxs-lookup"><span data-stu-id="61684-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="61684-126">**Uwaga:** Jeśli są dostępne komentarze do dodania w indywidualnych wierszach planu budżetu, można je dodać do tabeli w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="61684-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="61684-127">Wprowadź wszelkie dodatkowe instrukcje dla użytkownika końcowego i zastosuj do dokumentu niezbędne formatowanie lub style.</span><span class="sxs-lookup"><span data-stu-id="61684-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="61684-128">Zapisz dokument na lokalnym komputerze i zamknij plik.</span><span class="sxs-lookup"><span data-stu-id="61684-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="61684-129">Konfigurowanie używania szablonu uzasadnienia w procesie planowania budżetu</span><span class="sxs-lookup"><span data-stu-id="61684-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="61684-130">Wybierz kolejno opcje **Budżetowanie** &gt; **Ustawienia** &gt; **Planowanie budżetu** &gt; **Szablony dokumentów uzasadnienia**.</span><span class="sxs-lookup"><span data-stu-id="61684-130">Go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="61684-131">Kliknij przycisk **Nowy** i przejdź do nowo utworzonego dokumentu programu Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="61684-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="61684-132">Nadaj szablonowi nazwę wyświetlaną i opis.</span><span class="sxs-lookup"><span data-stu-id="61684-132">Enter a template display name and description.</span></span> <span data-ttu-id="61684-133">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="61684-133">Click **OK**.</span></span>
4.  <span data-ttu-id="61684-134">Wybierz kolejno opcje **Budżetowanie** &gt; **Ustawienia** &gt; **Planowanie** **budżetu** &gt; **Proces planowania budżetu**.</span><span class="sxs-lookup"><span data-stu-id="61684-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="61684-135">Zaznacz proces, w którym ma być używany szablon uzasadnienia, i kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="61684-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="61684-136">W polu **Szablon dokumentu uzasadnienia** zaznacz odpowiedni szablon i zapisz.</span><span class="sxs-lookup"><span data-stu-id="61684-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="61684-137">Edytowanie i zapisywanie spersonalizowanych dokumentów uzasadnienia</span><span class="sxs-lookup"><span data-stu-id="61684-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="61684-138">Utwórz plan budżetu lub otwórz istniejący plan budżetu.</span><span class="sxs-lookup"><span data-stu-id="61684-138">Create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="61684-139">W menu rozwijanym **Uzasadnienie** wybierz polecenie **Utwórz nowe uzasadnienie**.</span><span class="sxs-lookup"><span data-stu-id="61684-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="61684-140">Wypełnij pola szczegółów, a następnie w menu rozwijanym **Uzasadnienie** wybierz opcję przekazania spersonalizowanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="61684-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>




