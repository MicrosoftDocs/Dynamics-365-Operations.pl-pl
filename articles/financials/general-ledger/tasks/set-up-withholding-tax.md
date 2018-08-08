--- 
title: "Konfigurowanie potrąconych zaliczek na podatek"
description: "Potrącona zaliczka na podatek to podatek nałożony na dostawców, który nie powoduje utworzenia transakcji podatkowej."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 362df7c97adae2526cb61b07e3022dc3b63fc59e
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="c1974-103">Konfigurowanie potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="c1974-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c1974-104">Potrącona zaliczka na podatek to podatek nałożony na dostawców, który nie powoduje utworzenia transakcji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="c1974-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="c1974-105">Potrącona zaliczka na podatek obliczana dla płatności dostawców jest zobowiązaniem.</span><span class="sxs-lookup"><span data-stu-id="c1974-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="c1974-106">Z tego względu tylko konta bilansowe lub konta pasywów są odpowiednimi miejscami do księgowania potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="c1974-107">W tym przewodniku po zadaniach przedstawiono sposób konfigurowania zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="c1974-108">Wybierz kolejno opcje Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Kody potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="c1974-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c1974-109">Click New.</span></span>
3. <span data-ttu-id="c1974-110">W polu Kod potrąconej zaliczki na podatek wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c1974-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="c1974-111">W polu Nazwa potrąconej zaliczki na podatek nadaj nazwę kodowi zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="c1974-112">W polu Konto główne wybierz główne konto do księgowania zobowiązań z tytułu zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="c1974-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c1974-113">Click Save.</span></span>
7. <span data-ttu-id="c1974-114">Kliknij opcję Wartości.</span><span class="sxs-lookup"><span data-stu-id="c1974-114">Click Values.</span></span>
8. <span data-ttu-id="c1974-115">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c1974-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="c1974-116">W polu Wartość wprowadź wartość procentową używaną do obliczania zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="c1974-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c1974-117">Click Save.</span></span>
11. <span data-ttu-id="c1974-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c1974-118">Close the page.</span></span>
12. <span data-ttu-id="c1974-119">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c1974-119">Click Save.</span></span>
13. <span data-ttu-id="c1974-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c1974-120">Close the page.</span></span>
14. <span data-ttu-id="c1974-121">Wybierz kolejno opcje Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Grupy potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="c1974-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c1974-122">Click New.</span></span>
16. <span data-ttu-id="c1974-123">W polu Grupa potrąconej zaliczki na podatek nadaj identyfikator grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="c1974-124">W polu Opis nadaj nazwę grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="c1974-125">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c1974-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="c1974-126">W polu Kod potrąconej zaliczki na podatek wybierz kod zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="c1974-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="c1974-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c1974-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="c1974-128">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c1974-128">Click Save.</span></span>


