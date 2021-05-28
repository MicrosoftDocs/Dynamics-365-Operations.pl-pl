---
title: Skonfiguruj kody raportowania podatku u źródła dla typu podatku TDS
description: Kody raportowania potrąconych zaliczek na podatek są używane do generowania sprawozdań z formularzy 26Q i 27Q dla podatku potrąconego w źródle (TDS). W tym temacie opisano sposób skonfigurowania kroków kodów raportowania potrąconych zaliczek na podatek, aby można było skonfigurować kody raportowania TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023518"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a><span data-ttu-id="108e2-104">Skonfiguruj kody raportowania podatku u źródła dla typu podatku TDS</span><span class="sxs-lookup"><span data-stu-id="108e2-104">Set up withholding tax reporting codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="108e2-105">Kody raportowania potrąconych zaliczek na podatek są używane do generowania sprawozdań z formularzy 26Q i 27Q dla podatku potrąconego w źródle (TDS).</span><span class="sxs-lookup"><span data-stu-id="108e2-105">Withholding tax reporting codes are used to generate Form 26Q and Form 27Q statements for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="108e2-106">W tym temacie opisano sposób skonfigurowania kroków kodów raportowania potrąconych zaliczek na podatek, aby można było skonfigurować kody raportowania TDS.</span><span class="sxs-lookup"><span data-stu-id="108e2-106">This topic explains how to set up withholding tax reporting codes steps so that you can set up TDS reporting codes.</span></span>

1. <span data-ttu-id="108e2-107">Wybierz kolejno opcje **Podatek \> Konfiguracja \> Potrącona zaliczka na podatek \> Kody raportowania potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="108e2-107">Go to **Tax \> Setup \> Withholding tax \> Withholding tax reporting codes**.</span></span>

    <span data-ttu-id="108e2-108">[![Strona kodów raportowania potrąconych zaliczek na podatek](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span><span class="sxs-lookup"><span data-stu-id="108e2-108">[![Withholding tax reporting codes page](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span></span>

2. <span data-ttu-id="108e2-109">W polu **Typ podatku** wybierz **TDS**, aby zdefiniować kody raportowania podatku u źródła dla typu podatku potrącanego u źródła.</span><span class="sxs-lookup"><span data-stu-id="108e2-109">In the **Tax type** field, select **TDS** to define withholding tax reporting codes for the TDS tax type.</span></span>
3. <span data-ttu-id="108e2-110">W polu **Składnik potrąconej zaliczki na podatek** wybierz składnik TDS, dla których ma być definiowany kod raportowania potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="108e2-110">In the **Withholding tax component** field, select the TDS component to that you're defining the withholding tax reporting code for.</span></span> <span data-ttu-id="108e2-111">Pole **Grupa składników potrąconej zaliczki na podatek** zawiera grupę składników TDS zdefiniowaną dla definiowanego składnika TDS.</span><span class="sxs-lookup"><span data-stu-id="108e2-111">The **Withholding tax component group** field shows the TDS component group that was defined for the TDS component that you're defining.</span></span>

    <span data-ttu-id="108e2-112">Pole **Kod sekcji** na skróconej karcie **Ogólne** zawiera kod sekcji dołączony do grupy składników TDS.</span><span class="sxs-lookup"><span data-stu-id="108e2-112">The **Section code** field on the **General** FastTab shows the section code that is attached to the TDS component group.</span></span>

4. <span data-ttu-id="108e2-113">Na skróconej karcie **Ogólne** w polu **Kod raportowania** wybierz kod raportowania TDS:</span><span class="sxs-lookup"><span data-stu-id="108e2-113">On the **General** FastTab, in the **Reporting code** field, select the TDS reporting code:</span></span>

    - <span data-ttu-id="108e2-114">TDS</span><span class="sxs-lookup"><span data-stu-id="108e2-114">TDS</span></span>
    - <span data-ttu-id="108e2-115">TCS</span><span class="sxs-lookup"><span data-stu-id="108e2-115">TCS</span></span>
    - <span data-ttu-id="108e2-116">Dopłata</span><span class="sxs-lookup"><span data-stu-id="108e2-116">Surcharge</span></span>
    - <span data-ttu-id="108e2-117">PE\_Cess</span><span class="sxs-lookup"><span data-stu-id="108e2-117">PE\_Cess</span></span>
    - <span data-ttu-id="108e2-118">SHE\_Cess</span><span class="sxs-lookup"><span data-stu-id="108e2-118">SHE\_Cess</span></span>

5. <span data-ttu-id="108e2-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="108e2-119">Close the page.</span></span>
