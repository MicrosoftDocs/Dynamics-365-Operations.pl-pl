---
title: Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach
description: Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Currency
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264254
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 61d3ebe7204a248b6d4287215fc9ad42e9d08b76
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565347"
---
# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a><span data-ttu-id="81787-103">Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach</span><span class="sxs-lookup"><span data-stu-id="81787-103">Update how amounts are displayed on reports and documents</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81787-104">Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji.</span><span class="sxs-lookup"><span data-stu-id="81787-104">This topic provides information about how to update how amounts are displayed on reports and other documents for Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia.</span></span>

<span data-ttu-id="81787-105">Dla firm w Estonii, na Łotwie, Litwie, w Polsce, Czechach, na Węgrzech i w Rosji można skonfigurować pełne nazwy i krótkie nazwy jednostek i podjednostek waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-105">For legal entities in Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia, you can set up full names and short names for currency units and subunits.</span></span> <span data-ttu-id="81787-106">Tych nazw można używać do zmiany sposobu reprezentowania kwot w dokumentach i raportach.</span><span class="sxs-lookup"><span data-stu-id="81787-106">These names can be used to transform how amounts are represented on documents and reports.</span></span> <span data-ttu-id="81787-107">Na przykład kwota **100,20 PLN** może być wyświetlana jako **100 złotych 20 groszy**.</span><span class="sxs-lookup"><span data-stu-id="81787-107">For example: The amount **LTL 100.20** can be displayed as **100 Litas 20 Centas**.</span></span>

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a><span data-ttu-id="81787-108">Konfigurowanie długich i krótkich nazw jednostek i podjednostek walut</span><span class="sxs-lookup"><span data-stu-id="81787-108">Set up full and short names for currency units and subunits</span></span>
<span data-ttu-id="81787-109">Aby skonfigurować długie i krótkie nazwy jednostek i podjednostek walut dla języka, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="81787-109">To set up full and short names for currency units and subunits for a language, complete the following steps:</span></span>

1. <span data-ttu-id="81787-110">Otwórz stronę **Waluty**.</span><span class="sxs-lookup"><span data-stu-id="81787-110">Open the **Currencies** page.</span></span>
2. <span data-ttu-id="81787-111">Służy do wybrania waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-111">Select a currency.</span></span>
3. <span data-ttu-id="81787-112">W okienku akcji kliknij pozycję **Odchylenie**.</span><span class="sxs-lookup"><span data-stu-id="81787-112">On the Action Pane, click **Declension**.</span></span>
4. <span data-ttu-id="81787-113">Aby dodać pełną nazwę i krótką nazwę dla języka, kliknij przycisk **Nowy** i wypełnij poniższe pola.</span><span class="sxs-lookup"><span data-stu-id="81787-113">To add full name and short name for a language, click **New** and complete the following fields.</span></span>

   |                                                                        |                                                                                                                                                                                                                                                                        |
   |------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                         <span data-ttu-id="81787-114"><strong>Pole</strong></span><span class="sxs-lookup"><span data-stu-id="81787-114"><strong>Field</strong></span></span>                         |                                                                                                                      <span data-ttu-id="81787-115"><strong>Opis</strong></span><span class="sxs-lookup"><span data-stu-id="81787-115"><strong>Description</strong></span></span>                                                                                                                      |
   |                       <span data-ttu-id="81787-116"><strong>Język</strong></span><span class="sxs-lookup"><span data-stu-id="81787-116"><strong>Language</strong></span></span>                        |                                                                                                               <span data-ttu-id="81787-117">Wybierz język dla bieżącego tekstu.</span><span class="sxs-lookup"><span data-stu-id="81787-117">Select the language for the current text.</span></span>                                                                                                                |
   |    <span data-ttu-id="81787-118"><strong>Mianownik l. poj. (grupa pól Nazwa jednostek)</strong></span><span class="sxs-lookup"><span data-stu-id="81787-118"><strong>Singular nominative (Name of units field group)</strong></span></span>    |                                                                                       <span data-ttu-id="81787-119">Wprowadź formę liczby pojedynczej dla waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-119">Enter the singular form of the currency.</span></span> <span data-ttu-id="81787-120">Na przykład forma pojedyncza złotówki to „złoty”.</span><span class="sxs-lookup"><span data-stu-id="81787-120">For example, the singular form of Litas is Litas.</span></span>                                                                                       |
   |     <span data-ttu-id="81787-121"><strong>Mianownik l. mn. (grupa pól Nazwa jednostek)</strong></span><span class="sxs-lookup"><span data-stu-id="81787-121"><strong>Plural nominative (Name of units field group)</strong></span></span>     | <span data-ttu-id="81787-122">Wprowadź formę liczby mnogiej dla waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-122">Enter the plural form of the currency.</span></span> <span data-ttu-id="81787-123">Na przykład wpisz „złotych”.</span><span class="sxs-lookup"><span data-stu-id="81787-123">For example, enter Litai.</span></span> <span data-ttu-id="81787-124"><strong>Uwaga:</strong>: Pola <strong>Dopełniacz liczby pojedynczej</strong> i <strong>Dopełniacz l. mn.</strong> są dostępne zależnie od języka wybranego w polu <strong>Język</strong>.</span><span class="sxs-lookup"><span data-stu-id="81787-124"><strong>Note</strong>: The <strong>Singular genitive</strong> and <strong>Plural genitive</strong> fields are available based on the language that you select in the <strong>Language</strong> field.</span></span> |
   | <span data-ttu-id="81787-125"><strong>Mianownik l. poj. (grupa pól Nazwa części)</strong></span><span class="sxs-lookup"><span data-stu-id="81787-125"><strong>Singular nominative field (Name of parts field group)</strong></span></span> |                                                                                                        <span data-ttu-id="81787-126">Wprowadź formę liczby pojedynczej dla podjednostki waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-126">Enter the singular form of the subunit of the currency.</span></span>                                                                                                         |
   |     <span data-ttu-id="81787-127"><strong>Mianownik l. mn. (grupa pól Nazwa części)</strong></span><span class="sxs-lookup"><span data-stu-id="81787-127"><strong>Plural nominative (Name of parts field group)</strong></span></span>     |                                                                                                         <span data-ttu-id="81787-128">Wprowadź formę liczby mnogiej dla podjednostki waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-128">Enter the plural form of the subunit of the currency.</span></span>                                                                                                          |
   |    <span data-ttu-id="81787-129"><strong>Nazwa skrótowa jednostek (grupa pól Krótka nazwa)</strong></span><span class="sxs-lookup"><span data-stu-id="81787-129"><strong>Shortcut name of units (Short name field group)</strong></span></span>    |                                                                                         <span data-ttu-id="81787-130">Wprowadź kod ISO identyfikujący walutę.</span><span class="sxs-lookup"><span data-stu-id="81787-130">Enter the ISO code to identify the currency.</span></span> <span data-ttu-id="81787-131">Na przykład wpisz LTL w celu identyfikowania litów.</span><span class="sxs-lookup"><span data-stu-id="81787-131">For example, enter LTL to identify Litas.</span></span>                                                                                         |
   |   <span data-ttu-id="81787-132"><strong>Nazwa skrótowa części (grupa pól Krótka nazwa)</strong></span><span class="sxs-lookup"><span data-stu-id="81787-132"><strong>Shortcut name for parts (Short name field group)</strong></span></span>    |                                                                                               <span data-ttu-id="81787-133">Wprowadź nazwę podjednostki waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-133">Enter the denomination of the currency subunit.</span></span> <span data-ttu-id="81787-134">Na przykład wpisz „groszy”.</span><span class="sxs-lookup"><span data-stu-id="81787-134">For example, enter Centas.</span></span>                                                                                               |
   |       <span data-ttu-id="81787-135"><strong>Spójnik „i” między jednostkami i częściami</strong></span><span class="sxs-lookup"><span data-stu-id="81787-135"><strong>Conjunction 'and' between units and parts</strong></span></span>       |                                     <span data-ttu-id="81787-136">Zaznacz tę opcję, aby drukować spójnik„i” między jednostkami i częściami waluty.</span><span class="sxs-lookup"><span data-stu-id="81787-136">Select to print the conjunction “and” between the currency units and unit parts.</span></span> <span data-ttu-id="81787-137">Na przykład w fakturach i raportach kwota 100,20 PLN będzie wyświetlana jako „100 złotych i 20 groszy”.</span><span class="sxs-lookup"><span data-stu-id="81787-137">For example, on invoices or reports, the amount for LTL 100.20 will be displayed as 100 Litas and 20 Centas.</span></span>                                      |


5. <span data-ttu-id="81787-138">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="81787-138">Click **Save**.</span></span>




