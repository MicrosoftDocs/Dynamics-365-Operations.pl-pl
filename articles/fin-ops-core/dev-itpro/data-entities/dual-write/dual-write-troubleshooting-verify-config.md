---
title: Sprawdzanie poprawności konfiguracji podwójnego zapisu w aplikacjach finansowych i operacyjnych oraz usłudze Dataverse
description: W tym artykule wyjaśniono, jak można określić, czy podwójny zapis zostały skonfigurowany w aplikacjach finansowych i operacyjnych oraz usłudze Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 4ff7821fce661f174f57fb45667d4ceb3cfcede9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289399"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Sprawdzanie poprawności konfiguracji podwójnego zapisu w aplikacjach finansowych i operacyjnych oraz usłudze Dataverse

[!include [banner](../../includes/banner.md)]





Ten artykuł zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse. W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach finansowych i operacyjnych i w Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Sprawdzanie poprawności konfiguracji podwójnego zapisu w aplikacjach finansowych i operacyjnych

Aby określić, czy błędy widoczne podczas próby zapisania wierszy do aktualizacji pochodzą z podwójnego zapisu, należy najpierw sprawdzić, czy skonfigurowano podwójny zapis.

+ Jeśli masz uprawnienia administratora w aplikacjach finansowych i operacyjnych, przejdź do obszaru **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Podwójnego zapisu**. Jeśli są widoczne szczegóły połączonych środowisk i lista uruchomionych map tabeli, skonfigurowano podwójny zapis.

    ![Sprawdzanie połączenia aplikacji finansowych i operacyjnych, gdy użytkownik nie ma uprawnienia administratora.](media/verify_fin_ops_1.png)

+ Jeśli nie masz uprawnień administratora, zostanie wyświetlony komunikat o błędzie, *Nie można zapisać danych do jednostki nazwa jednostki.\<entity name\>*. W przykładzie na poniższej ilustracji nie można utworzyć wiersza odbiorcy w aplikacjach finansowych i operacyjnych, ponieważ skonfigurowano podwójny zapis, ale dane dotyczące grupy odbiorców i warunków płatności nie istnieją w Dataverse.

    ![Sprawdzanie połączenia aplikacji finansowych i operacyjnych, gdy użytkownik nie ma uprawnienia administratora.](media/verify_fin_ops_2.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w aplikacjach finansowych i operacyjnych, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Sprawdź, czy w Dataverse jest skonfigurowany tryb podwójnego zapisu

Jeśli w formularzu są tworzone dane, to w przypadku wyświetlenia kolumny **Firma** na stronach w Dataverse zostanie skonfigurowany podwójny zapis.

![Trwa weryfikowanie połączenia Dataverse.](media/verify_cds.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w Dataverse, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

Aby uzyskać informacje o wyświetlaniu szczegółów błędów w przypadku wystąpienia jakichkolwiek błędów podczas tworzenia danych w Dataverse, zobacz temat [Włączanie i wyświetlanie informacji o wtyczkach w Dataverse w celu wyświetlenia szczegółów błędu](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
