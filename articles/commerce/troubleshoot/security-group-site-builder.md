---
title: Nie można skonfigurować grupy zabezpieczeń dla Konstruktora witryn portalu Commerce podczas początkowego wdrażania
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy grupa zabezpieczeń rozwiązania Microsoft Azure Active Directory (Azure AD) dla Konstruktora witryn Commerce nie pojawia się jako opcja podczas tworzenia składników usługi handlu elektronicznego w u usługach Microsoft Dynamics Lifecycle Services (LCS) podczas początkowego wdrażania nowej dzierżawy usług handlu elektronicznego.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 7098c853c262fd7e0d48231634b232eef71c2b8d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292008"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Nie można skonfigurować grupy zabezpieczeń dla Konstruktora witryn portalu Commerce podczas początkowego wdrażania

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy grupa zabezpieczeń rozwiązania Microsoft Azure Active Directory (Azure AD) dla Konstruktora witryn Commerce nie pojawia się jako opcja podczas tworzenia składników usługi handlu elektronicznego w u usługach Microsoft Dynamics Lifecycle Services (LCS) podczas początkowego wdrażania nowej dzierżawy usług handlu elektronicznego.

## <a name="description"></a>opis

Podczas tworzenia składników portalu handlu elektronicznego w ramach procesu wdrażania nowej dzierżawy usługi handlu elektronicznego, która zawiera składnik Konstruktora witryn commerce, grupa zabezpieczeń Azure AD nie jest wyświetlana jako opcja w oknie dialogowym.

## <a name="resolution"></a>Rozdzielczość

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Inicjowanie obsługi witryny e-commerce z użytkownikiem w odpowiedniej dzierżawie

1. Przejdź do [portalu Azure](https://portal.azure.com/).
1. W dzierżawie, dla których został obsługiny projekt usługi LCS dla witryny e-commerce, postępuj zgodnie z instrukcjami w obszarze [Tworzenie grupy podstawowej i dodaj członków, używając Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).
1. Przejdź do usługi [LCS](https://lcs.dynamics.com/) i zaloguj się, używając konta, które ma tę samą dzierżawę co utworzona właśnie grupa zabezpieczeń Azure AD. Konto musi mieć dostęp do wyświetlania grupy zabezpieczeń Azure AD.
1. Aby skonfigurować witrynę e-commerce, należy wykonać kroki konfiguracji. Podczas inicjowania obsługi składników handlu elektronicznego grupa zabezpieczeń powinna być wyświetlana jako opcja w oknie dialogowym.

> [!NOTE]
> Aby mieć pewność, że pole w oknie dialogowym jest wypełnione listą grup zabezpieczeń, należy wybrać opcję **Enter** po wprowadzeniu nazwy utworzonej grupy zabezpieczeń Azure AD. W wynikach wyszukiwania zostaną wyświetlona lista wszystkich grup zabezpieczeń Azure AD, których nazwa rozpoczyna się wyszukiwany tekstem i do których użytkownik ma dostęp. Aby uzyskać szerszy wynik wyszukiwania, można użyć krótszych wyszukiwań.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Utwórz podstawową grupę i dodaj członków za pomocą Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Wdrażanie nowej dzierżawy handlu elektronicznego](../deploy-ecommerce-site.md)
