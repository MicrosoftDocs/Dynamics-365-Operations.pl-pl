---
title: "Szablony rekordów"
description: "Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje."
author: pvillads
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e89e4a74550597a4e497a1128fe91c07e766d697
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="record-templates"></a><span data-ttu-id="51a62-103">Szablony rekordów</span><span class="sxs-lookup"><span data-stu-id="51a62-103">Record templates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="51a62-104">Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje.</span><span class="sxs-lookup"><span data-stu-id="51a62-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="51a62-105">Szablony rekordów pomagają w szybkim tworzeniu rekordów w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51a62-105">Record templates can help you to create records more quickly in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="51a62-106">Istnieje możliwość tworzenia szablonów rekordów tylko dla niektórych typów rekordów w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51a62-106">You can create record templates for only some of the record types in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="51a62-107">Na przykład załóżmy, że wprowadzasz dane wynajmu dla wypożyczali samochodów w San Francisco.</span><span class="sxs-lookup"><span data-stu-id="51a62-107">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="51a62-108">Ponieważ większość klientów będzie prawdopodobnie pochodziła z San Francisco, byłoby dobrze, gdy pola **Stan**, **Kraju** i **Miasto** na formularzu wynajmu mogły wypełniać się automatycznie</span><span class="sxs-lookup"><span data-stu-id="51a62-108">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span> 

> [!Note]
> <span data-ttu-id="51a62-109">Szablony mogą być stosowane tylko w odniesieniu do segmentów systemu Finance and Operations, do których mają dostęp.</span><span class="sxs-lookup"><span data-stu-id="51a62-109">You can apply templates only for the areas of Finance and Operations that you have access to.</span></span> <span data-ttu-id="51a62-110">Jednak wszystkie tytuły szablonów są dla Ciebie widoczne podczas tworzenia nowego rekordu, a także dla innych użytkowników w przypadku tworzenia szablonów, które będą dostępne dla wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="51a62-110">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="51a62-111">Należy to wziąć pod uwagę podczas nadawania nazw szablonom.</span><span class="sxs-lookup"><span data-stu-id="51a62-111">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="51a62-112">Na przykład należy unikać nazw zawierających słowo „prowizja”, jeśli poufną informacją jest to, że wynagrodzenia niektórych pracowników mają charakter prowizyjny.</span><span class="sxs-lookup"><span data-stu-id="51a62-112">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span> 

<span data-ttu-id="51a62-113">Gdy jeden lub więcej szablonów, do których masz dostęp, istnieje dla określonego formularza i próbujesz utworzyć nowy rekord w formularzu, wyświetlany jest strona **Wybierz szablon dla...**.</span><span class="sxs-lookup"><span data-stu-id="51a62-113">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="51a62-114">Po wybraniu szablonu z listy jest tworzony nowy rekord, zawierający domyślne informacje utworzone na podstawie wybranego szablonu.</span><span class="sxs-lookup"><span data-stu-id="51a62-114">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="51a62-115">Jeśli nie chcesz używać szablonów podczas tworzenia nowych rekordów, zaznacz pole wyboru **Nie pytaj ponownie** na stronie **Wybierz szablon dla**.</span><span class="sxs-lookup"><span data-stu-id="51a62-115">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="51a62-116">Aby ponownie wyświetlić okno dialogowe wyboru szablonu, kliknij prawym przyciskiem myszy dowolny rekord, kliknij opcję **Informacje o rekordzie**, a następnie kliknij przycisk **Pokaż zaznaczenie szablonów**.</span><span class="sxs-lookup"><span data-stu-id="51a62-116">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>




