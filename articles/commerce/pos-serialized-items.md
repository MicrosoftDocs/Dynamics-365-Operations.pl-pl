---
title: Praca z pozycjami serializowanymi w punkcie sprzedaży
description: W tym temacie opisano sposób zarządzania pozycjami spersonalizowanymi w aplikacji punktu sprzedaży.
author: boycezhu
manager: annbe
ms.date: 04/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 1e0d6aa7cd5576578378e70c6ee808833314aff3
ms.sourcegitcommit: 919620b4aca425e6a1248ee12f50a622d2531e58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2020
ms.locfileid: "3290777"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Praca z pozycjami serializowanymi w punkcie sprzedaży

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Wielu sprzedawców detalicznych sprzedaje produkty wymagające kontroli numerów seryjnych. Te pozycje są nazywane *pozycjami serializowanymi*. Niektórzy sprzedawcy detaliczni mogą chcieć zachować numery seryjne dla celów związanych ze śledzeniem. Inni sprzedawcy detaliczni mogą przechwytywać numery seryjne podczas procesu sprzedaży dla celów związanych z usługami i gwarancjami. W tym temacie opisano sposób zarządzania pozycjami spersonalizowanymi w aplikacji punktu sprzedaży Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Konfiguracje numeru seryjnego

Pozycja jest traktowana jako serializowana, jeśli przypisano do niej grupę wymiarów śledzenia skonfigurowaną do zezwalania na numery seryjne. W module Commerce Headquarters na stronie **Grupy wymiarów śledzenia** wybierz opcję **Aktywny**, aby włączyć numery seryjne na potrzeby procesu obsługi zapasów. Aby włączyć numery seryjne dla procesu sprzedaży, wybierz opcję **Aktywny w procesie sprzedaży**.

Na skróconej karcie **Wymiary śledzenia**, jeśli opcja **Dozwolony pusty przychód** została włączona, numery seryjne będą opcjonalnymi danymi wejściowymi w procesie przyjmowania zapasów. Jeśli opcja jest wyłączona, numer seryjny jest wymagany.

Na skróconej karcie **Numery seryjne**, jeśli opcja **Kontrola numeru seryjnego** jest włączona, numer seryjny musi być unikatowy dla poszczególnych jednostek. Mówiąc inaczej, zduplikowane numery seryjne nie są dozwolone.

## <a name="serialized-items-in-the-receiving-process"></a>Pozycje serializowane w procesie przyjęcia

Operacja **Zapasy przychodzące** w aplikacji punktu sprzedaży umożliwia użytkownikom wykonywanie następujących zadań dla pozycji serializowanych:

- Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych, gdy pozycje są przyjmowane w sklepie za pośrednictwem zamówienia zakupu.
- Weryfikowanie wstępnie zarejestrowanych numerów seryjnych w odniesieniu do pozycji serializowanych, gdy pozycje są przyjmowane w sklepie za pośrednictwem zamówienia zakupu lub zamówienia przeniesienia.

> [!NOTE]
> Aby użyć operacji **Zapasy przychodzące** do rejestrowania lub weryfikowania pozycji serializowanej, do pozycji musi być przypisana grupa wymiarów śledzenia skonfigurowana do zezwalania na numery seryjne dla opcji **Aktywny**, a nie dla opcji **Aktywny w procesie sprzedaży**.

Aby rozpocząć proces przyjęcia, w operacji **zapasów przychodzących** można rozpocząć w widoku **Przyjmowane teraz**, skanując kod kreskowy pozycji lub wprowadzając identyfikator pozycji. Możesz również rozpocząć pracę w widoku **Pełna lista zamówień**, ręcznie wybierając pozycję.

Jeśli pozycja wybierana lub przyjmowana to pozycja serializowana, okienko **Szczegóły** pozycji zawiera link **Zarządzaj numerem seryjnym**, który otwiera stronę **Zarządzanie numerami seryjnymi**. Można również otworzyć stronę **Zarządzanie numerami seryjnymi**, wybierając pozycję **Numer seryjny** na pasku aplikacji w widoku szczegółów zamówienia lub wybierając pozycję **Zarządzaj numerem seryjnym** w oknie dialogowym, które monituje Cię podczas procesu przyjęcia. Strona **Zarządzanie numerami seryjnymi** zawiera listę wszystkich otwartych wierszy numerów seryjnych oczekujących na rejestrację lub weryfikację. Na tej stronie mogą znajdować się dwie karty: jedna dla bieżącej pozycji towaru i jedna dla wszystkich pozycji serializowanych w zamówieniu.

Pole **Stan** na stronie **Zarządzanie numerami seryjnymi** zawiera informacje o bieżącym etapie, na którym znajdują się poszczególne numery seryjne:

- **Nie zarejestrowano** — numer seryjny nie został wprowadzony lub wstępnie zarejestrowany numer seryjny nie został jeszcze zweryfikowany.
- **Rejestrowanie** — numer seryjny został zarejestrowany i zapisany lokalnie w bazie danych kanału sklepu lub wstępnie zarejestrowany numer seryjny został zweryfikowany. Tylko numery seryjne ze stanem **Rejestrowanie** zostaną przesłane do modułu Commerce Headquarter po zakończeniu przyjęcia.

### <a name="register-serial-numbers-against-serialized-items"></a>Rejestrowanie numerów seryjnych w odniesieniu do pozycji serializowanych

W przypadku zamówienia zakupu okno dialogowe, które monituje użytkownika podczas procesu przyjęcia pozycji serializowanej, oferuje opcję **Zarządzaj numerem seryjnym**. Można wybrać tę opcję, aby otworzyć stronę **Zarządzanie numerami seryjnymi** i rozpocząć rejestrowanie numerów seryjnych. Można również pominąć ten krok podczas procesu przyjęcia i wprowadzić dane wejściowe później, przed zaksięgowaniem przyjęcia.

Domyślnie jest wyświetlana karta dla bieżącej pozycji. Wszystkie wiersze numerów seryjnych mają pustą wartość numeru seryjnego i stan **Nie zarejestrowano**. Można zeskanować kody kreskowe numerów seryjnych lub wybrać pozycję **Numer seryjny** na pasku aplikacji w celu ciągłego wprowadzania numerów seryjnych w oknie dialogowym. Numery seryjne, które wprowadzisz, pojawią się na liście, a stan wierszy tych numerów seryjnych zmieni się na **Rejestrowanie**. Maksymalna liczba numerów seryjnych, które można zarejestrować na liście, jest równa ilości przyjmowanej. W przypadku popełnienia błędu możesz wybrać pozycję **Edytuj** lub **Wyczyść** w okienku **Szczegóły**, aby wprowadzić zmiany wprowadzonych numerów seryjnych.

Numery seryjne można również rejestrować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz zarejestrować numery seryjne.

Podczas rejestracji numeru seryjnego na tej stronie jest przeprowadzana weryfikacja duplikatów. W przypadku próby wprowadzenia powielonego numeru seryjnego dla pozycji z włączoną kontrolą numeru seryjnego zostanie wyświetlony komunikat o błędzie i trzeba będzie podać inny numer.

### <a name="validate-serial-numbers-on-serialized-items"></a>Weryfikowanie numerów seryjnych dla pozycji serializowanych

W przypadku zamówienia przeniesienia strona wychodząca musi wstępnie zarejestrować numery seryjne w pozycjach serializowanych w trakcie procesu wysyłki. W przypadku zamówienia zakupu dostawca może podać informacje o numerach seryjnych za pośrednictwem wcześniejszego zawiadomienia o wysyłce (ASN), a Ty możesz następnie zarejestrować numery pozycji do wysłania. W obu przypadkach numery seryjne są znane przed przyjęciem. Z tego względu po stronie przychodzącej wystarczy tylko sprawdzić, czy zaplanowane pozycje zostały przyjęte.

Aby zweryfikować numery seryjne, można otworzyć stronę **Zarządzanie numerami seryjnymi** w trakcie procesu przyjęcia lub w dowolnym momencie przed zaksięgowaniem przyjęcia. Dla każdej pozycji serializowanej ze wstępnie zarejestrowanymi numerami seryjnymi wszystkie numery seryjne są automatycznie ustawiane na początkowy stan **Nie zarejestrowano** na tej stronie. Aby zweryfikować numery seryjne, można je zeskanować lub wprowadzić. Podczas wprowadzania numeru seryjnego aplikacja sprawdza, czy odpowiada on wstępnie zarejestrowanemu numerowi seryjnemu. Jeśli numery są zgodne, ich stan zmienia się na **Rejestrowanie**. W przeciwnym razie zostanie wyświetlony komunikat o błędzie. Maksymalna liczba numerów seryjnych, które można zweryfikować na liście, jest równa ilości przyjmowanej.

Numery seryjne można również weryfikować na karcie **Wszystkie pozycje serializowane** na stronie **Zarządzanie numerami seryjnymi**. Na liście wybierz pozycję, względem której chcesz weryfikować numery seryjne.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Operacja zapasów przychodzących w punkcie sprzedaży](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)
