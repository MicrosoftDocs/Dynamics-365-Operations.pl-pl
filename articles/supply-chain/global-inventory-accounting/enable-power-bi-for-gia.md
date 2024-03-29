---
title: Włączanie usługi Power BI dla Globalnego księgowania zapasów
description: W tym artykule opisano sposób włączenia w Microsoft Power BI funkcji Globalnego księgowanie zapasów.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b1edfa314d2810bff4cf02762aeb66bee801858d
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135437"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Włączanie usługi Power BI dla Globalnego księgowania zapasów

[!include [banner](../includes/banner.md)]

Kafelki, pulpity nawigacyjne i raporty [PowerBI.com](https://powerbi.com/) można przypiąć do obszaru roboczego aplikacji Microsoft Dynamics 365.

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można włączyć raportowanie w Power BI, muszą być spełnione następujące warunki wstępne:

- Musisz być administratorem systemu w aplikacji Dynamics 365.
- Musisz mieć konto [PowerBI.com](https://powerbi.com/).
- Musisz mieć przynajmniej jeden pulpit i jeden raport na swoim koncie Power BI.
- Musisz być administratorem swojego konta Azure Active Directory (Azure AD).
- Domena Azure AD musi być taką samą domeną, jak używana dla konta [PowerBI.com](https://powerbi.com/).

## <a name="setup"></a>Konfiguracja

Aby skonfigurować integrację z Power BI, wykonaj poniższe kroki.

1. Zaloguj się do [Microsoft Dynamics LifeCycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Przejdź do **biblioteki udostępnionych aktywów**, wybierz **model raportu Power BI** jako typ składnika aktywów i pobierz pakiet **Globalne księgowanie zapasów**. 
1. Zaloguj się do [PowerBI.com](https://app.powerbi.com/) i wgraj plik raportu **Globalnego księgowania zapasów** Power BI, aby wykonać następujące kroki:

    1. Wybierz pozycję **Nowy**.
    1. Wybierz **Prześlij plik**.
    1. Wybierz plik raportu **Globalnego księgowanie zapasów** Power BI.

1. Aby skonfigurować raport **Globalnego księgowanie zapasów** Power BI, należy wykonać następujące kroki:

    1. Przejdź do obszaru roboczego **Mój obszar roboczy**, znajdź zestaw danych dla Globalnego księgowania zapasów, a następnie w menu **Opcje** wybierz polecenie **Ustawienia**.
    1. W opcji **Ustawienia globalnego księgowania zapasów** rozwiń pozycję **Parametry** i w razie potrzeby zaktualizuj wszystkie parametry. W szczególności należy sprawdzić następujące ustawienia:
        1. Zastąp domyślne wartości **Dataverse URL** przy użyciu wartości znalezionych w **Informacje o środowisku Power Platform** w LCS (w sekcji **Integracja platformy Power**).
        1. Zastąp wartości **Identyfikatora środowiska** za pomocą wartości znalezionych na stronie **Szczegóły środowiska** w usłudze LCS (w sekcji integracji **Zarządzaj środowiskami**).
        1. Wybierz łącze **Edytuj poświadczenia** obok etykiety **CDS** w sekcji **Poświadczeń źródła danych**. Następnie zaloguj się na swoje konto Dataverse przy użyciu metody uwierzytelniania **OAuth2**.
    1. Sprawdź, czy raporty Power BI znalezione w **Mój obszar roboczy \> Raporty \> Globalne księgowanie zapasów** działają teraz prawidłowo i wyświetlają zawartość systemu.

1. Zarejestruj aplikację zgodnie z opisem w temacie [Konfiguracja integracji PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).
1. Aby zintegrować raport **Globalnego księgowanie zapasów** Power BI w Dynamics 365 Supply Chain Management, należy wykonać następujące kroki:

    1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja PowerBI.com**.
    1. Wybierz opcję **Edycja**.
    1. Wybierz opcję **Włącz integrację PowerBI.com**.
    1. W polu **Identyfikator aplikacji** wprowadź identyfikator.
    1. W polu **Klucz aplikacji** wprowadź klucz.
    1. Wybierz opcję **Zapisz**.

1. Odśwież stronę, tak aby było wyświetlane okno dialogowe logowania Power BI.
1. Na karcie **Opcje** wybierz pozycję **Otwórz katalog raportu**, a następnie wybierz plik raportu **Globalne księgowanie zapasów** Power BI, który został przekazany wcześniej.
1. Odśwież stronę. Raport powinien zostać dodany.
1. Wybierz plik raportu **Globalnego księgowanie zapasów** w **Raporty Power BI**.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).
