---
title: Magazyn raportów wiekowania zapasów
description: W tym temacie opisano funkcje umożliwiające uruchamianie raportu wiekowania zapasów oraz udostępnianie danych wyjściowych w postaci formularza i wykresu.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 40b15448677f319c650c667cd7c4981c343f7a02
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205353"
---
# <a name="inventory-aging-report-storage"></a><span data-ttu-id="9ba9e-103">Magazyn raportów wiekowania zapasów</span><span class="sxs-lookup"><span data-stu-id="9ba9e-103">Inventory aging report storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ba9e-104">W Microsoft Dynamics 365 Supply Chain Management można uruchomić **magazyn raportów wiekowania zapasów** i udostępnić dane wyjściowe jako formularz i wykres.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging report storage** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="9ba9e-105">W formularzu pola kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="9ba9e-106">Wykres zawiera przegląd wizualny obsługujący filtrowanie i umożliwiający drążenie do szczegółów.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="9ba9e-107">Ponadto jednostka danych o nazwie **Raport wiekowania zapasów** umożliwia eksportowanie wyników raportu **magazynu raportów wiekowania zapasów** do formatu takiego jak plik Microsoft Excel lub plik PDF.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging report storage** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="9ba9e-108">Ta metoda uruchamiania raportu **magazynu raportów wiekowania zapasów** jest przydatna w przypadkach, gdy dane wyjściowe zawierają wiele wierszy.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-108">This method of running an **Inventory aging report storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="9ba9e-109">Na przykład produkcja będzie zawierała wiele wierszy, jeśli w systemie istnieje 50 000 sztuk i 300 sklepów utworzonych jako magazyny i żąda się przeliczeń zapasów według towarów, oddziału i magazynu.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="enable-the-inventory-value-storage-report-feature"></a><span data-ttu-id="9ba9e-110">Włączanie funkcji raportu magazynowania wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="9ba9e-110">Enable the Inventory value storage report feature</span></span>

<span data-ttu-id="9ba9e-111">Aby móc używać tej funkcji, musisz ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="9ba9e-112">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="9ba9e-113">W tym miejscu funkcja jest wyświetlana jako:</span><span class="sxs-lookup"><span data-stu-id="9ba9e-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="9ba9e-114">**Moduł** — zarządzanie kosztami</span><span class="sxs-lookup"><span data-stu-id="9ba9e-114">**Module** - Cost management</span></span>
- <span data-ttu-id="9ba9e-115">**Nazwa funkcji** - Magazyn raportów wiekowania zapasów</span><span class="sxs-lookup"><span data-stu-id="9ba9e-115">**Feature name** - Inventory aging report storage</span></span>

## <a name="run-an-inventory-aging-report-storage"></a><span data-ttu-id="9ba9e-116">Uruchom magazyn raportów wiekowania zapasów</span><span class="sxs-lookup"><span data-stu-id="9ba9e-116">Run an Inventory aging report storage</span></span>

1. <span data-ttu-id="9ba9e-117">Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Przechowywanie raportu wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-117">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="9ba9e-118">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-118">Select **New**.</span></span>
1. <span data-ttu-id="9ba9e-119">W polu **Nazwa** wprowadź unikatową nazwę raportu.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-119">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="9ba9e-120">Umożliwia wybór raportu **identyfikacja — ID** i przefiltrowanie go w miarę potrzeb</span><span class="sxs-lookup"><span data-stu-id="9ba9e-120">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="9ba9e-121">Wykonywanie raportu jest zawsze wykonywane w ramach zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-121">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="9ba9e-122">Po zakończeniu zadania wsadowego dane wyjściowe są wyświetlane na stronie **Magazyn raportu wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-122">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="9ba9e-123">Aby wyświetlić dane wyjściowe jako formularz z tradycyjnym układem siatki, wybierz opcję **Pokaż szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-123">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="9ba9e-124">Aby wyświetlić dane wyjściowe jako zagregowany wykres, wybierz opcję **Wyświetl wykres**.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-124">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ba9e-125">Formularz nie będzie zawierać sum częściowych, które są zdefiniowane w układzie raportu.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-125">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="9ba9e-126">Jednostka danych **raportu wiekowania zapasów** umożliwia eksportowanie danych wyjściowych raportu **magazynu raportów wiekowania zapasów** przez zastosowanie filtru dla pola **Identyfikator procesu — nazwa** w dowolnym formacie obsługiwanym przez funkcję zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-126">The **Inventory aging report** data entity lets you export the output of an **Inventory aging report storage** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]