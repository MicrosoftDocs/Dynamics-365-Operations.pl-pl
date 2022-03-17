---
title: Praca z ustawieniami funkcji
description: W tym temacie wyjaśniono, jak skonfigurować funkcje fakturowania elektronicznego.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 41ffc9c7009291a55392e50c5e490d3288d122bc
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371747"
---
# <a name="work-with-feature-setups"></a>Praca z ustawieniami funkcji

[!include [banner](../includes/banner.md)]

Aby skonfigurować generowanie plików elektronicznych i innych kroków przetwarzania (na przykład pliki podpisywania cyfrowego, przesłanie ich do rządowej usługi sieci web i odebranie odpowiedzi lub przechowywanie ich), należy skonfigurować proces przetwarzania, reguły możliwości zastosowania oraz zmienne dla funkcji fakturowania elektronicznego.

Informacje o konfiguracji są łączone w pojęciach *konfiguracji funkcji* i można je tworzyć, usuwać i korygować. W przypadku ukończonych wersji funkcji fakturowania elektronicznego informacje są także dostępne.

Można utworzyć tyle elementów konfiguracji funkcji, ile jest wymaganych do zdefiniowania różnych scenariuszy generowania, przetwarzania i odbierania plików elektronicznych. Chociaż elementy konfiguracji funkcji mają niezależne akcje przetwarzania i warunki wykonywania, są tworzone jako część jednej funkcji fakturowania elektronicznego oraz dziedziczą ich cykl życia i proces wdrażania.

## <a name="add-a-feature-setup"></a>Dodaj konfigurację funkcji

1. Zaloguj się na konto usługi Regulatory Configuration Services (RCS).
2. Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
3. Na stronie **Funkcje fakturowania elektronicznego** wybierz wersję funkcji fakturowania elektronicznego o statusie **Wersja robocza**.
4. Na karcie **Konfiguracje** wybierz pozycję **Dodaj**.
5. W rozwijanym oknie dialogowym **Utwórz konfigurację funkcji** w grupie pól **Nowe** wybierz opcję Konfiguracja niestandardowa.
 
    - **Ustawienia niestandardowe** – Utwórz nową konfigurację funkcji, która ma puste kanały, pustą listę potoków przetwarzania, pustą sekcję reguł możliwości zastosowania oraz domyślny zestaw zmiennych, w zależności od typu konfiguracji.
    - **Konfiguracja z funkcji** – Tworzenie kopii innej konfiguracji funkcji w zakresie bieżącej funkcji fakturowania elektronicznego.

6. Jeśli w ostatnim kroku wybrano opcję **Ustawienia niestandardowe**, wprowadź nazwę i opis elementu konfiguracji funkcji, a następnie w grupie pól **Typ konfiguracji** wybierz jedną z następujących opcji:

    - **Przetwarzanie procesu** — wybranie tej opcji powoduje generowanie i przetwarzanie wychodzących dokumentów elektronicznych. Dla tego typu konfiguracji system tworzy pustą listę potoków przetwarzania, pustą sekcję reguł możliwości zastosowania oraz domyślny zestaw zmiennych. Nie możesz pracować z kanałami dla przychodzących dokumentów elektronicznych.
    - **Kanał danych** – Wybierz tę opcję, aby skonfigurować proces odbierania przychodzących dokumentów elektronicznych z jednego ze zdefiniowanych kanałów i przekazywania ich bezpośrednio do Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management bez dodatkowych działań. W przypadku tego typu konfiguracji system tworzy predefiniowaną listę parametrów dla kanałów danych, pustą sekcję dla reguł stosowalności oraz zestaw zmiennych domyślnych. Nie możesz dodać żadnych akcji w potoku przetwarzania.
    - **Kanał danych i potok przetwarzania** — ten typ ustawień przypomina **typ konfiguracji kanału** danych. Jednak przed przekazem przychodzącego dokumentu elektronicznego do systemu Zarządzanie finansami lub Supply Chain Management można skonfigurować dodatkowe akcje w ramach przetwarzania.

7. Jeśli w ostatnim kroku wybrano opcję **Kanał danych** lub **Kanał danych** oraz proces przetwarzania, w polu **Wybierz kanał danych** musisz wybrać kanał, z którym ma zostać dokonana integracja.
8. Wybierz opcję **Utwórz**.

Po utworzeniu konfiguracji funkcji można ją wybrać **Edytuj**.

## <a name="edit-a-feature-setup"></a>Edytuj konfigurację funkcji

W zależności od typu konfiguracji funkcji można skonfigurować proces generowania wychodzących plików elektronicznych i przesyłania ich do zewnętrznych kanałów lub odbierania dokumentów przychodzących i przekazywania ich do aplikacji finansowych lub Supply Chain Management.

### <a name="data-channel"></a>Kanał danych

Kanał *danych pobiera plik* elektroniczny i przetwarza go lub przekazuje bezpośrednio do aplikacji finansowych lub Supply Chain Management. Ta opcja nie jest dostępna w konfiguracjach funkcji typu **Proces przetwarzania**.

Aby skonfigurować kanał danych, wprowadź nazwę kanału. Następnie należy zdefiniować parametry na podstawie wybranego typu kanału. Identyfikator kanału danych musi odnosić się do zmiennej utworzonej specjalnie do identyfikowania kanału danych. Zostanie on użyty jako odwołanie w aplikacjach finansowych lub Supply Chain Management.

Na karcie **Filtr załączników** należy zdefiniować zestaw filtrów, aby pobrać określone pliki z kanału. Można utworzyć kilka wierszy, jeśli spodziewane jest, że pliki będą mieć różne rozszerzenia nazw plików lub jeśli pliki muszą być przetwarzane inaczej w zależności od nazwy pliku. Oto główne parametry:

- **Nazwa** — umożliwia wprowadzenie nazwy pliku, do którego system będzie się odnosił podczas przetwarzania. W aplikacjach finansowych i Supply Chain Management pliki można zobaczyć w dzienniku przesyłania.
- **Filtr** — Zdefiniuj filtr, aby wybrać pliki.
- **Opcjonalne** — jeśli to pole wyboru jest wyczyszone, plik jest wymagany. W takim przypadku system będzie wyświetlał komunikat o błędzie, jeśli kanały nie zawierają plików odpowiadających filtrowi. Ten parametr jest stosowany do wiadomości e-mail.

Jeśli kanał jest adresatem, a przychodzący adres e-mail zawiera kilka załączników, możesz skonfigurować reguły definiujące sposób obsługi załączników przez usługę. Usługa może traktować każdy załącznik jako oddzielną fakturę elektroniczną lub traktować jeden załącznik jako fakturę główną i wszystkie inne załączniki jako dodatki.

### <a name="processing-pipeline"></a>Potok przetwarzania

Proces *przetwarzania* to zestaw *akcji*, które są uruchamiane sekwencyjnie do czasu ich pomyślnego ukończenia. Potoku przetwarzania można użyć do skonfigurowania procesu generowania plików elektronicznych i wykonywania innych kroków (na przykład plików podpisów cyfrowych, przesyłania ich do zewnętrznych usług sieci web i analizowania odpowiedzi oraz odbierania i przetwarzania dokumentów przychodzących).

Lista akcji jest wstępnie zdefiniowana. Za pomocą przycisków **Nowe** i **Usuń** można określić kombinację akcji logicznie definiującą wymagany proces przesyłania lub odbierania dokumentów.

Ważna jest kolejność działań. Kolejność można skorygować przy użyciu przycisków **W** górę i **W dół**.

Każda akcja ma zestaw parametrów, które można konfigurować lub korygować. Określony zestaw parametrów zależy od typu akcji.

- **Akcje** – Umożliwia wybranie typu akcji.
- **Nazwa akcji** – Wprowadź nazwę akcji. Ta nazwa będzie wyświetlana w dziennikach przesyłania oraz w komunikatach w aplikacjach finansowych i Supply Chain Management.
- **Opis** — zawiera więcej szczegółów dotyczących celu akcji w procesie.
- **Włącz ponawianie prób** — po zaznaczeniu tego pola wyboru można wybrać akcję w polu **Akcja ponawiania próby** i skonfigurować dodatkowe parametry na **karcie Parametry ponawiania prób**.

    Funkcja ponawiania pozwala skonfigurować działanie usługi w przypadku, gdy nie można uruchomić określonej akcji. Jeśli na przykład zewnętrzna usługa sieci web, z jaką próbujesz się połączyć, nie odpowiada, można określić, ile razy system ma ponownie użyć połączenia, w jakim interwale i z jakiego działania ma nawiązać przetwarzanie.

- **Wyniki eksportu** — to pole wyboru można zaznaczyć dla *jednej* akcji w potoku przetwarzania. Plik elektroniczny, jaki generuje akcja w aplikacji finansowej lub Supply Chain Management, można następnie wyeksportować ze **strony dziennika przesyłania dokumentów elektronicznych**.

### <a name="applicability-rules"></a>Reguły zastosowania

*Zasady stosowania* to konfigurowalne klauzule, które zapewniają kontekst uruchamiania funkcji fakturowania elektronicznego za pośrednictwem zestawu funkcji fakturowania elektronicznego.
Dokumenty biznesowe przesyłane z finansów lub Supply Chain Management do fakturowania elektronicznego nie zawierają wyraźnego odwołania, które umożliwia zestawowi możliwości fakturowania elektronicznego wywoływanie określonej wersji funkcji fakturowania elektronicznego i określonego elementu konfiguracji funkcji w celu przetworzenia przesyłania. Jednak gdy dokument biznesowy jest poprawnie skonfigurowany, zawiera wymagane elementy, które umożliwią Fakturowanie elektroniczne określenie, która wersja funkcji fakturowania elektronicznego i potok przetwarzania muszą zostać wybrane i uruchomione.

Reguły stosowania umożliwiają usłudze fakturowania elektronicznego znalezienie dokładnych funkcji fakturowania elektronicznego, których należy użyć do przetworzenia zgłoszenia. Aby znaleźć poprawne funkcje, pola **kontekstu** z przesłanego dokumentu biznesowego są zgodne z klauzulami z reguł możliwości zastosowania.

Możesz pracować z regułami stosowalności w następujący sposób:

- Wybierz **przycisk** Nowy, aby dodać nową klauzulę do zestawu reguł możliwości zastosowania.
- Wybierz przycisk **Usuń**, aby usunąć klauzurę.
- Wybierz kilka rekordów i użyj przycisku **Grupa** lub **Rozgrupuj**, aby utworzyć kombinację elementów lub instrukcji logicznych. Na przykład wybierz wiersze, które chcesz pogrupować, a następnie wybierz klauzulę **Grupa**. Gdy klauzule są zgrupowane, do siatki jest dodawana nowa kolumna. W tej kolumnie jest określany operator logiczny dla zgrupowanych klauzul. Obsługiwane są następujące typy operatorów:

    - Equal
    - Not equal
    - Większe niż/mniejsze niż
    - Większe lub równe/Mniejsze niż lub równe
    - Contains
    - Zacznij od

    > [!NOTE]
    > Kiedy rozgrupowujesz klauzulę, zawsze zaczynaj od najbardziej wewnętrznego poziomu grupowania.

### <a name="variables"></a>Zmienne

*Zmienne zapewniają* większą elastyczność podczas konfiguracji potoku przetwarzania i przepływu danych między akcjami. Niektóre parametry akcji odnoszą się do zmiennej w celu tymczasowego przechowywania danych lub plików elektronicznych. Niektóre zmienne są używane do przekazania danych między aplikacjami finansowymi lub Supply Chain Management oraz usługą fakturowania elektronicznego.

System domyślnie tworzy kilka zmiennych. Na przykład zmienna **BusinessDocumentDataModel** zawiera dane biznesowe w strukturze JavaScript Object Notation (JSON), która jest łączona z wywołaną przez połączoną aplikację w trakcie procesu przesyłania.

Dostępne są następujące typy zmiennych:

- **Stała** — kontener do przechowywania danych tymczasowych używanych w przetwarzaniu akcji potoku.
- **Od klienta** — zawartość zmiennej jest nabywana od klienta Dynamics 365 w trakcie wykonywania procesu przesyłania.
- **Do klienta** – Zawartość zmiennej jest udostępniana do importu przez klienta Dynamics 365 podczas realizacji procesu przesyłania.
- **Typ danych** — umożliwia wybór typu danych przechowywanych w zmiennej.

### <a name="parameters"></a>Parametry

Opcja **Wyłącz redukcję danych biznesowych** służy do optymalizowania struktury ładunku danych biznesowych, które pochodzą z aplikacji finansowych lub Supply Chain Management podczas przesyłania dokumentów elektronicznych. Optymalizacja pomaga redukować ilość danych przetwarzanych w usłudze fakturowania elektronicznego w celu dalszego przekształcenia w wymagany plik elektroniczny. Domyślna wartość to **Nie**.

- **Tak** — moduł finansowy lub Supply Chain Management wyśle plik JSON **modelu faktury** lub struktury **modelu obrachunkowego** (dla Brazylii) zdefiniowanej w module **Raportowanie elektroniczne**. Wszystkie elementy modelu są wypełniane danymi biznesowymi po stronie aplikacji, niezależnie od ostatecznej struktury pliku elektronicznego. Modele zwykle zawierają więcej danych biznesowych, niż wymaga docelowa struktura pliku i może być wymagany więcej czasu na wygenerowanie tych danych w aplikacji. Wartość **Tak** w przypadku tej opcji jest wymagana w przypadku rzadkość generowania różnych plików wyjściowych w jednej konfiguracji funkcji fakturowania elektronicznego i funkcji. Wartość **Tak** jest przydatna przy rozwiązywaniu problemów związanych z scenariuszami, strukturą plików elektronicznych oraz kompletnością danych biznesowych.
- **Nie** — w ramach finansów lub Supply Chain Management usługa będzie pierwsze wywołanie bez danych biznesowych. Celem tego wywołania jest uzyskiwanie informacji o konfiguracji raportowania elektronicznego, która będzie używana do przekształcenia pliku elektronicznego w potoku przetwarzania. Te informacje są zwracane do aplikacji, która używa jej do określenia podzestawu danych biznesowych, które powinny zostać uwzględnione w pliku JSON **modelu faktury** lub **modelu obrachunkowego** (dla Brazylii). Wartość **Nie** dla tej opcji pomaga zmniejszyć ilość danych biznesowych przesyłanych przez aplikację do usługi, ponieważ aplikacja może przesłać tylko dane biznesowe wymagane do pomyślnego wygenerowania pliku elektronicznego.

### <a name="validate-a-feature-setup"></a>Sprawdź ustawienia funkcji

Możesz uruchomić walidację, aby sprawdzić spójność całej konfiguracji. Na przykład, jeśli obowiązkowy parametr akcji został pozostawiony pusty, sprawdzanie poprawności wykryje tę niespójność i zostanie wyświetlony komunikat ostrzegawczy.

- Na stronie **Ustawienia wersji funkcji** w okienku akcji wybierz opcję **Weryfikuj**.

## <a name="delete-a-feature-setup"></a>Usuń ustawienia funkcji

1. Na stronie **Funkcje fakturowania elektronicznego** wybierz wersję funkcji fakturowania elektronicznego o statusie **Wersja robocza**.
2. Na karcie **Ustawienia** wybierz opcję **Usuń**.
3. W wyświetlonym oknie komunikatu wybierz przycisk **Tak**, aby potwierdzić usunięcie konfiguracji funkcji.
