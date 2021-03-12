---
title: Liczenie zapasów w magazynie
description: W tym temacie opisano proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a7f85cb91f36004a6bd6da714e7baa460a83a66
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000109"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="a7b34-103">Liczenie zapasów w magazynie</span><span class="sxs-lookup"><span data-stu-id="a7b34-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7b34-104">W tym temacie opisano proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie.</span><span class="sxs-lookup"><span data-stu-id="a7b34-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="a7b34-105">Procedura dotyczy funkcji „podstawowego magazynowania” dostępnej w module Zarządzanie zapasami, a nie funkcji magazynowania dostępnej w module Zarządzanie magazynem.</span><span class="sxs-lookup"><span data-stu-id="a7b34-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="a7b34-106">Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="a7b34-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="a7b34-107">Jeśli korzystasz z własnych danych, upewnij się, że masz skonfigurowane produkty i lokalizacje oraz utworzony arkusz magazynowy dla arkuszy inwentaryzacji.</span><span class="sxs-lookup"><span data-stu-id="a7b34-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="a7b34-108">Inwentaryzacja jest zwykle przeprowadzana przez pracownika magazynu.</span><span class="sxs-lookup"><span data-stu-id="a7b34-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="a7b34-109">Tworzenie arkusza inwentaryzacji zapasów</span><span class="sxs-lookup"><span data-stu-id="a7b34-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="a7b34-110">Przejdź do menu **Okienko nawigacji > Moduły > Zarządzanie zapasami > Wpisy w arkuszu > Zliczanie towarów > Inwentaryzacja**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="a7b34-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-111">Select **New**.</span></span>
3. <span data-ttu-id="a7b34-112">W polu **nazwa** wybierz z listy rozwijanej nazwę arkusza inwentaryzacji zapasów, którego chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="a7b34-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="a7b34-113">Niektóre inne pola zostaną wypełnione zgodnie z ustawieniami wybranego arkusza inwentaryzacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="a7b34-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="a7b34-114">W polu **Pracownik** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a7b34-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a7b34-115">Na liście **zaznacz** pracownika, z którego chcesz skorzystać.</span><span class="sxs-lookup"><span data-stu-id="a7b34-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="a7b34-116">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="a7b34-117">Utwórz wiersze arkusza</span><span class="sxs-lookup"><span data-stu-id="a7b34-117">Create journal lines</span></span>
1. <span data-ttu-id="a7b34-118">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-118">Select **New**.</span></span>
2. <span data-ttu-id="a7b34-119">W polu **Numer produktu** wybierz odpowiedni rekord z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="a7b34-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a7b34-120">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz opcję **A0001**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="a7b34-121">W polu **Oddział** wybierz odpowiedni rekord z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="a7b34-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a7b34-122">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz oddział **2**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="a7b34-123">W polu **Magazyn** wybierz odpowiedni rekord z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="a7b34-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a7b34-124">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz magazyn **24**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="a7b34-125">W polu **Lokalizacja** wybierz odpowiedni rekord z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="a7b34-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a7b34-126">Jeśli używasz danych firmy demonstracyjnej USMF, wybierz lokalizację **BULK-001**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="a7b34-127">W polu Policzono wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="a7b34-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="a7b34-128">Jeśli wprowadzisz zliczoną liczbę inną niż liczba widoczna w polu **Dostępne zapasy**, pole **Ilość** zostanie zaktualizowane w celu pokazania niezgodności.</span><span class="sxs-lookup"><span data-stu-id="a7b34-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="a7b34-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="a7b34-130">Księgowanie arkusza inwentaryzacji zapasów</span><span class="sxs-lookup"><span data-stu-id="a7b34-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="a7b34-131">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-131">Select **Post**.</span></span> <span data-ttu-id="a7b34-132">Jeśli podczas księgowania arkusza inwentaryzacji zapasów zliczona ilość jest inna niż ilość podana w polu **Dostępne zapasy**, nastąpi zaksięgowanie przyjęcia na magazyn lub wydania, zmiana poziomu i wartości zapasów oraz wygenerowanie transakcji finansowych.</span><span class="sxs-lookup"><span data-stu-id="a7b34-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="a7b34-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="a7b34-134">Wyświetlanie transakcji magazynowych</span><span class="sxs-lookup"><span data-stu-id="a7b34-134">View inventory transactions</span></span>
1. <span data-ttu-id="a7b34-135">Wybierz **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="a7b34-136">Wybierz **transakcje**.</span><span class="sxs-lookup"><span data-stu-id="a7b34-136">Select **Transactions**.</span></span> <span data-ttu-id="a7b34-137">Tutaj można zobaczyć wszystkie powiązane transakcje, które zostaną utworzone podczas księgowania arkusza inwentaryzacji zapasów.</span><span class="sxs-lookup"><span data-stu-id="a7b34-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

