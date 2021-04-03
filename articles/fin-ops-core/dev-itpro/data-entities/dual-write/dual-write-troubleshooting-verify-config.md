---
title: Weryfikowanie konfiguracji podwójnego zapisu w aplikacjach Finance and Operations i Dataverse
description: W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0a1da32713f3d4d19b4d343c5b67b416a6c4ffbb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566772"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Weryfikowanie konfiguracji podwójnego zapisu w aplikacjach Finance and Operations i Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse. W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finance and Operations i w Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Sprawdź, czy w aplikacji Finance and Operations jest skonfigurowany tryb podwójnego zapisu

Aby określić, czy błędy widoczne podczas próby zapisania wierszy do aktualizacji pochodzą z podwójnego zapisu, należy najpierw sprawdzić, czy skonfigurowano podwójny zapis.

+ Jeśli masz uprawnienia administratora w aplikacji Finance and Operations, przejdź do obszaru **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Podwójnego zapisu**. Jeśli są widoczne szczegóły połączonych środowisk i lista uruchomionych map tabeli, skonfigurowano podwójny zapis.

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik ma uprawnienia administratora](media/verify_fin_ops_1.png)

+ Jeśli nie masz uprawnień administratora, zostanie wyświetlony komunikat o błędzie, *Nie można zapisać danych do jednostki nazwa jednostki.\<entity name\>*. W przykładzie na poniższej ilustracji nie można utworzyć wiersza odbiorcy w aplikacji Finance and Operations, ponieważ skonfigurowano podwójny zapis, ale dane dotyczące grupy odbiorców i warunków płatności nie istnieją w Dataverse.

    ![Sprawdzanie połączenia aplikacji Finance and Operations, gdy użytkownik nie ma uprawnienia administratora](media/verify_fin_ops_2.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w aplikacjach Finance and Operations, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Sprawdź, czy w Dataverse jest skonfigurowany tryb podwójnego zapisu

Jeśli w formularzu są tworzone dane, to w przypadku wyświetlenia kolumny **Firma** na stronach w Dataverse zostanie skonfigurowany podwójny zapis.

![Trwa weryfikowanie połączenia Dataverse](media/verify_cds.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w Dataverse, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

Aby uzyskać informacje o wyświetlaniu szczegółów błędów w przypadku wystąpienia jakichkolwiek błędów podczas tworzenia danych w Dataverse, zobacz temat [Włączanie i wyświetlanie informacji o wtyczkach w Dataverse w celu wyświetlenia szczegółów błędu](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]