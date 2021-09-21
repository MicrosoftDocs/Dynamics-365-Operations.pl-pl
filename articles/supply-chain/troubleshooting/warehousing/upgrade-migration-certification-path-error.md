---
title: Błąd ścieżki certyfikacji podczas uaktualniania lub migrowania do systemu WMS
description: Jeśli aplikacja pokazuje błąd „Nie znaleziono kotwicy zaufania dla ścieżki certyfikacji” podczas uaktualniania lub migrowania do programu WMS, na tej stronie pokazano sposób rozwiązania problemu.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2cff41455268c43bdd99e285b9675f0c69be7de7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477282"
---
 # <a name="trust-anchor-for-certification-path-not-found-when-updating-and-migrating-to-wms"></a>Nie znaleziono kotwicy zaufania dla ścieżki certyfikacji podczas aktualizacji i migracji do WMS

## <a name="symptoms"></a>Objawy

Podczas uaktualniania i migracji do zaawansowanego zarządzania magazynem (WMS) aplikacja Warehouse Management wyświetlić następujący komunikat o błędzie:

> java.security.cert.certPathValidatorException: nie znaleziono kotwicy zaufania dla ścieżki certyfikacji.

## <a name="cause"></a>Powód

Taka sytuacja ma miejsce, ponieważ w środowiskach lokalnych nie ma zaufania do certyfikatów z podpisami własnymi w systemie Android 8+.

## <a name="resolution"></a>Rozwiązanie

Należy skorzystać z zewnętrznego (publicznego) urzędu certyfikującego (CA). Poprawka dotycząca tego problemu jest dostępna w wersji 1.9.0.0 aplikacji Warehouse Management. Aby uzyskać więcej informacji dotyczących tego problemu i sposobu jego rozwiązania, zobacz temat [Nie znaleziono kotwicy zaufania dla ścieżki certyfikacji podczas konfigurowania połączenia z aplikacją](certification-path-app-connection-error.md).
