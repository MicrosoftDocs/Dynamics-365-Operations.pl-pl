---
title: "Wpisywanie kombinacji wymiarów i kont (formant Wpis podzielony na segmenty)"
description: "Ten artykuł zawiera opis sposobów wprowadzania kombinacji kont i wymiarów albo kont księgowych. Narzędzie wprowadzania często jest nazywane formantem wpisów podzielonych na segmenty."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c9addb2897bac68115a38f0239764ab65af2378c
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="16900-104">Wpisywanie kombinacji wymiarów i kont (formant Wpis podzielony na segmenty)</span><span class="sxs-lookup"><span data-stu-id="16900-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16900-105">Ten artykuł zawiera opis sposobów wprowadzania kombinacji kont i wymiarów albo kont księgowych.</span><span class="sxs-lookup"><span data-stu-id="16900-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="16900-106">Narzędzie wprowadzania często jest nazywane formantem wpisów podzielonych na segmenty.</span><span class="sxs-lookup"><span data-stu-id="16900-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="16900-107">Użytkownicy wpisują kombinacje wymiarów i kont na różnych stronach, np. na stronach arkuszy głównych, budżetowania i definicji księgowania.</span><span class="sxs-lookup"><span data-stu-id="16900-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="16900-108">Prawidłowa kombinacja wymiarów i kont zależy od struktury konta przypisanego do księgi oraz zaawansowanych reguł przypisanych do struktury konta.</span><span class="sxs-lookup"><span data-stu-id="16900-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="16900-109">Gdy użytkownicy wpisują kombinację, mogą ręcznie wprowadzać wartości lub skorzystać z zaawansowanej funkcji wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="16900-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="16900-110">Podczas wypełniania pola można zacząć pisanie, a system poszuka wartości i opisu.</span><span class="sxs-lookup"><span data-stu-id="16900-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="16900-111">Na przykład jeśli wpiszesz 180, system poszuka każdej wartość rozpoczynającej się od tej kombinacji cyfr.</span><span class="sxs-lookup"><span data-stu-id="16900-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="16900-112">Lub możesz wpisać Gotówka, a system poszuka każdej wartości, w której opis zaczyna się słowem Gotówka.</span><span class="sxs-lookup"><span data-stu-id="16900-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="16900-113">Można również użyć symbolu wieloznacznego, takiego jak \*Gotówka lub \*180 , aby szukać wartości lub opisu zawierającego kryterium wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="16900-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="16900-114">W poniższej tabeli opisano skróty klawiaturowe, które mogą być używane po zamknięciu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="16900-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16900-115">Skrót klawiatury</span><span class="sxs-lookup"><span data-stu-id="16900-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="16900-116">Akcja</span><span class="sxs-lookup"><span data-stu-id="16900-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="16900-117">Alt+strzałka w dół</span><span class="sxs-lookup"><span data-stu-id="16900-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="16900-118">Otwórz wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="16900-118">Open the lookup.</span></span> <span data-ttu-id="16900-119">Ponowne naciśnięcie kombinacji klawiszy Alt + strzałka w dół powoduje przeniesienie wyróżnienia do segmentów w menu wysuwanym.</span><span class="sxs-lookup"><span data-stu-id="16900-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="16900-120">Enter i Shift+Enter</span><span class="sxs-lookup"><span data-stu-id="16900-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="16900-121">Separator planu kont</span><span class="sxs-lookup"><span data-stu-id="16900-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="16900-122">Strzałka w prawo i strzałka w lewo</span><span class="sxs-lookup"><span data-stu-id="16900-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="16900-123">Przejdź do następnego lub poprzedniego segmentu.</span><span class="sxs-lookup"><span data-stu-id="16900-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="16900-124">Tabulator</span><span class="sxs-lookup"><span data-stu-id="16900-124">Tab</span></span></td>
<td><span data-ttu-id="16900-125">Przejdź do następnego pola na siatce.</span><span class="sxs-lookup"><span data-stu-id="16900-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16900-126">W poniższej tabeli opisano skróty klawiaturowe, które mogą być używane po otwarciu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="16900-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16900-127">Skrót klawiatury</span><span class="sxs-lookup"><span data-stu-id="16900-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="16900-128">Akcja</span><span class="sxs-lookup"><span data-stu-id="16900-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="16900-129">Esc</span><span class="sxs-lookup"><span data-stu-id="16900-129">Esc</span></span></td>
<td><span data-ttu-id="16900-130">Zamknij wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="16900-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="16900-131">Strzałka w górę i strzałka w dół</span><span class="sxs-lookup"><span data-stu-id="16900-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="16900-132">Page Up i Page Down</span><span class="sxs-lookup"><span data-stu-id="16900-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="16900-133">Home i End</span><span class="sxs-lookup"><span data-stu-id="16900-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="16900-134">Przejdź do poprzedniej lub następnej wartości na listach, poprzedniej lub następnej grupy wartości lub pierwszego albo ostatniego elementu w wyszukiwaniu.</span><span class="sxs-lookup"><span data-stu-id="16900-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="16900-135">Separator planu kont</span><span class="sxs-lookup"><span data-stu-id="16900-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="16900-136">Strzałka w prawo i strzałka w lewo</span><span class="sxs-lookup"><span data-stu-id="16900-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="16900-137">Przejdź do następnego lub poprzedniego segmentu.</span><span class="sxs-lookup"><span data-stu-id="16900-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="16900-138">Karta</span><span class="sxs-lookup"><span data-stu-id="16900-138">Tab</span></span></td>
<td><span data-ttu-id="16900-139">Przejdź do następnego pola na siatce.</span><span class="sxs-lookup"><span data-stu-id="16900-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="16900-140">Alt+W</span><span class="sxs-lookup"><span data-stu-id="16900-140">Alt+W</span></span></td>
<td><span data-ttu-id="16900-141">Przełączanie między trybami <strong>Pokaż wszystkie</strong> i <strong>Pokaż prawidłowe</strong>.</span><span class="sxs-lookup"><span data-stu-id="16900-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>






