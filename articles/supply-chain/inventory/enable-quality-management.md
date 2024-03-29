---
title: Włączanie zarządzania kontrolą jakości i niezgodnością
description: Ten artykuł zawiera omówienie procesu konfigurowania funkcji zarządzania kontrolą jakości i niezgodnościami w systemie Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66229e3692e87f774c553eae955794330602598c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874051"
---
# <a name="enable-quality-and-nonconformance-management"></a>Włączanie zarządzania kontrolą jakości i niezgodnością

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie procesu konfigurowania funkcji zarządzania kontrolą jakości i niezgodnościami w systemie Microsoft Dynamics 365 Supply Chain Management.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>Włączanie zarządzania kontrolą jakości i niezgodnością

Aby włączyć zarządzanie kontrolą jakości w systemie, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Parametry modułu Zarządzanie zapasami i magazynem**.
1. Na karcie **Zarządzanie kontrolą jakości** ustaw opcję **Użyj zarządzania kontrolą jakości** na wartość *Tak*.
1. W polu **Stawka godzinowa** wpisz stawkę godzinową pracy w walucie lokalnej. Stawka godzinowa używana jest do obliczania kosztów operacji związanych z niezgodnością. Stawka godzinowa i obliczone koszty dostarczają informacji pomocniczych o niezgodności. Nie mają one styczności z innymi funkcjami.
1. Wybierz opcję **Konfigurowanie raportu**.
1. Dodaj nowe wiersze dla różnych typów raportów i wybierz typ dokumentu, który ma być używany z poszczególnymi raportami.
1. Zamknij stronę.
1. Zamknij stronę.

## <a name="quality-management-configuration-process"></a>Proces konfigurowania zarządzania kontrolą jakości

Aby można było rozpocząć korzystanie z funkcji zarządzania kontrolą jakości i generować zlecenia kontroli jakości, należy skonfigurować system i wymagania wstępne. Poniżej znajduje się lista kroków wymaganych do skonfigurowania zarządzania kontrolą jakości.

1. [Włącz zarządzania kontrolą jakości i niezgodnością](#enable-qm).
1. Opcjonalnie: [Skonfiguruj przyrządy testowe](quality-test-instruments.md).
1. [Skonfiguruj testy](quality-tests.md).
1. [Skonfiguruj zmienne i wyniki testów](quality-test-variables.md).
1. [Skonfiguruj grupy testowe](quality-test-groups.md).
1. Opcjonalnie: [Skonfiguruj grupy jakości i łącza do produktów](quality-groups.md).
1. Opcjonalnie: [Skonfiguruj skojarzenia jakości](quality-associations.md).

Po zakończeniu konfiguracji można rozpocząć tworzenie i przetwarzanie zleceń kontroli jakości. Aby uzyskać więcej informacji na temat tworzenia zleceń kontroli jakości i korzystania z nich, zobacz [Zlecenia kontroli jakości](quality-orders.md).

## <a name="nonconformance-management-configuration-process"></a>Proces konfigurowania zarządzania niezgodnościami

Aby można było rozpocząć korzystanie z funkcji zarządzania niezgodnościami i generować niezgodności, należy skonfigurować system i wymagania wstępne. Poniżej znajduje się lista kroków wymaganych do skonfigurowania zarządzania niezgodnościami.

1. [Włącz zarządzania kontrolą jakości i niezgodnością](#enable-qm).
1. [Skonfiguruj pracowników odpowiedzialnych za zatwierdzanie niezgodności](quality-responsible-workers.md).
1. [Skonfiguruj typy problemów](quality-problem-types.md).
1. [Skonfiguruj strefy kwarantanny](quality-quarantine-zones.md).
1. [Skonfiguruj typów diagnostyczne](quality-diagnostic-types.md).
1. [Skonfiguruj operacje](quality-operations.md).
1. Opcjonalnie: [Skonfiguruj opłaty związane z kontrolą jakości](quality-charges.md).

Po zakończeniu konfiguracji można rozpocząć tworzenie i przetwarzanie niezgodności. Aby uzyskać więcej informacji na temat tworzenia niezgodności i korzystania z nich [Tworzenie i przetwarzanie niezgodności](tasks/create-process-non-conformance.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie zarządzanie jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
