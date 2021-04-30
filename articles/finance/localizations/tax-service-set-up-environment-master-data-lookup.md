---
title: Ustawianie środowiska wyszukiwania danych głównych
description: W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.
author: kai-cloud
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869091"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Ustawianie środowiska wyszukiwania danych głównych

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.

1. Konfigurowanie integracji platformy zasilania w Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Integracja Microsoft Power Platform - Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Konfiguracja Dynamics 365 Finance i Microsoft Dataverse. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie rozwiązania](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) oraz [Uwierzytelnianie i autoryzacja](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Zaimportuj *rozwiązanie jednostki wirtualnej usługi podatkowej* z [jednostki wirtualnej Usługi podatkowej](https://go.microsoft.com/fwlink/?linkid=2158160).
4. Skonfiguruj usługę Dynamics 365 Regulatory Configuration Service (RCS). 
5. Utwórz zgłoszenie serwisowe dla firmy Microsoft, aby umożliwić wyświetlanie następujących funkcji:

      - ERCdsFeatura
      - TaxServiceCDSFeatura

6. W Finance przejdź do obszaru roboczego **Zarządzanie funkcjami** i włącz następujące funkcje:

      - (Wersja zapoznawcza) Obsługa elektronicznych źródeł danych raportowania Dataverse
      - (Wersja zapoznawcza) Obsługa źródeł danych usługi podatkowej Dataverse
      - (Wersja zapoznawcza) Funkcje globalizacji

5. Zaloguj się do RCS przy użyciu konta administratora dzierżawy.
6. Przejdź do **Raportowanie elektroniczne** > **Połączone aplikacje**. 
7. Wybierz pozycję **Nowy**, aby dodać rekord, i wprowadź następujące informacje o polu. 

   - W polu **Nazwa** wprowadź nazwę.
   - W polu **Typ** zaznacz opcję **Dataverse**.
   - W polu **Aplikacja** wprowadź adres URL Dataverse.
   - W polu **Dzierżawa** wprowadź dzierżawę.
   - W polu **Niestandardowy adres URL** wprowadź adres URL Dataverse i dołącz do niego „/api/data/v9.1”.

8. Wybierz pozycję **Sprawdź połączenie** i zakończ proces połączania. 

   [![Przycisk Sprawdź połączenie](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Przejdź do **Raportowanie elektroniczne** > **Konfiguracje podatku** i importuj konfiguracje podatku z [Konfiguracje podatku](https://go.microsoft.com/fwlink/?linkid=2158352).

   [![Strona Konfiguracje podatku, Drzewo modelu danych podatkowych](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Przejdź do **Mapowanie modelu dokumentu podlegającego opodatkowaniu** lub **Mapowania modelu Dataverse**, jeśli używasz konfiguracji firmy Microsoft, a w polu **Połączona aplikacja** wybierz rekord utworzony w kroku 7.
11. Ustaw opcję **Domyślnego mapowania modelu** jako **Tak**.

   [![Strona mapowania modelu](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
