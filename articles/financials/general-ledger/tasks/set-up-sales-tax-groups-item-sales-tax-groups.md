--- 
title: "Konfigurowanie grup podatków i grup podatków dla towarów"
description: "W tym nagraniu zadania przejdziesz przez proces konfigurowania grup podatków i podatków dla towarów."
author: twheeloc
manager: AnnBe
ms.date: 11/10/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4d7f1093edcfff65fd466fa8138b1bb5203648b3
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="02232-103">Konfigurowanie grup podatków i grup podatków dla towarów</span><span class="sxs-lookup"><span data-stu-id="02232-103">Set up sales tax groups and item sales tax groups</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02232-104">W tym nagraniu zadania przejdziesz przez proces konfigurowania grup podatków i podatków dla towarów.</span><span class="sxs-lookup"><span data-stu-id="02232-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="02232-105">Grupy podatków są grupami kodów podatków dołączonymi do odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="02232-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="02232-106">Są one także dołączane do kont księgowych dla transakcji, które nie zostały zaksięgowane do określonego dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="02232-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="02232-107">Grupy podatków dla towarów są grupami kodów podatków dołączonymi do zasobów takich jak produkty.</span><span class="sxs-lookup"><span data-stu-id="02232-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="02232-108">Podatki mające zastosowanie do konkretnej transakcji są określane na podstawie kodów podatków, które są zawarte zarówno w grupie podatków, jak i grupie podatków dla towaru związanej z transakcją.</span><span class="sxs-lookup"><span data-stu-id="02232-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="02232-109">Podatek można obliczyć tylko wtedy, gdy grupa podatków i grupa podatków dla towaru są wybrane dla każdej transakcji, w przypadku której istnieje konieczność obliczenia lub zarejestrowania podatku.</span><span class="sxs-lookup"><span data-stu-id="02232-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="02232-110">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="02232-110">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="02232-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="02232-111">Click New.</span></span>
3. <span data-ttu-id="02232-112">W polu Grupa podatków wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="02232-112">In the Sales tax group field, type a value.</span></span>
4. <span data-ttu-id="02232-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="02232-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="02232-114">Przełącz rozwinięcie sekcji Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="02232-114">Toggle the expansion of the Setup section.</span></span>
6. <span data-ttu-id="02232-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="02232-115">Click Add.</span></span>
7. <span data-ttu-id="02232-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="02232-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="02232-117">W polu Kod podatku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="02232-117">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="02232-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="02232-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="02232-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="02232-119">Click Save.</span></span>
11. <span data-ttu-id="02232-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="02232-120">Close the page.</span></span>
12. <span data-ttu-id="02232-121">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków dla towaru.</span><span class="sxs-lookup"><span data-stu-id="02232-121">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
13. <span data-ttu-id="02232-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="02232-122">Click New.</span></span>
14. <span data-ttu-id="02232-123">W polu Grupa podatków dla towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="02232-123">In the Item sales tax group field, type a value.</span></span>
15. <span data-ttu-id="02232-124">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="02232-124">In the Description field, type a value.</span></span>
16. <span data-ttu-id="02232-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="02232-125">Click Add.</span></span>
17. <span data-ttu-id="02232-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="02232-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="02232-127">W polu Kod podatku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="02232-127">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="02232-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="02232-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="02232-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="02232-129">Click Save.</span></span>


