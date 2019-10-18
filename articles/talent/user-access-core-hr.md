---
title: Użytkownik ma dostęp do Core HR, ale nie do aplikacji Onboard albo Attract
description: W tym temacie opisano, jak rozwiązać ten problem polegający na tym, że użytkownik może uzyskać dostęp do Microsoft Dynamics 365 Talent - Core HR, ale nie ma dostępu do Attract lub aplikacji Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 80b1f8aeabfd033f393463f4be5a61447377f2d9
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009313"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a><span data-ttu-id="896cb-103">Użytkownik ma dostęp do Core HR, ale nie do aplikacji Onboard albo Attract</span><span class="sxs-lookup"><span data-stu-id="896cb-103">User can access Core HR but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="896cb-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="896cb-104">**Environment details**</span></span>

- <span data-ttu-id="896cb-105">Wdrożenie programu Microsoft Dynamics Lifecycle Services (LCS) zostało przeprowadzone przez użytkownika A.</span><span class="sxs-lookup"><span data-stu-id="896cb-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="896cb-106">Użytkownik A dodał użytkownika B jako użytkownika do Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="896cb-106">User A added user B as a user to Microsoft Dynamics 365 Talent: Core HR.</span></span>

<span data-ttu-id="896cb-107">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="896cb-107">**Issue**</span></span>

<span data-ttu-id="896cb-108">Użytkownik B ma dostęp do aplikacji Core HR, ale nie ma dostępu do Talent: Attract ani aplikacji Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="896cb-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="896cb-109">Kiedy użytkownik próbuje przejść do **aplikacji Experience**, jest zamiast tego kierowany do środowiska wersji próbnej.</span><span class="sxs-lookup"><span data-stu-id="896cb-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="896cb-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="896cb-110">**Solution**</span></span>

<span data-ttu-id="896cb-111">Użytkownik B musi mieć przypisane uprawnia wyświetlenia środowiska Microsoft PowerApps utworzonego przez użytkownika A w procesie przypisywania.</span><span class="sxs-lookup"><span data-stu-id="896cb-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="896cb-112">Aby uzyskać informacje, zobacz sekcję „Przyznawanie dostępu do środowiska” w [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="896cb-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="896cb-113">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="896cb-113">**Long-term solution**</span></span>

<span data-ttu-id="896cb-114">Microsoft rozważa automatyczne przypisywanie odpowiednich praw do Onboard i Attract podczas dodawania użytkownika do Core HR.</span><span class="sxs-lookup"><span data-stu-id="896cb-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
