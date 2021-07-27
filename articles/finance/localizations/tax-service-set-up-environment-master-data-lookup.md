---
title: Ustawianie środowiska wyszukiwania danych głównych
description: W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 348643d7213b8c053d6a15b4b716a3ce75ba2fa2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346381"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Ustawianie środowiska wyszukiwania danych głównych

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować środowisko do korzystania z funkcji wyszukiwania danych podstawowych obliczania podatku.

1. Konfigurowanie integracji platformy zasilania w Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Integracja Microsoft Power Platform - Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Konfiguracja Dynamics 365 Finance i Microsoft Dataverse. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie rozwiązania](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) oraz [Uwierzytelnianie i autoryzacja](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Należy skonfigurować następujące encje: Aby uzyskać więcej informacji, zobacz [Włączanie wirtualnych encji](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).
      - CompanyInfoEntity
      - CurrencyEntity
      - CustCustomerV3Entity
      - DeliveryTermsEntity
      - EcoResProductCategoryEntity
      - EcoResReleasedProductV2Entity
      - LogisticsAddressCityEntity
      - LogisticsAddressCountryRegionTranslationEntity
      - LogisticsAddressStateEntity
      - PurchProcurementChargeCDSEntity
      - SalesChargeCDSEntity
      - TaxGroupEntity
      - TaxItemGroupHeadingEntity
      - VendVendorV2Entity
4. Skonfiguruj usługę Dynamics 365 Regulatory Configuration Service (RCS). 
5. Utwórz zgłoszenie serwisowe dla firmy Microsoft, aby umożliwić wyświetlanie następujących funkcji:

      - ERCdsFeatura
      - TaxServiceCDSFeatura

6. Przejdź do obszaru roboczego **Zarządzanie funkcjami** i włącz następujące funkcje:

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

   [![Przycisk Sprawdź połączenie.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Przejdź do **Raportowanie elektroniczne** > **Konfiguracje podatku** i importuj konfiguracje podatku z [Konfiguracje podatku](https://go.microsoft.com/fwlink/?linkid=2158352).

   [![Strona Konfiguracje podatku, Drzewo modelu danych podatkowych.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Przejdź do **Mapowanie modelu dokumentu podlegającego opodatkowaniu** lub **Mapowania modelu Dataverse**, jeśli używasz konfiguracji firmy Microsoft, a w polu **Połączona aplikacja** wybierz rekord utworzony w kroku 7.
11. Ustaw opcję **Domyślnego mapowania modelu** jako **Tak**.

   [![Strona mapowania modelu.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
