---
title: Odinstaluj rozwiązania do aranżacji aplikacji z podwójnym zapisem
description: W tym artykule opisano, jak odinstalować rozwiązania do aranżacji aplikacji z podwójnym zapisem.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: fd9dc98ec1323a2ef262a330a400a6bd3833e554
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288739"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Odinstaluj rozwiązania do aranżacji aplikacji z podwójnym zapisem

[!include [banner](../../includes/banner.md)]

W tym artykule opisano, jak odinstalować rozwiązania do aranżacji aplikacji z podwójnym zapisem.

Niektórzy klienci nieumyślnie instalują pakiet orkiestracji aplikacji do podwójnego zapisu, który instaluje wiele rozwiązań w swoim środowisku Microsoft Dataverse. Instalacja dodatkowych rozwiązań w pakiecie może spowodować nieoczekiwane i niepożądane problemy.

Aby rozwiązać problemy związane z instalacją pakietu aranżacji aplikacji podwójnego zapisu, odinstaluj niechciane rozwiązania podwójnego zapisu w następującej kolejności:

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (jeśli występuje)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (Aby odinstalować to rozwiązanie, należy otworzyć bilet pomocy technicznej w rozwiązaniu Microsoft)
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

Jeśli zainstalowano oprogramowanie party i globalna książka adresowa, odinstaluj rozwiązania w następującej kolejności:

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. Strona
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
