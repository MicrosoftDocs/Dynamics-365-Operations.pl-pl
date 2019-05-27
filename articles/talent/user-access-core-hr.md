---
title: Użytkownik ma dostęp do aplikacji Core HR, ale nie do Onboard albo Attract
description: W tym temacie opisano, jak rozwiązać ten problem polegający na tym, że użytkownik może uzyskać dostęp do Microsoft Dynamics 365 for Talent Core HR, ale nie ma dostępu do Attract lub aplikacji Onboard.
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
ms.openlocfilehash: ece6a81c54ef1421284fc79ab82ed3e31a972255
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518852"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="1e4cf-103">Użytkownik ma dostęp do aplikacji Core HR, ale nie do Onboard albo Attract</span><span class="sxs-lookup"><span data-stu-id="1e4cf-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1e4cf-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="1e4cf-104">**Environment details**</span></span>

- <span data-ttu-id="1e4cf-105">Wdrożenie programu Microsoft Dynamics Lifecycle Services (LCS) zostało przeprowadzone przez użytkownika A.</span><span class="sxs-lookup"><span data-stu-id="1e4cf-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="1e4cf-106">Użytkownik A dodał użytkownika B jako użytkownika do Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="1e4cf-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="1e4cf-107">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="1e4cf-107">**Issue**</span></span>

<span data-ttu-id="1e4cf-108">Użytkownik B ma dostęp do aplikacji Core HR, ale nie ma dostępu do Talent: Attract ani aplikacji Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="1e4cf-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="1e4cf-109">Kiedy użytkownik próbuje przejść do **aplikacji Experience**, jest zamiast tego kierowany do środowiska wersji próbnej.</span><span class="sxs-lookup"><span data-stu-id="1e4cf-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="1e4cf-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="1e4cf-110">**Solution**</span></span>

<span data-ttu-id="1e4cf-111">Użytkownik B musi mieć przypisane uprawnia wyświetlenia środowiska Microsoft PowerApps utworzonego przez użytkownika A w procesie przypisywania.</span><span class="sxs-lookup"><span data-stu-id="1e4cf-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="1e4cf-112">Aby uzyskać informacje, zobacz sekcję „Przyznawanie dostępu do środowiska” w [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="1e4cf-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="1e4cf-113">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="1e4cf-113">**Long-term solution**</span></span>

<span data-ttu-id="1e4cf-114">Microsoft rozważa automatyczne przypisywanie odpowiednich praw do Onboard i Attract podczas dodawania użytkownika do Core HR.</span><span class="sxs-lookup"><span data-stu-id="1e4cf-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
