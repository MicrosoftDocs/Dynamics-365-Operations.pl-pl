---
title: Sprawdź, czy w aplikacjach Finance and Operations i Common Data Service jest skonfigurowany tryb podwójnego zapisu
description: W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2ddac76871a3ac574a1edcb5446be6c64e5e4682
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997237"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a>Sprawdź, czy w aplikacjach Finance and Operations i Common Data Service jest skonfigurowany tryb podwójnego zapisu

[!include [banner](../../includes/banner.md)]



Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service. W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Common Data Service.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Sprawdź, czy w aplikacji Finance and Operations jest skonfigurowany tryb podwójnego zapisu

Aby określić, czy błędy widoczne podczas próby zapisania rekordów do aktualizacji pochodzą z podwójnego zapisu, należy najpierw sprawdzić, czy skonfigurowano podwójny zapis.

+ Jeśli masz uprawnienia administratora w aplikacji Finance and Operations, przejdź do obszaru **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Podwójnego zapisu**. Jeśli są widoczne szczegóły połączonych środowisk i lista uruchomionych map jednostek, skonfigurowano podwójny zapis.

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik ma uprawnienia administratora](media/verify_fin_ops_1.png)

+ Jeśli nie masz uprawnień administratora, zostanie wyświetlony komunikat o błędzie, *Nie można zapisać danych do jednostki nazwa jednostki.\<entity name\>*. W przykładzie na poniższej ilustracji nie można utworzyć rekordu odbiorcy w aplikacji Finance and Operations, ponieważ skonfigurowano podwójny zapis, ale dane dotyczące grupy odbiorców i warunków płatności nie istnieją w Common Data Service.

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik nie ma uprawnienia administratora](media/verify_fin_ops_2.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w aplikacjach Finance and Operations, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a>Sprawdź, czy w Common Data Service jest skonfigurowany tryb podwójnego zapisu

Jeśli w formularzu są tworzone dane, to w przypadku wyświetlenia pola **Firma** na stronach w Common Data Service zostanie skonfigurowany podwójny zapis.

![Trwa weryfikowanie połączenia Common Data Service](media/verify_cds.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w Common Data Service, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

Aby uzyskać informacje o wyświetlaniu szczegółów błędów w przypadku wystąpienia jakichkolwiek błędów podczas tworzenia danych w Common Data Service, zobacz temat [Włączanie i wyświetlanie informacji o wtyczkach w Common Data Service w celu wyświetlenia szczegółów błędu](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).
