---
title: Praca z pozycjami serializowanymi w punkcie sprzedaży
description: W tym temacie opisano sposób zarządzania pozycjami spersonalizowanymi w aplikacji punktu sprzedaży.
author: boycezhu
manager: annbe
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6ba01abc3d1a4496ec586a621aa03b4981f84d76
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415054"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Praca z pozycjami serializowanymi w punkcie sprzedaży

[!include [banner](includes/banner.md)]

Wielu sprzedawców detalicznych sprzedaje produkty wymagające kontroli numerów seryjnych. Te produkty są nazywane *pozycjami serializowanymi*. Niektórzy sprzedawcy detaliczni mogą chcieć zachować numery seryjne w zapasach sklepowych lub magazynowych dla celów związanych ze śledzeniem. Inni sprzedawcy detaliczni mogą przechwytywać numery seryjne podczas procesu sprzedaży dla celów związanych z usługami i gwarancjami. W tym temacie opisano sposób zarządzania pozycjami spersonalizowanymi w aplikacji punktu sprzedaży Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Konfiguracje numeru seryjnego

Pozycja jest traktowana jako serializowana, jeśli przypisano do niej grupę wymiarów śledzenia skonfigurowaną do zezwalania na numery seryjne. W module Commerce Headquarters, na stronie **Grupy wymiarów śledzenia** wybierz opcję **Aktywne**, aby włączyć numery seryjne dla procesu magazynowego, lub wybierz **Aktywne w module proces sprzedażowych**, aby włączyć numery seryjne dla procesu sprzedaży.

Na skróconej karcie **Wymiary śledzenia**, włącz parametr **Dozwolony pusty przychód**, aby zezwolić na użycie numerów seryjnych jako opcjonalnych danych wejściowych w procesie przyjmowania zapasów. Wyłączenie tego parametru wymusza użycie numeru seryjnego jako wymaganych danych wejściowych. Analogicznie, parametr **Dozwolone puste wydanie** określa, czy numer seryjny jest wymagany podczas procesu wysyłania zapasów do magazynu.

> [!NOTE]
> Aby użyć operacji **Zapasy przychodzące** oraz **Zapasy wychodzące** w punkcie sprzedaży do rejestrowania lub weryfikowania numerów seryjnych pozycji serializowanych, do pozycji musi być przypisana grupa wymiarów śledzenia skonfigurowana do zezwalania na numery seryjne dla opcji **Aktywny**, a nie dla opcji **Aktywny w procesie sprzedaży**.

## <a name="serial-number-management-page"></a>Strona zarządzania numerami seryjnymi

W operacji w punkcie sprzedaży **Zapasy przychodzące** i **Zapasy wychodzące** i gdy towar, który jest wybierany, odebrany lub wysłany, jest towarem serializowanym okienko **Szczegóły** zawiera opcję **Zarządzanie numerem seryjnym**, która łączy ze stroną **Zarządzania numerami seryjnymi**, gdzie można zarejestrować lub sprawdzić numery seryjne dla danego towaru. Można również otworzyć stronę **Zarządzanie numerami seryjnymi**, wybierając działanie **Numer seryjny** na pasku aplikacji w widoku szczegółów zamówienia lub wybierając pozycję **Zarządzaj numerem seryjnym** w oknie dialogowym, które monituje Cię podczas procesu przyjęcia lub wysyłki. 

Strona **Zarządzanie numerami seryjnymi** zawiera listę wszystkich otwartych wierszy numerów seryjnych oczekujących na rejestrację lub weryfikację. Na tej stronie mogą znajdować się dwie karty: jedna dla bieżącej pozycji towaru i inna dla wszystkich pozycji serializowanych w zamówieniu.

Pole **Stan** na stronie **Zarządzanie numerami seryjnymi** zawiera informacje o bieżącym etapie, na którym znajdują się poszczególne numery seryjne:

- **Nie zarejestrowano** — numer seryjny nie został wprowadzony lub wstępnie zarejestrowany numer seryjny nie został jeszcze zweryfikowany (w procesie przyjęcia).
- **Rejestrowanie** — numer seryjny został zarejestrowany i zapisany lokalnie w bazie danych kanału sklepu lub wstępnie zarejestrowany numer seryjny został zweryfikowany. Tylko numery seryjne ze stanem **Rejestrowanie** zostaną przesłane do modułu Commerce Headquarter po zakończeniu przyjęcia lub realizacji.

## <a name="receive-serialized-items"></a>Odbieranie serializowanych towarów

Operacja **Zapasy przychodzące** w aplikacji punktu sprzedaży umożliwia użytkownikom wykonywanie następujących zadań dla pozycji serializowanych:

- Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych, gdy pozycje są przyjmowane w sklepie za pośrednictwem zamówienia zakupu.
- Weryfikowanie wstępnie zarejestrowanych numerów seryjnych w odniesieniu do pozycji serializowanych, gdy pozycje są przyjmowane w sklepie za pośrednictwem zamówienia zakupu lub zamówienia przeniesienia.

### <a name="register-serial-numbers-against-serialized-items"></a>Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych

W przypadku zamówienia zakupu okno dialogowe, które monituje użytkownika podczas procesu przyjęcia pozycji serializowanej, oferuje opcję **Zarządzania numerem seryjnym**. Można wybrać tę opcję, aby otworzyć stronę **Zarządzanie numerami seryjnymi** i rozpocząć rejestrowanie numerów seryjnych. Można również pominąć ten krok podczas procesu przyjęcia i wprowadzić dane wejściowe później, przed zaksięgowaniem przyjęcia.

Domyślnie jest wyświetlana karta dla bieżącej pozycji. Wszystkie wiersze numerów seryjnych mają pustą wartość numeru seryjnego i stan **Nie zarejestrowano**. Można zeskanować kody kreskowe numerów seryjnych lub wybrać pozycję **Numer seryjny** na pasku aplikacji w celu ciągłego wprowadzania numerów seryjnych. Numery seryjne, które wprowadzisz, pojawią się na liście, a stan wierszy tych numerów seryjnych zmieni się na **Rejestrowanie**. Maksymalna liczba numerów seryjnych, które można zarejestrować na liście, jest równa ilości przyjmowanej. W przypadku popełnienia błędu możesz wybrać pozycję **Edytuj** lub **Wyczyść** w okienku **Szczegóły**, aby wprowadzić zmiany wprowadzonych numerów seryjnych.

Numery seryjne można również rejestrować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz zarejestrować numery seryjne.

### <a name="validate-serial-numbers-on-serialized-items"></a>Weryfikowanie numerów seryjnych dla pozycji serializowanych

W przypadku zamówienia przeniesienia strona wychodząca musi wstępnie zarejestrować numery seryjne w pozycjach serializowanych w trakcie procesu wysyłki. W przypadku zamówienia zakupu dostawca może podać informacje o numerach seryjnych za pośrednictwem wcześniejszego zawiadomienia o wysyłce (ASN), a Ty możesz następnie zarejestrować numery pozycji do wysłania. W obu przypadkach numery seryjne są znane przed przyjęciem. Z tego względu po stronie przychodzącej wystarczy tylko sprawdzić, czy zaplanowane pozycje zostały przyjęte.

Aby zweryfikować numery seryjne, można otworzyć stronę **Zarządzanie numerami seryjnymi** w trakcie procesu przyjęcia lub w dowolnym momencie przed zaksięgowaniem przyjęcia. Dla każdej pozycji serializowanej ze wstępnie zarejestrowanymi numerami seryjnymi wszystkie numery seryjne są automatycznie ustawiane na początkowy stan **Nie zarejestrowano** na tej stronie. Aby zweryfikować numery seryjne, można je zeskanować lub wprowadzić. Podczas wprowadzania numeru seryjnego aplikacja sprawdza, czy odpowiada on wstępnie zarejestrowanemu numerowi seryjnemu. Jeśli numery są zgodne, ich stan zmienia się na **Rejestrowanie**. W przeciwnym razie zostanie wyświetlony komunikat o błędzie. Można również bezpośrednio wybrać numer seryjny, a następnie wybrać opcję **Sprawdź numer seryjny** w okienku **Szczegóły**, aby szybko oznaczyć ten numer seryjny jako sprawdzony. Maksymalna liczba numerów seryjnych, które można zweryfikować na liście, jest równa ilości przyjmowanej.

Numery seryjne można również weryfikować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz weryfikować numery seryjne.

## <a name="ship-serialized-items"></a>Wysyłka towarów serializowanych

Za pomocą operacji w aplikacji punktu sprzedaży **Zapasy wychodzące** można rejestrować numery seryjne na towarach serializowanych podczas wysyłania ich z bieżącego sklepu za pośrednictwem zamówienia przeniesienia.

### <a name="register-serial-numbers-against-serialized-items"></a>Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych

W przypadku zamówienia przeniesienia okno dialogowe, które monituje użytkownika podczas procesu wysyłki pozycji serializowanej, oferuje opcję **Zarządzania numerem seryjnym**. Można wybrać tę opcję, aby otworzyć stronę **Zarządzanie numerami seryjnymi** i rozpocząć rejestrowanie numerów seryjnych. Można również pominąć ten krok podczas procesu wysyłki i wprowadzić dane wejściowe później, przed zaksięgowaniem wysyłki.

Domyślnie jest wyświetlana karta dla bieżącej pozycji. Wszystkie wiersze numerów seryjnych mają pustą wartość numeru seryjnego i stan **Nie zarejestrowano**. Można zeskanować kody kreskowe numerów seryjnych lub wybrać pozycję **Numer seryjny** na pasku aplikacji w celu ciągłego wprowadzania numerów seryjnych. Numery seryjne, które wprowadzisz, pojawią się na liście, a stan wierszy tych numerów seryjnych zmieni się na **Rejestrowanie**. Maksymalna liczba numerów seryjnych, które można zarejestrować na liście, jest równa ilości wysyłanej. W przypadku popełnienia błędu możesz wybrać pozycję **Edytuj** lub **Wyczyść** w okienku **Szczegóły**, aby wprowadzić zmiany wprowadzonych numerów seryjnych.

Numery seryjne można również rejestrować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz zarejestrować numery seryjne.

Opcjonalnie można włączyć sprawdzanie poprawności dostępności numeru seryjnego podczas rejestracji numeru seryjnego dla zamówienia przeniesienia wychodzącego. Przy takim sprawdzaniu w przypadku próby wysłania numeru seryjnego, który jest niedostępny w zapasach w magazynie wysyłek, zostanie wyświetlony komunikat o błędzie i trzeba podać inny numer.

Aby włączyć taką weryfikację jako wymaganie wstępne, należy zaplanować cykliczne wykonywanie następujących zadań:

- **Retail and Commerce** > **Retail and Commerce — składniki IT** > **Produkty i zapasy** > **Dostępność produktu z wymiarami śledzenia**
- **Retail and Commerce** > **Harmonogramy dystrybucji** > **1130** (**Dostępność produktu**)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Operacja zapasów przychodzących w punkcie sprzedaży](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Operacja zapasów wychodzących w punkcie sprzedaży](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)
