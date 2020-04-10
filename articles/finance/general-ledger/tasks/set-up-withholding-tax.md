---
title: Konfigurowanie potrąconych zaliczek na podatek
description: W tym temacie wyjaśniono sposób konfigurowania potrąconej zaliczki na podatek.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 135cca434a1689bf22ee468894dcf8746071e7ca
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144704"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="8859c-103">Konfigurowanie potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="8859c-103">Set up withholding tax</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8859c-104">W tym temacie wyjaśniono sposób konfigurowania potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="8859c-105">*Potrącona zaliczka na podatek* to podatek nałożony na dostawców, który nie powoduje utworzenia transakcji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="8859c-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="8859c-106">Potrącona zaliczka na podatek obliczana dla płatności dostawców jest zobowiązaniem.</span><span class="sxs-lookup"><span data-stu-id="8859c-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="8859c-107">Z tego względu tylko konta bilansowe lub konta pasywów są odpowiednimi miejscami do księgowania potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="8859c-108">W tym przewodniku po zadaniach przedstawiono sposób konfigurowania zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="8859c-109">Otwórz **Okienko nawigacji > Moduły > Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Kody potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="8859c-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="8859c-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8859c-110">Select **New**.</span></span>
3. <span data-ttu-id="8859c-111">W polu **Kod potrąconej zaliczki na podatek** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8859c-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="8859c-112">W polu **Nazwa potrąconej zaliczki na podatek** nadaj nazwę kodowi zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="8859c-113">W polu **Konto główne** wybierz główne konto do księgowania zobowiązań z tytułu zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="8859c-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8859c-114">Select **Save**.</span></span>
7. <span data-ttu-id="8859c-115">Wybierz **Wartości** i oznacz odpowiedni rekord na liście.</span><span class="sxs-lookup"><span data-stu-id="8859c-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="8859c-116">W polu **Wartość** wprowadź wartość procentową używaną do obliczania zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="8859c-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8859c-117">Select **Save**.</span></span>
10. <span data-ttu-id="8859c-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8859c-118">Close the page.</span></span>
11. <span data-ttu-id="8859c-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8859c-119">Select **Save**.</span></span>
12. <span data-ttu-id="8859c-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8859c-120">Close the page.</span></span>
13. <span data-ttu-id="8859c-121">Otwórz **Okienko nawigacji > Moduły > Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Grupy potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="8859c-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="8859c-122">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="8859c-122">Select **New**.</span></span>
15. <span data-ttu-id="8859c-123">W polu **Grupa potrąconej zaliczki na podatek** nadaj identyfikator grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="8859c-124">W polu **Opis** nadaj nazwę grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="8859c-125">W polu **Kod potrąconej zaliczki na podatek** wybierz kod zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="8859c-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="8859c-126">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8859c-126">Select **Save**.</span></span>
19. <span data-ttu-id="8859c-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8859c-127">Close the page.</span></span>

