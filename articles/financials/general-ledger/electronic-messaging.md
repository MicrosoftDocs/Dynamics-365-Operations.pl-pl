---
title: "Obsługa wiadomości elektronicznych"
description: "Ten temat zawiera przegląd i informacje o konfiguracji dla obsługi wiadomości elektronicznych w Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: 232398a6c4193d0074881e26fff361deb9784bf2
ms.openlocfilehash: 082ad886f40a52457900523f44158da3ed939458
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---

# <a name="electronic-messaging"></a>Obsługa wiadomości elektronicznych

[!include [banner](../includes/banner.md)]

Ten temat zawiera przegląd i informacje o konfiguracji dla obsługi wiadomości elektronicznych w Microsoft Dynamics 365 for Finance and Operations.

W ostatnim czasie władze i prawodawcy różnych krajów i regionów na całym świecie wprowadzili w życie wymagania w zakresie sprawozdawczości dla firm, które są zarejestrowane w tych krajach lub regionach. Celem tych wymagań jest możliwość uzyskiwania od tych firm danych w formie elektronicznej bezpośrednio z systemów, w których są księgowane, zapisywane i przetwarzane.

Funkcjonalność wiadomości elektroniczne w Finance and Operations obsługuje wiele procesów elektronicznej współpracy między Finance and Operations a systemami administracji państwowej do raportowania, przesyłania i odbierania oficjalnych informacji.

Funkcje wiadomości elektroniczne są zintegrowane z modułem **raportowania elektronicznego** (ER). Dlatego należy skonfigurować formaty ER dla wiadomości elektronicznych. Aby uzyskać więcej informacji, zobacz [Raportowanie elektroniczne (ER)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

Obsługa wiadomości elektronicznych opiera się na następujących jednostkach:

- **Wiadomość elektroniczna** — raport lub zgłoszenie, które powinny być zgłoszone i/lub transmitowane wewnętrznie. Przykładem jest raport, który zostanie wysłany do urzędu skarbowego.
- **Elementy wiadomości elektronicznych** — rekordy, które powinny być uwzględnione w komunikacie o błędzie.
- **Przetwarzanie wiadomości elektronicznych** — łańcuch akcji, połączonych lub nie, który powinien zostać uruchomiony, aby zebrać wymagane dane, wygenerować raporty, przechowywać dane w magazynie obiektów Blob Microsoft Azure, przekazywać raporty poza systemem, aktualizować bazę danych na podstawie uzyskanych informacji.

Na poniższej ilustracji przedstawiono przepływ danych do obsługi wiadomości elektronicznych.

![Obsługa wiadomości elektronicznych: przepływ danych](media/electronic-messaging-data-flow.png)

Funkcji wiadomości elektronicznych obsługuje następujące scenariusze:

- Ręczne tworzenie wiadomości i generowanie raportów, które opierają się na skojarzonych formatach eksportowania ER różnego typu: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, tekst i Microsoft Word.
- Automatyczne tworzy i przetwarza wiadomości na podstawie żądanych informacji i otrzymanych z urzędu za pośrednictwem skojarzonego formatu importu ER.
- Gromadzenie i przetwarzanie informacji ze źródła danych (Tabela Finance and Operations) jako elementów wiadomości.
- Przechowuj dodatkowe informacje i oceniaj różne wartości poprzez wywołanie specjalnie zdefiniowanych wykonywalnych klas w odniesieniu do wiadomości lub elementów wiadomości.
- Agregacja informacji zbieranych w elementach wiadomości, podział informacji według wiadomości i generowanie reportów w skojarzonych formatach eksportowania ER.
- Przekazywanie raportów generowanych do usługi sieci web przy użyciu informacji o zabezpieczeniach przechowywanych w Azure Key Vault.
- Uzyskiwanie odpowiedzi z usługi sieci web, interpretowanie odpowiedzi i aktualizowanie danych w Finance and Operations w razie potrzeby.
- Przechowywanie i przeglądanie wszystkich generowanych raportów.
- Przechowywanie i przeglądanie wszystkich informacji dziennika powiązanych z działaniami, które są uruchamiane dla wiadomości lub elementu wiadomości.
- Kontrolowanie przetwarzania za pomocą różnych stanów wiadomości i stanów elementu wiadomości.

## <a name="set-up-electronic-messaging"></a>Konfigurowanie wiadomości elektronicznych

Wiadomości elektroniczne mogą ułatwić obsługę różnych elektronicznych procesów raportowania dla różnych typów dokumentów. W niektórych scenariuszach złożonych wiadomości elektroniczne ustawiono tak, aby miały kombinację wielu statusów wiadomości, statusów elementów wiadomości, działań, dodatkowych pól i wykonywalnych klas. W tych scenariuszach pakiety jednostek danych są dostępne do importu. Korzystając z tych pakietów jednostek danych należy importować je do firmy przy użyciu narzędzia do zarządzania danymi. Aby uzyskać więcej informacji dotyczących sposobu używania narzędzia do zarządzania danymi, zobacz [zarządzanie danymi](../../dev-itpro/data-entities/data-entities-data-packages.md).

Jeśli nie importujesz pakietu jednostek danych, możesz ręcznie ustawić funkcje wiadomości elektronicznych. W takim przypadku należy skonfigurować następujące elementy: 

- [Sekwencje numerów](#number-sequences)
- [Typy i stany elementów wiadomości](#message-item-types-and-statuses)
- [Stany wiadomości](#message-statuses)
- [Dodatkowe pola](#additional-fields)
- [Ustawienia klasy wykonywalnej](#executable-class-settings)
- [Akcje wypełniania rekordów](#populate-records-actions)
- [Ustawienia usługi sieci Web](#web-service-settings)
- [Akcje przetwarzania wiadomości](#message-processing-actions)
- [Przetwarzanie wiadomości elektronicznych](#electronic-message-processing)

Poniższe sekcje zawierają więcej informacji o każdym z tych elementów.

### <a name="number-sequences"></a>Numery kolejne

Ustaw sekwencje numerów, zarówno dla wiadomości i elementów wiadomości. Sekwencje numerów umożliwiają automatyczne numerowanie wiadomości i elementów wiadomości, a numery, które są przypisane, będą stanowić unikatowe identyfikatory dla wiadomości i elementów wiadomości w systemie. Można ustawić sekwencje numerów dla elektronicznego przesyłania wiadomości na stronie **Parametry księgi głównej** (**księga główna**\>**Ustawienia księgi**\>**Parametry księgi głównej**).

### <a name="message-item-types-and-statuses"></a>Typy i stany elementów wiadomości

Typy elementów wiadomości określają typy rekordów, które będą używane w wiadomościach elektronicznych. Można skonfigurować typy elementów wiadomości na stronie **Typy elementów wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Typy elementów wiadomości**).

Stany elementu wiadomości określają stany, które będą stosowane w elementach wiadomości w przetwarzaniu, które konfigurujesz. Można skonfigurować typy elementów wiadomości na stronie **Stany elementów wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Stany elementów wiadomości**).

### <a name="message-statuses"></a>Stany wiadomości

Ustaw stany wiadomości, które mają być dostępne w przetwarzania wiadomości. Można skonfigurować stany wiadomości na stronie **Stany wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Stany wiadomości**).

### <a name="additional-fields"></a>Dodatkowe pola

Funkcja wiadomości elektronicznych umożliwia wypełnianie rekordów na podstawie tabeli transakcji. W ten sposób można przygotować rekordy do raportowania i je raportować. Czasami nie ma wystarczających informacji w tabeli transakcji do zraportowania rekordu zgodnie z wymaganiami raportu. Możesz wypełnić wszystkie informacje, które muszą zostać przekazane dla rekordu, ustawiając dodatkowe pola. Dodatkowe pola mogą być skojarzone zarówno z wiadomościami, jak i elementami wiadomości. Możesz ustawić dodatkowe pola na stronie **dodatkowe pola** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**dodatkowe pola**).

W poniższej tabeli opisano pola znajdujące się na stronie **Dodatkowe pola**.

| Pole                | opis |
|----------------------|-------------|
| Nazwa pola           | Wprowadź nazwę dodatkowego atrybutu elementów wiadomości, które są związane z procesem. Ta nazwa jest wyświetlana w interfejsie użytkownika podczas pracy z procesem. Może również być używana w konfiguracjach ER, które są związane z procesem. |
| opis          | Wprowadź opis dodatkowego atrybutu elementów wiadomości, które są związane z procesem. |
| Wartość pola          | Wprowadź wartość pola, która ma być użyta w odniesieniu do elementu wiadomości podczas raportowania. |
| Opis pola    | Wprowadź opis pola, który ma być użyty w odniesieniu do elementu wiadomości podczas raportowania. |
| Typ konta         | Niektóre wartości pola dodatkowego mogą być ograniczone do określonych typów kont. Wybierz jedną z następujących wartości: **wszystkie**, **odbiorca** lub **dostawca**. |
| Kod konta         | Jeśli wybrano opcję **odbiorcy** lub **dostawcy** w polu **typ konta**, możesz dodatkowo ograniczyć użycie wartości pól do określonej grupy lub tabeli. |
| Numer konta/grupy | W przypadku wybrania **odbiorcy** lub **dostawcy** w polu **typ konta** i po wprowadzeniu grupy lub tabeli w polu **kod konta** można wprowadzić określoną grupę lub kontrahenta w tym polu. |
| Weszła w życie            | Umożliwia wybranie daty rozpoczęcia uwzględniania wartości. |
| Data wygaśnięcia           | Umożliwia wybranie daty zakończenia uwzględniania wartości. |

### <a name="executable-class-settings"></a>Ustawienia klasy wykonywalnej

Klasa wykonywalna jest metodą X ++ lub klasą, której przetwarzanie wiadomości elektronicznej można wywołać w odniesieniu do akcji, jeżeli ocena jest wymagana dla procesu.

Można ręcznie ustawić klasę wykonywalną na stronie **Ustawienia klasy wykonywalnej** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**Ustawienia klasy wykonywalnej**). Utwórz wiersz i ustaw następujące pola.

| Pole                 | opis |
|-----------------------|-------------|
| Klasa wykonywalna      | Wprowadź nazwę, która będzie używana podczas akcji przetwarzania wiadomości, w związku z którą będzie wywoływana ta klasa. |
| opis           | Wpisz opis klasy wykonywalnej. |
| Nazwa klasy wykonywalnej | Wybierz klasę wykonywalną X ++. |
| Poziom wykonywania       | To pole jest ustawiane automatycznie, ponieważ wartość powinna być wstępnie zdefiniowana dla wybranej klasy wykonywalnej. To pole ogranicza poziom, przy którym jest uruchamiana powiązana ocena. |
| Opis klasy     | To pole jest ustawiane automatycznie, ponieważ wartość powinna być wstępnie zdefiniowana dla wybranej klasy wykonywalnej. |

### <a name="populate-records-actions"></a>Akcje wypełniania rekordów

Używaj akcji wypełniania rekordów, aby skonfigurować akcje, które dodają rekordy do tabeli elementów wiadomości, dzięki czemu można je dodawać do wiadomości elektronicznych. Na przykład, jeśli wiadomość elektroniczna musi zgłosić fakturę dla odbiorcy, należy skonfigurować akcję **wypełnienia rekordów**, która jest połączona w tabeli **arkusz faktur odbiorcy** (w polu **źródła danych**). Można ustawić akcje wypełniania rekordów na stronie **akcji wypełnienia rekordów** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**akcje wypełniania rekordów**). Utwórz nowy rekord dla każdej akcji, która ma dodawać rekordy do tabeli i ustaw następujące pola.

| Pole       | opis                                                               |
|-------------|---------------------------------------------------------------------------|
| Nazwisko        | Wprowadź nazwę akcji, która wypełnia rekordy w procesie.       |
| opis | Wprowadź opis akcji, która wypełnia rekordy w procesie. |

Na skróconej karcie **ustawienia źródeł danych** dodaj wiersz dla każdego źródła danych, które jest używane w procesie, a następnie ustaw następujące pola.

| Pole                  | opis |
|------------------------|-------------|
| Nazwisko                   | Wprowadź nazwę źródła danych. |
| Typ elementu wiadomości      | Wybierz typ elementu wiadomości, który ma być używany podczas tworzenia rekordów źródła danych. |
| Typ konta           | Wybierz typ konta, który ma być skojarzony z rekordami ze źródła danych. |
| Nazwa tabeli głównej      | Zaznacz tabelę w Finance and Operations, która ma być źródłem danych. |
| Pole numeru dokumentu  | Wybierz pole, z którego ma być pobrany numer dokumentu w wybranej tabeli. |
| Pole daty dokumentu    | Wybierz pole, z którego ma być pobrana data dokumentu w wybranej tabeli. |
| Pole konta dokumentu | Wybierz pole, z którego ma być pobrane konto dokumentu w wybranej tabeli. |
| Zapytanie użytkownika             | Jeśli to pole wyboru jest zaznaczone, istnieje możliwość ustawienia kwerendy przez zaznaczenie **Edytuj kwerendę** powyżej siatki. W przeciwnym razie będą wypełnione wszystkie rekordy ze źródła danych. |

### <a name="web-service-settings"></a>Ustawienia usługi sieci Web

Ustawienia usługi sieci web umożliwiają konfigurowanie bezpośredniego przesyłania danych do usługi sieci web. Istnieje możliwość ustawienia usługi sieci web na stronie **ustawienia usługi sieci Web** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**ustawienia usługi sieci Web**) .

W poniższej tabeli opisano pola znajdujące się na stronie **Ustawienia usługi sieci Web**.

| Pole                   | opis |
|-------------------------|-------------|
| Usługa sieci Web             | Wprowadź nazwę składnika usługi sieci Web. |
| opis             | Umożliwia wprowadzanie opisu usługi sieci web. |
| Adres internetowy        | Umożliwia wprowadzenie adresu internetowego usługi sieci Web. |
| Certyfikat             | Wybierz certyfikat Key Vault, który został wcześniej skonfigurowany. |
| Typ odpowiedzi — XML | Ustaw tę opcję na **Tak** w przypadku typu odpowiedzi XML. |
| Metoda żądania          | Określ metodę żądania. HTTP definiuje zestaw metod zapytania, który wskazuje akcję, która powinna być wykonywana dla danego zasobu. Metoda może być **GET**, **POST**, lub inną metodą HTTP. |
| Nagłówki żądań         | Określ żądania nagłówka. Żądanie nagłówka jest nagłówkiem protokołu HTTP, który może zostać użyty w żądaniu HTTP, a który nie jest powiązany z zawartością wiadomości. |
| Akceptuj kodowanie         | Określ akceptowanie kodowania. Nagłówek HTTP żądania akceptowania kodowania anonsuje kodowanie zawartości, które klient może zrozumieć. To kodowanie zawartości jest zazwyczaj algorytmem kompresji. |
| Typ zawartości            | Określ typ zawartości: Nagłówek jednostki typu zawartości wskazuje typ nośnika zasobu. |

### <a name="message-processing-actions"></a>Akcje przetwarzania wiadomości

Czynności przetwarzania wiadomości służą do tworzenia akcji dla procesów i konfigurowania ich parametrów. Można skonfigurować przetwarzanie akcji na stronie **Akcje przetwarzania wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Akcje przetwarzania wiadomości**).

W poniższych tabelach opisano pola na stronie **Akcje przetwarzania wiadomości**.

#### <a name="general-fasttab"></a>Skrócona karta Ogólne

| Pole                   | opis |
|-------------------------|-------------|
| Typ akcji             | Umożliwia wybranie typu akcji. Aby uzyskać informacje o dostępnych opcjach, zobacz sekcję [Typy akcji przetwarzania wiadomości](#message-processing-action-types). |
| Mapowanie formatu          | Wybierz format ER, który powinien zostać wywołany dla akcji. To pole jest dostępne tylko dla działań tupu **Eksport raportowania elektronicznego**, **Import raportowania elektronicznego**, i **Wiadomość dotycząca eksportu raportowania elektronicznego**. |
| Typ elementu wiadomości       | Wybierz typ rekordów, dla których powinna być oceniana akcja. To pole jest dostępne dla działań tupu **Poziom wykonywania elementu wiadomości**, **Eksport raportowania elektronicznego**, i **Import raportowania elektronicznego** i innych typów. Jeśli to pole pozostanie puste, wszystkie typy elementów wiadomości zdefiniowanych dla przetwarzania wiadomości są sprawdzane. |
| Klasa wykonywalna        | Wybierz ustawienia klasy wykonywalnej utworzone wcześniej. To pole jest dostępne tylko dla działań typu **Poziom wykonywania elementu wiadomości** i **Poziom wykonywania elementu wiadomości**. |
| Akcja wypełniania rekordów | Wybierz akcję Wypełnij rekordy, która została wcześniej skonfigurowana. To pole jest dostępne tylko dla działań typu **Wypełnij rekordy**. |

##### <a name="message-processing-action-types"></a>Typy akcji przetwarzania wiadomości

W polu **Typ akcji** są dostępne następujące opcje:

- **Wypełnij rekordy** — akcję **Wypełnij rekordy** należy wcześniej skonfigurować. Skojarz ją z akcją typu **Wypełnij rekordy**, aby umożliwić jej przetwarzanie. Zakłada się, że ten typ akcji jest używany dla pierwszej akcji w przetwarzaniu wiadomości. Z tego względu tylko stan wyniku można skonfigurować dla tego typu akcji. Nie można ustawić stanu początkowego.
- **Utwórz wiadomość** — użycie tego typu umożliwia użytkownikom ręczne tworzenia wiadomości na stronie **Wiadomość elektroniczna**. Stanu wyniku nie można skonfigurować dla tego typu akcji.
- **Poziom wykonywania wiadomości** — Użyj tego typu, aby skonfigurować wykonywalną klasę, która powinna zostać oceniona na poziomie wiadomości.
- **Poziom wykonywania elementu wiadomości** — Użyj tego typu, aby skonfigurować wykonywalną klasę, która powinna zostać oceniona na poziomie elementu wiadomości.
- **Eksport raportowania elektronicznego** — użyj tego szablonu dla akcji, które powinny generować raport, który opiera się na eksportowaniu konfiguracji ER na poziomie elementu wiadomości.
- **Wiadomość dotycząca eksportu raportowania elektronicznego** — użyj tego szablonu dla akcji, które powinny generować raport, który opiera się na eksportowaniu konfiguracji ER na poziomie wiadomości (np. kiedy wiadomość nie ma żadnego elementu wiadomości).
- **Import raportowania elektronicznego** — użyj tego szablonu dla akcji, które powinny generować raport, który opiera się na importowaniu konfiguracji ER.
- **Wiadomość dotycząca przetwarzania poziomu użytkownika** — użyj tego szablonu dla akcji, które zakładają wykonywanie niektórych akcji ręcznie przez użytkownika. Na przykład użytkownik może aktualizować stan wiadomości.
- **Przetwarzanie użytkownika** — użyj tego szablonu dla akcji, które zakładają wykonywanie niektórych akcji ręcznie przez użytkownika. Na przykład użytkownik może aktualizować stan elementów wiadomości.
- **Usługa sieci Web** — użyj tego szablonu dla akcji, które powinny przekazywać wygenerowany raport do usługi sieci web. Ten typ akcji nie jest używany do raportów komunikacji związanej z fakturami sprzedaży/zakupu we Włoszech.
- **Weryfikacja żądania** — użyj tego typu, aby żądać weryfikacji z serwera.

#### <a name="initial-statuses-fasttab"></a>Skrócona karta Stany początkowe

> [!NOTE]
> Skrócona karta **Stany początkowe** nie jest dostępna dla akcji, które mają typ początkowy **Wypełnij rekordy** lub **Utwórz wiadomość**.

| Pole               | opis                                                                                         |
|---------------------|-----------------------------------------------------------------------------------------------------|
| Stan elementu wiadomości | Wybierz status elementu wiadomości, dla której ma być oceniana wybrana akcji przetwarzania wiadomości. |
| opis         | Opis wybranego stanu elementu wiadomości.                                                  |

#### <a name="result-statuses-fasttab"></a>Skrócona karta Stany wyników

| Pole               | opis |
|---------------------|-------------|
| Stan komunikatu      | Wybierz status wiadomości, dla której ma być oceniana wybrana akcji przetwarzania wiadomości. To pole jest dostępne tylko dla akcji przetwarzania wiadomości, które zostały ocenione na poziomie wiadomości. Na przykład, jest dostępne dla działań typu **Eksport raportowania elektronicznego** i **Import raportowania elektronicznego**. Nie jest dostępne dla akcji typu **Przetwarzanie użytkownika** i **Poziom wykonywania elementu wiadomości**. |
| opis         | Opis wybranego stanu wiadomości. |
| Typ odpowiedzi       | Typ odpowiedzi wybranego stanu wiadomości. |
| Stan elementu wiadomości | Wybierz stany wynikowe, które powinny być dostępne po ocenie wybranej akcji przetwarzania wiadomości. To pole jest dostępne tylko dla akcji przetwarzania wiadomości, które zostały ocenione na poziomie elementu wiadomości. Na przykład jest dostępne dla akcji typu **Przetwarzanie użytkownika** i **Poziom wykonywania elementu wiadomości**. W przypadku akcji przetwarzania, które są oceniane na poziomie wiadomości, to pole wyświetla stan pozycji wiadomości, który został skonfigurowany dla stanu wybranej wiadomości. |

### <a name="electronic-message-processing"></a>Przetwarzanie wiadomości elektronicznych

Wiadomość elektroniczna jest pojęciem podstawowych funkcji Wiadomości elektroniczne. Agreguje akcje, które mają być wykonywane dla wiadomości elektronicznych. Akcje można połączyć za pomocą stanu początkowego i stanu wynikowego. Ewentualnie akcje typu **Przetwarzanie użytkownika** mogą być rozpoczynane niezależnie. Na stronie **Przetwarzanie wiadomości elektronicznych** (**Podatek**\>**Ustawienia**\>**Wiadomości elektroniczne**\>**Przetwarzanie wiadomości elektronicznych**), można również wybrać dodatkowe pola, które mają być obsługiwane do przetwarzania.

Skrócona karta **Akcja** pozwala na dodanie wstępnie zdefiniowanych akcji do przetwarzania. Można określić, czy akcję należy uruchomić osobno lub czy może być zainicjowana przez przetwarzanie. (Akcje użytkownika muszą być uruchamiane oddzielnie).

Skrócona karta **Dodatkowe pola elementów wiadomości** pozwala na dodanie wstępnie zdefiniowanych dodatkowych pól, które są związane z elementami wiadomości. Należy dodać dodatkowe pola dla każdego typu elementu wiadomości do którego odnoszą się pola.

Skrócona karta **Dodatkowe pola wiadomości** pozwala na dodanie wstępnie zdefiniowanych dodatkowych pól, które są związane z wiadomościami.

Skrócona karta **Role zabezpieczeń** pozwala skonfigurować role zabezpieczeń, które są wstępnie zdefiniowane w systemie do określonego przetwarzania. Użytkownicy, którzy mają określoną rolę widzieli tylko przetwarzanie zdefiniowane dla tej roli.

Skrócona karta **Partia** umożliwia skonfigurowanie przetwarzania do pracy w systemie przetwarzania wsadowego.

## <a name="work-with-electronic-messages-functionality"></a>Praca z funkcją Wiadomości elektroniczne

Podczas pracy na poziomie komunikatu strona **Wiadomości elektroniczne** (**podatek**\>**zapytania i raporty**\>**wiadomości elektroniczne**\>**Wiadomości elektroniczne**) jest bardziej użyteczna. Podczas pracy na poziomie zbiorów danych (element wiadomości), strona **Elementy wiadomości elektronicznych** (**podatek**\>**zapytania i raporty**\>**wiadomości elektroniczne**\>**Elementy wiadomości elektronicznych**) jest bardziej użyteczna.

### <a name="electronic-messages"></a>Wiadomości elektroniczne

Strona **Wiadomości elektroniczne** przedstawia przetwarzanie, które dostępne w zależności od roli użytkownika. Role zabezpieczeń są skojarzone z przetwarzaniem w ustawieniach tego przetwarzania. Dla każdego dostępnego przetwarzania strona pokazuje wiadomości elektronicznych i informacje związane z nimi.

Skrócona karta **Wiadomości** pokazuje wiadomości elektroniczne dla wybranego przetwarzania. W zależności od stanu wybranej wiadomości i wstępnie zdefiniowanego przetwarzania możesz uruchomić niektóre akcje, wybierając przyciski nas siatką:

- **Nowy** – ten przycisk jest skojarzony z akcjami typu **Utwórz wiadomość**.
- **Usuń** — ten przycisk jest dostępny, jeśli jest zaznaczone pole wyboru **Zezwalaj na usuwanie** dla bieżącego stanu wybranej wiadomości.
- **Generuj raport** — ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca eksportu raportowania elektronicznego**.
- **Wyślij raport** – ten przycisk jest skojarzony z akcjami typu **Usługa sieci web**.
- **Aktualizuj stan** — ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca przetwarzania poziomu użytkownika** typu.
- **Element wiadomości** – otwórz stronę **Elementy wiadomości elektronicznej**.

Skrócona karta **Dziennik akcji** wyświetla informacje o wszystkich akcjach uruchomionych dla wybranej wiadomości.

Skrócona karta **Dodatkowe pola wiadomości** pokazuje wszystkie dodatkowe pola, które są zdefiniowane dla wiadomości w ustawieniach przetwarzania. Pokazuje także wartości z tych dodatkowych pól.

Skrócona karta **Elementy wiadomości** pokazuje wszystkie elementy wiadomości, które są powiązane z wybraną wiadomością.

Można przejrzeć wszystkie załączniki wybranej wiadomości. Załączniki to raporty, które zostały już wygenerowane i odebrane. Zaznacz wiadomość, aby przejrzeć załączniki, a następnie wybierz przycisk **Załącznik** w okienku akcji.

![Przycisk Załącznik](media/attachment-icon.png)

Strona **Załączniki** pokazane wszystkie załączniki, które są związane z wiadomością. Aby wyświetlić plik, wybierz go z listy po lewej stronie, a następnie wybierz **Otwórz** w okienku akcji.

![Przycisk Otwórz](media/open-button.png)

Aby przejrzeć załącznik, który jest powiązany z określoną akcją uruchomioną wcześniej dla wiadomości, zaznacz wiadomość na stronie **Wiadomości elektroniczne**, a następnie wybierz skróconą kartę **Dziennik akcji**, wybierz akcję. Następnie wybierz przycisk **Załącznik** w okienku akcji.

Można również uruchomić przez zaznaczenie całego przetwarzania lub po prostu określonej akcji, wybierając **Uruchom przetwarzanie** w okienku akcji.

### <a name="electronic-message-items"></a>Elementy wiadomości elektronicznych

Strona **Elementy wiadomości elektronicznych** przedstawia wszystkie elementy wiadomości i dziennika akcji, które zostały wykonywane dla każdego elementu wiadomości. Zawiera także dodatkowe pola, które są zdefiniowane dla elementów wiadomości oraz wartości tych dodatkowych pól.

W poniższej tabeli opisano pola znajdujące się na karcie **Elementy wiadomości**.

<table>
<thead>
<tr>
<th>Pole</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Przetwarzanie</td>
<td>Nazwa przetwarzania, która została użyta do utworzenia elementu wiadomości.</td>
</tr>
<tr>
<td>Element wiadomości</td>
<td>Identyfikator elementu wiadomości. Identyfikator jest przypisywany automatycznie na podstawie numeru sekwencji <strong>Elementu wiadomości</strong> określonego na stronie <strong>Parametry księgi głównej</strong>.</td>
</tr>
<tr>
<td>Data elementu wiadomości</td>
<td>Data utworzenia elementu wiadomości.</td>
</tr>
<tr>
<td>Typ elementu wiadomości</td>
<td>Typ elementu wiadomości. Można skonfigurować kilka typów elementów wiadomości dla tego samego przetwarzanie (na przykład <strong>Faktury przychodzące </strong> i <strong>Faktury wychodzące</strong>). To pole może być wypełnione automatycznie tylko wtedy, gdy faktura jest dodawana do tabeli Elementy wiadomości.</td>
</tr>
<tr>
<td>Stan elementu wiadomości</td>
<td>Rzeczywisty stan elementu wiadomości. Dostępne stany różnią się w zależności od typu elementu wiadomości. Oto kilka przykładów:
<ul>
<li><strong>Wypełnione</strong> — rekord został dodany do tabeli elementów wiadomości.</li>
<li><strong>Oceniane</strong> — dodatkowe atrybuty zostały obliczone dla towaru wiadomości.</li>
<li><strong>Zgłoszone</strong> — element wiadomości został pomyślnie dodany do raportu.</li>
<li><strong>Wykluczone</strong> — ten stan mogą być przydatny w przypadku, gdy trzeba wykluczyć niektóre elementy wiadomości z raportu przed jego wyeksportowaniem.</li>
</ul>
</td>
</tr>
<tr>
<td>Data transmisji</td>
<td>W przypadku przetwarzania, które automatycznie przesyła wygenerowany raport poza system, data, kiedy wiadomość została przekazana.</td>
</tr>
<tr>
<td>Numer dokumentu</td>
<td>To pole jest wypełniane automatycznie na podstawie konfiguracji akcji wypełniania rekordu. To pole może być wypełnione automatycznie tylko wtedy, gdy faktura jest dodawana do tabeli Elementy wiadomości.</td>
</tr>
<tr>
<td>Numer konta</td>
<td>Numer konta odbiorcy lub dostawcy (lub wartość innego pola, w zależności od pola, które jest określone w akcji <strong>Wypełnij rekordy</strong>). To pole może być wypełnione automatycznie tylko wtedy, gdy faktura jest dodawana do tabeli Elementy wiadomości.</td>
</tr>
<tr>
<td>Wiadomość</td>
<td>Numer wiadomości. Numer jest przypisywany automatycznie na podstawie numeru sekwencji <strong>Wiadomość</strong> określonego na stronie <strong>Parametry księgi głównej</strong>.</td>
</tr>
<tr>
<td>Stan komunikatu</td>
<td>Rzeczywisty stan wiadomości elektronicznej.</td>
</tr>
<tr>
<td>Następna akcja</td>
<td>Następne akcje, które mogą być zainicjowane dla bieżącego stanu elementu wiadomości.</td>
</tr>
</tbody>
</table>

Karta **Dodatkowe pola** pokazuje dodatkowe pola dla elementu wybranej wiadomości i ich wartości.

#### <a name="run-processing"></a>Uruchom przetwarzanie

Wybierz **Uruchom przetwarzanie** w okienku akcji, aby uruchomić przetwarzania elementów wiadomości. Aby uruchomić określoną akcję w oknie dialogowym **Uruchom przetwarzanie** ustaw opcję **Wybierz akcję** na **tak**, a następnie wybierz odpowiednią akcję. Aby uruchomić całe przetwarzanie, zostaw opcję **Wybierz akcję** na **Nie**.

#### <a name="generate-report"></a>Generuj raport

Wybierz **Wygeneruj raport** w okienku akcji, aby wygenerować raport. Ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca eksportu raportowania elektronicznego**.

#### <a name="update-status"></a>Aktualizacja stanu

Wybierz **Aktualizacja stanu** w okienku akcji, aby zaktualizować stan jednego lub kilku elementów wiadomości. W oknie dialogowym **Aktualizacja stanu** użyj skróconej karty **Rekordy do uwzględnienia** do wybierania elementów wiadomości do aktualizacji. Upewnij się, że poprawnie zdefiniowano kryteria wyboru, ponieważ stany elementów wiadomości zostaną zaktualizowane zgodnie z tymi kryteriami, początkowy stan wybranej akcji oraz wartość **Nowy stan** zostaną ustawiona. Po zakończeniu aktualizacji stanu będzie trudno określić elementy, które właśnie zostały zaktualizowane. W związku z tym będzie trudno cofnąć aktualizacje stanu.

#### <a name="electronic-messages"></a>Wiadomości elektroniczne

Wybierz **Wiadomość elektroniczna** w okienku akcji, aby przejrzeć wiadomość elektroniczną powiązaną z pozycją wybranej wiadomości.

Można także przejrzeć wszystkie pliki, które odpowiadają elementowi wiadomości. Wybierz pole **Wiadomość** dla elementu wiadomości lub wybierz **Wiadomość elektroniczna** w okienku akcji. Na stronie **Wiadomość elektroniczna** wybierz wiadomość, aby przejrzeć raport dla, a następnie wybierz przycisk **Załącznik** w okienku akcji.

![Przycisk Załącznik](media/attachment-icon.png)

Strona **Załączniki** pokazane wszystkie załączniki, które są związane z wiadomością. Aby wyświetlić plik, wybierz go z listy po lewej stronie, a następnie wybierz **Otwórz** w okienku akcji.

![Przycisk Otwórz](media/open-button.png)

#### <a name="original-document"></a>Dokument oryginalny

Wybierz **Oryginalny dokument** w okienku akcji, aby otworzyć oryginalny dokument dla elementu wybranej wiadomości.

## <a name="example"></a>Przykład

Po utworzeniu formatu ER, przyporządkowaniu go do źródeł danych i wykonaniu go, można uruchomić go za pomocą obszaru roboczego **Raportowanie elektroniczne** . Raport jest generowany, który można zapisać lokalnie.

Aby kontrolować następujące aspekty procesu raportowania, należy skonfigurować przetwarzanie wiadomości elektronicznych:

- Informacje dziennika o tym, kto wygenerował raport.
- Rejestruj po wygenerowaniu raportu.
- Zapisz raporty, które zostały wygenerowane za poprzednie okresy.

Ta sekcja zawiera przykłady, które pokazują, jak można skonfigurować funkcję Wiadomości elektroniczne do tworzenia procesu generowania raportów.

### <a name="set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Konfigurowanie i uruchamianie przetwarzania do wywołania prostego formatu eksportowania ER to wygenerować raportu programu Excel

Ta sekcja zawiera przykład, który pokazuje, jak można skonfigurować wiadomości elektroniczne do generowania raportu, który jest oparty na formacie eksportowania ER do programu Excel. Aby podążać za tym przykładem, format eksportowania ER Excel musi już być utworzony, mapowany na źródła danych i zakończony. Numer sekwencji musi być skonfigurowany w wiadomościach elektronicznych.

Kiedy ustawiasz przetwarzanie, warto najpierw zdefiniować akcje przetwarzania i stany, które zostaną skonfigurowane. Na poniższej ilustracji przedstawiono, jak wygląda przetwarzanie w tym przykładzie.

![Schemat przetwarzania](media/processing-scheme.png)

#### <a name="create-message-statuses"></a>Tworzenie stanów wiadomości

1. Przejdź do menu **Podatek \>ustawienia \>wiadomości elektroniczne \>Stany wiadomości**.
2. Utwórz następujące stany wiadomości:

    - Nowy
    - Przygotowane
    - Wygenerowane

    ![Stany wiadomości](media/message-statuses.png)

3. W wierszu stanu **nowy** zaznacz pole **Zezwalaj na usuwanie**, aby umożliwić użytkownikom usuwanie wiadomości o tym stanie.

#### <a name="create-additional-fields"></a>Utwórz dodatkowe pola

1. Przejdź do menu **Podatek \>ustawienia \>wiadomości elektroniczne \>Dodatkowe pola**.
2. Dodaj dodatkowe pole i jego wartości. Oto przykład.

    ![Dodatkowe pola](media/additional-fields.png)

3. Ustaw opcję **Edycja użytkownika** jako **tak**, aby umożliwić użytkownikom edycję tego pola.

#### <a name="create-message-processing-actions"></a>Tworzenie akcji przetwarzania wiadomości

Na przykład użytkownik utworzy następujące akcje:

- **Utwórz komunikat**
- **Aktualizuj do stanu Przygotowane**
- **Generuj raport**
- **Aktualizuj do stanu początkowego** (opcjonalnie)

1. Przejdź do menu **Podatek \>ustawienia \>wiadomości elektroniczne \>Akcje przetwarzania wiadomości**.
2. Utwórz akcję o nazwie **Utwórz wiadomość**. Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Utwórz wiadomość**.
3. Tworzenie akcji o nazwie **Aktualizuj do stanu Przygotowane**i ustaw następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Wiadomość dotycząca przetwarzania poziomu użytkownika**.
    - Na skróconej karcie **początkowe stany** w polu **stan wiadomości** zaznacz **nowa**.
    - Na skróconej karcie **Stany wyników** w polu **stan wiadomości** zaznacz **Przygotowane**. W polu **typu odpowiedzi** wprowadź **Pomyślnie wykonane**.

4. Utwórz akcję o nazwie **Generuj raport**i ustaw następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Eksport raportowania elektronicznego**. W polu **mapowanie formatu** wybierz format eksportu ER. Dostępne opcje to **Excel**, **XML**, **JSON**, **Tekst** i **Inne**.
    - Na skróconej karcie **Stany początkowe** w polu **stan wiadomości** zaznacz **Przygotowane**.
    - Na skróconej karcie **Stany wyników** w polu **stan wiadomości** zaznacz **Wygenerowane**. W polu **typu odpowiedzi** wprowadź **Pomyślnie wykonane**.

    ![Akcja Generowanie raportu](media/generate-report-action.png)

5. Opcjonalnie: aby umożliwić użytkownikom ponowne generowanie raportu wiele razy, możesz utworzyć akcję **aktualizacji do stanu początkowego** i ustawić następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Wiadomość dotycząca przetwarzania poziomu użytkownika**.
    - Na skróconej karcie **Stany początkowe** w polu **stan wiadomości** zaznacz **Wygenerowane**.
    - Na skróconej karcie **Stany wyników** w polu **stan wiadomości** zaznacz **Przygotowane** lub **Nowe**. W polu **typu odpowiedzi** wprowadź **Pomyślnie wykonane**.

#### <a name="electronic-message-processing"></a>Przetwarzanie wiadomości elektronicznych

W tym przykładzie wszystkie akcje powinny być ustawione tak, żeby działały oddzielnie. Zakłada się, że każda akcja zostanie zainicjowana przez użytkownika.

1. Przejdź do menu **Podatek \>ustawienia \>wiadomości elektroniczne \>Przetwarzanie wiadomości elektronicznych**.
2. Dodaj rekord do przetwarzania i dodaj wszystkie uprzednio zdefiniowane akcje oraz dodatkowe pole.
3. Opcjonalnie: Na skróconej karcie **ról zabezpieczeń** zdefiniuj role zabezpieczeń do przetwarzania, aby ograniczyć dostęp do określonego raportowania.
4. Przejdź do menu **Podatek \>Zapytania i raporty \>wiadomości elektroniczne \>wiadomości elektroniczne**.
5. Wybierz **Nowa**, aby utworzyć wiadomość. W tym momencie można dodać daty i opis. Można też zaktualizować wartość dodatkowego pola, jeśli jest to konieczne.

    ![Tworzenie wiadomości elektronicznej](media/create-electronic-message.png)

Siatka na skróconej karcie **dziennik akcji** jest automatycznie wypełniany na podstawie dziennika wszystkich akcji wykonanych w odniesieniu do wiadomości.

Można teraz usunąć lub zaktualizować stan wiadomości. Aby zaktualizować stan wiadomości, zaznacz **aktualizuj stan**, a następnie w polu **nowy stan** zaznacz **Przygotowane**. Następnie wybierz opcję **OK**.

![Aktualizowanie stanu wiadomości](media/update-status.png)

Stan wiadomości jest ustawiony na **Przygotowane** i możesz teraz wygenerować raport, wybierając **Generowanie raportu**. Raport zostanie wygenerowany, a stan wiadomości i dziennik akcji zostaną zaktualizowane. Aby obejrzeć wygenerowany raport, naciśnij przycisk **załącznik** w okienku akcji.

