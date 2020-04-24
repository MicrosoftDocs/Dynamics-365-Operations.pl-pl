---
title: Raport wiekowania zapasów
description: W tym temacie opisano funkcje umożliwiające uruchamianie raportu wiekowania zapasów oraz udostępnianie danych wyjściowych w postaci formularza i wykresu.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 790c8fe3a52bce652227f1cef97eff6496476100
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201630"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="58cc0-103">Raport wiekowania zapasów</span><span class="sxs-lookup"><span data-stu-id="58cc0-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="58cc0-104">W rozwiązaniu Microsoft Dynamics 365 Supply Chain Management można uruchomić raport **wiekowania zapasów** i udostępnić dane wyjściowe jako formularz i wykres.</span><span class="sxs-lookup"><span data-stu-id="58cc0-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="58cc0-105">W formularzu pola kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu.</span><span class="sxs-lookup"><span data-stu-id="58cc0-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="58cc0-106">Wykres zawiera przegląd wizualny obsługujący filtrowanie i umożliwiający drążenie do szczegółów.</span><span class="sxs-lookup"><span data-stu-id="58cc0-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="58cc0-107">Ponadto jednostka danych o nazwie **Raport wiekowania zapasów** umożliwia eksportowanie wyników raportu **wiekowania zapasów** do formatu takiego jak plik Microsoft Excel lub plik PDF.</span><span class="sxs-lookup"><span data-stu-id="58cc0-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="58cc0-108">Ta metoda uruchamiania raportu **wiekowania zapasów** jest przydatna w przypadkach, gdy dane wyjściowe zawierają wiele wierszy.</span><span class="sxs-lookup"><span data-stu-id="58cc0-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="58cc0-109">Na przykład produkcja będzie zawierała wiele wierszy, jeśli w systemie istnieje 50 000 sztuk i 300 sklepów utworzonych jako magazyny i żąda się przeliczeń zapasów według towarów, oddziału i magazynu.</span><span class="sxs-lookup"><span data-stu-id="58cc0-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="58cc0-110">Przeprowadź raport wiekowania zapasów</span><span class="sxs-lookup"><span data-stu-id="58cc0-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="58cc0-111">Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Przechowywanie raportu wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="58cc0-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="58cc0-112">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="58cc0-112">Select **New**.</span></span>
1. <span data-ttu-id="58cc0-113">W polu **Nazwa** wprowadź unikatową nazwę raportu.</span><span class="sxs-lookup"><span data-stu-id="58cc0-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="58cc0-114">Umożliwia wybór raportu **identyfikacja — ID** i przefiltrowanie go w miarę potrzeb</span><span class="sxs-lookup"><span data-stu-id="58cc0-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="58cc0-115">Wykonywanie raportu jest zawsze wykonywane w ramach zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="58cc0-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="58cc0-116">Po zakończeniu zadania wsadowego dane wyjściowe są wyświetlane na stronie **Magazyn raportu wiekowania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="58cc0-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="58cc0-117">Aby wyświetlić dane wyjściowe jako formularz z tradycyjnym układem siatki, wybierz opcję **Pokaż szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="58cc0-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="58cc0-118">Aby wyświetlić dane wyjściowe jako zagregowany wykres, wybierz opcję **Wyświetl wykres**.</span><span class="sxs-lookup"><span data-stu-id="58cc0-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="58cc0-119">Formularz nie będzie zawierać sum częściowych, które są zdefiniowane w układzie raportu.</span><span class="sxs-lookup"><span data-stu-id="58cc0-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="58cc0-120">Jednostka danych **raportu wiekowania zapasów** umożliwia eksportowanie danych wyjściowych **raportu wiekowania zapasów** przez zastosowanie filtru dla pola **Identyfikator procesu — nazwa** w dowolnym formacie obsługiwanym przez funkcję zarządzania danymi.</span><span class="sxs-lookup"><span data-stu-id="58cc0-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
