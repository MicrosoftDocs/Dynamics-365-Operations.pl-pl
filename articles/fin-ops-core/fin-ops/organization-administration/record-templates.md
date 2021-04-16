---
title: Omówienie szablonów rekordów
description: Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje.
author: pvillads
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d802d8bb86313dba512f52ec977b4dd18aa25c61
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747544"
---
# <a name="record-templates-overview"></a><span data-ttu-id="1a884-103">Omówienie szablonów rekordów</span><span class="sxs-lookup"><span data-stu-id="1a884-103">Record templates overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a884-104">Ten artykuł zawiera wprowadzenie do koncepcji szablonów rekordów oraz wyjaśnienia, jak używać tych szablonów do tworzenia rekordów udostępniających informacje.</span><span class="sxs-lookup"><span data-stu-id="1a884-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="1a884-105">Szablony rekordów ułatwiają szybkie tworzenie rekordów, jednak można tworzyć szablony rekordów dla niektórych typów rekordów.</span><span class="sxs-lookup"><span data-stu-id="1a884-105">Record templates can help you to create records more quickly, however you can only create record templates for some record types.</span></span>

<span data-ttu-id="1a884-106">Na przykład załóżmy, że wprowadzasz dane wynajmu dla wypożyczali samochodów w San Francisco.</span><span class="sxs-lookup"><span data-stu-id="1a884-106">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="1a884-107">Ponieważ większość klientów będzie prawdopodobnie pochodziła z San Francisco, byłoby dobrze, gdy pola **Stan**, **Kraju** i **Miasto** na formularzu wynajmu mogły wypełniać się automatycznie</span><span class="sxs-lookup"><span data-stu-id="1a884-107">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span>

> [!NOTE]
> <span data-ttu-id="1a884-108">Użytkownicy mogą stosować szablony wyłącznie w odniesieniu do segmentów, do których mają dostęp.</span><span class="sxs-lookup"><span data-stu-id="1a884-108">You can apply templates only in areas that you have access to.</span></span> <span data-ttu-id="1a884-109">Jednak wszystkie tytuły szablonów są dla Ciebie widoczne podczas tworzenia nowego rekordu, a także dla innych użytkowników w przypadku tworzenia szablonów, które będą dostępne dla wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="1a884-109">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="1a884-110">Należy to wziąć pod uwagę podczas nadawania nazw szablonom.</span><span class="sxs-lookup"><span data-stu-id="1a884-110">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="1a884-111">Na przykład należy unikać nazw zawierających słowo „prowizja”, jeśli poufną informacją jest to, że wynagrodzenia niektórych pracowników mają charakter prowizyjny.</span><span class="sxs-lookup"><span data-stu-id="1a884-111">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span>

<span data-ttu-id="1a884-112">Gdy jeden lub więcej szablonów, do których masz dostęp, istnieje dla określonego formularza i próbujesz utworzyć nowy rekord w formularzu, wyświetlany jest strona **Wybierz szablon dla...**.</span><span class="sxs-lookup"><span data-stu-id="1a884-112">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="1a884-113">Po wybraniu szablonu z listy jest tworzony nowy rekord, zawierający domyślne informacje utworzone na podstawie wybranego szablonu.</span><span class="sxs-lookup"><span data-stu-id="1a884-113">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="1a884-114">Jeśli nie chcesz używać szablonów podczas tworzenia nowych rekordów, zaznacz pole wyboru **Nie pytaj ponownie** na stronie **Wybierz szablon dla**.</span><span class="sxs-lookup"><span data-stu-id="1a884-114">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="1a884-115">Aby ponownie wyświetlić okno dialogowe wyboru szablonu, kliknij prawym przyciskiem myszy dowolny rekord, kliknij opcję **Informacje o rekordzie**, a następnie kliknij przycisk **Pokaż zaznaczenie szablonów**.</span><span class="sxs-lookup"><span data-stu-id="1a884-115">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]