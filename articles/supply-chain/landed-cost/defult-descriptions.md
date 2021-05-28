---
title: Domyślne opisy księgi głównej
description: Opisów domyślnych można użyć do zaktualizowania pola Opis w księgowaniach załączników do księgi głównej.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 25dd72c86b22b50eccef22a5d2cbcfcf04280684
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021619"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="ee8a1-103">Domyślne opisy księgi głównej</span><span class="sxs-lookup"><span data-stu-id="ee8a1-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee8a1-104">Opisów domyślnych można użyć do zaktualizowania pola **Opis** w księgowaniach załączników do księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="ee8a1-105">Ta funkcjonalność została ulepszona tak, aby działała z kosztem dostawy.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="ee8a1-106">Aby skonfigurować domyślne opisy dla księgować w księdze, przejdź do **Administracja organizacyjna \> Konfiguracja \> Domyślne opisy**.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="ee8a1-107">W poniższej tabeli wymieniono nowe wartości, które zostały dodane w polu **Opis** na stronie **Domyślne opisy**, aby obsługiwać koszt dostawy.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="ee8a1-108">Typ opisu</span><span class="sxs-lookup"><span data-stu-id="ee8a1-108">Description type</span></span> | <span data-ttu-id="ee8a1-109">Notatki</span><span class="sxs-lookup"><span data-stu-id="ee8a1-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="ee8a1-110">Wycena importu — Naliczenie kosztów</span><span class="sxs-lookup"><span data-stu-id="ee8a1-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="ee8a1-111">Po zaksięgowaniu faktury za zamówienie zakupu naliczony koszt jest przetwarzany w celu oszacowania kosztów podróży.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="ee8a1-112">Można określić domyślne opisy, aby dodać numer podróży do opisu.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="ee8a1-113">Użyj *%4* jako numeru przesyłki.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="ee8a1-114">Wycena importu – zamówienie towaru w drodze</span><span class="sxs-lookup"><span data-stu-id="ee8a1-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="ee8a1-115">Jeśli jest przetwarzane w drodze, faktura zamówienia zakupu jest księgowana, a towary są księgowane na koncie towarów w drodze.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="ee8a1-116">Można określić opisy domyślne, aby dodać numer zamówienia w drodze do opisu.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="ee8a1-117">Użyj *%4* dla numeru zamówienia w drodze.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="ee8a1-118">Zapasy – Zamknięcie – Korekta</span><span class="sxs-lookup"><span data-stu-id="ee8a1-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="ee8a1-119">Gdy faktura zobowiązań (AP) jest przetwarzana dla kosztu podróży, przetwarzana jest korekta zapasów w celu oszacowania kosztów podróży.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="ee8a1-120">Można określić domyślne opisy, aby dodać numer podróży do opisu.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="ee8a1-121">Użyj *%4* jako numeru przesyłki.</span><span class="sxs-lookup"><span data-stu-id="ee8a1-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="ee8a1-122">Aby uzyskać więcej informacji na temat pracy ze stroną **Opisy domyślne**, zobacz temat [Konfigurowanie domyślnych opisów dla automatycznego księgowania](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="ee8a1-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
