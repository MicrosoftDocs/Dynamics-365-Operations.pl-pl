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
ms.openlocfilehash: f74389648034bf036ce48ac84b3421a8a340f105
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686661"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>Przerwy funkcjonalne między raportami wartości zapasów/wiekowania i ich wersji magazynowej

Funkcje [Magazyn raportów wiekowania zapasów](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage) i [Raport magazynu wartości zapasów](/dynamics365/supply-chain/cost-management/inventory-value-report-storage) umożliwiają Supply Chain Management wyświetlanie dużych ilości transakcji magazynowych. W każdym przypadku wyniki raportów są zapisywane w celu przeglądania i eksportowania, w przeciwieństwie do wersji tych raportów bez magazynowania. Jednak niektóre funkcje, które istnieją w wersjach tych raportów bez magazynu, nie istnieją w wersjach magazynu. Poniższe podsekcje podsumowują różnice i udostępniają rozwiązania.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Raporty magazynowania nie zawierają sum częściowych, nawet jeśli są włączone w układzie raportu

Sumy częściowe mogą powodować problemy podczas eksportowania wyniku, zwłaszcza jeśli użytkownicy zmienią sekwencję rekordów.

Aby sprawdzić sumy częściowe, można wyeksportować wyniki do Microsoft Excel. Alternatywnie, jeśli chcesz sprawdzić sumy częściowe w ramach Supply Chain Management, użyj funkcji [Zarządzanie funkcjamit](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview), aby włączyć funkcje *Kontrolka nowej siatki* i *Grupowania w siatkach*, które zapewniają znacznie bardziej elastyczny sposób wyświetlania sum częściowych dla dowolnej grupy według kolumny. Aby uzyskać dodatkowe informacje, zobacz [Zdolności siatki](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities).

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Raport magazynowania wartości zapasów nie obsługuje informacji o koncie księgowym

Bilans próbny można uruchomić, aby uzyskać saldo konta zapasów i porównać je z raportem **Magazynu wartości zapasów**.
