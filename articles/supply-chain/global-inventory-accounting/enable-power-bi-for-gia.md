---
title: Włączanie usługi Power BI dla Globalnego księgowania zapasów
description: W tym temacie opisano sposób włączenia w Microsoft Power BI funkcji Globalnego księgowanie zapasów.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273209"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Włączanie usługi Power BI dla Globalnego księgowania zapasów

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

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
    1. W ustawieniach **Globalnego księgowania zapasów** rozwiń pozycję **Parametry** i w razie potrzeby zaktualizuj wszystkie parametry.

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
