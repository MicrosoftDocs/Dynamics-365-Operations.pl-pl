---
# required metadata
title: 'Określanie celu na urządzenia, rynek i lokalizację geograficzną'
description: 'W tym temacie opisano sposób tworzenia, edytowania i zarządzania grupami odbiorców i obiektów docelowych w konstruktorze witryn Microsoft Dynamics 365 Commerce przy użyciu informacji o urządzeniach, rynku i geolokalizacji.'
author: sushma-rao
ms.date: 07/30/2021
ms.topic: overview
ms.prod: null
ms.technology: null
audience: Application User
ms.reviewer: v-chgri
ms.custom: null
ms.assetid: null
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: '2021-07-31'
ms.dyn365.ops.version: AX 10.0.21
---

# <a name="device-market-and-geolocation-targeting"></a>Określanie celu na urządzenia, rynek i lokalizację geograficzną

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób tworzenia, edytowania i zarządzania grupami odbiorców i obiektów docelowych w konstruktorze witryn Microsoft Dynamics 365 Commerce przy użyciu informacji o urządzeniach, rynku i geolokalizacji.

Dynamics 365 Commerce umożliwia personalizację odmian zawartości strony (znanej jako *cele*) dla określonych grup klientów (znanych jako *odbiorcy*), aby zwiększyć zaangażowanie i satysfakcję użytkowników. Możesz najpierw utworzyć grupę odbiorców lub cel. Jednak pomyślne środowisko kierowania wymaga obu tych składników.

Tworzysz grupy odbiorców i zarządzasz nimi w konstruktorze witryn Commerce na podstawie danych klientów, takich jak lokalizacja, informacje o urządzeniu, stan logowania i inne dynamicznie pozyskiwane informacje z żądań sieci web klientów. Można również tworzyć cele i zarządzać na moduły e-commerce i fragmenty w konstruktorze witryny Commerce.

**Zastrzeżenie:** Użytkownik jest odpowiedzialny za korzystanie z tej funkcji zgodnie ze wszystkimi obowiązującymi przepisami i regulacjami, w tym z tymi, które są związane z kierowaniem i profilowania. 

## <a name="audiences"></a>Odbiorcy

Grupa odbiorców to grupa użytkowników, a członkostwo w grupie zależy od zestawu reguł dynamicznych. Te reguły są proste testy logiczne, które są uruchamiane na informacje, które są dostępne w żądaniach klientów lub innych dostępnych segmentów. Można połączyć wiele reguł przy użyciu operatorów AND/OR.

Commerce natywnie obsługuje podstawowe segmenty, takie jak informacje o urządzeniu, stan logowania, polecanie i parametry ciągu zapytania. Obsługuje również rozszerzalne segmenty za pośrednictwem połączeń z dostawcami zewnętrznymi.

### <a name="basic-segments"></a>Segmenty podstawowe

Domyślnie dostępne są następujące segmenty, które mogą być uwzględniane w definicjach odbiorców:

- **Stan zalogowania** — sprawdzenie, czy użytkownik jest uwierzytelniony.
- **Platforma urządzeń** — test dla następujących typów urządzeń:

    - Telefon komórkowy
    - Komputer stacjonarny
    - Tablet
    - Inna

- **System operacyjny urządzenia** — test dla następujących systemów operacyjnych:

    - Windows
    - Linux
    - iOS
    - Android, Inne

- **Parametry ciągu kwerendy** — test pod kątem istnienia pary klucz-wartość w parametrze ciągu zapytania adresu URL żądania. Na przykład dla adresu URL `www.fabrikam.com/en-us/request?promo=true` można zapisać regułę, aby sprawdzić, czy parametr **promocyjny** ma wartość **true**.
- **Cookie** — przetestuj wartość pliku cookie ustawioną dla domeny w adresie URL żądania. Na przykład żądanie Fabrikam.com może zawierać plik cookie o nazwie **CustomLayout** i wartości **1**. Test plików cookie sprawdza istnienie pliku cookie, ale nie tworzy go jawnie. W poprzednim przykładzie JavaScript musi wcześniej ustawić plik cookie **CustomLayout** z innego modułu lub innego procesu biznesowego.

    > [!NOTE]
    > Upewnij się, że korzystanie z plików cookie jest zgodne z obowiązującymi przepisami prawa.

- **Polecający** — jeśli użytkownik postępuje zgodnie z linkiem do żądania strony, strona odsyłacza jest adresem URL strony, która hostowała łącze.

### <a name="extensible-segments"></a>Segmenty rozszerzalne

Commerce umożliwia rozszerzenie listy dostępnych segmentów, łącząc się z zewnętrznymi dostawcami segmentacji. Dostawca segmentacji opisze typy dostępnych segmentów. Aby uzyskać więcej informacji na temat łączenia się z dostawcą geolokalizacji lub segmentacji, zobacz [Konfigurowanie i włączanie łączników](e-commerce-extensibility/connectors.md).

> [!NOTE]
> - Jeśli dostawca zewnętrzny jest włączony, może połączyć się z usługą, która ma nieprzewidywalną wydajność. Aby zapewnić lepsze środowisko użytkownika, jeśli użytkownik zażąda strony zawierającej kierowanie, a ta strona odwołuje się do grupy odbiorców, która sprawdza dostawcę segmentu innej firmy, wyświetlana jest domyślna wersja strony.
> - Użytkownik musi wyrazić zgodę na zezwalanie na pliki cookie. Przeglądarka użytkownika następnie żąda wszystkich segmentów od odpowiednich dostawców, a wyniki są umieszczane w pliku cookie, który jest zwracany do użytkownika. Kolejne żądania do strony będą używać tych informacji do wyświetlania docelowej zawartości dla użytkownika. Aby uzyskać więcej informacji na temat zgodności plików cookie, zobacz [Zgodność z plikami cookie](cookie-compliance.md).

**Zastrzeżenie:** Jeśli włączysz tę funkcję, Twoje dane zostaną udostępnione wybranym systemom innych firm. Użytkownik kontroluje, jakie dane, jeśli w ogóle, przekazujesz stronie trzeciej. Użytkownik przyjmuje do wiadomości, że standardy przetwarzania danych i zgodności osób trzecich mogą różnić się od standardów Microsoft Dynamics 365 Commerce. Twoja prywatność jest ważna dla Microsoft. Więcej informacji na ten temat znajduje się w [Oświadczeniu o ochronie prywatności i plikach cookie](https://privacy.microsoft.com/privacystatement).

### <a name="create-an-audience-in-site-builder"></a>Tworzenie grupy odbiorców w kreatorze witryn

Aby utworzyć odbiorców w konstruktorze witryn Commerce, należy wykonać następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Odbiorcy**.
1. Wybierz pozycję **Nowy**.
1. Wprowadź nazwę grupy odbiorców. Opcjonalnie można również dodać znaczniki i opis.
1. Wybierz pozycję **Utwórz**, a następnie **dodaj nowy blok reguł**. Blok reguł to zbiór reguł, które są połączone przez warunki AND. Można również utworzyć wiele bloków reguł, które mają warunki OR między nimi.
1. Wybierz źródło danych dla segmentów, a następnie określ nazwę segmentu, operatora i wartości. Można utworzyć i usunąć więcej reguł w bloku reguł lub utworzyć i usunąć całe bloki reguł. Można również przenieść bloki reguł w górę lub w dół, zgodnie z wymaganiami.

    > [!NOTE]
    > Na liście może znajdować się maksymalnie 100 wartości, a każdy element listy może zawierać maksymalnie 50 znaków.

1. Jeśli konfiguracja grupy odbiorców jest zadowalająca, wybierz pozycję **Zakończ edycję**. Następnie możesz wybrać pozycję **Publikuj**, aby udostępnić grupę odbiorców do użycia na żywo. Możesz też opublikować grupę odbiorców wraz z celem. 

Aby edytować grupę odbiorców, wybierz hiperłącze na karcie **Odbiorcy**, a następnie wybierz pozycję **Edytuj** w wyświetlonym edytorze odbiorców. Aby wyświetlić listę obiektów docelowych i stron, które są skierowane do grupy odbiorców, wybierz grupę odbiorców w widoku listy odbiorców, a następnie wybierz pozycję **Wyświetl przypisania**. Aby usunąć grupę odbiorców w widoku listy odbiorców lub edytorze odbiorców, należy ją cofnąć, jeśli została już opublikowana, a następnie wybierz pozycję **Usuń** na pasku poleceń.

> [!NOTE]
> Odbiorcy są koncepcją na poziomie witryny w kreatorze witryn w Commerce. Możesz współużytkować tę samą grupę odbiorców w wielu celach.

## <a name="targets"></a>Cele

Celem jest środowisko użytkownika, które jest wyświetlane członkom co najmniej jednej wybranej grupy odbiorców. Może zawierać odmiany jednego lub więcej modułów na stronie lub we fragmencie. 

Można zdefiniować harmonogram dla obiektów docelowych, aby określić, jak długo powinny pozostać aktywne. Należy zauważyć, że ta akcja jest oddzielona od akcji planowania grupy publikowania, która określa, kiedy kolekcja zawartości zostanie opublikowana. Możesz też wyświetlić podgląd celów, aby zobaczyć, jak będą wyglądać dla członków wybranych grup odbiorców. Ponadto można nadać priorytet obiektom docelowym, aby określić, który obiekt docelowy powinien być wyświetlany w przypadku konfliktu.

### <a name="create-a-target"></a>Tworzenie celów

Aby utworzyć powłokę docelową dla modułów stron w kreatorze witryn Commerce, wykonaj poniższe kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Strony**. Następnie wybierz hiperłącze dla strony, na której są przeznaczone moduły.
1. Wybierz **Edytuj**, aby sprawdzić stronę do edycji.
1. W menu **Cel** wybierz pozycję **Nowy cel**, aby utworzyć nową powłokę docelową. Można utworzyć wiele obiektów docelowych na stronie, zgodnie z wymaganiami.
1. Wprowadź nazwę i opis celu, a następnie wybierz **Dalej**.
1. Wybierz **Dodaj**, aby uwzględnić odbiorców, którzy zobaczą treści docelowe, lub wykluczyć odbiorców. Następnie kliknij przycisk **Dalej**.

    > [!NOTE]
    > Przypisanie odbiorców jest opcjonalnym krokiem podczas tworzenia celu. Jednak przed opublikowaniem obiektu docelowego musisz dołączyć co najmniej jedną grupę odbiorców, aby upewnić się, że zamierzone grupy użytkowników zobaczą docelową zawartość.

1. Zdefiniuj przedział czasu wyświetlania obiektu docelowego, wybierając strefę czasową oraz daty i godziny rozpoczęcia i zakończenia. Możesz ustawić cel tak, aby był wyświetlany przez cały czas w oknie, lub można wybrać określone dni i godziny. Po zakończeniu wybierz przycisk **Dalej**.

    > [!NOTE]
    > Określone godziny i strefa czasowa są globalne. Jeśli chcesz wyznaczać cele dla różnych lokalizacji o różnych porach lub w różnych strefach czasowych, musisz utworzyć różne cele i zdefiniować żądany harmonogram dla każdej lokalizacji.

1. Przejrzyj szczegóły, a gdy wszystko wygląda poprawnie, wybierz pozycję **Utwórz środowisko docelowe**, a następnie **przejdź do celu**. Tworzona jest powłoka docelowa. Teraz można dodawać do niego moduły.
1. Wybierz moduł docelowy, wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj do bieżącego celu**. Gdy obierasz cel na moduł nadrzędny, wszystkie moduły podrzędne stają się częścią tego celu. Moduły docelowe są podświetlone na zielono.
1. Dokonaj niezbędnych aktualizacji zawartości do modułu docelowego i dodaj więcej modułów do obiektu docelowego zgodnie z wymaganiami. Wybierz **Zapisz**, żeby zapisać wszystkie zmiany.
1. Przed opublikowaniem obiektu docelowego wybierz pozycję **Podgląd** na pasku poleceń, aby go przejrzeć. Dostępne są następujące opcje:

    - **Podstawowy podgląd** — wybierz tę opcję, aby wyświetlić podgląd tylko wybranej odmiany (domyślnej strony lub obiektu docelowego), bez żadnych powiązanych grup odbiorców.
    - **Podgląd zaawansowany** — wybierz tę opcję, jeśli masz wiele obiektów docelowych na stronie i chcesz wyświetlić podgląd jako użytkownik należący do wybranego zestawu odbiorców lub w określonym dniu/godzinie. Wybierz przycisk **Dalej**, aby wybrać z listy odpowiednich odbiorców. Możesz też usunąć filtr, aby wybrać spośród wszystkich odbiorców.

1. Gdy konfiguracja docelowa jest zadowalająca, musisz opublikować stronę, aby obiekt docelowy został opublikowany. Wybierz pozycję **Publikuj**, aby obiekt docelowy został natychmiast opublikowany. Alternatywnie można użyć grupy publikowania, aby zaplanować, kiedy strona zostanie wyświetlona. Aby uzyskać informacje o grupach publikacji, zobacz temat [Praca z grupami publikacji](publish-groups.md).

Można również kierować fragmenty. Procedura jest podobna. Jednak w kroku 1 wybierz **Fragmenty** zamiast **stron** w lewym okienku nawigacji.

> [!NOTE]
> Aby uniknąć negatywnego wpływu na wskaźniki, możesz mieć eksperyment lub obiekty docelowe na stronie lub we fragmencie. Nie możesz mieć zarówno eksperymentu, jak i celów.

### <a name="manage-targets"></a>Zarządzaj celami

Aby edytować, duplikować lub usuwać obiekty docelowe, przejdź do domyślnej strony lub fragmentu i wykonaj następujące kroki.

1. W menu rozwijanym wybierz pozycję **Cel**, a następnie wybierz pozycję **Zarządzaj obiektami docelowymi**.
1. Wybierz cel do edycji, duplikatu lub usunięcia.
1. Jeśli masz wiele obiektów docelowych w tym samym module lub jeśli wiele obiektów docelowych ma sprzeczne harmonogramy, wybierz **Priorytet celów**, aby określić kolejność, w której powinny być wyświetlane. Jeśli dodasz więcej niż jeden cel na stronie lub we fragmencie, na pasku powiadomień pojawi się również przycisk **Priorytet celów**, aby przypomnieć o nadaniu priorytetu obiektom docelowym. Jeśli nie określono żadnego priorytetu, domyślnie wybierany jest ostatni cel.

### <a name="localize-targets"></a>Lokalizuj obiekty docelowe

Obiekty docelowe na stronach i we fragmentach są automatycznie uwzględniane, gdy pliki XLIFF są eksportowane i importowane do celów lokalizacji. Jeśli jednak nie są wymagane żadne ustawienia regionalne, można usunąć obiekty docelowe dla nich po zaimportowaniu zlokalizowanych plików XLIFF.

> [!NOTE]
> Obiekty docelowe są zarządzane na kanał i ustawienia regionalne. Zmiany wprowadzone w docelowych w jednym kanale lub ustawieniach regionalnych nie są automatycznie przenoszone do innych kanałów lub ustawień regionalnych.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
