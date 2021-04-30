---
title: Konfigurowanie nazw arkuszy wynajmu
description: W tym temacie opisano sposób definiowania nazw arkuszy wynajmu. Nazwy arkuszy wynajmu określają arkusze, w których są księgowane wpisy inicjowane z modułu Wynajem składnika majątku.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c139df124b249ec9dc5d16096e6f45f22d435456
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880893"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="7ca70-104">Konfigurowanie nazw arkuszy wynajmu</span><span class="sxs-lookup"><span data-stu-id="7ca70-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ca70-105">Nazwy arkuszy wynajmu określają arkusze, w których są księgowane transakcje z modułu Wynajem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="7ca70-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="7ca70-106">Tylko nazwy arkuszy przypisane do typu arkusza **Wynajem składnika majątku** są wyświetlane w polach **Początkowe rozpoznawanie** i **Nazwa arkusza miesięcznego** na stronie **Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="7ca70-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="7ca70-107">Do pola **Nazwa arkusza faktur** można przypisać tylko typ arkusza **Rejestracja faktury dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="7ca70-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="7ca70-108">Aby skonfigurować nazwy arkuszy wynajmu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7ca70-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="7ca70-109">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="7ca70-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="7ca70-110">Na karcie **Ogólne** w polu **Nazwa arkusza początkowego ujęcia** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="7ca70-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="7ca70-111">Wszystkie wpisy w arkuszu dotyczące początkowego ujęcia będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="7ca70-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="7ca70-112">W polu **Nazwa arkusza faktur** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="7ca70-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="7ca70-113">Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Tak** w księdze wynajmu, faktury opłat z tytułu wynajmu i płatności wydatków będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="7ca70-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="7ca70-114">W polu **Nazwa arkusza wynajmu** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="7ca70-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="7ca70-115">Wszystkie wpisy dotyczące amortyzacji, odsetek i przeklasyfikowania zobowiązań krótkoterminowych będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="7ca70-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="7ca70-116">Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Nie** w księdze wynajmu, wpisy opłat z tytułu wynajmu i płatności wydatków również będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="7ca70-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
