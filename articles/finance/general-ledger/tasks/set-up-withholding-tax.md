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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ae7b13f743336e01f17248c8d6492b31e8044ef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222318"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="95d1a-103">Konfigurowanie potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="95d1a-103">Set up withholding tax</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="95d1a-104">W tym temacie wyjaśniono sposób konfigurowania potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="95d1a-105">*Potrącona zaliczka na podatek* to podatek nałożony na dostawców, który nie powoduje utworzenia transakcji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="95d1a-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="95d1a-106">Potrącona zaliczka na podatek obliczana dla płatności dostawców jest zobowiązaniem.</span><span class="sxs-lookup"><span data-stu-id="95d1a-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="95d1a-107">Z tego względu tylko konta bilansowe lub konta pasywów są odpowiednimi miejscami do księgowania potrąconych zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="95d1a-108">W tym przewodniku po zadaniach przedstawiono sposób konfigurowania zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="95d1a-109">Otwórz **Okienko nawigacji > Moduły > Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Kody potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="95d1a-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-110">Select **New**.</span></span>
3. <span data-ttu-id="95d1a-111">W polu **Kod potrąconej zaliczki na podatek** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="95d1a-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="95d1a-112">W polu **Nazwa potrąconej zaliczki na podatek** nadaj nazwę kodowi zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="95d1a-113">W polu **Konto główne** wybierz główne konto do księgowania zobowiązań z tytułu zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="95d1a-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-114">Select **Save**.</span></span>
7. <span data-ttu-id="95d1a-115">Wybierz **Wartości** i oznacz odpowiedni rekord na liście.</span><span class="sxs-lookup"><span data-stu-id="95d1a-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="95d1a-116">W polu **Wartość** wprowadź wartość procentową używaną do obliczania zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="95d1a-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-117">Select **Save**.</span></span>
10. <span data-ttu-id="95d1a-118">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="95d1a-118">Close the page.</span></span>
11. <span data-ttu-id="95d1a-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-119">Select **Save**.</span></span>
12. <span data-ttu-id="95d1a-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="95d1a-120">Close the page.</span></span>
13. <span data-ttu-id="95d1a-121">Otwórz **Okienko nawigacji > Moduły > Podatek > Podatki pośrednie > Potrącona zaliczka na podatek > Grupy potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="95d1a-122">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-122">Select **New**.</span></span>
15. <span data-ttu-id="95d1a-123">W polu **Grupa potrąconej zaliczki na podatek** nadaj identyfikator grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="95d1a-124">W polu **Opis** nadaj nazwę grupie zaliczek na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="95d1a-125">W polu **Kod potrąconej zaliczki na podatek** wybierz kod zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="95d1a-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="95d1a-126">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="95d1a-126">Select **Save**.</span></span>
19. <span data-ttu-id="95d1a-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="95d1a-127">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]