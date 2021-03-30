---
title: Obliczanie i korygowanie podatku na fakturze od dostawcy
description: W tym temacie wyjaśniono, jak dostosować podatek od sprzedaży na fakturze od dostawcy w Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4d01fe7587e01c04af28be934a235d955455216
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204744"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="16dd5-103">Obliczanie i korygowanie podatku na fakturze od dostawcy</span><span class="sxs-lookup"><span data-stu-id="16dd5-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="16dd5-104">W tym temacie wyjaśniono, jak dostosować podatek od sprzedaży na fakturze od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="16dd5-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="16dd5-105">Jeśli oryginalny dokument źródłowy zawiera kwoty podatku inne niż obliczone, można skorygować te kwoty przed zaksięgowaniem.</span><span class="sxs-lookup"><span data-stu-id="16dd5-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="16dd5-106">W zadaniu wykorzystano firmę demonstracyjną DEMF.</span><span class="sxs-lookup"><span data-stu-id="16dd5-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="16dd5-107">W okienku nawigacji przejdź do **moduły > Rozrachunki z dostawcami > faktury > arkusz faktur**.</span><span class="sxs-lookup"><span data-stu-id="16dd5-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="16dd5-108">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="16dd5-108">Select **New**.</span></span>
3. <span data-ttu-id="16dd5-109">W polu **nazwa** nowego wiersza wybierz opcję z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="16dd5-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="16dd5-110">W okienku akcji wybierz **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="16dd5-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="16dd5-111">W polu **Konto** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="16dd5-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="16dd5-112">W polu **Faktura** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="16dd5-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="16dd5-113">W polu **Kredyt** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="16dd5-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="16dd5-114">W polu **Konto przeciwstawne** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="16dd5-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="16dd5-115">Wybierz **Podatek**.</span><span class="sxs-lookup"><span data-stu-id="16dd5-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="16dd5-116">W polu **Całkowita rzeczywista kwota podatku** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="16dd5-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="16dd5-117">Na karcie **Korekta** można skorygować kwoty podatku według kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="16dd5-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="16dd5-118">Wybierz **Resetuj aktualne kwoty na podstawie obliczonych**.</span><span class="sxs-lookup"><span data-stu-id="16dd5-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="16dd5-119">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="16dd5-119">Select **OK**.</span></span>
14. <span data-ttu-id="16dd5-120">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="16dd5-120">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]