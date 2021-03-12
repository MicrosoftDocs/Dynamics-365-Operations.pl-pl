---
title: Przygotowanie firmy w procesie konsolidacji
description: Podczas konsolidacji transakcje z kilku zestawów kont podmiotów prawnych są gromadzone w jednym zestawie kont podmiotów prawnych. W tym temacie wyjaśniono, jak przygotować firmę do konsolidacji.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: f6fce69724945448f961769dd383d1047a5d13c4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990315"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a><span data-ttu-id="b729f-104">Przygotowanie firmy w procesie konsolidacji</span><span class="sxs-lookup"><span data-stu-id="b729f-104">Prepare a legal entity for the consolidation process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b729f-105">Podczas konsolidacji transakcje z kilku zestawów kont podmiotów prawnych są gromadzone w jednym zestawie kont podmiotów prawnych.</span><span class="sxs-lookup"><span data-stu-id="b729f-105">During a consolidation, you gather transactions from several sets of legal entity accounts into a single set of legal entity accounts.</span></span> <span data-ttu-id="b729f-106">W tym temacie wyjaśniono, jak przygotować firmę do konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="b729f-106">This topic explains how to prepare a legal entity for a consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="b729f-107">Zalecamy użycie narzędzia Management Reporter dla Microsoft Dynamics 365 Finance w celu połączenia wyników finansowych wielu firm w skonsolidowanym formacie.</span><span class="sxs-lookup"><span data-stu-id="b729f-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="b729f-108">Program Management Reporter umożliwia tworzenie skonsolidowanych raportów finansowych dla różnych firm, używanie programu Excel do importowania danych konsolidacji z innych źródeł oraz przetłumaczenie kwot na dowolną liczbę walut raportowania bez konieczności uruchamiania procesu konsolidacji w Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b729f-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

<span data-ttu-id="b729f-109">Można wydrukować raporty, takie jak sprawozdania finansowe z firmy skonsolidowanej.</span><span class="sxs-lookup"><span data-stu-id="b729f-109">You can print reports, such as financial statements, from the consolidated legal entity.</span></span> <span data-ttu-id="b729f-110">Jednak nie można użyć firmy skonsolidowanej dla transakcji dziennych.</span><span class="sxs-lookup"><span data-stu-id="b729f-110">However, you can't use the consolidated legal entity for daily transactions.</span></span>

<span data-ttu-id="b729f-111">Można konsolidować dane z firm, które używają innych baz danych niż firma skonsolidowana.</span><span class="sxs-lookup"><span data-stu-id="b729f-111">You can consolidate data from legal entities that use different databases than the consolidated legal entity.</span></span> <span data-ttu-id="b729f-112">Ten proces konsolidacji jest nazywany *konsolidacją importu*.</span><span class="sxs-lookup"><span data-stu-id="b729f-112">This consolidation process is referred to as an *import consolidation*.</span></span> <span data-ttu-id="b729f-113">Firmy mogą także użyć tej samej bazy danych jako skonsolidowane firmy.</span><span class="sxs-lookup"><span data-stu-id="b729f-113">Alternatively, the legal entities can use the same database as the consolidated legal entity.</span></span> <span data-ttu-id="b729f-114">Ten proces konsolidacji jest nazywany *konsolidacją online*.</span><span class="sxs-lookup"><span data-stu-id="b729f-114">This consolidation process is referred to as an *online consolidation*.</span></span>

<span data-ttu-id="b729f-115">Firma skonsolidowana gromadzi wyniki i salda swoich oddziałów.</span><span class="sxs-lookup"><span data-stu-id="b729f-115">The consolidated legal entity collects the results and balances of the subsidiaries.</span></span> <span data-ttu-id="b729f-116">W celu przygotowania firmy skonsolidowanej do konsolidacji, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b729f-116">To prepare a consolidated legal entity for a consolidation, follow these steps.</span></span>

1. <span data-ttu-id="b729f-117">Wybierz kolejno opcje **Księga główna \> Konfiguracja \> Organizacja \> Firmy**.</span><span class="sxs-lookup"><span data-stu-id="b729f-117">Go to **General ledger \> Setup \> Organization \> Legal entities**.</span></span>
2. <span data-ttu-id="b729f-118">Kliknij opcje **Nowy**, aby utworzyć nowy podmiot prawny, który będzie konsolidowaną firmą.</span><span class="sxs-lookup"><span data-stu-id="b729f-118">Select **New** to create the legal entity that will be the consolidated legal entity.</span></span>
3. <span data-ttu-id="b729f-119">Zaznacz pole wyboru **Użyj w procesie konsolidacji finansowej**, a następnie wprowadź informacje o konsolidowanej firmie.</span><span class="sxs-lookup"><span data-stu-id="b729f-119">Select the **Use for financial consolidation process** check box, and then enter information about the consolidated legal entity.</span></span> <span data-ttu-id="b729f-120">Pamiętaj, aby wprowadzić te informacje dokładnie tak, jak chcesz, aby pojawiały się w sprawozdaniach finansowych podmiotu prawnego objętego konsolidacją.</span><span class="sxs-lookup"><span data-stu-id="b729f-120">Be sure to enter this information exactly as you want it to appear on financial statements for the consolidated legal entity.</span></span>
4. <span data-ttu-id="b729f-121">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b729f-121">Close the page.</span></span>
5. <span data-ttu-id="b729f-122">Wybierz firmę skonsolidowaną w polu w prawym górnym rogu strony, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="b729f-122">Select the consolidated legal entity in the field in the upper-right corner of the page, and then select **OK**.</span></span>
6. <span data-ttu-id="b729f-123">Wybierz kolejno opcje **Księga główna \> Ustawienia \> Księga**.</span><span class="sxs-lookup"><span data-stu-id="b729f-123">Go to **General ledger \> Setup \> Ledger**.</span></span>
7. <span data-ttu-id="b729f-124">Umożliwia wybranie planu kont, kalendarza obrachunkowego, waluty rozliczeniowej, opcjonalnej waluty raportowania i domyślnego typu kursu wymiany dla konsolidowanej firmy.</span><span class="sxs-lookup"><span data-stu-id="b729f-124">Select the chart of accounts, the fiscal calendar, the accounting currency, an optional reporting currency, and the default type of exchange rate for the consolidated legal entity.</span></span> 
8. <span data-ttu-id="b729f-125">Wybierz kolejno opcje **Księga główna \> Ustawienia \> Waluta \> Kursy wymiany waluty**.</span><span class="sxs-lookup"><span data-stu-id="b729f-125">Go to **General ledger \> Setup \> Currency \> Currency exchange rates**.</span></span>
9. <span data-ttu-id="b729f-126">Skonfiguruj kursy wymiany w odpowiednich okresach dla walut oddziałów firm.</span><span class="sxs-lookup"><span data-stu-id="b729f-126">Set up currency exchange rates in relevant periods for the currencies of the subsidiary legal entities.</span></span>
10. <span data-ttu-id="b729f-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b729f-127">Close the page.</span></span>
11. <span data-ttu-id="b729f-128">Jeśli firma skonsolidowana ma przedstawicielstwa, które używają walut obcych, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="b729f-128">If the consolidated legal entity has subsidiaries that use foreign currencies, follow these steps:</span></span>

    1. <span data-ttu-id="b729f-129">Wybierz kolejno opcje **Księga główna \> Ustawienia \> Księgowanie \> Konta dla transakcji automatycznych**.</span><span class="sxs-lookup"><span data-stu-id="b729f-129">Go to **General ledger \> Setup \> Posting \> Accounts for automatic transactions**.</span></span>
    2. <span data-ttu-id="b729f-130">W polu **Typ księgowania** wybierz odpowiednie konto:</span><span class="sxs-lookup"><span data-stu-id="b729f-130">In the **Posting type** field, select an appropriate account:</span></span>

        - <span data-ttu-id="b729f-131">Jeśli podmiot prawny ma zagraniczne spółki zależne, które są współzależne finansowo lub operacyjnie z podmiotem dominującym, wybierz odpowiednie konto dla **Rachunku zysków i strat dla różnic konsolidacyjnych** typu księgowania.</span><span class="sxs-lookup"><span data-stu-id="b729f-131">If the legal entity has foreign subsidiaries that are financially or operationally interdependent with the parent legal entity, select an appropriate account for the **Profit and loss account for consolidation differences** posting type.</span></span>
        - <span data-ttu-id="b729f-132">Jeżeli następuje konsolidowanie oddziału, który jest finansowo i funkcjonalnie niezależny od firmy nadrzędnej lub podmiotu prawnego, z wynikami kilku oddziałów, które są finansowo i funkcjonalnie niezależne od firmy nadrzędnej i jeśli korzysta się z metod przeliczania walut do konsolidowania danych, należy wybrać odpowiednie konto dla **Konto bilansowe na potrzeby różnic konsolidacji** typu księgowania.</span><span class="sxs-lookup"><span data-stu-id="b729f-132">If you're consolidating a subsidiary that is financially and operationally independent of the parent legal entity, or a legal entity that contains the results of several subsidiaries that are financially and operationally independent of the parent legal entity, and if you're using translation methods to consolidate the data, select an appropriate account for the **Balance account for consolidation differences** posting type.</span></span>

    3. <span data-ttu-id="b729f-133">W polu **Główne konto** wybierz konta główne, które będą używane dla korekty przeszacowania w walucie obcej.</span><span class="sxs-lookup"><span data-stu-id="b729f-133">In the **Main account** field, select the main accounts that should be used for foreign currency revaluation adjustments.</span></span>
    4. <span data-ttu-id="b729f-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b729f-134">Close the page.</span></span>

    <span data-ttu-id="b729f-135">Jeśli tworzysz firmę skonsolidowaną na początku okresu, możesz dostosować kwoty walut obcych według zmian kursu wymiany w trakcie okresu konsolidacji.</span><span class="sxs-lookup"><span data-stu-id="b729f-135">If you create the consolidated legal entity early in a period, you can revalue foreign currency amounts as exchange rates change during the consolidation period.</span></span>

<span data-ttu-id="b729f-136">Firma skonsolidowanej jest teraz skonfigurowana jako zadanie okresowe **Konsolidacja**.</span><span class="sxs-lookup"><span data-stu-id="b729f-136">The consolidated legal entity is now set up for the **Consolidate** periodic job.</span></span> <span data-ttu-id="b729f-137">Można wykonać konsolidację importu lub konsolidację online.</span><span class="sxs-lookup"><span data-stu-id="b729f-137">You can do either an import consolidation or an online consolidation.</span></span>

- <span data-ttu-id="b729f-138">Aby przeprowadzić konsolidację importu, przejdź do **Księga główna \> Okresowe \> Konsolidacja \> Konsolidacja \[Importuj z\]**.</span><span class="sxs-lookup"><span data-stu-id="b729f-138">To do an import consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Import from\]**.</span></span>
- <span data-ttu-id="b729f-139">Aby przeprowadzić konsolidację online, przejdź do **Księga główna \> Okresowe \> Konsolidacja \> Konsolidacja \[Online\]**.</span><span class="sxs-lookup"><span data-stu-id="b729f-139">To do an online consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Online\]**.</span></span>

> [!NOTE]
> <span data-ttu-id="b729f-140">Zanim będzie można przeprowadzić konsolidację, należy przygotować do niej oddziały firmy.</span><span class="sxs-lookup"><span data-stu-id="b729f-140">Before you can process the consolidation, you must prepare the subsidiary legal entities for consolidation.</span></span> <span data-ttu-id="b729f-141">Aby zapoznać się z dodatkowymi informacjami, zobacz [Konfigurowanie firmy zależnej do konsolidacji](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="b729f-141">For more information, see [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span>
