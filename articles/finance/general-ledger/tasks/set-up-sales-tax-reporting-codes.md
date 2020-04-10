---
title: Ustawianie kodów raportowania podatku
description: Kody raportowania podatków odnoszą się do numeru pola w raporcie podatku.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 460e41d69a78cda664e0d3af828fdc482169ac52
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145082"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="9deff-103">Ustawianie kodów raportowania podatku</span><span class="sxs-lookup"><span data-stu-id="9deff-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9deff-104">Kody raportowania podatków odnoszą się do numeru pola w raporcie podatku.</span><span class="sxs-lookup"><span data-stu-id="9deff-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="9deff-105">Są one wykorzystywane w układach raportów specyficznych dla krajów oraz w raporcie Płatności podatku według kodu na potrzeby drukowania kwot podatków dla okresu rozliczeniowego sumowanego według kodu raportowania.</span><span class="sxs-lookup"><span data-stu-id="9deff-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="9deff-106">Po utworzeniu kodów raportowania podatków można tworzyć do nich odwołania na skróconych kartach Konfiguracja raportu znajdujących się na stronie Kod podatku.</span><span class="sxs-lookup"><span data-stu-id="9deff-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="9deff-107">To nagranie wykorzystuje firmę demonstracyjną DEMF.</span><span class="sxs-lookup"><span data-stu-id="9deff-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="9deff-108">Otwórz **Okienko nawigacji**, następnie wybierz **Podatek > Ustawienia > Podatek > Kody raportowania podatku**.</span><span class="sxs-lookup"><span data-stu-id="9deff-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="9deff-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="9deff-109">Click **New**.</span></span>
3. <span data-ttu-id="9deff-110">Zaznacz układ raportu, do którego odnosi się kod raportowania.</span><span class="sxs-lookup"><span data-stu-id="9deff-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="9deff-111">Ten układ jest używany do filtrowania dostępnych kodów raportowania dla kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="9deff-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="9deff-112">Każdy kod podatku należy do okresu rozliczeniowego obowiązującego w urzędzie skarbowym, który wykorzystuje układ raportu.</span><span class="sxs-lookup"><span data-stu-id="9deff-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="9deff-113">W polu **Kod raportowania** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="9deff-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="9deff-114">W polu **Tekst raportu** wprowadź opis, który ma być wyświetlany w raportach.</span><span class="sxs-lookup"><span data-stu-id="9deff-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="9deff-115">W polu **Krótki opis** wprowadź opis przeznaczony do celów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="9deff-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="9deff-116">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9deff-116">Click **Save**.</span></span>

