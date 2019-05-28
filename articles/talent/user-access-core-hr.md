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
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>Użytkownik ma dostęp do aplikacji Core HR, ale nie do Onboard albo Attract

[!include [banner](includes/banner.md)]

**Szczegóły środowiska**

- Wdrożenie programu Microsoft Dynamics Lifecycle Services (LCS) zostało przeprowadzone przez użytkownika A.
- Użytkownik A dodał użytkownika B jako użytkownika do Microsoft Dynamics 365 for Talent Core HR.

**Wystawienie**

Użytkownik B ma dostęp do aplikacji Core HR, ale nie ma dostępu do Talent: Attract ani aplikacji Talent: Onboard. Kiedy użytkownik próbuje przejść do **aplikacji Experience**, jest zamiast tego kierowany do środowiska wersji próbnej.

**Rozwiązanie**

Użytkownik B musi mieć przypisane uprawnia wyświetlenia środowiska Microsoft PowerApps utworzonego przez użytkownika A w procesie przypisywania.

Aby uzyskać informacje, zobacz sekcję „Przyznawanie dostępu do środowiska” w [Inicjowanie obsługi rozwiązania Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Rozwiązanie długoterminowe**

Microsoft rozważa automatyczne przypisywanie odpowiednich praw do Onboard i Attract podczas dodawania użytkownika do Core HR.
