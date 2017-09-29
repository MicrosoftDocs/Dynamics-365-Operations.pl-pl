---
title: "Domyślne konta przeciwstawne dla arkuszy faktur od dostawcy i arkuszy zatwierdzania faktur"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="092bb-102">Domyślne konta przeciwstawne dla arkuszy faktur od dostawcy i arkuszy zatwierdzania faktur</span><span class="sxs-lookup"><span data-stu-id="092bb-102">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="092bb-103">Domyślne konta przeciwstawne są używane w następujących formularzach arkusza stron od dostawcy:</span><span class="sxs-lookup"><span data-stu-id="092bb-103">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="092bb-104">Arkusz faktur</span><span class="sxs-lookup"><span data-stu-id="092bb-104">Invoice journal</span></span>
-   <span data-ttu-id="092bb-105">Arkusz zatwierdzania faktur</span><span class="sxs-lookup"><span data-stu-id="092bb-105">Invoice approval journal</span></span>

<span data-ttu-id="092bb-106">Skorzystaj z poniższej tabeli, aby określić miejsce przypisania domyślnych kont i transakcji przeciwstawnej dla arkuszy faktur.</span><span class="sxs-lookup"><span data-stu-id="092bb-106">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="092bb-107">Konfigurowanie domyślnych kont tutaj</span><span class="sxs-lookup"><span data-stu-id="092bb-107">Set up default accounts here</span></span></th>
<th><span data-ttu-id="092bb-108">Gdzie są dostarczane domyślne konta</span><span class="sxs-lookup"><span data-stu-id="092bb-108">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="092bb-109">Jak ta opcja wpływa na przetwarzanie</span><span class="sxs-lookup"><span data-stu-id="092bb-109">How this option affects processing</span></span></th>
<th><span data-ttu-id="092bb-110">Kiedy należy używać tej opcji</span><span class="sxs-lookup"><span data-stu-id="092bb-110">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="092bb-111"><strong>Grupa dostawców</strong> — pozwala ustawić domyślne konta przeciwstawne dla grup dostawców na stronie <strong>Ustawienia konta domyślnego</strong>, którą można otworzyć ze strony <strong>Grupy dostawców</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-111"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="092bb-112">Konto dostawcy</span><span class="sxs-lookup"><span data-stu-id="092bb-112">Vendor account</span></span></li>
<li><span data-ttu-id="092bb-113">Zapisy arkuszy dla kont dostawców w grupie dostawców, jeśli domyślne konta nie zostały określone dla kont dostawców</span><span class="sxs-lookup"><span data-stu-id="092bb-113">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="092bb-114">Domyślne konta przeciwstawne dla grup dostawców są pokazywane jako domyślne konta przeciwstawne dla dostawców na stronie <strong>Ustawienia konta domyślnego</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-114">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="092bb-115">Można otworzyć tę stronę ze strony listy <strong>Wszyscy dostawcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-115">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="092bb-116">Zaznacz tę opcję, jeśli zwykle płacisz za te same typy towarów z tej samej grupy dostawców przez dłuższy czas.</span><span class="sxs-lookup"><span data-stu-id="092bb-116">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="092bb-117"><strong>Konto dostawcy</strong> — pozwala ustawić domyślne konta dostawcy na stronie <strong>Ustawienia konta domyślnego</strong>, którą można otworzyć ze strony <strong>Dostawcy</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-117"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="092bb-118">Zapisy arkusza dla konta dostawcy</span><span class="sxs-lookup"><span data-stu-id="092bb-118">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="092bb-119">Domyślne konta przeciwstawne dla kont dostawców są wyświetlane jako domyślne konta przeciwstawne dla zapisów w arkuszu dla konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="092bb-119">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="092bb-120">Zaznacz tę opcję, jeśli zwykle płacisz za te same typy towarów od tych samych dostawców przez dłuższy czas.</span><span class="sxs-lookup"><span data-stu-id="092bb-120">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="092bb-121"><strong>Nazwy arkuszy</strong> — pozwala ustawić domyśle konta przeciwstawne na stronie <strong>Nazwy arkuszy</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-121"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="092bb-122">Wybierz opcję <strong>Stałe konto przeciwstawne</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-122">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="092bb-123">Warto pamiętać, że nie można określić domyślnych kont przeciwstawnych dla nazwy arkusza, jeśli typem arkusza dla nazwy arkuszy jest <strong>Rejestr faktur</strong> lub <strong>Zatwierdzenie</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-123">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="092bb-124">Nagłówek arkusza, dla którego używana jest nazwa arkusza.</span><span class="sxs-lookup"><span data-stu-id="092bb-124">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="092bb-125">Zapisy w arkuszach w arkuszach używających nazwy arkusza</span><span class="sxs-lookup"><span data-stu-id="092bb-125">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="092bb-126">Jeśli opcja <strong>Stałe konto przeciwstawne</strong> na stronie <strong>Nazwy arkuszy</strong> jest zaznaczona, konto przeciwstawne dla nazwy arkusza zastępuje domyślne konto przeciwstawne dla dostawcy lub grupy dostawców.</span><span class="sxs-lookup"><span data-stu-id="092bb-126">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="092bb-127">Ta opcja służy do konfigurowania arkuszy dla określonych kosztów i wydatków, które są naliczane dla określonych kont, niezależnie od dostawcy czy grupy dostawców, do której przynależy dostawca.</span><span class="sxs-lookup"><span data-stu-id="092bb-127">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="092bb-128"><strong>Nazwy arkuszy</strong> — pozwala ustawić domyśle konta przeciwstawne na stronie <strong>Nazwy arkuszy</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-128"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="092bb-129">Usuń zaznaczenie opcji <strong>Stałe konto przeciwstawne</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-129">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="092bb-130">Warto pamiętać, że nie można określić domyślnych kont przeciwstawnych dla nazwy arkusza, jeśli typem arkusza dla nazwy arkuszy jest <strong>Rejestr faktur</strong> lub <strong>Zatwierdzenie</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-130">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="092bb-131">Nagłówek arkusza</span><span class="sxs-lookup"><span data-stu-id="092bb-131">Journal header</span></span></li>
<li><span data-ttu-id="092bb-132">Zapisy w arkuszach w arkuszach używających nazwy arkusza</span><span class="sxs-lookup"><span data-stu-id="092bb-132">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="092bb-133">Te wpisy domyślne są używane na stronach nagłówka arkusza, a konto przeciwstawne na stronie nagłówka arkusza jest używane jako domyślny wpis na stronach załącznika arkusza.</span><span class="sxs-lookup"><span data-stu-id="092bb-133">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="092bb-134">Domyślne konta ze strony <strong>Nazwy arkuszy</strong> są używane tylko wtedy, gdy nie są ustawione domyślne konta dla konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="092bb-134">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="092bb-135">Ta opcja służy do konfigurowania domyślnych kont do użycia, gdy domyślne konto przeciwstawne dostawcy nie jest przypisane.</span><span class="sxs-lookup"><span data-stu-id="092bb-135">Use this option to set up default accounts that are used when a default vendor offset account isn't assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="092bb-136"><strong>Nagłówek arkusza</strong> — pozwala ustawić domyślne konto przeciwstawne dla arkusza, które będzie używane jako domyślny wpis na stronach załącznika arkusza.</span><span class="sxs-lookup"><span data-stu-id="092bb-136"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="092bb-137">Warto pamiętać, że nie można określić domyślnych kont przeciwstawnych dla nagłówka arkusza, jeśli typem arkusza dla nazwy arkuszy jest <strong>Rejestr faktur</strong> lub <strong>Zatwierdzenie</strong>.</span><span class="sxs-lookup"><span data-stu-id="092bb-137">Note that you can't specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="092bb-138">Zapisy arkusza w arkuszu</span><span class="sxs-lookup"><span data-stu-id="092bb-138">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="092bb-139">Domyślne konto przeciwstawne dla arkusza jest używane jako domyślny wpis na stronach załącznika arkusza.</span><span class="sxs-lookup"><span data-stu-id="092bb-139">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="092bb-140">Opcja ta pomaga przyspieszyć wprowadzanie danych, jeśli większość zapisów w arkuszu ma to samo konto przeciwstawne.</span><span class="sxs-lookup"><span data-stu-id="092bb-140">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>






