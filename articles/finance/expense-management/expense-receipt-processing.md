---
title: Przetwarzanie paragonów kosztowych
description: Ten temat zawiera informacje o przetwarzaniu za pomocą optycznego rozpoznawania znaków (OCR) dla paragonów. Ta funkcja ma na celu zwiększenie komfortu pracy użytkownika podczas tworzenia raportów z wydatków w Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 2e819521828b054f70476b1eb061ee08c486d09f
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113693"
---
# <a name="public-preview-expense-receipt-processing"></a><span data-ttu-id="993ec-104">Publiczna wersja - podgląd: przetwarzanie wydatków z paragonów</span><span class="sxs-lookup"><span data-stu-id="993ec-104">Public Preview: Expense receipt processing</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


<span data-ttu-id="993ec-105">Wpisywanie wydatków zostało ulepszone przez wprowadzenie optycznego rozpoznawania znaków (OCR) do przetwarzania paragonów.</span><span class="sxs-lookup"><span data-stu-id="993ec-105">Expense entry has been enhanced through the introduction of optical character recognition (OCR) processing for receipts.</span></span> <span data-ttu-id="993ec-106">Ta funkcja ma na celu zwiększenie komfortu pracy użytkownika podczas tworzenia raportów z wydatków.</span><span class="sxs-lookup"><span data-stu-id="993ec-106">This feature is designed to improve the user experience when expense reports are created.</span></span>

## <a name="key-features"></a><span data-ttu-id="993ec-107">Najważniejsze funkcje</span><span class="sxs-lookup"><span data-stu-id="993ec-107">Key features</span></span>

- <span data-ttu-id="993ec-108">Nazwa handlowca, data i łączna kwota są wyodrębniane z paragonów.</span><span class="sxs-lookup"><span data-stu-id="993ec-108">The merchant name, date, and total amount are extracted from receipts.</span></span>
- <span data-ttu-id="993ec-109">Funkcja próbuje dopasować niepołączone paragony do niepołączonych transakcji dotyczących wydatków.</span><span class="sxs-lookup"><span data-stu-id="993ec-109">The feature tries to match unattached receipts to unattached expense transactions.</span></span>
- <span data-ttu-id="993ec-110">Użytkownicy mogą tworzyć ręcznie wprowadzone transakcje wydatków z paragonów.</span><span class="sxs-lookup"><span data-stu-id="993ec-110">Users can create manually entered expense transactions from receipts.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="993ec-111">Przykłady użycia</span><span class="sxs-lookup"><span data-stu-id="993ec-111">Usage examples</span></span>

- <span data-ttu-id="993ec-112">**Umożliwia automatyczne dołączanie paragonów, które uwzględniają transakcje karty kredytowej podczas tworzenia raportu z wydatków**.</span><span class="sxs-lookup"><span data-stu-id="993ec-112">**Automatically attach receipts that include credit card transactions when an expense report is created.**</span></span>

    1. <span data-ttu-id="993ec-113">Otwórz obszar roboczy **Zarządzanie wydatkami**.</span><span class="sxs-lookup"><span data-stu-id="993ec-113">Open the **Expense management** workspace.</span></span>
    2. <span data-ttu-id="993ec-114">Na karcie **Przychody** sprawdź, czy istnieją niedołączone paragony.</span><span class="sxs-lookup"><span data-stu-id="993ec-114">On the **Receipts** tab, verify that unattached receipts exist.</span></span> <span data-ttu-id="993ec-115">Możesz również wgrać paragony na karcie **Przychody**.</span><span class="sxs-lookup"><span data-stu-id="993ec-115">You can also upload receipts on the **Receipts** tab.</span></span>
    3. <span data-ttu-id="993ec-116">Na karcie **Wydatki** sprawdź, czy istnieją niedołączone wydatki.</span><span class="sxs-lookup"><span data-stu-id="993ec-116">On the **Expenses** tab, verify that unattached expenses exist.</span></span> <span data-ttu-id="993ec-117">Zazwyczaj administrator wydatków importuje te wydatki z danych od dostawcy karty kredytowej.</span><span class="sxs-lookup"><span data-stu-id="993ec-117">Typically, the expense administrator imports these expenses from the credit card provider.</span></span>
    4. <span data-ttu-id="993ec-118">Wybierz **Nowy raport o wydatkach**.</span><span class="sxs-lookup"><span data-stu-id="993ec-118">Select **New expense report**.</span></span> <span data-ttu-id="993ec-119">Należy zauważyć, że po utworzeniu raportu o wydatkach można również uwzględnić wydatki i paragony.</span><span class="sxs-lookup"><span data-stu-id="993ec-119">Notice that you can include expenses, and receipts, now as well, when you create an expense report.</span></span> <span data-ttu-id="993ec-120">W przypadku dodania zarówno wydatków, jak i paragonów zostanie wyzwolone automatyczne dopasowywanie paragonów do wydatków.</span><span class="sxs-lookup"><span data-stu-id="993ec-120">If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.</span></span>

- <span data-ttu-id="993ec-121">**Utwórz wydatek lub Dopasuj wydatek z paragonu**.</span><span class="sxs-lookup"><span data-stu-id="993ec-121">**Create an expense, or match an expense from a receipt.**</span></span>

    1. <span data-ttu-id="993ec-122">W raporcie z wydatków na karcie **Paragony** dołącz paragon, zaznaczając opcję **Dodaj paragony**.</span><span class="sxs-lookup"><span data-stu-id="993ec-122">On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.</span></span>
    2. <span data-ttu-id="993ec-123">W obszarze przekazanego obrazu paragonu zwróć uwagę na opcje **Utwórz** i **Powiąż**.</span><span class="sxs-lookup"><span data-stu-id="993ec-123">Under the uploaded image of the receipt, notice the **Create** and **Match** options.</span></span>

        - <span data-ttu-id="993ec-124">Wybierz opcję **Utwórz**, aby utworzyć ręcznie wprowadzaną transakcję wydatku, a następnie wypełnij wartości wyodrębnione z paragonu.</span><span class="sxs-lookup"><span data-stu-id="993ec-124">Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.</span></span>
        - <span data-ttu-id="993ec-125">W przypadku wybrania opcji **Powiąż**, system próbuje dopasować istniejący wydatek do paragonu.</span><span class="sxs-lookup"><span data-stu-id="993ec-125">If you select **Match**, the system tries to match an existing expense to the receipt.</span></span>

## <a name="installation"></a><span data-ttu-id="993ec-126">Instalacja</span><span class="sxs-lookup"><span data-stu-id="993ec-126">Installation</span></span>

<span data-ttu-id="993ec-127">Ta funkcja działa w połączeniu z **Funkcją wypracowania raportów z wydatków**, ułatwiającą uproszczenie pracy z wydatkami.</span><span class="sxs-lookup"><span data-stu-id="993ec-127">This feature works in combination with the **Expense reports re-imagined** feature to help simplify the expense experience.</span></span>

<span data-ttu-id="993ec-128">Aby skorzystać z tych zaawansowanych funkcji wydatków, należy zainstalować dodatek usługi zarządzania wydatkami dla rozwiązania Microsoft Dynamics 365 Finance i włączyć funkcje w wystąpieniu.</span><span class="sxs-lookup"><span data-stu-id="993ec-128">To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance.</span></span> <span data-ttu-id="993ec-129">Dostęp do dodatku można uzyskać z poziomu projektu w ramach usługi Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="993ec-129">You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="993ec-130">Zaloguj się do usługi LCS i otwórz żądane środowisko.</span><span class="sxs-lookup"><span data-stu-id="993ec-130">Sign in to LCS, and open the desired environment.</span></span>
2. <span data-ttu-id="993ec-131">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="993ec-131">Go to **Full details**.</span></span>
3. <span data-ttu-id="993ec-132">Wybierz opcję **Zarządzaj** lub przewiń w dół do skróconej karty **dodatków środowiska**.</span><span class="sxs-lookup"><span data-stu-id="993ec-132">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
4. <span data-ttu-id="993ec-133">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="993ec-133">Select **Install a new add-in**.</span></span>
5. <span data-ttu-id="993ec-134">Wybierz **Usługę zarządzania wydatkami**.</span><span class="sxs-lookup"><span data-stu-id="993ec-134">Select **Expense Management Service**.</span></span>
6. <span data-ttu-id="993ec-135">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="993ec-135">Follow the installation guide, and agree to the terms and conditions.</span></span>
7. <span data-ttu-id="993ec-136">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="993ec-136">Select **Install**.</span></span>

<span data-ttu-id="993ec-137">W obszarze roboczym **Zarządzanie funkcjami** włącz następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="993ec-137">In the **Feature management** workspace, turn on the following features:</span></span>

- <span data-ttu-id="993ec-138">Raporty wydatków w nowej wersji</span><span class="sxs-lookup"><span data-stu-id="993ec-138">Expense reports re-imagined</span></span>
- <span data-ttu-id="993ec-139">Automatyczne uzgadnianie i tworzenie wydatku z paragonu</span><span class="sxs-lookup"><span data-stu-id="993ec-139">Auto-match and create expense from receipt</span></span>

<span data-ttu-id="993ec-140">Po włączeniu tych funkcji są wykonywane następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="993ec-140">When you turn on these features the following actions occur:</span></span>

- <span data-ttu-id="993ec-141">Istniejący obszar roboczy **Zarządzania wydatkami** jest zastępowany nowym obszarem roboczym.</span><span class="sxs-lookup"><span data-stu-id="993ec-141">The existing **Expense management** workspace is replaced with the new workspace.</span></span>
- <span data-ttu-id="993ec-142">Zostanie dodany nowy element menu widoczności pola wydatków.</span><span class="sxs-lookup"><span data-stu-id="993ec-142">A new menu item for expense field visibility is added.</span></span>
- <span data-ttu-id="993ec-143">Można nadal otworzyć poprzednią stronę **Raportów z wydatków**, przechodząc do modułu **Zarządzanie wydatkami > Moje wydatki> Raporty o wydatkach**.</span><span class="sxs-lookup"><span data-stu-id="993ec-143">You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.</span></span>
- <span data-ttu-id="993ec-144">Przepływy pracy i wszelkie zatwierdzenia nadal powodują przekierowanie do istniejącej strony raportów z wydatków.</span><span class="sxs-lookup"><span data-stu-id="993ec-144">Workflows and any approvals still take you to the existing expense reports page.</span></span>
- <span data-ttu-id="993ec-145">Paragony będą przetwarzane przez usługi poznawcze Microsoft Azure Cognitive Services, a metadane zostaną wyodrębnione i dodane.</span><span class="sxs-lookup"><span data-stu-id="993ec-145">Receipts will be processed through Microsoft Azure Cognitive Services, and metadata will be extracted and added.</span></span>
- <span data-ttu-id="993ec-146">Dodawana jest opcja umożliwiająca utworzenie raportu z wydatków, który zawiera dopasowane niedołączone paragony.</span><span class="sxs-lookup"><span data-stu-id="993ec-146">An option is added that lets you create an expense report that includes matched unattached receipts.</span></span>
- <span data-ttu-id="993ec-147">Opcja dodawana do raportów z wydatków umożliwia utworzenie wiersza wydatku na podstawie paragonu lub próbę dopasowania istniejącego paragonu do istniejącego wiersza wydatku.</span><span class="sxs-lookup"><span data-stu-id="993ec-147">An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.</span></span>

<span data-ttu-id="993ec-148">Aby uzyskać więcej informacji o nowej funkcji wypracowywania raportów z wydatków, przejrzyj [Nowa funkcja analizowania raportów z wydatków](ExpenseWorkspaceNew.md).</span><span class="sxs-lookup"><span data-stu-id="993ec-148">For more information about the Expense reports re-imagined feature, see [Expense reports reimagined](ExpenseWorkspaceNew.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="993ec-149">Często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="993ec-149">Frequently asked questions</span></span>

<span data-ttu-id="993ec-150">**Czy firma Microsoft używa moich danych do swoich modeli?**</span><span class="sxs-lookup"><span data-stu-id="993ec-150">**Does Microsoft use my data for its models?**</span></span>

<span data-ttu-id="993ec-151">Nie, firma Microsoft opracowała ogólny model nauki dla usługi przetwarzania potwierdzeń odbioru.</span><span class="sxs-lookup"><span data-stu-id="993ec-151">No, Microsoft has built a general machine learning model for its receipt processing service.</span></span> <span data-ttu-id="993ec-152">Ten model nie jest oparty na wgrywanych przez Ciebie paragonach.</span><span class="sxs-lookup"><span data-stu-id="993ec-152">This model isn't based on the receipts that you upload.</span></span>

<span data-ttu-id="993ec-153">**Gdzie jest dostępna i przetwarzana ta funkcja?**</span><span class="sxs-lookup"><span data-stu-id="993ec-153">**Where is this feature available and processed?**</span></span>

<span data-ttu-id="993ec-154">Obecnie są obsługiwane Stany Zjednoczone.</span><span class="sxs-lookup"><span data-stu-id="993ec-154">Currently, the United States is supported.</span></span>

<span data-ttu-id="993ec-155">**Gdzie przechodzą moje paragony?**</span><span class="sxs-lookup"><span data-stu-id="993ec-155">**Where do my receipts go?**</span></span>

<span data-ttu-id="993ec-156">Finanse będą kontaktować się z usługami poznawczymi w celu wyodrębnienia danych z pól.</span><span class="sxs-lookup"><span data-stu-id="993ec-156">Finance will contact Cognitive Services to extract the field data.</span></span> <span data-ttu-id="993ec-157">Usługi poznawcze zachowają kopię paragonu do 24 godzin, podczas gdy trwać będzie przetwarzanie.</span><span class="sxs-lookup"><span data-stu-id="993ec-157">Cognitive Services will retain a copy of your receipt for up to 24 hours while processing occurs.</span></span> <span data-ttu-id="993ec-158">Po zakończeniu przetwarzania, usługi poznawcze usuną paragon.</span><span class="sxs-lookup"><span data-stu-id="993ec-158">After processing is completed, Cognitive Services will remove the receipt.</span></span> <span data-ttu-id="993ec-159">Paragony nadal są przechowywane w Finance.</span><span class="sxs-lookup"><span data-stu-id="993ec-159">Receipts are still stored in Finance.</span></span>

<span data-ttu-id="993ec-160">Aby uzyskać więcej informacji, przeczytaj temat [Włączanie funkcji rozpoznawania paragonów z nowymi możliwościami Form Recognizer](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span><span class="sxs-lookup"><span data-stu-id="993ec-160">For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span></span>
