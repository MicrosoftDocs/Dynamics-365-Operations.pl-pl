---
title: Ustawianie kodów raportowania podatku
description: Kody raportowania podatków odnoszą się do numeru pola zawartego w raporcie podatku.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be24e18da63d1a613c3c6e72f7c767c7af9b6656
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222150"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="aa396-103">Ustawianie kodów raportowania podatku</span><span class="sxs-lookup"><span data-stu-id="aa396-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aa396-104">Kody raportowania podatków odnoszą się do numeru pola zawartego w raporcie podatku.</span><span class="sxs-lookup"><span data-stu-id="aa396-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="aa396-105">Są one używane w układach raportów właściwych dla danego kraju.</span><span class="sxs-lookup"><span data-stu-id="aa396-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="aa396-106">Są także używane w raporcie Płatności podatku według kodu.</span><span class="sxs-lookup"><span data-stu-id="aa396-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="aa396-107">Ten raport przedstawia kwoty podatku dla okresu rozliczeniowego podsumowanego dla każdego kodu raportowania.</span><span class="sxs-lookup"><span data-stu-id="aa396-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="aa396-108">Po utworzeniu kodów raportowania podatków można tworzyć do nich odwołania na skróconych kartach Konfiguracja raportu, do których można przejść ze strony **Kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="aa396-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="aa396-109">To nagranie wykorzystuje firmę demonstracyjną DEMF.</span><span class="sxs-lookup"><span data-stu-id="aa396-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="aa396-110">Otwórz **Okienko nawigacji**, następnie wybierz **Podatek > Ustawienia > Podatek > Kody raportowania podatku**.</span><span class="sxs-lookup"><span data-stu-id="aa396-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="aa396-111">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="aa396-111">Click **New**.</span></span>
3. <span data-ttu-id="aa396-112">Zaznacz układ raportu, do którego odnosi się kod raportowania.</span><span class="sxs-lookup"><span data-stu-id="aa396-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="aa396-113">Ten układ jest używany do filtrowania dostępnych kodów raportowania dla kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="aa396-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="aa396-114">Każdy kod podatku należy do okresu rozliczeniowego obowiązującego w urzędzie skarbowym, który wykorzystuje układ raportu.</span><span class="sxs-lookup"><span data-stu-id="aa396-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="aa396-115">W polu **Kod raportowania** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="aa396-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="aa396-116">W polu **Tekst raportu** wprowadź opis, który ma być wyświetlany w raportach.</span><span class="sxs-lookup"><span data-stu-id="aa396-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="aa396-117">W polu **Krótki opis** wprowadź opis przeznaczony do celów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="aa396-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="aa396-118">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="aa396-118">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]