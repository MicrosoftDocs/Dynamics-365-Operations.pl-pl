---
title: Konfigurowanie grup podatków i grup podatków dla towarów
description: W tym nagraniu zadania przejdziesz przez proces konfigurowania grup podatków i podatków dla towarów.
author: twheeloc
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e97766be1207fb66b38f25b1e423fb21cec9e726
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222174"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="e2e45-103">Konfigurowanie grup podatków i grup podatków dla towarów</span><span class="sxs-lookup"><span data-stu-id="e2e45-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2e45-104">W tym nagraniu zadania przejdziesz przez proces konfigurowania grup podatków i podatków dla towarów.</span><span class="sxs-lookup"><span data-stu-id="e2e45-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="e2e45-105">Grupy podatków są grupami kodów podatków dołączonymi do odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="e2e45-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="e2e45-106">Są one także dołączane do kont księgowych dla transakcji, które nie zostały zaksięgowane do określonego dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e2e45-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="e2e45-107">Grupy podatków dla towarów są grupami kodów podatków dołączonymi do zasobów takich jak produkty.</span><span class="sxs-lookup"><span data-stu-id="e2e45-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="e2e45-108">Podatki mające zastosowanie do konkretnej transakcji są określane na podstawie kodów podatków, które są zawarte zarówno w grupie podatków, jak i grupie podatków dla towaru związanej z transakcją.</span><span class="sxs-lookup"><span data-stu-id="e2e45-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="e2e45-109">Podatek można obliczyć tylko wtedy, gdy grupa podatków i grupa podatków dla towaru są wybrane dla każdej transakcji, w przypadku której istnieje konieczność obliczenia lub zarejestrowania podatku.</span><span class="sxs-lookup"><span data-stu-id="e2e45-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="e2e45-110">Otwórz **Okienko nawigacji > Podatek > Podatki pośrednie > Podatek > Grupy podatków**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="e2e45-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-111">Click **New**.</span></span>
3. <span data-ttu-id="e2e45-112">W polu **Grupa podatków** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2e45-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="e2e45-113">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2e45-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="e2e45-114">Przełącz rozwinięcie sekcji **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="e2e45-115">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-115">Click **Add**.</span></span>
7. <span data-ttu-id="e2e45-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e2e45-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="e2e45-117">W polu **Kod podatku** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e2e45-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="e2e45-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e2e45-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="e2e45-119">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-119">Click **Save**.</span></span>
11. <span data-ttu-id="e2e45-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e2e45-120">Close the page.</span></span>
12. <span data-ttu-id="e2e45-121">Wybierz kolejno opcje **Podatek > Podatki pośrednie > Podatek > Grupy podatków dla towaru**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="e2e45-122">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-122">Click **New**.</span></span>
14. <span data-ttu-id="e2e45-123">W polu **Grupa podatków dla towaru** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2e45-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="e2e45-124">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e2e45-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="e2e45-125">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-125">Click **Add**.</span></span>
17. <span data-ttu-id="e2e45-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e2e45-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="e2e45-127">W polu **Kod podatku** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="e2e45-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="e2e45-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e2e45-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="e2e45-129">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e2e45-129">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]