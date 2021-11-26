---
title: Włącz odnośniki danych główne do konfiguracji obliczania podatku
description: W tym temacie wyjaśniono, jak skonfigurować i włączyć funkcję wyszukiwania danych podstawowych obliczania podatku.
author: kai-cloud
ms.date: 11/03/2021
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
ms.openlocfilehash: dafeac01aaff62cbbd5ce6ecb0af0ef111f513b2
ms.sourcegitcommit: 76fe020f9c5f4e5cc2e93f5ccb3b040f12b0363e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2021
ms.locfileid: "7749517"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Włącz odnośniki danych główne do konfiguracji obliczania podatku 

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować i włączyć funkcję wyszukiwania danych podstawowych obliczania podatku. Dostępna jest lista rozwijana, na podstawie których można wybrać wartości w konfiguracji obliczania podatku dla takich pól, jak **Konto dostawcy**, **Kod towaru** czy **Termin dostawy**. Te wartości pochodzą ze połączonego środowiska Microsoft Dynamics 365 Finance, używając źródła danych Microsoft Dataverse.

1. Konfigurowanie integracji platformy Microsoft Power Platform w Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Integracja Microsoft Power Platform - Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Po ukończeniu tego kroku nazwa środowiska Microsoft Power Platform pojawi się w sekcji **Integracja Power Platform**.
2. Przejdź do [centrum administracyjnego Microsoft Power Platform](https://admin.powerplatform.microsoft.com/environments) i wybierz nazwę środowiska. Podano adres URL środowiska.
3. Konfiguracja Dynamics 365 Finance i Dataverse. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie rozwiązania encji wirtualnej](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) oraz [Uwierzytelnianie i autoryzacja](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
4. Należy skonfigurować następujące encje: Aby uzyskać więcej informacji, zobacz [Włączanie wirtualnych encji Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

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

5. Włącz Regulatory Configuration Service (RCS). Otwórz i przejdź do obszaru roboczego **Zarządzanie funkcjami** i włącz następujące funkcje:

    - Obsługa elektronicznych źródeł danych raportowania Dataverse
    - Obsługa źródeł danych usługi podatkowej Dataverse
    - Funkcje globalizacji

6. Zaloguj się do RCS przy użyciu konta administratora dzierżawy.
7. Przejdź do **Raportowanie elektroniczne** > **Połączone aplikacje**. 
8. Wybierz pozycję **Nowy**, aby dodać rekord, i wprowadź następujące informacje o polu. 

    - W polu **Nazwa** wprowadź nazwę.
    - W polu **Typ** zaznacz opcję **Dataverse**.
    - W polu **Aplikacja** wprowadź adres URL Dataverse.
    - W polu **Dzierżawa** wprowadź dzierżawę.
    - W polu **Niestandardowy adres URL** wprowadź adres URL Dataverse i dołącz do niego „/api/data/v9.1”.

9. Wybierz pozycję **Sprawdź połączenie** i zakończ proces połączania. 

    [![Przycisk Sprawdź połączenie.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. Przejdź do **Raportowanie elektroniczne** > **Konfiguracje podatku** i importuj konfiguracje podatku z [Konfiguracje podatku](https://go.microsoft.com/fwlink/?linkid=2158352).

    [![Strona Konfiguracje podatku, Drzewo modelu danych podatkowych.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. Przejdź do **Mapowanie modelu dokumentu podlegającego opodatkowaniu** lub **Mapowania modelu Dataverse**, jeśli używasz konfiguracji firmy Microsoft, a w polu **Połączona aplikacja** wybierz rekord utworzony w kroku 7.
12. Ustaw opcję **Domyślnego mapowania modelu** jako **Tak**.

    [![Strona mapowania modelu.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
