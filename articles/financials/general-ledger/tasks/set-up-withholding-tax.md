---
title: Konfigurowanie potrąconych zaliczek na podatek
description: Potrącona zaliczka na podatek to podatek nałożony na dostawców, który nie powoduje utworzenia transakcji podatkowej.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 382b6332665af2491563960a75d498a4f007aba8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562795"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="3e1ca-103">Konfigurowanie potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="3e1ca-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3e1ca-104">Potrącona zaliczka na podatek to podatek nałożony na dostawców, który nie powoduje utworzenia transakcji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="3e1ca-105">Potrącona zaliczka na podatek obliczana dla płatności dostawców jest zobowiązaniem.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="3e1ca-106">Z tego względu tylko konta bilansowe lub konta pasywów są odpowiednimi miejscami do księgowania potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="3e1ca-107">W tym przewodniku po zadaniach przedstawiono sposób konfigurowania zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="3e1ca-108">Wybierz kolejno opcje Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Kody potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="3e1ca-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-109">Click New.</span></span>
3. <span data-ttu-id="3e1ca-110">W polu Kod potrąconej zaliczki na podatek wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="3e1ca-111">W polu Nazwa potrąconej zaliczki na podatek nadaj nazwę kodowi zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="3e1ca-112">W polu Konto główne wybierz główne konto do księgowania zobowiązań z tytułu zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="3e1ca-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-113">Click Save.</span></span>
7. <span data-ttu-id="3e1ca-114">Kliknij opcję Wartości.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-114">Click Values.</span></span>
8. <span data-ttu-id="3e1ca-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="3e1ca-116">W polu Wartość wprowadź wartość procentową używaną do obliczania zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="3e1ca-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-117">Click Save.</span></span>
11. <span data-ttu-id="3e1ca-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-118">Close the page.</span></span>
12. <span data-ttu-id="3e1ca-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-119">Click Save.</span></span>
13. <span data-ttu-id="3e1ca-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-120">Close the page.</span></span>
14. <span data-ttu-id="3e1ca-121">Wybierz kolejno opcje Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Grupy potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="3e1ca-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-122">Click New.</span></span>
16. <span data-ttu-id="3e1ca-123">W polu Grupa potrąconej zaliczki na podatek nadaj identyfikator grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="3e1ca-124">W polu Opis nadaj nazwę grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="3e1ca-125">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="3e1ca-126">W polu Kod potrąconej zaliczki na podatek wybierz kod zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="3e1ca-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="3e1ca-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3e1ca-128">Click Save.</span></span>

