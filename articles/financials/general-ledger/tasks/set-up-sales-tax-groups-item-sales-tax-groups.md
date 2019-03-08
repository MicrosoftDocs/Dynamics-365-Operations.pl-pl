---
title: Konfigurowanie grup podatków i grup podatków dla towarów
description: W tym nagraniu zadania przejdziesz przez proces konfigurowania grup podatków i podatków dla towarów.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec5bbe37aa06f18172c417e903538cadc8a6f312
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "320059"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="1553c-103">Konfigurowanie grup podatków i grup podatków dla towarów</span><span class="sxs-lookup"><span data-stu-id="1553c-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1553c-104">W tym nagraniu zadania przejdziesz przez proces konfigurowania grup podatków i podatków dla towarów.</span><span class="sxs-lookup"><span data-stu-id="1553c-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="1553c-105">Grupy podatków są grupami kodów podatków dołączonymi do odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="1553c-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="1553c-106">Są one także dołączane do kont księgowych dla transakcji, które nie zostały zaksięgowane do określonego dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1553c-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="1553c-107">Grupy podatków dla towarów są grupami kodów podatków dołączonymi do zasobów takich jak produkty.</span><span class="sxs-lookup"><span data-stu-id="1553c-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="1553c-108">Podatki mające zastosowanie do konkretnej transakcji są określane na podstawie kodów podatków, które są zawarte zarówno w grupie podatków, jak i grupie podatków dla towaru związanej z transakcją.</span><span class="sxs-lookup"><span data-stu-id="1553c-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="1553c-109">Podatek można obliczyć tylko wtedy, gdy grupa podatków i grupa podatków dla towaru są wybrane dla każdej transakcji, w przypadku której istnieje konieczność obliczenia lub zarejestrowania podatku.</span><span class="sxs-lookup"><span data-stu-id="1553c-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="1553c-110">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków.</span><span class="sxs-lookup"><span data-stu-id="1553c-110">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="1553c-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1553c-111">Click New.</span></span>
3. <span data-ttu-id="1553c-112">W polu Grupa podatków wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1553c-112">In the Sales tax group field, type a value.</span></span>
4. <span data-ttu-id="1553c-113">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1553c-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1553c-114">Przełącz rozwinięcie sekcji Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="1553c-114">Toggle the expansion of the Setup section.</span></span>
6. <span data-ttu-id="1553c-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1553c-115">Click Add.</span></span>
7. <span data-ttu-id="1553c-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="1553c-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="1553c-117">W polu Kod podatku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1553c-117">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="1553c-118">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1553c-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1553c-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1553c-119">Click Save.</span></span>
11. <span data-ttu-id="1553c-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1553c-120">Close the page.</span></span>
12. <span data-ttu-id="1553c-121">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Grupy podatków dla towaru.</span><span class="sxs-lookup"><span data-stu-id="1553c-121">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
13. <span data-ttu-id="1553c-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1553c-122">Click New.</span></span>
14. <span data-ttu-id="1553c-123">W polu Grupa podatków dla towaru wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1553c-123">In the Item sales tax group field, type a value.</span></span>
15. <span data-ttu-id="1553c-124">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1553c-124">In the Description field, type a value.</span></span>
16. <span data-ttu-id="1553c-125">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1553c-125">Click Add.</span></span>
17. <span data-ttu-id="1553c-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="1553c-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="1553c-127">W polu Kod podatku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="1553c-127">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="1553c-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1553c-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="1553c-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1553c-129">Click Save.</span></span>

