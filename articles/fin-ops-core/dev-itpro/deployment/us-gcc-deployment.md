---
title: Dynamics 365 Finance i Dynamics 365 Supply Chain Management w amerykańskiej Government Community Cloud (GCC)
description: Ten temat zawiera informacje dotyczące produktów Microsoft Dynamics 365 US Government instytucji rządowych, które są dostępne dla kwalifikujących się jednostek rządowych i prywatnych.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 17702ada5bf75a44652e194c2555a83e76e7a36b
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817447"
---
# <a name="dynamics-365-finance-and-dynamics-365-supply-chain-management-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance i Dynamics 365 Supply Chain Management w amerykańskiej Government Community Cloud (GCC)

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Wybrane produkty Microsoft Dynamics 365 Stany Zjednoczone (USA) są dostępne kwalifikującym się jednostkom rządowym i prywatnym. Jednostki są ograniczone do następujących typów:

- Amerykańskie federalne, stanowe, lokalne, plemienne i terytorialne jednostki rządowe
- Podmioty prywatne, które korzystają z programu Dynamics 365 US Government w celu świadczenia rozwiązań jednostkom rządowym lub kwalifikującym się członkom społeczności użytkowników chmury
- Podmioty prywatne, których dane klientów podlegają przepisom rządowym — usługa Dynamics 365 US Government jest odpowiednia do spełnienia wymogów prawnych

Aby uzyskać więcej informacji, zobacz temat [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Onboarding

Aby zakończyć wstępne dołączanie do projektu implementacji w u usługach Microsoft Dynamics Lifecycle Services (LCS), postępuj zgodnie z instrukcjami w tej instrukcji [Przygotowanie do przeprowadzenia projektu implementacji](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). Nie należy jednak używać łącza do publicznej usługi LCS dostarczonej w tych instrukcjach. Zamiast tego możesz użyć następującego adresu URL, aby otworzyć usługę LCS dla US Government Community Cloud (GCC): <https://gov.lcs.microsoftdynamics.us>.

Po zakończeniu początkowego dołączania postępuj zgodnie z instrukcjami [Dołączania do projektu](../lifecycle-services/project-onboarding.md). Po raz kolejny użyj usługi [LCS dla GCC](https://gov.lcs.microsoftdynamics.us) zamiast publicznej usługi LCS.

## <a name="environment-deployment"></a>Wdrażanie środowiska

Po zakończeniu dołączania projektu możesz przejrzeć dodatkowe możliwości usługi LCS opisane w usługach [Lifecycle Services (LCS) dla odbiorców aplikacji Finance and Operations](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). Następnie przejdź do wdrożenia środowiska.

- Aby wdrożyć środowiska zarządzane przez firmę Microsoft za pomocą usługi LCS, postępuj zgodnie z instrukcjami w użytą usługę [Lifecycle Services (LCS) dla odbiorców aplikacji Finance and Operations](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- Dla środowisk hostowanych w chmurze zobacz temat [Wdrażanie środowisk programistycznych i uzyskiwanie do nich dostępu](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md). Musisz także zakończyć proces dołączania Menedżera zasobów dla łączników, jak opisano w temacie [Zakończenie procesu dołączania usługi Azure Resource Manager dla projektów usługi Lifecycle Services instytucji rządowych USA](arm-onbarding-us-goverment.md).

> [!NOTE]
> W przypadku projektów LCS instytucji rządowych USA obsługiwane są tylko subskrypcje Azure specyficzne dla usługi Azure Government.

## <a name="features-that-arent-available"></a>Funkcje, które nie są dostępne

Niektóre funkcje nie będą dostępne do wdrożenia w GCC lub nie będą dostępne do użycia z usługą Dynamics 365 w GCC. Na przykład usługi Azure DevOps Services nie będą dostępne w GCC. Można jednak korzystać z usług lokalnych Azure DevOps lub publicznych Azure DevOps. Aby uzyskać szczegółowe informacje o dostępności funkcji, zobacz temat [Dostępność funkcji dla instytucji rządowych (USA) dotyczących aplikacji biznesowych](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Czy Dynamics 365 Finance i Dynamics 365 Supply Chain Management są obsługiwane w GCC-High?

Nie Dynamics 365 Finance i Dynamics 365 Supply Chain Management są obsługiwane tylko w GCC.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Czy mogę używać publicznej usługi Azure DevOps z rozwiązaniem Finance i Supply Chain Management w GCC?

Tak, można korzystać z usług publicznych Azure DevOps, jeśli nie masz wymagań dotyczących rozwiązania, które jest certyfikowane przez program Federal Risk and Authorization Management Program (FEDRAMP). Można również użyć usługi Azure DevOps Server.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Czy można wdrożyć 1-warstwowe środowisko hostowane w chmurze w subskrypcji usługi Azure Commercial?

Nie W usłudze [LCS dla GCC](https://gov.lcs.microsoftdynamics.us) musisz użyć subskrypcji systemu Azure Government, aby wdrożyć środowisko hostowane w chmurze.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>Co zrobić, jeśli jest potrzebny pakiet z biblioteki udostępnionych zasobów, ale nie jest dostępny w usłudze LCS dla GCC?

Możesz pobrać ten sam pakiet z biblioteki udostępnionych zasobów w [publicznej usłudze LCS](https://lcs.dynamics.com). Pakiet może także być pobrany przez partnera.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>Czy narzędzie uaktualniania kodu jest dostępne w GCC?

Nie, narzędzie uaktualniania kodu nie jest obecnie dostępne w GCC. Można jednak utworzyć projekt prospektu w [publicznej usłudze LCS](https://lcs.dynamics.com) i użyć narzędzia uaktualniania kodu. Pamiętaj, że nie możesz wdrażać środowisk w projektach prospektów.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>Czy mój partner może otworzyć bilet pomocy technicznej w moich imieniu?

Tak. Jeśli jednak partner używa tożsamości spoza GCC, bilet pomocy technicznej zostanie skierowany do publicznej kolejki pomocy technicznej. Zalecane jest otwieranie biletów pomocy technicznej za pomocą uprawnienia GCC odbiorcy w usłudze LCS.

## <a name="see-also"></a>Informacje dodatkowe

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [Dostępność funkcji amerykańskich instytucji rządowych dla aplikacji biznesowych](https://aka.ms/BAPFunctionalParity).
- [Przewodnik użytkownika usługi Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Omówienie wdrażania w chmurze](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
