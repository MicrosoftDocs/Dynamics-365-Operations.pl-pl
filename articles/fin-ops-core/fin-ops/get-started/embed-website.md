---
title: Osadzanie aplikacji innych firm
description: W tym artykule opisano sposób osadzania aplikacji innych firm w celu rozszerzenia funkcjonalności produktu.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3c07befc7150ff0a121fd3aaa0b5233df9f431e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868616"
---
# <a name="embed-third-party-apps"></a>Osadzanie aplikacji innych firm

[!include [banner](../includes/banner.md)]

Wielu odbiorców używa wielu aplikacji do prowadzenia działalności gospodarczej. Niektóre z tych aplikacji to aplikacje sieci web innych firm, które działają w połączeniu z aplikacjami finansowymi i operacyjnymi. Aby zapewnić bezproblemowe korzystanie z aplikacji, można za pomocą funkcji **Aplikacje dla całej strony** osadzać aplikacje innych firm bezpośrednio w aplikacjach finansowych i operacyjnych (pod warunkiem że aplikacje innych firm pozwalają na osadzanie ich w tej aplikacji). Dzięki temu użytkownicy będą mieli dostęp do wymaganych przez nich witryn internetowych i aplikacji bez konieczności przełączania kart lub okien.

Aby można było osadzać aplikacje innych firm w produkcie, należy włączyć funkcję **Aplikacje dla całej strony** w module Zarządzanie funkcjami. Następnie można użyć jednej z poniższych metod, aby osadzić aplikację lub witrynę internetową innej firmy. Te metody są analogiczne do metod używanych do osadzania aplikacji kanwy z usługi Microsoft Power Apps w aplikacjach finansowych i operacyjnych.

- Osadź aplikację lub witrynę internetową na istniejącej stronie jako nową kartę (karta przestawna, karta skrócona, blok albo sekcja obszaru roboczego).
- Utwórz nowe, środowisko na pełnej stronie dla aplikacji lub witryny internetowej z pulpitu nawigacyjnego.

## <a name="embed-a-website-on-an-existing-page"></a>Osadzanie witryny internetowej na istniejącej stronie

Tej procedury należy użyć w celu uzupełnienia istniejącej strony w systemie o osadzoną aplikację.

1. Otwórz stronę, w której chcesz osadzić aplikację.
2. Otwórz okienko **Dodaj aplikację**:

    1. Wybierz **Ustawienia**, a następnie **Personalizuj**, aby otworzyć pasek narzędzi **Personalizacja**.
    2. Wybierz **Więcej \> Dodaj aplikację**.

3. Wybierz region strony, w którym chcesz dodać aplikację. Ten region musi być *kontenerem karty* dla karty przestawnej, skróconej karty, bloku lub sekcji obszaru roboczego.
4. Wybierz opcję **Witryna internetowa**.
5. Konfigurowanie osadzonej aplikacji:

    - **Nazwa** — umożliwia wprowadzenie tekstu, który ma być wyświetlany na karcie zawierającej osadzoną aplikację. Zazwyczaj ten tekst jest nazwą aplikacji.
    - **URL** — Umożliwia określenie lokalizacji aplikacji.

    > [!IMPORTANT]
    > - Ze względów bezpieczeństwa adres URL musi korzystać z protokołu Hypertext Transfer Protocol Secure (HTTPS).
    > - Aplikacja lub witryna internetowa musi być skonfigurowana tak, aby zezwalała na osadzenie jej.

6. Wybierz przycisk **Zapisz**, aby osadzić aplikację na stronie. Aplikacja jest dodawana jako ostatnia karta lub sekcja w grupie.
7. Potwierdź, że aplikacja jest wyświetlana zgodnie z oczekiwaniami. Jeśli aplikacja nie jest renderowana, zobacz sekcję [Rozwiązywanie problemów](#troubleshooting) w dalszej części tego artykułu.
8. Otwórz selektor widoku i wybierz opcję **Zapisz** (jeśli aplikacja ma być skojarzona z bieżącym widokiem) lub **Zapisz jako** (aby zapisać aplikację w innym widoku).

    Jeśli strona nie ma selektora widoku (na przykład, jeśli strona jest oknem dialogowym lub obszarem roboczym), możesz pominąć ten krok.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Osadzanie witryny internetowej jako środowisko na pełnej stronie z pulpitu nawigacyjnego

Tej procedury należy użyć, jeśli aplikacja, którą chcesz osadzić, nie jest powiązana z istniejącą stroną lub chcesz mieć środowisko na pełnej stronie dla aplikacji w obrębie aplikacji finansowych i operacyjnych.

1. Otwórz pulpit nawigacyjny.
2. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) na pulpicie nawigacyjnym, wybierz opcję **Personalizuj**, a następnie wybierz polecenie **Dodaj stronę**.
3. W okienku **Dodaj stronę** wybierz opcję **Witryna internetowa**.
4. Konfigurowanie osadzonej aplikacji:

    - **Nazwa** — służy do wprowadzania tekstu, który ma być wyświetlany na kafelku dodawanym do aplikacji osadzonej na pulpicie nawigacyjnym. Zazwyczaj ten tekst jest nazwą aplikacji.
    - **URL** — Umożliwia określenie lokalizacji aplikacji.

    > [!IMPORTANT]
    > - Ze względów bezpieczeństwa adres URL musi używać protokołu HTTPS.
    > - Aplikacja lub witryna internetowa musi być skonfigurowana tak, aby zezwalała na osadzenie jej.

5. Wybierz przycisk **Zapisz**, aby dodać aplikację do pulpitu nawigacyjnego jako nowy kafelek.
6. Wybierz nowy kafelek na pulpicie nawigacyjnym i potwierdź, że aplikacja jest wyświetlana zgodnie z oczekiwaniami. Jeśli aplikacja nie jest renderowana, zobacz sekcję [Rozwiązywanie problemów](#troubleshooting) w dalszej części tego artykułu.

## <a name="sharing-embedded-apps"></a>Udostępnianie osadzonych aplikacji

Po osadzeniu aplikacji za pomocą jednej z metod opisanych w poprzednich sekcjach można udostępnić widok innym użytkownikom w systemie. Aby udostępnić osadzoną aplikację, należy użyć jednej z następujących metod:

- **Publikowanie widoku (zalecane):** Jeśli aplikacja osadzona została zapisana w widoku, zalecany i preferowany sposób jej udostępniania to publikowanie tego widoku użytkownikom, którzy mają odpowiednie role zabezpieczeń w docelowych firmach. W takim przypadku tylko żądani użytkownicy zobaczą osadzoną aplikację na tej stronie. Aby uzyskać więcej informacji dotyczących sposobu publikowania widoku, zobacz temat [Publikowanie widoków](saved-views.md#publishing-views).

    Możesz również opublikować aplikację, która została osadzona jako środowisko na całej stronie, z pulpitu nawigacyjnego. Na pulpicie nawigacyjnym wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kafelek skojarzony z aplikacją, wybierz opcję **Personalizuj**, a następnie wybierz pozycję **Publikuj stronę**. Jest wyświetlane środowisko przypominające środowisko *Publikowanie widoków* i możliwe jest wybranie ról zabezpieczeń, dla których zostanie ono opublikowane. W wersji 10.0.21 i nowszych, jeśli jest włączona funkcja **Usprawniona obsługa zapisanych widoków dla firmy** można także opublikować aplikację dla żądanych firm.

- **Kopiowanie personalizacji:** dla stron, które nie obsługują widoków (na przykład okien dialogowych lub obszarów roboczych) lub w przypadku środowisk aplikacji dla całej strony można skopiować tę personalizację odpowiednim użytkownikom. Aby uzyskać więcej informacji, zobacz [Udostępnianie personalizacji](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>Wyświetlanie osadzonych aplikacji

Aby wyświetlić osadzoną aplikację na stronie w aplikacjach finansowych i operacyjnych, otwórz stronę z osadzoną aplikacją. Pamiętaj, że na niektórych stronach dostęp do aplikacji osadzonych można uzyskać za pomocą przycisku **Power Apps** w standardowym okienku akcji. Alternatywnie mogą być wyświetlane bezpośrednio na stronie w postaci nowej karty lub karty skróconej, lub bloku, lub nowej sekcji w obszarze roboczym.

## <a name="editing-or-removing-embedded-apps"></a>Edytowanie lub usuwanie aplikacji osadzonych

Po osadzeniu aplikacji na stronie może być konieczne edytowanie jej konfiguracji (na przykład przez zmianę etykiety sekcji lub adresu URL). Może też być konieczne usunięcie jej ze strony. Należy użyć jednej z poniższych procedur, aby zmodyfikować konfigurację osadzonej aplikacji lub całkowicie ją usunąć.

### <a name="apps-that-are-embedded-on-existing-pages"></a>Aplikacje osadzone na istniejących stronach

1. Otwórz stronę, w której aplikacja jest osadzona.
2. Wybierz **Ustawienia**, a następnie **Personalizuj**, aby otworzyć pasek narzędzi **Personalizacja**.
3. Wybierz narzędzie **Wybierz**, a następnie aplikację osadzoną.
4. Aby zmodyfikować aplikację, dokonaj wymaganych zmian w jej konfiguracji, a następnie wybierz pozycję **Zapisz**.

    Ewentualnie, aby usunąć aplikację, wybierz opcję **Usuń**.

5. Zapisz ponownie lub opublikuj ponownie widok. Jeśli opuścisz tę stronę bez jawnego zapisywania widoku, żadna z akcji wykonanych w okienku **Edytuj witrynę internetową** nie zostanie zachowana.

### <a name="apps-that-are-embedded-from-the-dashboard"></a>Aplikacje osadzone z pulpitu nawigacyjnego

1. Otwórz pulpit nawigacyjny.
2. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kafelek skojarzony z osadzoną aplikacją i wybierz opcję **Personalizuj**.
3. Aby edytować aplikację, wybierz pozycję **Edytuj stronę**. W okienku **Edytuj witrynę internetową**, dokonaj wymaganych zmian w konfiguracji aplikacji, a następnie wybierz pozycję **Zapisz**.

    Ewentualnie, aby usunąć aplikację, wybierz opcję **Usuń stronę**.

## <a name="appendix"></a>Dodatek

### <a name="troubleshooting"></a>Rozwiązywanie problemów

Jeśli witryna sieci web nie jest renderowana prawidłowo po jej osadzeniu w aplikacji Finance and Operation lub jeśli zostanie wyświetlony komunikat o błędzie informujący o odmowie połączenia adresu URL, witryna internetowa jest prawdopodobnie skonfigurowana tak, aby uniemożliwić jej osadzenie w ramce iframe. Aby określić, czy witryna internetowa może zostać osadzona, należy wykonać następujące kroki.

1. Otwórz narzędzia deweloperskie przeglądarki, która jest w użyciu.
2. Na karcie **Sieć** znajdź i wybierz odpowiedź z osadzonej witryny.
3. Na karcie **Nagłówki**, w obszarze **Nagłówki odpowiedzi**, poszukaj nagłówka **x-frame-options**. Jeśli w nagłówkach odpowiedzi znajduje się nagłówek **x-frame-options** i ma wartość **DENY** lub **SAMEORIGIN**, tej witryny internetowej obecnie nie można osadzić. Jej bezpieczne osadzenie musi zostać uzgodnione z właścicielem aplikacji.

### <a name="developer-modeling-a-website-on-a-form"></a>[Deweloper] Modelowanie witryny internetowej w formularzu

Chociaż ten artykuł jest skoncentrowany na osadzaniu aplikacji lub witryn internetowych innych firm za pomocą personalizacji, deweloperzy mogą również osadzać je w formularzu, korzystając ze środowiska deweloperskiego Visual Studio. Należy tylko dodać do formularza formant **WebsiteHostControl**. Właściwości metadanych dostępne dla formantu zapewniają te same możliwości, co funkcje personalizacji.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
