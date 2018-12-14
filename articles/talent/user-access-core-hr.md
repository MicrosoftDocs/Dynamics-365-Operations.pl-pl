---
title: "Użytkownik ma dostęp do aplikacji Core HR, ale nie do Onboard albo Attract"
description: "W tym temacie opisano, jak rozwiązać ten problem polegający na tym, że użytkownik może uzyskać dostęp do Microsoft Dynamics 365 for Talent Core HR, ale nie ma dostępu do Attract lub aplikacji Onboard."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2e5d0b1bf993aec89c7d2c6d4916732f5824310d
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---

# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>Użytkownik ma dostęp do aplikacji Core HR, ale nie do Onboard albo Attract

[!include [banner](includes/banner.md)]

**Szczegóły środowiska**

- Wdrożenie programu Microsoft Dynamics Lifecycle Services (LCS) zostało przeprowadzone przez użytkownika A.
- Użytkownik A dodał użytkownika B jako użytkownika do Microsoft Dynamics 365 for Talent Core HR.

**Wydaj**

Użytkownik B ma dostęp do aplikacji Core HR, ale nie ma dostępu do Talent: Attract ani aplikacji Talent: Onboard. Kiedy użytkownik próbuje przejść do **aplikacji Experience**, jest zamiast tego kierowany do środowiska wersji próbnej.

**Rozwiązanie**

Użytkownik B musi mieć przypisane uprawnia wyświetlenia środowiska Microsoft PowerApps utworzonego przez użytkownika A w procesie przypisywania.

Aby uzyskać informacje, zobacz sekcję „Przyznawanie dostępu do środowiska” w [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Rozwiązanie długoterminowe**

Microsoft rozważa automatyczne przypisywanie odpowiednich praw do Onboard i Attract podczas dodawania użytkownika do Core HR.

