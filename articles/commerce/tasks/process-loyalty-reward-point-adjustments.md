---
title: Przetwarzanie korekt punktów lojalnościowych
description: Ta procedura przedstawia sposób wyszukiwania informacji o karcie lojalnościowej i korygowania punktów lojalnościowych.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40f66e51c08e574049097a6e2602998875a897e9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991344"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="e4929-103">Przetwarzanie korekt punktów lojalnościowych</span><span class="sxs-lookup"><span data-stu-id="e4929-103">Process loyalty reward point adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4929-104">Ta procedura przedstawia sposób wyszukiwania informacji o karcie lojalnościowej i korygowania punktów lojalnościowych.</span><span class="sxs-lookup"><span data-stu-id="e4929-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="e4929-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="e4929-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="e4929-106">Zadanie jest przeznaczone dla roli Kierownik ds. operacyjnych sprzedaży lub Menedżer ds. obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="e4929-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="e4929-107">Przejdź do okna Karty lojalnościowe.</span><span class="sxs-lookup"><span data-stu-id="e4929-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="e4929-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e4929-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e4929-109">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e4929-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e4929-110">Kliknij opcję Transakcje kartą.</span><span class="sxs-lookup"><span data-stu-id="e4929-110">Click Card transactions.</span></span>
    * <span data-ttu-id="e4929-111">Na tej stronie można wyświetlić wszystkie transakcje lojalnościowe dla wybranej karty lojalnościowej.</span><span class="sxs-lookup"><span data-stu-id="e4929-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="e4929-112">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e4929-112">Close the page.</span></span>
6. <span data-ttu-id="e4929-113">Kliknij opcję Korekty karty.</span><span class="sxs-lookup"><span data-stu-id="e4929-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="e4929-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e4929-114">Click New.</span></span>
8. <span data-ttu-id="e4929-115">W polu Punkty lojalnościowe wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e4929-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="e4929-116">W polu Kwota lub ilość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="e4929-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="e4929-117">Można dodać lub usunąć punkty z karty lojalnościowej przy użyciu kwoty dodatniej lub ujemnej.</span><span class="sxs-lookup"><span data-stu-id="e4929-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="e4929-118">W polu Program lojalnościowy wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="e4929-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="e4929-119">W polu Komentarz wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e4929-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="e4929-120">Kliknij przycisk Księguj korektę.</span><span class="sxs-lookup"><span data-stu-id="e4929-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="e4929-121">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="e4929-121">Click Yes.</span></span>
14. <span data-ttu-id="e4929-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e4929-122">Close the page.</span></span>
    * <span data-ttu-id="e4929-123">Normalnie na tym etapie należałoby odświeżyć stronę, aby wyświetlić wynik korekty punktów lojalnościowych na karcie Podsumowanie punktów lojalnościowych. Jednak jeśli wykonujesz procedurę w ramach przewodnika po zadaniach, nie odświeżaj teraz, ponieważ jeśli to zrobisz, przewodnik się zatrzyma.</span><span class="sxs-lookup"><span data-stu-id="e4929-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="e4929-124">Kliknij opcję Transakcje kartą.</span><span class="sxs-lookup"><span data-stu-id="e4929-124">Click Card transactions.</span></span>
16. <span data-ttu-id="e4929-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e4929-125">Close the page.</span></span>

