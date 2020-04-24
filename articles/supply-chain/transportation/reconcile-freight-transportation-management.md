---
title: Uzgadnianie frachtu w module Zarządzanie transportem
description: W tym artykule opisano proces uzgadniania frachtu.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e1680572f1ba9816c9ec45ef52498cab1f45247
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206226"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="4249b-103">Uzgadnianie frachtu w module Zarządzanie transportem</span><span class="sxs-lookup"><span data-stu-id="4249b-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4249b-104">W tym artykule opisano proces uzgadniania frachtu.</span><span class="sxs-lookup"><span data-stu-id="4249b-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="4249b-105">Uzgadnianie frachtu można wykonać ręcznie lub skonfigurować jego wykonywanie automatyczne.</span><span class="sxs-lookup"><span data-stu-id="4249b-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="4249b-106">Aby używać automatycznego uzgadnianie frachtu, należy skonfigurować główną inspekcję, gdzie można zdefiniować kryteria określające, które listy frachtowe mają być uzgadniane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="4249b-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="4249b-107">Proces uzgadniania frachtu</span><span class="sxs-lookup"><span data-stu-id="4249b-107">The freight reconciliation process</span></span>
<span data-ttu-id="4249b-108">Stawki frachtowe są obliczane przez aparat stawki skojarzony z odnośnym przewoźnikiem.</span><span class="sxs-lookup"><span data-stu-id="4249b-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="4249b-109">Po potwierdzeniu ładunku jest generowany list frachtowy, a do niego są przenoszone stawki frachtowe.</span><span class="sxs-lookup"><span data-stu-id="4249b-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="4249b-110">Stawki frachtowe są przypisywane jako opłaty dodatkowe do odnośnego dokumentu źródłowego (zamówienia zakupu, zamówienia sprzedaży i/lub zamówienie przeniesienia), w zależności od konfiguracji używanej w standardowym procesie fakturowania.</span><span class="sxs-lookup"><span data-stu-id="4249b-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="4249b-111">Proces uzgadniania frachtu (nazywany także procesem dopasowywania) może się rozpocząć natychmiast po otrzymaniu faktury za fracht od firmy przewozowej.</span><span class="sxs-lookup"><span data-stu-id="4249b-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="4249b-112">Fakturę można odebrać elektronicznie lub na papierze.</span><span class="sxs-lookup"><span data-stu-id="4249b-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="4249b-113">Jeśli faktura jest otrzymywana na papierze, można wygenerować fakturę elektroniczną, używając listu frachtowego jako szablonu.</span><span class="sxs-lookup"><span data-stu-id="4249b-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span> 

<span data-ttu-id="4249b-114">[![Proces uzgadniania frachtu](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="4249b-114">[![Freight reconcilation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="4249b-115">Ręczne uzgadnianie</span><span class="sxs-lookup"><span data-stu-id="4249b-115">Manual reconciliation</span></span>
<span data-ttu-id="4249b-116">Jeśli uzgadniasz fracht ręcznie, trzeba dopasować każdy wiersz faktury do wiersza lub wierszy listu frachtowego dla fakturowanego ładunku.</span><span class="sxs-lookup"><span data-stu-id="4249b-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="4249b-117">To dopasowanie odbywa się na stronie **Dopasowywanie opłat frachtowych i faktur**.</span><span class="sxs-lookup"><span data-stu-id="4249b-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="4249b-118">Jeśli kwota w wierszu faktury nie pasuje do kwoty w liście frachtowym, dla różnicy należy wybrać przyczynę uzgodnienia.</span><span class="sxs-lookup"><span data-stu-id="4249b-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="4249b-119">Jeśli istnieje wiele przyczyn uzgodnienia, można rozdzielić niezgodną kwotę między nie.</span><span class="sxs-lookup"><span data-stu-id="4249b-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="4249b-120">Przyczyna uzgodnienia określa, jak kwoty różnic są księgowane w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="4249b-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="4249b-121">Po uzgodnieniu całej kwoty faktury faktura jest przedstawiana do zatwierdzenia, po czym następuje zaksięgowanie arkusza.</span><span class="sxs-lookup"><span data-stu-id="4249b-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="4249b-122">Poniższa ilustracja pokazuje sposób generowania faktury za fracht oraz uzgadniania frachtu.</span><span class="sxs-lookup"><span data-stu-id="4249b-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span> 
<span data-ttu-id="4249b-123">[![Zadania uzgadniania frachtu](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="4249b-123">[![Freight reconcilation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>
## <a name="automatic-reconciliation"></a><span data-ttu-id="4249b-124">Automatyczne uzgadnianie</span><span class="sxs-lookup"><span data-stu-id="4249b-124">Automatic reconciliation</span></span>
<span data-ttu-id="4249b-125">Aby użyć automatycznego uzgadniania, należy określić harmonogram uzgadniania oraz faktury i przewoźników, których uzgadnianie ma dotyczyć.</span><span class="sxs-lookup"><span data-stu-id="4249b-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="4249b-126">Dopasowywanie wierszy faktur i listów frachtowych odbywa się zgodnie z konfiguracją głównej inspekcji i typem listu frachtowego.</span><span class="sxs-lookup"><span data-stu-id="4249b-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="4249b-127">Po uruchomieniu automatycznego uzgadniania należy zidentyfikować wszystkie faktury, których nie jest w stanie dopasować system.</span><span class="sxs-lookup"><span data-stu-id="4249b-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="4249b-128">Następnie należy wykonać ręczne przetwarzanie tych faktur, zanim będzie można zaksięgować wszystkie faktury do zapłaty.</span><span class="sxs-lookup"><span data-stu-id="4249b-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>



