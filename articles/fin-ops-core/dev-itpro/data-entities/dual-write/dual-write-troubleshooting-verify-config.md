---
title: Sprawdzanie poprawności konfiguracji podwójnego zapisu w aplikacjach Finanse i Działania i usłudze Dataverse
description: W tym artykule wyjaśniono, jak można określić, czy podwójny zapis zostały skonfigurowany w aplikacjach finansowych i operacyjnych oraz usłudze Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 7131e6c2c4ca4d9c6bb84ad74bf425faf28bd92c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884467"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Sprawdzanie poprawności konfiguracji podwójnego zapisu w aplikacjach Finanse i Działania i usłudze Dataverse

[!include [banner](../../includes/banner.md)]





Ten artykuł zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji podwójnego zapisu między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse. W tym temacie wyjaśniono, jak można określić, czy podwójne zapisywanie jest skonfigurowane w aplikacjach Finanse i Działania i w Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Sprawdzanie poprawności konfiguracji podwójnego zapisu w aplikacjach Finanse i Działania

Aby określić, czy błędy widoczne podczas próby zapisania wierszy do aktualizacji pochodzą z podwójnego zapisu, należy najpierw sprawdzić, czy skonfigurowano podwójny zapis.

+ Jeśli masz uprawnienia administratora w aplikacji Finanse i Działania, przejdź do obszaru **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Podwójnego zapisu**. Jeśli są widoczne szczegóły połączonych środowisk i lista uruchomionych map tabeli, skonfigurowano podwójny zapis.

    ![Sprawdzanie połączenia aplikacji Finanse i Działania, gdy użytkownik nie ma uprawnienia administratora.](media/verify_fin_ops_1.png)

+ Jeśli nie masz uprawnień administratora, zostanie wyświetlony komunikat o błędzie, *Nie można zapisać danych do jednostki nazwa jednostki.\<entity name\>*. W przykładzie na poniższej ilustracji nie można utworzyć wiersza odbiorcy w aplikacji Finanse i Działania, ponieważ skonfigurowano podwójny zapis, ale dane dotyczące grupy odbiorców i warunków płatności nie istnieją w Dataverse.

    ![Sprawdzanie połączenia aplikacji Finanse i Działania, gdy użytkownik nie ma uprawnienia administratora.](media/verify_fin_ops_2.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w aplikacjach Finanse i Działania, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Sprawdź, czy w Dataverse jest skonfigurowany tryb podwójnego zapisu

Jeśli w formularzu są tworzone dane, to w przypadku wyświetlenia kolumny **Firma** na stronach w Dataverse zostanie skonfigurowany podwójny zapis.

![Trwa weryfikowanie połączenia Dataverse.](media/verify_cds.png)

Aby uzyskać informacje dotyczące rozwiązywania problemów podczas tworzenia danych w Dataverse, należy zapoznać się z [Rozwiązywanie problemów z synchronizacją na żywo](dual-write-troubleshooting-live-sync.md).

Aby uzyskać informacje o wyświetlaniu szczegółów błędów w przypadku wystąpienia jakichkolwiek błędów podczas tworzenia danych w Dataverse, zobacz temat [Włączanie i wyświetlanie informacji o wtyczkach w Dataverse w celu wyświetlenia szczegółów błędu](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]