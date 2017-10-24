---
title: "Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu"
description: "W tym artykule opisano sposób wykluczania wartości odstających z historycznych danych, które są używane do obliczania prognozy popytu. Poprzez wykluczenie wartości odstających, można zwiększyć dokładność prognozy."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ea3f08b20e25af6ebb738c2373b65532d74a0c80
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="60a59-104">Usuwanie wartości odstających z danych transakcji historycznych podczas obliczania prognozy popytu</span><span class="sxs-lookup"><span data-stu-id="60a59-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="60a59-105">W tym artykule opisano sposób wykluczania wartości odstających z historycznych danych, które są używane do obliczania prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="60a59-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="60a59-106">Poprzez wykluczenie wartości odstających, można zwiększyć dokładność prognozy.</span><span class="sxs-lookup"><span data-stu-id="60a59-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="60a59-107">Można wykluczyć wartości odstające, aby zwiększyć dokładność prognozy.</span><span class="sxs-lookup"><span data-stu-id="60a59-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="60a59-108">To zadanie jest opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="60a59-108">This is an optional task.</span></span> <span data-ttu-id="60a59-109">Poniżej znajduje się omówienie procesu:</span><span class="sxs-lookup"><span data-stu-id="60a59-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="60a59-110">Kliknij kolejno opcje **Planowanie główne** &gt; **Ustawienia** &gt; **Prognozowanie popytu** &gt; **Usuwanie wartości odstających**, aby otworzyć stronę **Usuwanie wartości odstających**, na której przy użyciu zapytania można wybrać transakcje do wykluczenia.</span><span class="sxs-lookup"><span data-stu-id="60a59-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="60a59-111">Wybierz firmę, do której odnosi się kwerenda, a następnie wprowadź nazwę i opis.</span><span class="sxs-lookup"><span data-stu-id="60a59-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="60a59-112">W polu **Data kwerendy** zostanie automatycznie ustawiona bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="60a59-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="60a59-113">Wybierz pole wyboru **Aktywna**, aby wykluczyć transakcje znalezione w wyniku kwerendy z danych historycznych.</span><span class="sxs-lookup"><span data-stu-id="60a59-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="60a59-114">To ustawienie zostanie wprowadzone dopiero po utworzeniu prognozy podstawowej.</span><span class="sxs-lookup"><span data-stu-id="60a59-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="60a59-115">Na stronie **Kwerenda usuwania wartości odstających** istnieje możliwość dodawania, usuwania i wybierania kryteriów określających, które transakcje zostaną wykluczone podczas obliczania bazowej prognozy.</span><span class="sxs-lookup"><span data-stu-id="60a59-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="60a59-116">Na przykład wybierz dany towar lub transakcję zamówienia, które chcesz wykluczyć.</span><span class="sxs-lookup"><span data-stu-id="60a59-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="60a59-117">Kliknij opcję **Wyświetl transakcje**.</span><span class="sxs-lookup"><span data-stu-id="60a59-117">Click **Display transactions**.</span></span> <span data-ttu-id="60a59-118">Na stronie **Transakcje wartości odstających** wyświetlane są transakcje, które spełniają kryteria określone w kwerendzie i które mają być wykluczone z historycznych danych podczas obliczania prognozy popytu.</span><span class="sxs-lookup"><span data-stu-id="60a59-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="60a59-119">**Uwaga:** można także tworzyć kwerendy na podstawie istniejącej kwerendy.</span><span class="sxs-lookup"><span data-stu-id="60a59-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="60a59-120">Wybierz kwerendę do skopiowania i kliknij przycisk **Duplikuj**.</span><span class="sxs-lookup"><span data-stu-id="60a59-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="60a59-121">Pole **Data kwerendy** identyfikuje wersję.</span><span class="sxs-lookup"><span data-stu-id="60a59-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="60a59-122">Można użyć kwerendy w istniejącej formie lub kliknąć opcję **Edytuj kwerendę** w celu zmodyfikowania kryteriów.</span><span class="sxs-lookup"><span data-stu-id="60a59-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="60a59-123">Opcjonalnie można zmodyfikować nazwę i opis nowej kwerendy.</span><span class="sxs-lookup"><span data-stu-id="60a59-123">You can optionally modify the name and description of the new query.</span></span>

<a name="see-also"></a><span data-ttu-id="60a59-124">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="60a59-124">See also</span></span>
--------

[<span data-ttu-id="60a59-125">Wprowadzenie do prognozowania popytu</span><span class="sxs-lookup"><span data-stu-id="60a59-125">Introduction to demand forecasting</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="60a59-126">Monitorowanie dokładności prognozy</span><span class="sxs-lookup"><span data-stu-id="60a59-126">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




