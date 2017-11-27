---
title: "Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach"
description: "Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264254
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a9e63af61b42ef3f5ef1d05a659cbec572e04a4f
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a><span data-ttu-id="704d4-103">Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach</span><span class="sxs-lookup"><span data-stu-id="704d4-103">Update how amounts are displayed on reports and documents</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="704d4-104">Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji.</span><span class="sxs-lookup"><span data-stu-id="704d4-104">This topic provides information about how to update how amounts are displayed on reports and other documents for Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia.</span></span>

<span data-ttu-id="704d4-105">Dla firm w Estonii, na Łotwie, Litwie, w Polsce, Czechach, na Węgrzech i w Rosji można skonfigurować pełne nazwy i krótkie nazwy jednostek i podjednostek waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-105">For legal entities in Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia, you can set up full names and short names for currency units and subunits.</span></span> <span data-ttu-id="704d4-106">Tych nazw można używać do zmiany sposobu reprezentowania kwot w dokumentach i raportach.</span><span class="sxs-lookup"><span data-stu-id="704d4-106">These names can be used to transform how amounts are represented on documents and reports.</span></span> <span data-ttu-id="704d4-107">Na przykład kwota **100,20 PLN** może być wyświetlana jako **100 złotych 20 groszy**.</span><span class="sxs-lookup"><span data-stu-id="704d4-107">For example: The amount **LTL 100.20** can be displayed as **100 Litas 20 Centas**.</span></span>

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a><span data-ttu-id="704d4-108">Konfigurowanie długich i krótkich nazw jednostek i podjednostek walut</span><span class="sxs-lookup"><span data-stu-id="704d4-108">Set up full and short names for currency units and subunits</span></span>
<span data-ttu-id="704d4-109">Aby skonfigurować długie i krótkie nazwy jednostek i podjednostek walut dla języka, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="704d4-109">To set up full and short names for currency units and subunits for a language, complete the following steps:</span></span>

1.  <span data-ttu-id="704d4-110">Otwórz stronę **Waluty**.</span><span class="sxs-lookup"><span data-stu-id="704d4-110">Open the **Currencies** page.</span></span>
2.  <span data-ttu-id="704d4-111">Służy do wybrania waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-111">Select a currency.</span></span>
3.  <span data-ttu-id="704d4-112">W okienku akcji kliknij pozycję **Odchylenie**.</span><span class="sxs-lookup"><span data-stu-id="704d4-112">On the Action Pane, click **Declension**.</span></span>
4.  <span data-ttu-id="704d4-113">Aby dodać pełną nazwę i krótką nazwę dla języka, kliknij przycisk **Nowy** i wypełnij poniższe pola.</span><span class="sxs-lookup"><span data-stu-id="704d4-113">To add full name and short name for a language, click **New** and complete the following fields.</span></span>
    |                                                           |                                                                                                                                                                                                                    |
    |-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="704d4-114">**Pole**</span><span class="sxs-lookup"><span data-stu-id="704d4-114">**Field**</span></span>                                                 | <span data-ttu-id="704d4-115">**Opis**</span><span class="sxs-lookup"><span data-stu-id="704d4-115">**Description**</span></span>                                                                                                                                                                                                    |
    | <span data-ttu-id="704d4-116">**Język**</span><span class="sxs-lookup"><span data-stu-id="704d4-116">**Language**</span></span>                                              | <span data-ttu-id="704d4-117">Wybierz język dla bieżącego tekstu.</span><span class="sxs-lookup"><span data-stu-id="704d4-117">Select the language for the current text.</span></span>                                                                                                                                                                          |
    | <span data-ttu-id="704d4-118">**Mianownik l. poj. (grupa pól Nazwa jednostek)**</span><span class="sxs-lookup"><span data-stu-id="704d4-118">**Singular nominative (Name of units field group)**</span></span>       | <span data-ttu-id="704d4-119">Wprowadź formę liczby pojedynczej dla waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-119">Enter the singular form of the currency.</span></span> <span data-ttu-id="704d4-120">Na przykład forma pojedyncza złotówki to „złoty”.</span><span class="sxs-lookup"><span data-stu-id="704d4-120">For example, the singular form of Litas is Litas.</span></span>                                                                                                                         |
    | <span data-ttu-id="704d4-121">**Mianownik l. mn. (grupa pól Nazwa jednostek)**</span><span class="sxs-lookup"><span data-stu-id="704d4-121">**Plural nominative (Name of units field group)**</span></span>         | <span data-ttu-id="704d4-122">Wprowadź formę liczby mnogiej dla waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-122">Enter the plural form of the currency.</span></span> <span data-ttu-id="704d4-123">Na przykład wpisz „złotych”.</span><span class="sxs-lookup"><span data-stu-id="704d4-123">For example, enter Litai.</span></span> <span data-ttu-id="704d4-124">**Uwaga:**: Pola **Dopełniacz liczby pojedynczej** i **Dopełniacz l. mn.** są dostępne zależnie od języka wybranego w polu **Język**.</span><span class="sxs-lookup"><span data-stu-id="704d4-124">**Note**: The **Singular genitive** and **Plural genitive** fields are available based on the language that you select in the **Language** field.</span></span> |
    | <span data-ttu-id="704d4-125">**Mianownik l. poj. (grupa pól Nazwa części)**</span><span class="sxs-lookup"><span data-stu-id="704d4-125">**Singular nominative field (Name of parts field group)**</span></span> | <span data-ttu-id="704d4-126">Wprowadź formę liczby pojedynczej dla podjednostki waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-126">Enter the singular form of the subunit of the currency.</span></span>                                                                                                                                                            |
    | <span data-ttu-id="704d4-127">**Mianownik l. mn. (grupa pól Nazwa części)**</span><span class="sxs-lookup"><span data-stu-id="704d4-127">**Plural nominative (Name of parts field group)**</span></span>         | <span data-ttu-id="704d4-128">Wprowadź formę liczby mnogiej dla podjednostki waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-128">Enter the plural form of the subunit of the currency.</span></span>                                                                                                                                                              |
    | <span data-ttu-id="704d4-129">**Nazwa skrótowa jednostek (grupa pól Krótka nazwa)**</span><span class="sxs-lookup"><span data-stu-id="704d4-129">**Shortcut name of units (Short name field group)**</span></span>       | <span data-ttu-id="704d4-130">Wprowadź kod ISO identyfikujący walutę.</span><span class="sxs-lookup"><span data-stu-id="704d4-130">Enter the ISO code to identify the currency.</span></span> <span data-ttu-id="704d4-131">Na przykład wpisz LTL w celu identyfikowania litów.</span><span class="sxs-lookup"><span data-stu-id="704d4-131">For example, enter LTL to identify Litas.</span></span>                                                                                                                             |
    | <span data-ttu-id="704d4-132">**Nazwa skrótowa części (grupa pól Krótka nazwa)**</span><span class="sxs-lookup"><span data-stu-id="704d4-132">**Shortcut name for parts (Short name field group)**</span></span>      | <span data-ttu-id="704d4-133">Wprowadź nazwę podjednostki waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-133">Enter the denomination of the currency subunit.</span></span> <span data-ttu-id="704d4-134">Na przykład wpisz „groszy”.</span><span class="sxs-lookup"><span data-stu-id="704d4-134">For example, enter Centas.</span></span>                                                                                                                                         |
    | <span data-ttu-id="704d4-135">**Spójnik „i” między jednostkami i częściami**</span><span class="sxs-lookup"><span data-stu-id="704d4-135">**Conjunction 'and' between units and parts**</span></span>             | <span data-ttu-id="704d4-136">Zaznacz tę opcję, aby drukować spójnik„i” między jednostkami i częściami waluty.</span><span class="sxs-lookup"><span data-stu-id="704d4-136">Select to print the conjunction “and” between the currency units and unit parts.</span></span> <span data-ttu-id="704d4-137">Na przykład w fakturach i raportach kwota 100,20 PLN będzie wyświetlana jako „100 złotych i 20 groszy”.</span><span class="sxs-lookup"><span data-stu-id="704d4-137">For example, on invoices or reports, the amount for LTL 100.20 will be displayed as 100 Litas and 20 Centas.</span></span>                      |

5.  <span data-ttu-id="704d4-138">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="704d4-138">Click **Save**.</span></span>





