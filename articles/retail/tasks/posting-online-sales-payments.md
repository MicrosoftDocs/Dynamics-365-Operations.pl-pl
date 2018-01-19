--- 
title: "Księgowanie sprzedaży i płatności online"
description: "Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 3799515c538826ac2a0b37a26e83f375591f9813
ms.contentlocale: pl-pl
ms.lasthandoff: 01/19/2018

---
# <a name="post-online-sales-and-payments"></a><span data-ttu-id="5d89a-103">Księgowanie sprzedaży i płatności online</span><span class="sxs-lookup"><span data-stu-id="5d89a-103">Post online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5d89a-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego, aby tworzyć zamówienia sprzedaży i płatności dla transakcji w sklepie internetowym.</span><span class="sxs-lookup"><span data-stu-id="5d89a-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="5d89a-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="5d89a-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5d89a-106">Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="5d89a-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="5d89a-107">Kliknij opcję Synchronizuj zamówienia.</span><span class="sxs-lookup"><span data-stu-id="5d89a-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="5d89a-108">W polu Hierarchia organizacyjna wybierz opcję „Sklepy sieci sprzedaży według regionów”.</span><span class="sxs-lookup"><span data-stu-id="5d89a-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="5d89a-109">Wybierz określony sklep internetowy albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="5d89a-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="5d89a-110">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="5d89a-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="5d89a-111">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="5d89a-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="5d89a-112">Zaznacz pole wyboru Przetwarzanie wsadowe lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="5d89a-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="5d89a-113">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="5d89a-113">Click Recurrence.</span></span>
7. <span data-ttu-id="5d89a-114">Wybierz opcję Brak daty zakończenia.</span><span class="sxs-lookup"><span data-stu-id="5d89a-114">Select the No end date option.</span></span>
8. <span data-ttu-id="5d89a-115">W polu Liczba wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="5d89a-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="5d89a-116">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5d89a-116">Click OK.</span></span>
10. <span data-ttu-id="5d89a-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="5d89a-117">Click OK.</span></span>


