---
title: Dodawanie wymiarów finansowych do obszaru roboczego Dyrektor finansowy
description: W tym temacie wyjaśniono, jak dodawać wymiary finansowe do obszaru roboczego Dyrektor finansowy, dzięki czemu będzie można ich używać w raportach ksiąg i budżetów.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 457c547947ce6182d03e7a8276b380bc08535bca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985119"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="f8a03-103">Dodawanie wymiarów finansowych do obszaru roboczego Dyrektor finansowy</span><span class="sxs-lookup"><span data-stu-id="f8a03-103">Add financial dimensions to the CFO workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8a03-104">W tym temacie wyjaśniono, jak dodawać wymiary finansowe do obszaru roboczego Dyrektor finansowy, dzięki czemu będzie można ich używać w raportach ksiąg i budżetów.</span><span class="sxs-lookup"><span data-stu-id="f8a03-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="f8a03-105">Obszar roboczy Dyrektor finansowy zawiera kartę **Przegląd** i kartę **Finanse**. Raporty na tych dwóch kartach dodatkowo wykorzystują dwie miary: LedgerActivityMeasure i BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="f8a03-105">The CFO workspace has an **Overview** tab and a **Financial** tab. The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="f8a03-106">Występuje zbiór między tymi dwoma miarami i jednostką DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="f8a03-106">There is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="f8a03-107">W związku z tym można wybierać wymiary.</span><span class="sxs-lookup"><span data-stu-id="f8a03-107">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="f8a03-108">W aplikacji Finance na stronie **Magazyn jednostek** zaktualizuj miary **LedgerActivityMeasure** i **BudgetActivityMeasure**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-108">In Finance, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="f8a03-109">W programie Microsoft Visual Studio otwórz Eksploratora aplikacji i wyszukaj element **LedgerCFO**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-109">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="f8a03-110">W obszarze **Zasoby** otwórz zasób **LedgerCFOWorkspacePBIX**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-110">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="f8a03-111">Gdy zasób zostanie otwarty na pulpicie Microsoft Power BI, wybierz kolejno opcje **Pobierz dane**, **Baza danych programu SQL Server** i **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-111">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="f8a03-112">Wprowadź nazwę serwera, a jako bazę danych wpisz **AxDW**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-112">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="f8a03-113">Zaznacz element **DirectQuery** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-113">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="f8a03-114">Wyszukaj i zaznacz element **LedgerActivityMeasure\_DimensionCombination**, a następnie wybierz opcję **Załaduj**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-114">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f8a03-115">Na liście **Pola** zmień nazwę tabeli na **Wymiary finansowe**, tak aby łatwiej ją było zidentyfikować.</span><span class="sxs-lookup"><span data-stu-id="f8a03-115">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="f8a03-116">Wybierz kolejno opcje **Zarządzanie relacjami** i **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-116">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="f8a03-117">W pierwszym polu wybierz opcję **Działania na księdze głównej**, a następnie zaznacz element **LedgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-117">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="f8a03-118">W drugim polu zaznacz element **LedgerActivityMeasure\_DimensionCombination** (lub **Wymiary finansowe**, jeśli nazwa tabeli została zmieniona).</span><span class="sxs-lookup"><span data-stu-id="f8a03-118">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="f8a03-119">Zaznacz nagłówek **DimensionCombinationRECID**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-119">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="f8a03-120">W polu **Kardynalność** zaznacz opcję **Wiele do jednego**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-120">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="f8a03-121">W polu **Kierunek filtrowania krzyżowego** zmień wartość na **Pojedyncze**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-121">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="f8a03-122">Zaznacz opcje **Aktywuj tę relację** i **Przyjmij integralność referencyjną**, a następnie kliknij kolejno przyciski **OK** i **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-122">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="f8a03-123">[![Tworzenie relacji](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="f8a03-123">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="f8a03-124">Na liście **Pola** powinna być widoczna tabela oraz dostępne wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="f8a03-124">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="f8a03-125">Przeciągnij żądane wymiary finansowe do filtrów na poziomie raportu.</span><span class="sxs-lookup"><span data-stu-id="f8a03-125">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="f8a03-126">Zapisz zmiany.</span><span class="sxs-lookup"><span data-stu-id="f8a03-126">Save your changes.</span></span>
15. <span data-ttu-id="f8a03-127">W drzewie obiektów aplikacji (AOT) kliknij prawym przyciskiem myszy swój projekt i wybierz polecenie **Synchronizuj**.</span><span class="sxs-lookup"><span data-stu-id="f8a03-127">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="f8a03-128">Skompiluj projekt, a następnie otwórz aplikację, aby wyświetlić rezultat.</span><span class="sxs-lookup"><span data-stu-id="f8a03-128">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="f8a03-129">[![Skonfigurowana przestrzeń robocza](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="f8a03-129">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>
