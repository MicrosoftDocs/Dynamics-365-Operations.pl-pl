---
title: Konfigurowanie nazw arkuszy wynajmu
description: W tym temacie opisano sposób definiowania nazw arkuszy wynajmu. Nazwy arkuszy wynajmu określają arkusze, w których są księgowane wpisy inicjowane z modułu Wynajem składnika majątku.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8b1b908dfd6d1d6072b6efa83f13ae5784c85c1
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446989"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="67847-104">Konfigurowanie nazw arkuszy wynajmu</span><span class="sxs-lookup"><span data-stu-id="67847-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67847-105">Nazwy arkuszy wynajmu określają arkusze, w których są księgowane transakcje z modułu Wynajem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="67847-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="67847-106">Tylko nazwy arkuszy przypisane do typu arkusza **Wynajem składnika majątku** są wyświetlane w polach **Początkowe rozpoznawanie** i **Nazwa arkusza miesięcznego** na stronie **Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="67847-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="67847-107">Do pola **Nazwa arkusza faktur** można przypisać tylko typ arkusza **Rejestracja faktury dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="67847-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="67847-108">Aby skonfigurować nazwy arkuszy wynajmu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="67847-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="67847-109">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="67847-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="67847-110">Na karcie **Ogólne** w polu **Nazwa arkusza początkowego ujęcia** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="67847-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="67847-111">Wszystkie wpisy w arkuszu dotyczące początkowego ujęcia będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="67847-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="67847-112">W polu **Nazwa arkusza faktur** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="67847-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="67847-113">Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Tak** w księdze wynajmu, faktury opłat z tytułu wynajmu i płatności wydatków będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="67847-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="67847-114">W polu **Nazwa arkusza wynajmu** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="67847-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="67847-115">Wszystkie wpisy dotyczące amortyzacji, odsetek i przeklasyfikowania zobowiązań krótkoterminowych będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="67847-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="67847-116">Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Nie** w księdze wynajmu, wpisy opłat z tytułu wynajmu i płatności wydatków również będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="67847-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>
