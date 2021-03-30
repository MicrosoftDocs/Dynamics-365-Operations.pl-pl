---
title: Rozwiązywanie problemów z uaktualnieniem i migracją do zaawansowanego zarządzania magazynem
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas uaktualnienia i migracji do zaawansowanego zarządzania magazynem.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f5bfee31ce27e919086f978fb3ff88ca61a65eba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208094"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a>Rozwiązywanie problemów z uaktualnieniem i migracją do zaawansowanego zarządzania magazynem

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas uaktualnienia i migracji do zaawansowanego zarządzania magazynem.

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a>Zgłaszany jest następujący komunikat o błędzie: „java.security.cert.certPathValidatorException: nie znaleziono kotwicy zaufania dla ścieżki certyfikacji”.

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie jest wyświetlany w aplikacji magazynu, ponieważ certyfikaty z podpisem własnym nie są zaufane w systemie Android 8 lub wyższym w środowiskach lokalnych.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Należy skorzystać z zewnętrznego (publicznego) urzędu certyfikującego (CA). Poprawka dotycząca tego problemu jest dostępna w wersji 1.9.0.0 aplikacji magazynu. Aby uzyskać więcej informacji o tym problemie i sposobach jego rozwiązywania, zapoznaj się z tematami [Rozwiązywanie problemów z połączeniem aplikacji magazynowej](troubleshoot-warehouse-app-connection.md).

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a>Jaki jest zatwierdzony proces przenoszenia się z magazynu podstawowego do magazynu zaawansowanego?

### <a name="issue-description"></a>Opis problemu

Obecnie jest używany moduł zarządzania zapasami/magazynem oraz korzystania z podstawowych funkcji magazynu, a użytkownik chce przejść do zaawansowanej wersji magazynowej w celu wykorzystania urządzeń przenośnych, grup czynności i pracy. Występują jednak problemy podczas próby dokonania tego przeniesienia. Na przykład nie można zmienić produktów w taki sposób, aby korzystały z wymiarów magazynowania (oddział, magazyn i lokalizacja), ponieważ produkty mają względem nich transakcje. W związku z tym należy poznać zatwierdzony proces przenoszenia się z magazynu podstawowego do magazynu zaawansowanego.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby uzyskać więcej informacji dotyczących procesu przenoszenia z magazynu podstawowego do magazynu zaawansowanego, należy zapoznać się z poniższymi wpisami blogu i dokumentacją:

- [Włącz proces zarządzania magazynowego dla istniejących pozycji i magazynów](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [Migracja Microsoft Dynamics AX WMS do nowej funkcji magazynu i transportu R3](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [Migracja pozycji WMSI/WMS2](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [Uaktualnienie zarządzania magazynem z Microsoft Dynamics AX 2012 do Supply Chain Management](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]