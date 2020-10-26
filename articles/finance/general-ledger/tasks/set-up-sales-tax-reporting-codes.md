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
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c18f4fb0db31a959647bb10d2b99d940646676e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976800"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="88662-103">Ustawianie kodów raportowania podatku</span><span class="sxs-lookup"><span data-stu-id="88662-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="88662-104">Kody raportowania podatków odnoszą się do numeru pola w raporcie podatku.</span><span class="sxs-lookup"><span data-stu-id="88662-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="88662-105">Są one wykorzystywane w układach raportów specyficznych dla krajów oraz w raporcie Płatności podatku według kodu na potrzeby drukowania kwot podatków dla okresu rozliczeniowego sumowanego według kodu raportowania.</span><span class="sxs-lookup"><span data-stu-id="88662-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="88662-106">Po utworzeniu kodów raportowania podatków można tworzyć do nich odwołania na skróconych kartach Konfiguracja raportu znajdujących się na stronie Kod podatku.</span><span class="sxs-lookup"><span data-stu-id="88662-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="88662-107">To nagranie wykorzystuje firmę demonstracyjną DEMF.</span><span class="sxs-lookup"><span data-stu-id="88662-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="88662-108">Otwórz **Okienko nawigacji**, następnie wybierz **Podatek > Ustawienia > Podatek > Kody raportowania podatku**.</span><span class="sxs-lookup"><span data-stu-id="88662-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="88662-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="88662-109">Click **New**.</span></span>
3. <span data-ttu-id="88662-110">Zaznacz układ raportu, do którego odnosi się kod raportowania.</span><span class="sxs-lookup"><span data-stu-id="88662-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="88662-111">Ten układ jest używany do filtrowania dostępnych kodów raportowania dla kodu podatku.</span><span class="sxs-lookup"><span data-stu-id="88662-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="88662-112">Każdy kod podatku należy do okresu rozliczeniowego obowiązującego w urzędzie skarbowym, który wykorzystuje układ raportu.</span><span class="sxs-lookup"><span data-stu-id="88662-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="88662-113">W polu **Kod raportowania** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="88662-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="88662-114">W polu **Tekst raportu** wprowadź opis, który ma być wyświetlany w raportach.</span><span class="sxs-lookup"><span data-stu-id="88662-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="88662-115">W polu **Krótki opis** wprowadź opis przeznaczony do celów wewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="88662-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="88662-116">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="88662-116">Click **Save**.</span></span>

