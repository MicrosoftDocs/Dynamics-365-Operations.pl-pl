---
title: Skonfiguruj informacje o grupie TDS, PAN i TAN dla dostawców i klientów
description: W tym temacie wyjaśniono, jak skonfigurować informacje o grupie potrącanej z podatku w źródle (TDS), trwały numer konta (PAN) i numerze konta podatkowego (TAN) dla dostawców i odbiorców.
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
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023509"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a><span data-ttu-id="f0c40-103">Skonfiguruj informacje o grupie TDS, PAN i TAN dla dostawców i klientów</span><span class="sxs-lookup"><span data-stu-id="f0c40-103">TDS group, PAN, and TAN information setup for vendors and customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f0c40-104">W tym temacie wyjaśniono, jak skonfigurować informacje o grupie potrącanej z podatku w źródle (TDS), trwały numer konta (PAN) i numerze konta podatkowego (TAN) dla dostawców i odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f0c40-104">This topic explains how to set up information about the Tax Deducted at Source (TDS) group, permanent account number (PAN), and tax account number (TAN) for vendors and customers.</span></span>

1. <span data-ttu-id="f0c40-105">Przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy** lub **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="f0c40-105">Go to **Accounts payable \> Vendors \> All vendors** or **Accounts receivable \> Customers \> All customers**.</span></span>

    <span data-ttu-id="f0c40-106">[![Strona wszystkich dostawców](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span><span class="sxs-lookup"><span data-stu-id="f0c40-106">[![All vendors page](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span></span>

2. <span data-ttu-id="f0c40-107">Wybierz **Nowy** na okienku akcji, aby utworzyć dostawcę lub odbiorcę, i wprowadź wymagane szczegóły.</span><span class="sxs-lookup"><span data-stu-id="f0c40-107">On the Action Pane, select **New** to create a vendor or customer, and enter the required details.</span></span> <span data-ttu-id="f0c40-108">Możesz również wybrać istniejącego dostawcę lub dostawcę.</span><span class="sxs-lookup"><span data-stu-id="f0c40-108">Alternatively, select an existing vendor or customer.</span></span>
3. <span data-ttu-id="f0c40-109">Na skróconej karcie **Faktura i dostawa**, w sekcji **Potrącona zaliczka na podatek**, aby **obliczyć potrąconą zaliczkę na podatek** ustaw wartość **Tak**, TDS lub podatek potrącony w źródle (TCS) dla dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f0c40-109">On the **Invoice and delivery** FastTab, in the **Withholding tax** section, set the **Calculate withholding tax** option to **Yes** to calculate withholding tax, TDS, or Tax Collected at Source (TCS) for the vendor or customer.</span></span>
4. <span data-ttu-id="f0c40-110">Identyfikator TDS faktury zakupu jest obliczany na podstawie domyślnej grupy TDS zdefiniowanej dla dostawcy lub odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="f0c40-110">TDS for a purchase invoice is calculated based on the default TDS group that is defined for the vendor or customer.</span></span> <span data-ttu-id="f0c40-111">W polu **Grupa TDS** wybierz grupę TDS.</span><span class="sxs-lookup"><span data-stu-id="f0c40-111">In the **TDS group** field, select the default TDS group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0c40-112">Po wybraniu grupy TDS w polu **Grupa TDS** pola **Grupa potrąconej zaliczki na podatek** i grupa **TCS** stają się niedostępne.</span><span class="sxs-lookup"><span data-stu-id="f0c40-112">When you select a TDS group in the **TDS group** field, the **Withholding tax group** and **TCS group** fields become unavailable.</span></span>

5. <span data-ttu-id="f0c40-113">Na skróconej **karcie Informacje podatkowe**, w sekcji **Informacje PAN**, w polu **Stan** wybierz stan stałego numeru konta dla dostawcy lub odbiorcy:</span><span class="sxs-lookup"><span data-stu-id="f0c40-113">On the **Tax information** FastTab, in the **PAN information** section, in the **Status** field, select the status of the permanent account number for the vendor or customer:</span></span>

    - <span data-ttu-id="f0c40-114">**Niedostępny** — dostawca lub odbiorca nie ma konta PAN.</span><span class="sxs-lookup"><span data-stu-id="f0c40-114">**Not available** – The vendor or customer doesn't have a PAN.</span></span>
    - <span data-ttu-id="f0c40-115">**Otrzymane** — dostawca lub odbiorca ma numer PAN.</span><span class="sxs-lookup"><span data-stu-id="f0c40-115">**Received** – The vendor or customer has a PAN.</span></span>
    - <span data-ttu-id="f0c40-116">**Zastosowane** — dostawca lub odbiorca złożył wniosek o PAN.</span><span class="sxs-lookup"><span data-stu-id="f0c40-116">**Applied** – The vendor or customer has applied for a PAN.</span></span>
    - <span data-ttu-id="f0c40-117">**Nieprawidłowy** — dostawca lub odbiorca ma numer PAN, ale jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="f0c40-117">**Invalid** – The vendor or customer has a PAN, but it isn't valid.</span></span>

6. <span data-ttu-id="f0c40-118">Jeśli wybrano opcję **Odebrane** w polu **Stan**, aby wskazać, że dostawca lub odbiorca ma opcję PAN, w polu **Numer** wprowadź nazwę PAN.</span><span class="sxs-lookup"><span data-stu-id="f0c40-118">If you selected **Received** in the **Status** field to indicate that the vendor or customer has a PAN, enter the PAN in the **Number** field.</span></span> <span data-ttu-id="f0c40-119">Znak PAN musi składać się z pięciu znaków alfabetycznych, czterech cyfr i jednego znaku alfabetycznego.</span><span class="sxs-lookup"><span data-stu-id="f0c40-119">The PAN must consist of five alphabetic characters, then four numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="f0c40-120">Oto przykład: **ABCDE1260A**.</span><span class="sxs-lookup"><span data-stu-id="f0c40-120">Here is an example: **ABCDE1260A**.</span></span>
7. <span data-ttu-id="f0c40-121">Jeśli wybrano opcję **Zastosowano** w polu **Stan**, aby wskazać, że dostawca lub odbiorca ma opcję PAN, w polu **Numer odnośnika** wprowadź numer odnośnika.</span><span class="sxs-lookup"><span data-stu-id="f0c40-121">If you selected **Applied** in the **Status** field to indicate that the vendor or customer has applied for PAN, enter the reference number in the **Reference number** field.</span></span>
8. <span data-ttu-id="f0c40-122">W polu **Rodzaj osoby oceniającej** wybierz rodzaj kategorii osoby oceniającej, do której należy dostawca lub klient:</span><span class="sxs-lookup"><span data-stu-id="f0c40-122">In the **Nature of assessee** field, select the nature of assessee category that the vendor or customer belongs to:</span></span>

    - <span data-ttu-id="f0c40-123">Firma</span><span class="sxs-lookup"><span data-stu-id="f0c40-123">Company</span></span>
    - <span data-ttu-id="f0c40-124">HUF</span><span class="sxs-lookup"><span data-stu-id="f0c40-124">HUF</span></span>
    - <span data-ttu-id="f0c40-125">Akceptuj</span><span class="sxs-lookup"><span data-stu-id="f0c40-125">Firm</span></span>
    - <span data-ttu-id="f0c40-126">Osoba fizyczna</span><span class="sxs-lookup"><span data-stu-id="f0c40-126">Individual</span></span>
    - <span data-ttu-id="f0c40-127">AOP</span><span class="sxs-lookup"><span data-stu-id="f0c40-127">AOP</span></span>
    - <span data-ttu-id="f0c40-128">BOI</span><span class="sxs-lookup"><span data-stu-id="f0c40-128">BOI</span></span>
    - <span data-ttu-id="f0c40-129">Urząd lokalny</span><span class="sxs-lookup"><span data-stu-id="f0c40-129">Local authority</span></span>
    - <span data-ttu-id="f0c40-130">Inne</span><span class="sxs-lookup"><span data-stu-id="f0c40-130">Others</span></span>

    <span data-ttu-id="f0c40-131">[![Skrócona karta informacji podatkowych](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span><span class="sxs-lookup"><span data-stu-id="f0c40-131">[![Tax information FastTab](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span></span>

9. <span data-ttu-id="f0c40-132">Następnie w okienku akcji, na karcie **Dostawca**, w grupie **Rejestracja** wybierz **Identyfikatory rejestracji**, aby otworzyć stronę **Zarządzaj adresami**.</span><span class="sxs-lookup"><span data-stu-id="f0c40-132">On the Action Pane, on the **Vendor** tab, in the **Registration** group, select **Registration IDs** to open the **Manage addresses** page.</span></span>
10. <span data-ttu-id="f0c40-133">Na stronie **Zarządzanie adresami**, na skróconej karcie **Informacje o podatku** wybierz pozycję **Dodaj** lub **Edytuj**, aby otworzyć stronę **Zarządzaj informacjami o podatku**, na której możesz zachować wpis rejestracji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="f0c40-133">On the **Manage addresses** page, on the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>
11. <span data-ttu-id="f0c40-134">Na stronie **Zarządzanie informacjami o podatkach**, na skróconej karcie **Potrącona zaliczka na podatek** w polu **Numer konta podatkowego (TAN)** wprowadź numer TAN .</span><span class="sxs-lookup"><span data-stu-id="f0c40-134">On the **Manage tax information** page, on the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the TAN.</span></span> <span data-ttu-id="f0c40-135">Znak TAN musi składać się z czterech znaków alfabetycznych, pięciu cyfr i jednego znaku alfabetycznego.</span><span class="sxs-lookup"><span data-stu-id="f0c40-135">The TAN must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="f0c40-136">Oto przykład: **AFGH54821T**.</span><span class="sxs-lookup"><span data-stu-id="f0c40-136">Here is an example: **AFGH54821T**.</span></span>
12. <span data-ttu-id="f0c40-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f0c40-137">Close the page.</span></span>
