---
title: Obliczanie podatku TDS w transakcjach międzyfirmowych
description: W tym temacie opisano proces, który jest używany do obliczania podatku potrąconego w źródle (TDS) dla transakcji międzyfirmowych w fazach.
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
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023511"
---
# <a name="tds-calculation-on-intercompany-transactions"></a><span data-ttu-id="22716-103">Obliczanie podatku TDS w transakcjach międzyfirmowych</span><span class="sxs-lookup"><span data-stu-id="22716-103">TDS calculation on intercompany transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22716-104">W tym temacie opisano proces, który jest używany do obliczania podatku potrąconego w źródle (TDS) dla transakcji międzyfirmowych w fazach.</span><span class="sxs-lookup"><span data-stu-id="22716-104">This topic describes the process that is used to calculate Tax Deducted at Source (TDS) on intercompany transactions in phases.</span></span>

<span data-ttu-id="22716-105">Podczas tworzenia międzyfirmowego zamówienia zakupu lub zamówienia sprzedaży do obliczania kwoty podatku TDS jest używana domyślna grupa TDS zdefiniowana dla odbiorcy lub dostawcy.</span><span class="sxs-lookup"><span data-stu-id="22716-105">When an intercompany purchase order or sales order is created, the default TDS group that is defined for the customer or vendor is used to calculate the TDS amount.</span></span> <span data-ttu-id="22716-106">Kwota TDS jest księgowana na kontach rozrachunków z dostawcami lub należności po zaksięgowaniu faktury.</span><span class="sxs-lookup"><span data-stu-id="22716-106">The TDS amount is posted to the recoverable or payable accounts after the invoice is posted.</span></span>

<span data-ttu-id="22716-107">Dla międzyfirmowe zamówienie sprzedaży zakupu lub zamówienia zakupu jest automatycznie tworzone zamówienie zakupu lub zamówienie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="22716-107">An intercompany sales order or purchase order is automatically created for the original purchase order or sales order.</span></span> <span data-ttu-id="22716-108">Domyślna grupa TDS jest wyświetlana na zamówieniu międzyfirmowym, dzięki czemu można je obliczyć.</span><span class="sxs-lookup"><span data-stu-id="22716-108">The default TDS group is shown on the intercompany order, so that TDS can be calculated.</span></span> <span data-ttu-id="22716-109">Możesz zmienić grupę TDS.</span><span class="sxs-lookup"><span data-stu-id="22716-109">You can change the TDS group.</span></span> <span data-ttu-id="22716-110">Fakturę można zakłać tylko wtedy, gdy kwota netto faktury na automatycznie utworzonym zamówieniu międzyfirmowym jest taka liczba jak kwota netto faktury na oryginalnym zamówieniu.</span><span class="sxs-lookup"><span data-stu-id="22716-110">The invoice can be posted only if the net invoice amount on the intercompany order that is automatically created matches the net invoice amount on the original order.</span></span> <span data-ttu-id="22716-111">(Kwota netto jest kwotą faktury po potrąceniu TDS.)</span><span class="sxs-lookup"><span data-stu-id="22716-111">(The net amount is the invoice amount after TDS is deducted.)</span></span>

<span data-ttu-id="22716-112">Na przykład faktura sprzedaży zostanie utworzona na 50 000 i zostanie do niej dołączona grupa TDS o wartości **10%**.</span><span class="sxs-lookup"><span data-stu-id="22716-112">For example, a sales invoice is created for 50,000, and the **10%** TDS group is attached to it.</span></span> <span data-ttu-id="22716-113">Zaksięgowana kwota faktury wynosi 45 000, a zaksięgowana kwota TDS dla faktury sprzedaży to 5000.</span><span class="sxs-lookup"><span data-stu-id="22716-113">The posted invoice amount is 45,000, and the posted TDS amount for the sales invoice is 5,000.</span></span> <span data-ttu-id="22716-114">Zamówienie zakupu jest automatycznie tworzone dla międzyfirmowe zamówienie sprzedaży, do których jest dołączona grupa TDS w wysokości **10%**.</span><span class="sxs-lookup"><span data-stu-id="22716-114">A purchase order is automatically created for the intercompany sales order, and the  **10%** TDS group is attached to it.</span></span> <span data-ttu-id="22716-115">Jeśli zmienisz wartość grupy TDS na **15%**, nie będzie można zakturować faktury, ponieważ kwota netto utworzonej automatycznie międzyfirmowe zamówienie sprzedaży nie odpowiada kwocie netto faktury z oryginalnego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="22716-115">If you change the TDS group to **15%**, you can't post the invoice, because the net invoice amount of the intercompany sales order that was automatically created doesn't match the net invoice amount of the original sales order.</span></span>

<span data-ttu-id="22716-116">Arkusz płatności utworzony dla faktury międzyfirmowej jest księgowany automatycznie.</span><span class="sxs-lookup"><span data-stu-id="22716-116">A payment journal that is created for an intercompany invoice is automatically posted.</span></span> <span data-ttu-id="22716-117">Ten arkusz płatności może być księgowany tylko wtedy, gdy kwota płatności netto w nim odpowiada kwocie płatności netto w oryginalnym arkuszu płatności.</span><span class="sxs-lookup"><span data-stu-id="22716-117">That payment journal can be posted only if the net payment amount on it matches the net payment amount on the original payment journal.</span></span>
