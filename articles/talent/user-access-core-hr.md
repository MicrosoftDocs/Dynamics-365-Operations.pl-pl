---
title: Użytkownik ma dostęp do aplikacji Human Resources, ale nie do aplikacji Onboard albo Attract
description: W tym temacie opisano, jak rozwiązać ten problem polegający na tym, że użytkownik może uzyskać dostęp do Microsoft Dynamics 365 Talent — Human Resources, ale nie ma dostępu do Attract lub aplikacji Onboard.
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462216"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a><span data-ttu-id="671af-103">Użytkownik ma dostęp do aplikacji Human Resources, ale nie do aplikacji Onboard albo Attract</span><span class="sxs-lookup"><span data-stu-id="671af-103">User can access Human Resources but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="671af-104">**Szczegóły środowiska**</span><span class="sxs-lookup"><span data-stu-id="671af-104">**Environment details**</span></span>

- <span data-ttu-id="671af-105">Wdrożenie programu Microsoft Dynamics Lifecycle Services (LCS) zostało przeprowadzone przez użytkownika A.</span><span class="sxs-lookup"><span data-stu-id="671af-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="671af-106">Użytkownik A dodał użytkownika B jako użytkownika do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="671af-106">User A added user B as a user to Microsoft Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="671af-107">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="671af-107">**Issue**</span></span>

<span data-ttu-id="671af-108">Użytkownik B ma dostęp do aplikacji Human Resources, ale nie ma dostępu do Talent: Attract ani aplikacji Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="671af-108">User B can access Human Resources, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="671af-109">Kiedy użytkownik próbuje przejść do **aplikacji Experience**, jest zamiast tego kierowany do środowiska wersji próbnej.</span><span class="sxs-lookup"><span data-stu-id="671af-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="671af-110">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="671af-110">**Solution**</span></span>

<span data-ttu-id="671af-111">Użytkownik B musi mieć przypisane uprawnia wyświetlenia środowiska Microsoft Power Apps utworzonego przez użytkownika A w procesie przypisywania.</span><span class="sxs-lookup"><span data-stu-id="671af-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="671af-112">Aby uzyskać informacje, zobacz sekcję „Przyznawanie dostępu do środowiska” w [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="671af-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="671af-113">**Rozwiązanie długoterminowe**</span><span class="sxs-lookup"><span data-stu-id="671af-113">**Long-term solution**</span></span>

<span data-ttu-id="671af-114">Microsoft rozważa automatyczne przypisywanie odpowiednich praw do Onboard i Attract podczas dodawania użytkownika do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="671af-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Human Resources.</span></span>
