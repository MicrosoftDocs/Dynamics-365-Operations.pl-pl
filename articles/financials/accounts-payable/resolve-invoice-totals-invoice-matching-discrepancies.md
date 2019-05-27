---
title: Usuwanie rozbieżności podczas uzgadniania sum faktur
description: Uzgadnianie sum faktury może pomóc zagwarantować, że rozbieżność sum faktury i kwot oczekiwanych nie wykracza poza dopuszczalne limity tolerancji.
author: abruer
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63f4747c13d70d45404069a200124336d6f54947
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1512331"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="8b859-103">Usuwanie rozbieżności podczas uzgadniania sum faktur</span><span class="sxs-lookup"><span data-stu-id="8b859-103">Resolve discrepancies during invoice totals matching</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8b859-104">Jednym z typów weryfikację uzgadniania faktur jest uzgadnianie sum faktur.</span><span class="sxs-lookup"><span data-stu-id="8b859-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="8b859-105">Aby określić, czy system powinien wykonywać uzgadnianie sum faktur, na stronie **Parametry rozrachunków z dostawcami** na karcie **Sprawdzanie poprawności faktur** ustaw dla opcji **Dopasuj sumy faktur** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="8b859-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="8b859-106">Uzgadnianie sum faktury może pomóc zagwarantować, że rozbieżność sum faktury i kwot oczekiwanych nie wykracza poza dopuszczalne limity tolerancji.</span><span class="sxs-lookup"><span data-stu-id="8b859-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="8b859-107">Na stronie **Szczegóły uzgadniania sum faktur** porównywanych jest sześć sum.</span><span class="sxs-lookup"><span data-stu-id="8b859-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="8b859-108">Jeśli którakolwiek z nich odbiera od oczekiwanej sumy odpowiedniego zamówienia zakupu, dodawana jest flaga rozbieżności.</span><span class="sxs-lookup"><span data-stu-id="8b859-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="8b859-109">Aby sprawdzić oflagowaną fakturę z rozbieżnościami, w obszarze roboczym **Wprowadzanie faktur od dostawcy** kliknij tytuł **Faktury oczekujące**.</span><span class="sxs-lookup"><span data-stu-id="8b859-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="8b859-110">Następnie w okienku akcji na karcie **Przegląd** kliknij **Szczegóły uzgadniania**.</span><span class="sxs-lookup"><span data-stu-id="8b859-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="8b859-111">Jeśli wykryto rozbieżności w uzgadnianiu, ikony ostrzeżenia są wyświetlane obok kwoty faktury.</span><span class="sxs-lookup"><span data-stu-id="8b859-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="8b859-112">Można wyświetlić szczegółowe informacje o sumach, przeglądając szczegóły uzgadniania sum faktur.</span><span class="sxs-lookup"><span data-stu-id="8b859-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="8b859-113">Po znalezieniu rozbieżności konieczne może być skontaktowanie się z dostawcą, jeśli zachodzi podejrzenie, że informacje na fakturze są niepoprawne.</span><span class="sxs-lookup"><span data-stu-id="8b859-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="8b859-114">W zależności od umowy z dostawcą można wykonać jedno z następujących działań:</span><span class="sxs-lookup"><span data-stu-id="8b859-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="8b859-115">Zaakceptowanie różnicy cen i zaksięgowanie faktury z rozbieżnościami.</span><span class="sxs-lookup"><span data-stu-id="8b859-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="8b859-116">Konfiguracja systemu może wymagać zatwierdzenia przed zaksięgowaniem faktury z rozbieżnościami w uzgadnianiu.</span><span class="sxs-lookup"><span data-stu-id="8b859-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="8b859-117">W takim przypadku trzeba zatwierdzić rozbieżności uzgadniania i opcjonalnie można wprowadzić komentarz do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="8b859-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="8b859-118">Następnie można zaksięgować fakturę.</span><span class="sxs-lookup"><span data-stu-id="8b859-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="8b859-119">Odpowiednie poprawienie kwoty faktury i zaksięgowanie faktury.</span><span class="sxs-lookup"><span data-stu-id="8b859-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="8b859-120">Zażądanie od dostawcy pełnej zapłaty i nowej, poprawionej faktury.</span><span class="sxs-lookup"><span data-stu-id="8b859-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="8b859-121">Aby uzyskać więcej informacji, zobacz [Badanie lub rozwiązywanie wyjątków](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="8b859-121">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>


