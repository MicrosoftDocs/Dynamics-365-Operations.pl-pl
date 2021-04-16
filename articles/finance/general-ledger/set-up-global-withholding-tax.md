---
title: Konfigurowanie globalne potrąconych zaliczek na podatek
description: W tym temacie wymieniono kroki konfigurowania globalnego zaliczki na podatek dla sprzedaży i zakupów.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3270b3f75d719fef9a7eb991c49e9d6585cd44d8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815315"
---
# <a name="set-up-global-withholding-tax"></a><span data-ttu-id="710b2-103">Konfigurowanie globalne potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="710b2-103">Set up global withholding tax</span></span>

<span data-ttu-id="710b2-104">W tym temacie wymieniono kroki konfigurowania globalnego zaliczki na podatek dla sprzedaży i zakupów.</span><span class="sxs-lookup"><span data-stu-id="710b2-104">This topic lists the steps for setting up global withholding tax for sales and purchases.</span></span> 

1. <span data-ttu-id="710b2-105">Konfigurowanie urzędów skarbowych dla potrąconych zaliczek na podatek na stronie **Urzędy odpowiedzialne za zaliczki na podatek**.</span><span class="sxs-lookup"><span data-stu-id="710b2-105">Set up withholding tax authorities on the **Withholding tax authorities** page.</span></span>

2. <span data-ttu-id="710b2-106">Ustawianie okresów rozliczenia potrąconej zaliczki na podatek na stronie **Okresy rozliczenia potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="710b2-106">Set up withholding settlement periods on the **Withholding tax settlement periods** page.</span></span>

3. <span data-ttu-id="710b2-107">Skonfiguruj grupę księgowania potrąconej zaliczki na stronie **Potrącona zaliczka na podatek > grupa księgowania w księdze głównej**.</span><span class="sxs-lookup"><span data-stu-id="710b2-107">Set up withholding ledger posting group on the **Withholding tax > ledger posting group** page.</span></span>

   > [!Note] 
   >
   > <span data-ttu-id="710b2-108">Konto **Potrąconej zaliczki na podatek** zostanie przypisane do konta głównego z **Typem księgowania** potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="710b2-108">**Withholding tax** account will be assigned with a main account with **Posting type** of Withholding tax.</span></span> <span data-ttu-id="710b2-109">Konto **Przesunięcie potrąconej zaliczki na podatek** zostanie przypisane do konta głównego z **Typem księgowania** „Potrąceniej zaliczki na podatek”.</span><span class="sxs-lookup"><span data-stu-id="710b2-109">**Withholding tax offset** account will also be assigned with a main account with **Posting type** "Withholding tax offset".</span></span> <span data-ttu-id="710b2-110">Przejdź do **Księga główna > Plan kont > Konta > Głowne konta**, ustaw **Typ księgowania** w formularzu podrzędnym **Sprawdzanie poprawności księgowania** dla kont głównych.</span><span class="sxs-lookup"><span data-stu-id="710b2-110">Go to **General ledger > Chart of accounts > Accounts > Main accounts**, set up the **Posting type** in the **Posting validation** sub-form for the main accounts.</span></span>

4. <span data-ttu-id="710b2-111">Konfigurowanie kodów dla potrąconych zaliczek na podatek na stronie **Kody potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="710b2-111">Set up withholding tax codes on the **Withholding tax codes** page.</span></span>

5. <span data-ttu-id="710b2-112">Konfigurowanie grup dla potrąconych zaliczek na podatek na stronie **Grupy potrąconych zaliczek na podatek**.</span><span class="sxs-lookup"><span data-stu-id="710b2-112">Set up withholding tax groups on the **Withholding tax groups** page.</span></span>

6. <span data-ttu-id="710b2-113">Ustawianie typów przychodu potrąconej zaliczki na podatek na stronie **Typy** **przychodu potrąconej** zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="710b2-113">Set up withholding tax revenue types on the **Withholding tax revenue** **types** page.</span></span>

7. <span data-ttu-id="710b2-114">Konfigurowanie grup dla potrąconych zaliczek na podatek na stronie **Grupy potrąconych zaliczek na podatek za pozycję** dla pozycji lub usługi.</span><span class="sxs-lookup"><span data-stu-id="710b2-114">Set up withholding tax groups on the **Item withholding tax groups** page for an item or service.</span></span>

8. <span data-ttu-id="710b2-115">Ustaw **Minimalna kwota faktury** na stronie **Parametry księgi głównej > Potrącona zaliczka na podatek**.</span><span class="sxs-lookup"><span data-stu-id="710b2-115">Set up **Minimum invoice amount** on the **General ledger parameters > Withholding tax** page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]