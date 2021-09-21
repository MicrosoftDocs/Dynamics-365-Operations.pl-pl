---
title: Przerwy funkcjonalne między raportami wartości zapasów/wiekowania i ich wersji magazynowej
description: Przerwy funkcjonalne między raportami wartości zapasów/wiekowania i ich wersji magazynowej
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a72e2d32e755e137cebbc0bf7afb0bed08fb93f2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477332"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>Przerwy funkcjonalne między raportami wartości zapasów/wiekowania i ich wersji magazynowej

Funkcje [Magazyn raportów wiekowania zapasów](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage.md) i [Raport magazynu wartości zapasów](/dynamics365/supply-chain/cost-management/inventory-value-report-storage.md) umożliwiają Supply Chain Management wyświetlanie dużych ilości transakcji magazynowych. W każdym przypadku wyniki raportów są zapisywane w celu przeglądania i eksportowania, w przeciwieństwie do wersji tych raportów bez magazynowania. Jednak niektóre funkcje, które istnieją w wersjach tych raportów bez magazynu, nie istnieją w wersjach magazynu. Poniższe podsekcje podsumowują różnice i udostępniają rozwiązania.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Raporty magazynowania nie zawierają sum częściowych, nawet jeśli są włączone w układzie raportu

Sumy częściowe mogą powodować problemy podczas eksportowania wyniku, zwłaszcza jeśli użytkownicy zmienią sekwencję rekordów.

Aby sprawdzić sumy częściowe, można wyeksportować wyniki do Microsoft Excel. Alternatywnie, jeśli chcesz sprawdzić sumy częściowe w ramach Supply Chain Management, użyj funkcji [Zarządzanie funkcjamit](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby włączyć funkcje *Kontrolka nowej siatki* i *Grupowania w siatkach*, które zapewniają znacznie bardziej elastyczny sposób wyświetlania sum częściowych dla dowolnej grupy według kolumny. Aby uzyskać dodatkowe informacje, zobacz [Zdolności siatki](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities.md).

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Raport magazynowania wartości zapasów nie obsługuje informacji o koncie księgowym

Bilans próbny można uruchomić, aby uzyskać saldo konta zapasów i porównać je z raportem **Magazynu wartości zapasów**.
