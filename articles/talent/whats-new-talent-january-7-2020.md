---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (7 stycznia 2020 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462240"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a><span data-ttu-id="447cb-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (7 stycznia 2020 r.)</span><span class="sxs-lookup"><span data-stu-id="447cb-103">What's new or changed in Dynamics 365 Talent (January 7, 2020)</span></span>

<span data-ttu-id="447cb-104">W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="447cb-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="447cb-105">Zmiany w Attract</span><span class="sxs-lookup"><span data-stu-id="447cb-105">Changes in Attract</span></span>

<span data-ttu-id="447cb-106">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="447cb-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="447cb-107">Zmiany w Onboard</span><span class="sxs-lookup"><span data-stu-id="447cb-107">Changes in Onboard</span></span>

<span data-ttu-id="447cb-108">Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="447cb-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="447cb-109">Zmiany w Core HR</span><span class="sxs-lookup"><span data-stu-id="447cb-109">Changes in Core HR</span></span>

<span data-ttu-id="447cb-110">Zmiany opisane w tej części dotyczą kompilacji 8.1.2697.</span><span class="sxs-lookup"><span data-stu-id="447cb-110">Changes described in this section apply to build number 8.1.2697.</span></span> <span data-ttu-id="447cb-111">Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="447cb-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a><span data-ttu-id="447cb-112">Nie można usunąć pracowników, którzy nie mają rekordów zatrudnienia — (386157)</span><span class="sxs-lookup"><span data-stu-id="447cb-112">Can't delete workers that don't have employment records - (386157)</span></span>

<span data-ttu-id="447cb-113">Ta zmiana powoduje dodanie opcji usuwania w formularzu **pracownicy bez zatrudnienia**.</span><span class="sxs-lookup"><span data-stu-id="447cb-113">This change adds a delete option in the **Workers without employment** form.</span></span> <span data-ttu-id="447cb-114">Pracownicy są wyświetlani w tym formularzu, gdy dla pracownika nie istnieją przyszłe, aktywne lub historyczne zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="447cb-114">Workers appear in this form when no future, active, or historical employments exist for the worker.</span></span> <span data-ttu-id="447cb-115">W tej wersji funkcja usuwania jest włączona tylko dla administratorów systemu.</span><span class="sxs-lookup"><span data-stu-id="447cb-115">In this release, delete is only enabled for System Administrators.</span></span> <span data-ttu-id="447cb-116">Jednak w przyszłotygodniowym wydaniu zabezpieczenia zostaną zaktualizowane, aby umożliwić wszystkim użytkownikom z rolą asystenta działu kadr usuwanie pracowników bez zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="447cb-116">However, in next week's release, security will be updated to allow all users with the HR assistant role to remove employees without employments.</span></span> <span data-ttu-id="447cb-117">Zmiany te można również wprowadzić ręcznie, wykonując następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="447cb-117">You can also make these changes manually by following the following steps.</span></span>

1. <span data-ttu-id="447cb-118">Przejdź do **Konfiguracja zabezpieczeń**.</span><span class="sxs-lookup"><span data-stu-id="447cb-118">Go to **Security configuration**.</span></span>
2. <span data-ttu-id="447cb-119">Na karcie **uprawnienia** odfiltruj listę **uprawnień**, aby **obsługiwać pracowników**.</span><span class="sxs-lookup"><span data-stu-id="447cb-119">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>
3. <span data-ttu-id="447cb-120">W kolumnie **odwołania** wybierz **Wyświetl elementy menu**.</span><span class="sxs-lookup"><span data-stu-id="447cb-120">In the **References** column, select **Display menu items**.</span></span>
4. <span data-ttu-id="447cb-121">W kolumnie **Wyświetl elementy menu** wybierz **HcmWOrkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="447cb-121">In **Display menu items**, select **HcmWOrkersWithoutEmployment**.</span></span>
5. <span data-ttu-id="447cb-122">Ustaw zezwolenie na **usuwanie**.</span><span class="sxs-lookup"><span data-stu-id="447cb-122">Set the **Delete** permission to Grant.</span></span>
6. <span data-ttu-id="447cb-123">Wybierz kartę **nieopublikowane obiekty**.</span><span class="sxs-lookup"><span data-stu-id="447cb-123">Select the **Unpublished objects** tab.</span></span>
7. <span data-ttu-id="447cb-124">Wybierz opcję **Publikuj wszystko**.</span><span class="sxs-lookup"><span data-stu-id="447cb-124">Select **Publish all**.</span></span>
