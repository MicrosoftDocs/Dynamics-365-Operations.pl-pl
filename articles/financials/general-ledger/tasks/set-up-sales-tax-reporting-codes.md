---
title: Ustawianie kodów raportowania podatku
description: Kody raportowania podatków odnoszą się do numeru pola w raporcie podatku.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4543cf7eaa0b1ef8e32d3fdafa2c354cd3739256
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "335676"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="2efd6-103">Ustawianie kodów raportowania podatku</span><span class="sxs-lookup"><span data-stu-id="2efd6-103">Set up sales tax reporting codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2efd6-104">Kody raportowania podatków odnoszą się do numeru pola w raporcie podatku.</span><span class="sxs-lookup"><span data-stu-id="2efd6-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="2efd6-105">Są one wykorzystywane w układach raportów specyficznych dla krajów oraz w raporcie Płatności podatku według kodu na potrzeby drukowania kwot podatków dla okresu rozliczeniowego sumowanego według kodu raportowania.</span><span class="sxs-lookup"><span data-stu-id="2efd6-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="2efd6-106">Po utworzeniu kodów raportowania podatków można tworzyć do nich odwołania na skróconych kartach Konfiguracja raportu znajdujących się na stronie Kod podatku.</span><span class="sxs-lookup"><span data-stu-id="2efd6-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="2efd6-107">To nagranie wykorzystuje firmę demonstracyjną DEMF.</span><span class="sxs-lookup"><span data-stu-id="2efd6-107">This recording uses the DEMF demo company.</span></span>



1. <span data-ttu-id="2efd6-108">Wybierz kolejno opcje Podatek > Ustawienia > Podatek > Kody raportowania podatku.</span><span class="sxs-lookup"><span data-stu-id="2efd6-108">Go to Tax > Setup > Sales tax > Sales tax reporting codes.</span></span>
2. <span data-ttu-id="2efd6-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="2efd6-109">Click New.</span></span>
3. <span data-ttu-id="2efd6-110">Zaznacz układ raportu, do którego odnosi się kod raportowania.</span><span class="sxs-lookup"><span data-stu-id="2efd6-110">Select the report layout that the reporting code belongs to.</span></span>
    * <span data-ttu-id="2efd6-111">Ten układ jest używany do filtrowania dostępnych kodów raportowania dla kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="2efd6-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="2efd6-112">Każdy kod podatku należy do okresu rozliczeniowego obowiązującego w urzędzie skarbowym, który wykorzystuje układ raportu.</span><span class="sxs-lookup"><span data-stu-id="2efd6-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="2efd6-113">Wpisz liczbę odwołującą się do pola w raporcie podatku.</span><span class="sxs-lookup"><span data-stu-id="2efd6-113">Enter a number that refers to a field on a sales tax report.</span></span>
5. <span data-ttu-id="2efd6-114">W polu Tekst raportu wprowadź opis, który ma być wyświetlany w raportach.</span><span class="sxs-lookup"><span data-stu-id="2efd6-114">In the Report text field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="2efd6-115">W polu Krótki opis wprowadź opis przeznaczony do celów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="2efd6-115">In the Brief description field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="2efd6-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="2efd6-116">Click Save.</span></span>

