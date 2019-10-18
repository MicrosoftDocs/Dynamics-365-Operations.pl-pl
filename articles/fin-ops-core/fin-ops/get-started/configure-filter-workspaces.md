---
title: Konfigurowanie i filtrowanie obszarów roboczych
description: Ten artykuł zawiera omówienie metod konfigurowania i filtrowania obszarów roboczych.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace, HcmBenefitWorkspace, BudgetPlanningWorkspace, BusinessProcessGenericWorkspace, RetailCatalogManagementWorkspace, RetailCategoryAndProductWorkspace, RetailChannelManagementWorkspace, HcmCompensationWorkspace, CAMCostAccountingLedgerAdminWorkspace, CostAdminWorkspace, CostAnalysisWorkspace, CAMCostControlWorkspace, CustomerCollectionManagerWorkspace, CustomerInvoiceWorkspace, CustPaymentWorkspace, DataManagementWorkspace, DataValidationWorkspace, ERWorkspace, LedgerPeriodCloseProjectWorkspace, AssetWorkspace, GeneralJournalEntryWorkspace, VendVendorPortalInvoiceWorkspace, BudgetTrackingWorkspace, ReqCreatePlanWorkspace, BusinessProcessGenericOwnerWorkspace, SelfHealingWorkspace, WHSOutboundWorkMonitoringWorkspace, WHSWavePlanningWorkspace, PayrollWorkspace, HcmWorkforceWorkspace, RetailDiscountPricingWorkspace, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, EcoResProductVariantMaintainWorkspace, JmgShopSupervisorWorkspace, ProjProjectManagementWorkspace, VendVendorPortalWorkspace, PurchOrderMaintainWorkspace, PurchOrderProcessReceiptsWorkspace, HcmRecruitmentWorkspace, EcoResProductMaintainWorkspace, FMClerkWorkspace, OpResLifecycleManagementWorkspace, RetailITWorkspace, RetailChannelOperationsWorkspace, RetailStoreManagementWorkspace, SalesOrderProcessingWorkspace, SalesReturnWorkspace, SystemAdministrationWorkspaceForm, VendVendorRequestForQuotationsWorkspace, VendVendorProfileManagementWorkspace, VendInvoiceWorkspace, VendPaymentWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17491
ms.assetid: 541e6012-4680-4684-8494-e9b5ca4684ee
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 974980e1633e3f909b7c73964e811c351a042a7b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191208"
---
# <a name="configure-and-filter-workspaces"></a>Konfigurowanie i filtrowanie obszarów roboczych

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metod konfigurowania i filtrowania obszarów roboczych.

## <a name="configuring-a-workspace"></a>Konfiguracja obszaru roboczego

Można zmienić wygląd i zachowanie niektórych obszarów roboczych poprzez aktualizację ustawień mających zastosowanie do całego obszaru roboczego. Jeśli obszar roboczy można skonfigurować, w okienku akcji znajduje się przycisk z instrukcją, że jego kliknięcie pozwoli dokonać zmian w konfiguracji. Na przykład na poniższej ilustracji przycisk ma nazwę **Konfiguruj mój obszar roboczy**.

[![configure-and-filter-workspaces](./media/configure-and-filter-workspaces.png)](./media/configure-and-filter-workspaces.png)

Po kliknięciu przycisku pojawia się okno dialogowe, gdzie można zmodyfikować wstępnie zdefiniowane ustawienia obszaru roboczego. Konkretne ustawienia widoczne w tym oknie zależą od obszaru roboczego oraz od formantów i danych biznesowych dostępnych w obszarze.

[![configure-my-workspace](./media/configure-my-workspace.png)](./media/configure-my-workspace.png)

## <a name="filtering-a-workspace"></a>Filtrowanie obszaru roboczego

W wielu obszarach można filtrować wyświetlaną w nich zawartość. Dostępne formanty mogą pozwalać na filtrowanie całej zawartości obszaru lub tylko zawartości z określonej części obszaru. Filtry w obszarze roboczym mogą mieć postać pól wyszukiwania, kombi, tekstu w formacie dowolnym i innych. Jednak każdy typ filtru ma takie same skutki, jak opisano w poniższych sekcjach.

### <a name="workspace-wide-filters"></a>Filtr całego obszaru roboczego

Za pomocą filtra całego obszaru roboczego można filtrować cały obszar. Filtr całego obszaru roboczego znajduje się w lewym górnym rogu obszaru roboczego. Gdy zaznaczysz określoną wartość na liście rozwijanej, zawartość obszaru roboczego będzie filtrowana na podstawie tego wyboru.

[![workspace-filter](./media/workspace-filter.png)](./media/workspace-filter.png)

Jeśli klikniesz, aby otworzyć filtr, zobaczysz szereg opcji.

[![workspace-filter-expanded](./media/workspace-filter-expanded.png)](./media/workspace-filter-expanded.png)

Wybierz opcję, aby na jej podstawie przefiltrować obszar roboczy.

### <a name="workspace-section-filters"></a>Filtry sekcji obszaru roboczego

Jeśli poszczególne sekcje obszaru roboczego mają własne filtry, każdą sekcję można filtrować oddzielnie. Na ilustracji poniżej filtr (pole z napisem „Filtr”) jest przykładem filtra pola tekstu w formacie dowolnym.

[![workspace-section-filters](./media/workspace-section-filters.png)](./media/workspace-section-filters.png)

Podobnie jak w przypadku filtra całego obszaru roboczego, wybierz lub wprowadź wartość, aby według niej wyfiltrować zawartość sekcji.
