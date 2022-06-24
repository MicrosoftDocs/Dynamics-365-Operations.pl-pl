---
title: Włączanie i konfigurowanie opłat automatycznych według kanałów
description: W tym artykule wyjaśniono, jak włączyć i skonfigurować opłaty automatyczne według kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 93141fe49989a4d7f514009c627db936c11ca8ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854959"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a>Włączanie i konfigurowanie opłat automatycznych według kanałów

W tym artykule wyjaśniono, jak włączyć i skonfigurować opłaty automatyczne (auto opłaty) według kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Może istnieć sytuacja, w której opłaty za recykling lub inne opłaty muszą być stosowane do grupy produktów sprzedawanych we wszystkich lub niektórych sklepach w określonym stanie (np. w Kalifornii). Funkcja **Włącz filtrowanie opłat automatycznych według kanałów** w module Commerce umożliwia określenie automatycznych opłat według kanałów (na przykład: konkretny sklepu fizycznego). Ta funkcja jest włączana w Dynamics 365 Commerce wersja 10.0.10 i nowsze.

Aby włączyć i skonfigurować opłaty automatyczne według kanałów, należy wykonać następujące zadania:

- Włącz funkcję **Włącz filtrowanie automatycznych opłat według kanałów**.
- Skonfiguruj cel hierarchii organizacyjnej.
- Definiuj opłaty automatyczne według kanałów.

> [!NOTE]
> Funkcja **Włącz filtrowanie automatycznych opłat według kanałów** działa tylko wtedy, gdy włączona jest również funkcja zaawansowane opłaty automatyczne. Aby uzyskać informacje dotyczące włączania funkcji zaawansowanych opłat automatycznych, należy zapoznać się z [Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md).

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a>Włącz funkcję Włącz filtrowanie automatycznych opłat według kanałów

Aby włączyć automatyczne opłaty według kanału w module Commerce, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
1. Na karcie **Niewłączone**, na liście **Nazwa funkcji** znajdź i zaznacz opcję **Włącz filtrowanie automatycznych opłat według kanałów**.
1. W prawym dolnym rogu wybierz opcję **Włącz teraz**. Po włączeniu tej funkcji zostanie ona wyświetlona na liście na karcie **Wszystkie**.
1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. W lewym okienku znajdź i zaznacz zadanie **1110** (**Konfiguracja globalna**).
1. W okienku akcji wybierz opcję **Uruchom teraz**, aby propagować zmiany konfiguracji.

> [!WARNING]
> Jeśli po wywłączeniu funkcji **Włącz filtrowanie automatycznych opłat według kanałów** po jej użyciu, pole **Relacja kanału detalicznego** w obszarze **Automatyczne opłaty** nie będzie już wyświetlane i wszystkie istniejące konfiguracje zostaną utracone. Jeśli usunięcie **Relacji kanału detalicznego** spowoduje, że reguły automatycznego pobierania opłat zostaną zduplikowane, próba wyłączenia tej funkcji nie powiedzie się. Przed wyłączeniem tej funkcji należy sprawdzić wszystkie reguły automatycznego pobierania opłat i wprowadzić wszelkie wymagane zmiany.

## <a name="configure-the-organization-hierarchy-purpose"></a>Skonfiguruj cel hierarchii organizacyjnej

Utworzono nowy cel hierarchii organizacyjnej o nazwie **Automatyczne opłaty detaliczne** w celu zarządzania hierarchią opłat automatycznych według kanałów.

Aby przypisać hierarchię domyślną do celu hierarchii organizacyjnej w module Commerce, wykonaj następujące kroki.
        
1. Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Cele hierarchii organizacyjnej**.
1. W lewym okienku wybierz opcję **Automatyczne opłaty detaliczne**.
1. W obszarze **Przypisane hierarchie** wybierzopcję **Dodaj**.
1. W oknie dialogowym **Hierarchie organizacji** wybierz hierarchię organizacyjną (np. **Sklepy detaliczne według regionów**), a następnie kliknij **OK**.
1. W obszarze **Przypisane hierarchie** wybierzopcję **Ustaw jako domyślny**.
1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. W lewym okienku znajdź i zaznacz zadanie **1040** (**Produkty**).
1. W okienku akcji wybierz opcję **Uruchom teraz**.
1. Powtórz dwa poprzednie kroki, aby uruchomić zadania **1070** (**konfiguracja kanału**) i **1110** (**konfiguracja globalna**).

![Konfiguracja celu hierarchii automatycznej opłaty w organizacji sieci sprzedaży.](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a>Definiuj opłaty automatyczne według kanałów

Po włączeniu funkcji **Włącz filtrowanie automatycznych opłat według kanałów** i skonfigurowaniu celu hierarchii organizacja **Automatyczne opłaty detaliczne** można zdefiniować automatyczne opłaty według kanałów na poziomie nagłówka zamówienia lub na poziomie wiersza zamówienia.

Aby zdefiniować automatyczne opłaty według kanału w module Commerce, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia opłat \> Opłaty automatyczne**.
1. W lewym okienku w polu **Poziom** wybierz opcję **Nagłówek** lub **Wiersz**, w zależności od wymagań biznesowych.
1. W polu **Kod kanału sprzedaży** wybierz odpowiedni kod kanału (np. **tabelę** lub **grupę**). Jeśli ustawienie domyślne, **Wszystkie**, jest używana, reguły opłat są stosowane do wszystkich kanałów.

    - W przypadku wybrania opcji **Grupa** należy się upewnić, że Grupa opłat kanału sprzedaży jest tworzona w **Retail i Commerce \> Ustawienia kanału \> Opłaty \> Grupy opłat kanałów detalicznych**.
    - W przypadku wybrania opcji **Tabela** można wybrać konkretny kanał (np. **San Francisco**) w polu **Relacja kanału detalicznego**.

1. Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.
1. W lewym okienku znajdź i zaznacz zadanie **1040** (**Produkty**).
1. W okienku akcji wybierz opcję **Uruchom teraz**.
1. Powtórz dwa poprzednie kroki, aby uruchomić zadania **1070** (**konfiguracja kanału**) i **1110** (**konfiguracja globalna**).
    
![Zdefiniowane opłaty automatyczne według kanałów.](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a>Przykładowy scenariusz

W poniższym przykładzie przedstawiono kroki wymagane do skonfigurowania produktu, tak aby opłaty za recykling były naliczane, gdy produkt jest sprzedawany za pośrednictwem kanału San Francisco sklepu fizycznego. W przykładzie pokazano również, w jaki sposób automatycznie opłaty są wyświetlane w punkcie sprzedaży Commerce (POS).

W organizacji definiowany jest kod opłat o nazwie **RECYKLING**, co pokazano na poniższej ilustracji.

![Kod opłat za RECYKLING.](media/Auto-charges-charge-code.png)

Automatyczna opłata jest utworzona na poziomie wiersza. Ma następujące ustawienia:

- W polu **Kod konta** jest ustawiona wartość **Wszystkie**.
- W polu **Kod pozycji** jest ustawiona wartość **Tabela**.
- Pole **Relacja pozycji** ma wartość identyfikatora produktu **91001**.
- W polu **Kod metody dostawy** jest ustawiona wartość **Wszystkie**.
- W polu **Kod kanału sprzedaży** jest ustawiona wartość **Tabela**.
- Pole **Relacja kanału detalicznego** jest ustawione na sklep **San Francisco**.

Utworzono wiersz opłat automatycznych. Ma następujące ustawienia:

- Pole **Waluta** ma ustawioną wartość **USD**.
- W polu **Kod opłat** jest ustawiona wartość **RECYKLING**.
- W polu **Kategoria** jest ustawiona wartość **Ustawiona**.
- Pole **Opłaty** ma ustawioną wartość **$6.25**.

![Konfiguracja automatycznej opłaty na poziomie wiersza i wiersza opłat automatycznych.](media/Auto-charges-recyclingfee-line-fee.png)

W aplikacji POS zamówienie sprzedaży jest tworzone w kanale sklepu **San Francisco**. Wiersz **Opłat** zawiera opłatę za recykling **$6,25**.

Po wybraniu **Opcje transakcji \> Opłaty \> Zarządzaj opłatami** w aplikacji punktu sprzedaży, można wyświetlić kod opłat i opis opłaty za recykling.

![Opłata za recykling w aplikacji punktu sprzedaży.](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md)

[Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]