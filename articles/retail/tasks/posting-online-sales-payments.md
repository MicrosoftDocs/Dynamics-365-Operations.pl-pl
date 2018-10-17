--- 
title: "Księgowanie sprzedaży i płatności online"
description: "Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym."
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="54604-103">Księgowanie sprzedaży i płatności online</span><span class="sxs-lookup"><span data-stu-id="54604-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="54604-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym.</span><span class="sxs-lookup"><span data-stu-id="54604-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="54604-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="54604-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="54604-106">Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="54604-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="54604-107">Kliknij opcję Synchronizuj zamówienia.</span><span class="sxs-lookup"><span data-stu-id="54604-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="54604-108">W polu Hierarchia organizacyjna wybierz opcję „Sklepy sieci sprzedaży według regionów”.</span><span class="sxs-lookup"><span data-stu-id="54604-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="54604-109">Wybierz określony sklep internetowy albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="54604-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="54604-110">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="54604-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="54604-111">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="54604-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="54604-112">Zaznacz pole wyboru Przetwarzanie wsadowe lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="54604-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="54604-113">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="54604-113">Click Recurrence.</span></span>
7. <span data-ttu-id="54604-114">Wybierz opcję Brak daty zakończenia.</span><span class="sxs-lookup"><span data-stu-id="54604-114">Select the No end date option.</span></span>
8. <span data-ttu-id="54604-115">W polu Liczba wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="54604-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="54604-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="54604-116">Click OK.</span></span>
10. <span data-ttu-id="54604-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="54604-117">Click OK.</span></span>


