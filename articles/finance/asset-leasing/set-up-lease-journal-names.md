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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 89c5fc768aafe9e5de9adcde32e7b4d0a084941b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990924"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="39755-104">Konfigurowanie nazw arkuszy wynajmu</span><span class="sxs-lookup"><span data-stu-id="39755-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39755-105">Nazwy arkuszy wynajmu określają arkusze, w których są księgowane transakcje z modułu Wynajem składnika majątku.</span><span class="sxs-lookup"><span data-stu-id="39755-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="39755-106">Tylko nazwy arkuszy przypisane do typu arkusza **Wynajem składnika majątku** są wyświetlane w polach **Początkowe rozpoznawanie** i **Nazwa arkusza miesięcznego** na stronie **Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="39755-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="39755-107">Do pola **Nazwa arkusza faktur** można przypisać tylko typ arkusza **Rejestracja faktury dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="39755-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="39755-108">Aby skonfigurować nazwy arkuszy wynajmu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="39755-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="39755-109">Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="39755-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="39755-110">Na karcie **Ogólne** w polu **Nazwa arkusza początkowego ujęcia** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="39755-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="39755-111">Wszystkie wpisy w arkuszu dotyczące początkowego ujęcia będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="39755-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="39755-112">W polu **Nazwa arkusza faktur** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="39755-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="39755-113">Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Tak** w księdze wynajmu, faktury opłat z tytułu wynajmu i płatności wydatków będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="39755-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="39755-114">W polu **Nazwa arkusza wynajmu** wybierz arkusz.</span><span class="sxs-lookup"><span data-stu-id="39755-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="39755-115">Wszystkie wpisy dotyczące amortyzacji, odsetek i przeklasyfikowania zobowiązań krótkoterminowych będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="39755-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="39755-116">Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Nie** w księdze wynajmu, wpisy opłat z tytułu wynajmu i płatności wydatków również będą księgowane w arkuszu o tej nazwie.</span><span class="sxs-lookup"><span data-stu-id="39755-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>
