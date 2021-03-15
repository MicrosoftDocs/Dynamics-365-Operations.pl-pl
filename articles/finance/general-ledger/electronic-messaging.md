---
title: Obsługa wiadomości elektronicznych
description: Ten temat zawiera przegląd informacji o konfiguracji elektronicznego przesyłania wiadomości w Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: d4ecc29e47d68129df424c4212505413cf6c8889
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968986"
---
# <a name="electronic-messaging"></a>Obsługa wiadomości elektronicznych

[!include [banner](../includes/banner.md)]

Ten temat zawiera przegląd informacji o konfiguracji elektronicznego przesyłania wiadomości.

W ostatnim czasie władze i prawodawcy różnych krajów i regionów na całym świecie wprowadzili w życie wymagania w zakresie sprawozdawczości dla firm, które są zarejestrowane w tych krajach lub regionach. Celem tych wymagań jest możliwość uzyskiwania od tych firm danych w formie elektronicznej bezpośrednio z systemów, w których są księgowane, zapisywane i przetwarzane.

Funkcjonalność wiadomości elektroniczne w Finance obsługuje wiele procesów elektronicznej współpracy między Finance a systemami administracji państwowej do raportowania, przesyłania i odbierania oficjalnych informacji.

Funkcje wiadomości elektroniczne są zintegrowane z modułem **raportowania elektronicznego** (ER). Dlatego należy skonfigurować formaty ER dla wiadomości elektronicznych. Aby uzyskać więcej informacji, zobacz [Raportowanie elektroniczne (ER)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

Obsługa wiadomości elektronicznych opiera się na następujących jednostkach:

- **Wiadomość elektroniczna** — raport lub zgłoszenie, które powinny być zgłoszone i/lub transmitowane wewnętrznie. Przykładem jest raport, który zostanie wysłany do urzędu skarbowego.
- **Elementy wiadomości elektronicznych** — rekordy, które powinny być uwzględnione w komunikacie o błędzie.
- **Przetwarzanie wiadomości elektronicznych** — łańcuch akcji, który powinien zostać uruchomiony, aby zebrać wymagane dane, wygenerować raporty, przechowywać dane w magazynie obiektów Blob Microsoft Azure, przekazywać raporty poza systemem, aktualizować bazę danych na podstawie uzyskanych informacji. Akcje w łańcuchu mogą być połączone albo odłączone

Na poniższej ilustracji przedstawiono przepływ danych do obsługi wiadomości elektronicznych.

![Obsługa wiadomości elektronicznych: przepływ danych](media/electronic-messaging-data-flow.png)

Funkcji wiadomości elektronicznych obsługuje następujące scenariusze:

- Ręczne tworzenie wiadomości i generowanie raportów, które opierają się na skojarzonych formatach eksportowania ER różnego typu: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, tekst i Microsoft Word.
- Automatyczne tworzy i przetwarza wiadomości na podstawie żądanych informacji i otrzymanych z urzędu za pośrednictwem skojarzonego formatu importu ER.
- Gromadzenie i przetwarzanie informacji ze źródła danych jako elementów wiadomości. Źródło danych jest tabelą rozwiązania Finance.
- Przechowuj dodatkowe informacje i oceniaj różne wartości poprzez wywołanie specjalnie zdefiniowanych wykonywalnych klas w odniesieniu do wiadomości lub elementów wiadomości.
- Agregacja informacji zbieranych w elementach wiadomości, podział informacji według wiadomości i generowanie reportów w skojarzonych formatach eksportowania ER.
- Przekazywanie raportów generowanych do usługi sieci web przy użyciu informacji o zabezpieczeniach przechowywanych w Azure Key Vault.
- Uzyskiwanie odpowiedzi z usługi sieci web, interpretowanie odpowiedzi i aktualizowanie danych w Finance w razie potrzeby.
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
- [Aplikacje sieci Web](#web-applications)
- [Ustawienia usługi sieci Web](#web-service-settings)
- [Akcje przetwarzania wiadomości](#message-processing-actions)
- [Przetwarzanie wiadomości elektronicznych](#electronic-message-processing)

Poniższe sekcje zawierają więcej informacji o każdym z tych elementów.

### <a name="number-sequences"></a>Numery kolejne

Ustaw sekwencje numerów, zarówno dla wiadomości i elementów wiadomości. Sekwencje numerów umożliwiają automatyczne numerowanie wiadomości i elementów wiadomości. Przypisane numery posłużą jako unikatowe identyfikatory dla wiadomości i elementów wiadomości w systemie. Można ustawić sekwencje numerów dla elektronicznego przesyłania wiadomości na stronie **Parametry księgi głównej** (**księga główna**\>**Ustawienia księgi**\>**Parametry księgi głównej**).

### <a name="message-item-types-and-statuses"></a>Typy i stany elementów wiadomości

Typy elementów wiadomości określają typy rekordów, które będą używane w wiadomościach elektronicznych. Można skonfigurować typy elementów wiadomości na stronie **Typy elementów wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Typy elementów wiadomości**).

Stany elementu wiadomości określają stany, które będą stosowane w elementach wiadomości w przetwarzaniu, które konfigurujesz. Można skonfigurować typy elementów wiadomości na stronie **Stany elementów wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Stany elementów wiadomości**).

Parametr stanu elementu wiadomości **Zezwalaj na usuwanie** określa, czy użytkownik może usunąć pozycję wiadomości w tym stanie przez stronę **wiadomości elektroniczne** lub **Elementy wiadomości elektronicznych**.

### <a name="message-statuses"></a>Stany wiadomości

Ustaw stany wiadomości, które mają być dostępne w przetwarzania wiadomości. Można skonfigurować stany wiadomości na stronie **Stany wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Stany wiadomości**).

W poniższej tabeli opisano pola znajdujące się na stronie **Stany wiadomości**.

| Nazwa pola          | Opis |
|---------------------|-------------|
| Stan wiadomości      | Wprowadź unikatową nazwę stanu wiadomości. Stany wiadomości są używane do charakteryzowania stanu wiadomości elektronicznej w każdym momencie. Wprowadzona nazwa jest wyświetlana na stronie **wiadomości elektroniczne** i w dzienniku, który jest powiązany z elektronicznymi wiadomościami. |
| Opis         | Wprowadź opis wybranego stanu wiadomości. |
| Typ odpowiedzi       | Wybierz typ odpowiedzi dla wybranego stanu wiadomości. Niektóre akcje w przetwarzaniu mogą spowodować więcej niż jeden typ odpowiedzi. Na przykład akcja typu **usługa sieci Web** może spowodować typ odpowiedzi albo **pomyślnie wykonane** albo **błąd techniczny** w zależności od wyniku jej wykonania. W takim przypadku należy zdefiniować stany komunikatu dla obu typów odpowiedzi. Zobacz [Typy akcji przetwarzania wiadomości](#message-processing-action-types), aby uzyskać więcej informacji dotyczących typów akcji i związanych z nimi typów odpowiedzi. |
| Stan elementu wiadomości | Czasami stan wiadomości elektronicznej musi mieć wpływ na stan elementów pokrewnych wiadomości. Wybierz stan elementu wiadomości w tym polu, aby skojarzyć go ze stanem wiadomości. |
| Zezwalaj na usuwanie        | Zaznacz to pole, jeśli chcesz, aby użytkownicy mogli usuwać wiadomości elektroniczne z tym stanem na stronie **wiadomości elektroniczne**. |

### <a name="additional-fields"></a>Dodatkowe pola

Funkcja wiadomości elektronicznych umożliwia wypełnianie rekordów na podstawie tabeli transakcji. W ten sposób można przygotować rekordy do raportowania i je raportować. Jednak tabele transakcji czasami nie mają wystarczających informacji, aby wypełnić rekordy w sposób, który spełnia wymagania dotyczące raportowania. Możesz wypełnić wszystkie informacje, które muszą zostać przekazane dla rekordu, ustawiając dodatkowe pola. Dodatkowe pola mogą być skojarzone zarówno z wiadomościami, jak i elementami wiadomości. Możesz ustawić dodatkowe pola na stronie **dodatkowe pola** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**dodatkowe pola**).

W poniższej tabeli opisano ogólne pola znajdujące się na stronie **Dodatkowe pola**.

| Pole       | Opis |
|-------------|-------------|
| Nazwa pola  | Wprowadź nazwę dodatkowego atrybutu elementów wiadomości, które są związane z procesem. Ta nazwa jest wyświetlana w interfejsie użytkownika podczas pracy z procesem. Może również być używana w konfiguracjach ER, które są związane z procesem. |
| Opis | Należy wpisać opis dodatkowego pola. |
| Edycja użytkownika   | Ustaw tę opcję na **tak**, jeśli chcesz, aby użytkownicy mogli zmieniać wartość dodatkowego pola w interfejsie użytkownika. |
| Licznik     | Ustaw tę opcję na **tak**, jeśli dodatkowe pole powinno zawierać sekwencję numerów w wiadomościach elektronicznych. Wartości dodatkowego pola są wypełniane automatycznie podczas uruchamiania akcji typu **Eksport raportowania elektronicznego**. |
| Ukryte      | Ustaw tę opcję na **tak**, jeśli dodatkowe pole powinno być ukryta w interfejsie użytkownika. |

Pozostałe pola mogą mieć różne wartości dla przetwarzania. Wartości te można zdefiniować na skróconej karcie **wartości**. W poniższej tabeli opisano dostępne pola.

| Pole                | Opis |
|----------------------|-------------|
| Wartość pola          | Wprowadź wartość pola, która ma być użyta w odniesieniu do wiadomości lub elementu wiadomości podczas raportowania. |
| Opis          | Należy wpisać opis wartości pola. |
| Typ konta         | Niektóre wartości pola mogą być ograniczone do określonych typów kont. Wybierz jedną z następujących wartości: **wszystkie**, **odbiorca** lub **dostawca**. |
| Kod konta         | Jeśli wybrano opcję **odbiorcy** lub **dostawcy** w polu **typ konta**, możesz dodatkowo ograniczyć użycie wartości pól do określonej grupy lub tabeli. |
| Numer konta/grupy | W przypadku wybrania **odbiorcy** lub **dostawcy** w polu **typ konta** i po wprowadzeniu grupy lub tabeli w polu **kod konta** można wprowadzić określoną grupę lub kontrahenta w tym polu. |
| Weszła w życie            | Umożliwia wybranie daty rozpoczęcia uwzględniania wartości. |
| Data wygaśnięcia           | Umożliwia wybranie daty zakończenia uwzględniania wartości. |

Domyślnie kombinacje różnych kryteriów, które są definiowane przez pola **numer konta/grupy**, **kod konta**, **Data wprowadzenia** i **Data ważności** nie wpływają na wybór wartości dodatkowych pól. Jednak te kombinacje mogą być używane w klasie wykonywalnej do implementacji określonej logiki, która oblicza wartości dla dodatkowych pól.

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

Niektóre klasy wykonywalne mogą mieć wymagane parametry, które muszą być zdefiniowane zanim klasa wykonywalna zostanie uruchomiona po raz pierwszy. Aby zdefiniować te parametry, zaznacz **parametry** w okienku akcji, ustaw pola w oknie dialogowym, które zostanie wyświetlone, a następnie wybierz **OK**. Należy pamiętać o wybraniu **OK**. W przeciwnym razie parametry nie zostaną zapisane w bazie danych, a klasa wykonywalna nie zostanie poprawnie wywołana.

### <a name="populate-records-actions"></a>Akcje wypełniania rekordów

Używaj akcji wypełniania rekordów, aby skonfigurować akcje, które dodają rekordy do tabeli elementów wiadomości, dzięki czemu można je dodawać do wiadomości elektronicznych. Na przykład, jeśli wiadomość elektroniczna musi zgłosić fakturę dla odbiorcy, należy skonfigurować akcję wypełnienia rekordów, która jest połączona w polu **Źródło danych** w tabeli Arkusz faktur dla odbiorcy. Można ustawić akcje wypełniania rekordów na stronie **akcji wypełnienia rekordów** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**akcje wypełniania rekordów**). Utwórz nowy rekord dla każdej akcji, która ma dodawać rekordy do tabeli i ustaw następujące pola.

| Pole       | Opis |
|-------------|-------------|
| nazwa        | Wprowadź nazwę akcji, która wypełnia rekordy w procesie. |
| Opis | Podaj opis akcji wypełniania rekordów. |

Na skróconej karcie **ustawienia źródeł danych** dodaj wiersz dla każdego źródła danych, które jest używane w procesie, a następnie ustaw następujące pola.

| Pole                  | opis |
|------------------------|-------------|
| Nazwisko                   | Wprowadź nazwę źródła danych. |
| Typ elementu wiadomości      | Wybierz typ elementu wiadomości, który ma być używany podczas tworzenia rekordów źródła danych. |
| Typ konta           | Wybierz typ konta, który ma być skojarzony z rekordami ze źródła danych. |
| Nazwa tabeli głównej      | Wybierz tabelę, która powinna być źródłem danych. |
| Pole numeru dokumentu  | Wybierz pole, z którego ma być pobrany numer dokumentu w wybranej tabeli. |
| Pole daty dokumentu    | Wybierz pole, z którego ma być pobrana data dokumentu w wybranej tabeli. |
| Pole konta dokumentu | Wybierz pole, z którego ma być pobrane konto dokumentu w wybranej tabeli. |
| Zapytanie użytkownika             | Jeśli to pole wyboru jest zaznaczone, istnieje możliwość ustawienia kwerendy przez zaznaczenie **Edytuj kwerendę** powyżej siatki. W przeciwnym razie będą wypełnione wszystkie rekordy ze źródła danych. |

### <a name="web-applications"></a>Aplikacje sieci Web

Ustawienia aplikacji sieci web umożliwiają konfigurowanie aplikacji sieci web, tak aby obsługiwała Open Authorization (OAuth) 2.0. OAuth jest otwartym standardem umożliwiającym użytkownikom przyznanie bezpiecznego delegowanego dostępu do aplikacji w ich imieniu, bez udostępniania poświadczeń dostępu. Można także przejść przez proces autoryzacji, otrzymując kod autoryzacji i token dostępu. Istnieje możliwość ustawienia aplikacji sieci web na stronie **ustawienia aplikacji sieci Web** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**ustawienia aplikacji sieci Web**) .

W poniższej tabeli opisano pola znajdujące się na stronie **Ustawienia aplikacji sieci Web**.

| Pole                        | Opis |
|------------------------------|-------------|
| Nazwa aplikacji             | Wprowadź nazwę składnika aplikacji sieci Web. |
| Opis                  | Umożliwia wprowadzanie opisu aplikacji sieci web. |
| Podstawowy adres URL                     | Umożliwia wprowadzenie podstawowego adresu internetowego aplikacji sieci Web. |
| Ścieżka URL autoryzacji       | Określ ścieżkę do utworzenia adresu URL dla autoryzacji. |
| Ścieżka URL tokenu               | Określ ścieżkę do utworzenia adresu URL dla tokenu. |
| Adres URL przekierowania                 | Wprowadź adres URL przekierowania. |
| Identyfikator klienta                    | Wprowadź identyfikator klienta aplikacji sieci web. |
| Wpis tajny klienta                | Wprowadź wpis tajny klienta aplikacji sieci web. |
| Token serwera                 | Wprowadź token serwera aplikacji sieci web. |
| Mapowanie formatu autoryzacji | Wybierz odpowiedni format encja-relacja używany do generowania żądań dla autoryzacji. |
| Mapowanie modelu tokenu importu   | Wybierz mapowanie modelu importowania raportu elektronicznego używane do przechowywania tokenu dostępu. |
| Przyznany zakres                | Zakres, który jest przyznawany dla żądania do aplikacji. To pole jest aktualizowane automatycznie. |
| Token dostępu wygaśnie za  | Pozostały czas do wygaśnięcia tokenu dostępu. | 
| Zaakceptuj                       | Określ właściwość **akceptacji** żądania sieciowego. Na przykład wpisz **application/vnd.hmrc.1.0+json**. |
| Typ zawartości                 | Określ typ zawartości: Na przykład wpisz **application/json**. |

Ponadto dostępne są następujące przyciski w okienku akcji na stronie **aplikacje sieci Web**, które służą do obsługi procesu autoryzacji:

- **Pobierz kod autoryzacji:** Inicjowanie autoryzacji aplikacji sieci web.
- **Uzyskać tokenu dostępu** — inicjowanie procesu pobierania tokenu dostępu.
- **Odśwież token dostępu** — odświeżanie tokenu dostępu.

Gdy token dostępu do aplikacji sieci web przechowywany w bazie danych systemu w formacie zaszyfrowanym może służyć do żądań do usługi sieci web. Ze względów bezpieczeństwa dostęp do tokenu dostępu musi być ograniczony tylko do tych ról zabezpieczeń, które muszą mieć możliwość odpowiedzi na te żądania. Jeśli użytkownik spoza grupy zabezpieczeń spróbuje odpowiedzieć na żądanie, zostanie wyświetlony komunikat o błędzie z informacją, że użytkownik nie ma uprawnień do współpracy za pomocą wybranej aplikacji sieci web. Aby skonfigurować role zabezpieczeń, które muszą mieć dostęp do tokenu dostępu, należy użyć skróconej karty **ról zabezpieczeń** na stronie **aplikacji sieci Web**. Gdy role zabezpieczeń nie zostały zdefiniowane dla aplikacji sieci web, tylko administrator systemu będzie mógł współpracować przy użyciu tej aplikacji sieci web.

### <a name="web-service-settings"></a>Ustawienia usługi sieci Web

Ustawienia usługi sieci web umożliwiają konfigurowanie bezpośredniego przesyłania danych do usługi sieci web. Istnieje możliwość ustawienia usługi sieci web na stronie **ustawienia usługi sieci Web** (**Podatek**\>**ustawienia**\>**wiadomości elektroniczne**\>**ustawienia usługi sieci Web**) .

W poniższej tabeli opisano pola znajdujące się na stronie **Ustawienia usługi sieci Web**.

| Pole                          | opis |
|--------------------------------|-------------|
| Usługa sieci Web                    | Wprowadź nazwę składnika usługi sieci Web. |
| opis                    | Umożliwia wprowadzanie opisu usługi sieci web. |
| Adres internetowy               | Umożliwia wprowadzenie adresu internetowego usługi sieci Web. Jeśli dla usługi sieciowej jest określona aplikacja sieci web i adres internetowy usługi sieciowej powinien być taki sam, jak zdefiniowany dla wybranej aplikacji sieci web, wybierz **Kopiuj bazowy URL**, aby skopiować Bazowy URL z aplikacji sieci web do tego pola. |
| Certyfikat                    | Wybierz certyfikat Key Vault, który został wcześniej skonfigurowany. |
| Aplikacja sieci Web                | Wybierz certyfikat Key Vault, który został wcześniej skonfigurowany. |
| Typ odpowiedzi — XML        | Ustaw tę opcję na **Tak** w przypadku typu odpowiedzi XML. |
| Metoda żądania                 | Określ metodę żądania. HTTP definiuje zestaw metod zapytania, który wskazuje akcję, która powinna być wykonywana dla danego zasobu. Metodą żądania może być **GET**, **POST** lub inna metoda HTTP. |
| Nagłówki żądań                | Określ żądania nagłówka. Żądanie nagłówka jest nagłówkiem protokołu HTTP, który może zostać użyty w żądaniu HTTP, a który nie jest powiązany z zawartością wiadomości. |
| Zaakceptuj                         | Określ właściwość **akceptacji** żądania sieciowego. |
| Akceptuj kodowanie                | Określ wartość **akceptowanie kodowania**. Nagłówek HTTP żądania akceptowania kodowania anonsuje kodowanie zawartości, które klient może zrozumieć. To kodowanie zawartości jest zazwyczaj algorytmem kompresji. |
| Typ zawartości                   | Określ typ zawartości: Nagłówek jednostki typu zawartości HTTP wskazuje typ nośnika zasobu. |
| Kod pomyślnej odpowiedzi       | Określ kod stanu HTTP określający, że żądanie zakończyło się pomyślnie. |
| Mapowanie formatu nagłówków żądań | Wybierz odpowiedni format encja-relacja używany do generowania nagłówków żądań sieciowych. |

### <a name="message-processing-actions"></a>Akcje przetwarzania wiadomości

Czynności przetwarzania wiadomości służą do tworzenia akcji dla procesów i konfigurowania ich parametrów. Można skonfigurować przetwarzanie akcji na stronie **Akcje przetwarzania wiadomości** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne**\> **Akcje przetwarzania wiadomości**).

W poniższych tabelach opisano pola na stronie **Akcje przetwarzania wiadomości**.

#### <a name="general-fasttab"></a>Skrócona karta Ogólne

| Pole                       | opis |
|-----------------------------|-------------|
| Typ akcji                 | Umożliwia wybranie typu akcji. Aby uzyskać informacje o dostępnych opcjach, zobacz sekcję [Typy akcji przetwarzania wiadomości](#message-processing-action-types). |
| Mapowanie formatu              | Wybierz format ER, który powinien zostać wywołany dla akcji. To pole jest dostępne tylko dla działań tupu **Eksport raportowania elektronicznego**, **Import raportowania elektronicznego**, i **Wiadomość dotycząca eksportu raportowania elektronicznego**. |
| Mapowanie formatu w ścieżce URL | Wybierz format ER, który powinien zostać wywołany dla akcji. To pole jest dostępne tylko dla działań typu **Usługa sieci Web**. Służy do określania ścieżki adresu URL, który zostanie dodany do podstawowego adresu internetowego określonego dla wybranego serwera sieci web. |
| Typ elementu wiadomości           | Wybierz typ rekordów, dla których powinna być oceniana akcja. To pole jest dostępne dla działań typu **Poziom wykonywania elementu wiadomości**, **Eksport raportowania elektronicznego**, i **Import raportowania elektronicznego**, **Usługa sieci Web** i innych typów. Jeśli to pole pozostanie puste, wszystkie typy elementów wiadomości zdefiniowanych dla przetwarzania wiadomości są sprawdzane. |
| Klasa wykonywalna            | Wybierz ustawienia klasy wykonywalnej utworzone wcześniej. To pole jest dostępne tylko dla działań typu **Poziom wykonywania elementu wiadomości** i **Poziom wykonywania elementu wiadomości**. |
| Akcja wypełniania rekordów     | Wybierz akcję Wypełnij rekordy, która została wcześniej skonfigurowana. To pole jest dostępne tylko dla działań typu **Wypełnij rekordy**. |
| Usługa sieci Web                 | Wybierz usługę sieci web, która została wcześniej skonfigurowana. To pole jest dostępne tylko dla działań typu **Usługa sieci Web**. |
| Nazwa pliku                   | Określ nazwę pliku, który będzie wynikiem akcji. Ten plik może być odpowiedzią z serwera sieci web lub raportu, który zostanie wygenerowany. To pole jest dostępne tylko dla działań **usługi sieci Web** i **Wiadomość eksportu raportowania elektronicznego**. |
| Pokaż okno dialogowe                 | Ustaw tę opcję jako **Tak**, jeśli okno dialogowe musi być widoczne dla użytkownika przed generowaniem raportu. To pole jest dostępne tylko dla działań typu **Wiadomość eksportu raportowania elektronicznego**. |

##### <a name="message-processing-action-types"></a>Typy akcji przetwarzania wiadomości

W polu **Typ akcji** są dostępne następujące opcje:

- **Utwórz wiadomość** — użycie tego typu akcji umożliwia użytkownikom ręczne tworzenia wiadomości na stronie **Wiadomość elektroniczna**. Stanu wyniku nie można skonfigurować dla tego typu akcji.
- **Wypełnij rekordy** — akcję **Wypełnij rekordy** należy wcześniej skonfigurować. Skojarz ją z akcją typu Wypełnij rekordy, aby umożliwić jej przetwarzanie. Zakłada się, że ten typ akcji jest używany dla pierwszej akcji w trakcie przetwarzania wiadomości (gdy nie jest tworzona wiadomość z wyprzedzeniem) lub jako akcja dodawania elementów wiadomości do wcześniej utworzonej wiadomości (przez akcję typu **Utwórz wiadomość**). Z tego względu można ustawić tylko stan wyniku elementów wiadomości dla tego typu akcji. Stan początkowy można ustawić tylko dla wiadomości.
- **Poziom wykonywania wiadomości** — Użyj tego typu akcji, aby skonfigurować wykonywalną klasę, która powinna zostać oceniona na poziomie wiadomości.
- **Poziom wykonywania elementu wiadomości** — Użyj tego typu akcji, aby skonfigurować wykonywalną klasę, która powinna zostać oceniona na poziomie elementu wiadomości.
- **Eksport raportowania elektronicznego** — użyj tego typu akcji dla akcji, które powinny generować raport, który opiera się na eksportowaniu konfiguracji ER na poziomie elementu wiadomości.
- **Wiadomość dotycząca eksportu raportowania elektronicznego** — użyj tego typu akcji dla akcji, które powinny generować raport, który opiera się na eksportowaniu konfiguracji ER na poziomie wiadomości (np. kiedy wiadomość nie ma żadnego elementu wiadomości).
- **Import raportowania elektronicznego** — użyj tego akcji dla akcji, które powinny generować raport, który opiera się na importowaniu konfiguracji ER.
- **Wiadomość dotycząca przetwarzania poziomu użytkownika** — użyj tego typu akcji dla akcji, które zakładają wykonywanie niektórych akcji ręcznie przez użytkownika na poziomie wiadomości. Na przykład użytkownik może aktualizować stan wiadomości.
- **Przetwarzanie użytkownika** — użyj tego typu akcji dla akcji, które zakładają wykonywanie niektórych akcji ręcznie przez użytkownika na poziomie elementu wiadomości. Na przykład użytkownik może aktualizować stan elementów wiadomości.
- **Usługa sieci Web** — użyj tego typu akcji dla akcji, które powinny przekazywać wygenerowany raport do usługi sieci web. Ten typ akcji nie jest używany do raportów komunikacji związanej z fakturami sprzedaży/zakupu we Włoszech. W przypadku akcji typu **usługa sieci Web** strona **akcje przetwarzania wiadomości** zawiera kartę skróconą **Dodatkowe szczegóły**, na której można określić tekst potwierdzenia. Ten tekst potwierdzenia będzie widoczny dla użytkownika zanim zostanie udzielona odpowiedź na żądanie do wybranej usługi sieciowej.
- **Weryfikacja żądania** — użyj tego typu akcji, aby żądać weryfikacji z serwera.

#### <a name="initial-statuses-fasttab"></a>Skrócona karta Stany początkowe

> [!NOTE]
> Skrócona karta **Stany początkowe** nie jest dostępna dla akcji, które mają typ początkowy **Utwórz wiadomość**.

| Pole               | Opis |
|---------------------|-------------|
| Stan elementu wiadomości | Wybierz status elementu wiadomości, dla której ma być oceniana wybrana akcji przetwarzania wiadomości. |
| opis         | Opis wybranego stanu elementu wiadomości. |

#### <a name="result-statuses-fasttab"></a>Skrócona karta Stany wyników

| Pole               | opis |
|---------------------|-------------|
| Stan komunikatu      | Wybierz status wiadomości, dla której ma być oceniana wybrana akcji przetwarzania wiadomości. To pole jest dostępne tylko dla akcji przetwarzania wiadomości, które zostały ocenione na poziomie wiadomości. Na przykład opcja ta jest dostępna dla typów akcji **Eksport raportowania elektronicznego** i **Import raportowania elektronicznego**, ale nie jest dostępna dla typów **Przetwarzanie użytkownika** i **Poziom wykonywania elementu wiadomości**. |
| opis         | Opis wybranego stanu wiadomości. |
| Typ odpowiedzi       | Typ odpowiedzi wybranego stanu wiadomości. |
| Stan elementu wiadomości | Wybierz stany wynikowe, które powinny być dostępne po ocenie wybranej akcji przetwarzania wiadomości. To pole jest dostępne tylko dla akcji przetwarzania wiadomości, które zostały ocenione na poziomie elementu wiadomości. Na przykład jest dostępne dla akcji typu **Przetwarzanie użytkownika** i **Poziom wykonywania elementu wiadomości**. W przypadku akcji przetwarzania, które są oceniane na poziomie wiadomości, to pole wyświetla stan pozycji wiadomości, który został skonfigurowany dla stanu wybranej wiadomości. |

W poniższej tabeli przedstawiono stany wyników, które muszą być ustawione dla różnych typów akcji i odpowiedzi.

| Typ akcji wiadomości elektronicznej/typ odpowiedzi | Wykonano pomyślnie | Błąd biznesowy | Błąd techniczny | Definiowana przez użytkownika | Anulowanie |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| Utwórz komunikat                               | X                     |                |                 |              |        |
| Eksport raportowania elektronicznego                  | X                     |                |                 |              |        |
| Import raportowania elektronicznego                  |                       |                |                 |              |        |
| Usługa sieci Web                                  | X                     |                | X               |              |        |
| Przetwarzanie użytkownika                              |                       |                |                 |              |        |
| Poziom wykonywania wiadomości                      |                       |                |                 |              |        |
| Wypełnij rekordy                             |                       |                |                 |              |        |
| Poziom wykonywania elementu wiadomości                 |                       |                |                 |              |        |
| Weryfikacja żądania                         | X                     | X              | X               |              |        |
| Wiadomość dotycząca eksportu raportowania elektronicznego          | X                     |                |                 |              |        |
| Wiadomość dotycząca przetwarzania poziomu użytkownika                |                       |                |                 |              |        |

### <a name="electronic-message-processing"></a>Przetwarzanie wiadomości elektronicznych

Wiadomość elektroniczna jest pojęciem podstawowych funkcji Wiadomości elektroniczne. Agreguje akcje, które mają być wykonywane dla wiadomości elektronicznych. Akcje można połączyć za pomocą stanu początkowego i stanu wynikowego. Ewentualnie akcje typu **Przetwarzanie użytkownika** mogą być rozpoczynane niezależnie. Na stronie **Przetwarzanie wiadomości elektronicznych** (**Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Przetwarzanie wiadomości elektronicznych**), można również wybrać dodatkowe pola, które mają być obsługiwane do przetwarzania na poziomie wiadomości lub elementu wiadomości.

Skrócona karta **Akcja** pozwala na dodanie wstępnie zdefiniowanych akcji do przetwarzania. Można określić, czy akcję należy uruchomić osobno lub czy może być zainicjowana przez przetwarzanie. Aby określić, że działanie podczas przetwarzania może być inicjowane tylko przez użytkownika, ustaw pole **uruchom oddzielnie** jako **tak** dla tej akcji. Jeśli akcja powinna zostać włączona przez przetwarzanie wiadomości lub elementów wiadomości, które mają stan zdefiniowany jako początkowy dla akcji, ustaw pole **uruchom osobno** jako **Nie**. Akcja typu **akcji użytkownika** musi być zawsze uruchomiona oddzielnie.

Czasami kilka akcji trzeba zagregować w sekwencję, nawet jeśli pierwsza akcja jest ustawiona tak, aby została wykonana oddzielnie. Na przykład użytkownik musi zainicjować generowanie raportu, ale natychmiast po utworzeniu raport musi zostać wysłany do usługi sieciowej i odpowiedź z usługi sieci web musi być zarejestrowana w systemie. W takiej sytuacji można utworzyć nierozdzielną sekwencję czynności, które będą zawsze razem wykonywane. Na skróconej karcie **Akcja** wybierz **Nierozdzielne sekwencje** powyżej siatki i utwórz sekwencję. Następnie, dla wszystkich akcji, które muszą być wykonywane razem, wybierz sekwencję w polu **nierozdzielnych sekwencji**. W takim przypadku pole **uruchom oddzielnie** można ustawić jako **tak** dla pierwszej akcji w sekwencji, ale trzeba je ustawić jako **Nie** dla wszystkich innych akcji.

Skrócona karta **Dodatkowe pola elementów wiadomości** pozwala na dodanie wstępnie zdefiniowanych dodatkowych pól, które są związane z elementami wiadomości. Należy dodać dodatkowe pola dla każdego typu elementu wiadomości do którego odnoszą się pola.

Skrócona karta **Dodatkowe pola wiadomości** pozwala na dodanie wstępnie zdefiniowanych dodatkowych pól, które są związane z wiadomościami.

Skrócona karta **Role zabezpieczeń** pozwala skonfigurować role zabezpieczeń, które są wstępnie zdefiniowane w systemie do określonego przetwarzania. Użytkownicy, którzy mają określoną rolę widzieli tylko przetwarzanie zdefiniowane dla tej roli.

Skrócona karta **Partia** umożliwia skonfigurowanie przetwarzania do pracy w systemie przetwarzania wsadowego.

## <a name="work-with-the-electronic-messages-functionality"></a>Praca z funkcją Wiadomości elektroniczne

Podczas pracy na poziomie komunikatu strona **Wiadomości elektroniczne** (**podatek**\>**zapytania i raporty**\>**wiadomości elektroniczne**\>**Wiadomości elektroniczne**) jest bardziej użyteczna. Podczas pracy na poziomie zbiorów danych (element wiadomości), strona **Elementy wiadomości elektronicznych** (**podatek**\>**zapytania i raporty**\>**wiadomości elektroniczne**\>**Elementy wiadomości elektronicznych**) jest bardziej użyteczna.

### <a name="electronic-messages"></a>Wiadomości elektroniczne

Strona **Wiadomości elektroniczne** przedstawia przetwarzanie, które dostępne w zależności od roli użytkownika. Role zabezpieczeń są skojarzone z przetwarzaniem w ustawieniach tego przetwarzania. Dla każdego dostępnego przetwarzania strona pokazuje wiadomości elektronicznych i informacje związane z nimi.

Skrócona karta **Wiadomości** pokazuje wiadomości elektroniczne dla wybranego przetwarzania. W zależności od stanu wybranej wiadomości i wstępnie zdefiniowanego przetwarzania możesz uruchomić niektóre akcje, wybierając przyciski nas siatką:

- **Nowy** – ten przycisk jest skojarzony z akcjami typu **Utwórz wiadomość**.
- **Usuń** — ten przycisk jest dostępny, jeśli jest zaznaczone pole wyboru **Zezwalaj na usuwanie** dla bieżącego stanu wybranej wiadomości.
- **Zbieranie danych** — ten przycisk jest skojarzony z typem akcji **wypełnienia rekordów**.
- **Generuj raport** — ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca eksportu raportowania elektronicznego**.
- **Wyślij raport** – ten przycisk jest skojarzony z akcjami typu **Usługa sieci web**.
- **Importuj raport** — ten przycisk jest skojarzony z akcjami typu **Import raportu elektronicznego**.
- **Aktualizuj stan** — ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca przetwarzania poziomu użytkownika** typu.
- **Element wiadomości** – otwórz stronę **Elementy wiadomości elektronicznej**.

Skrócona karta **Dziennik akcji** wyświetla informacje o wszystkich akcjach uruchomionych dla wybranej wiadomości. Jeśli akcja spowodowała błąd, informacje o błędzie są dołączane do powiązanego wiersza siatki. Aby przejrzeć informacje dotyczące błędu, wybierz wiersz w siatce, a następnie wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.

Skrócona karta **Dodatkowe pola wiadomości** pokazuje wszystkie dodatkowe pola, które są zdefiniowane dla wiadomości w ustawieniach przetwarzania. Pokazuje także wartości z tych dodatkowych pól.

Skrócona karta **Elementy wiadomości** pokazuje wszystkie elementy wiadomości, które są powiązane z wybraną wiadomością. W zależności od stanu wybranego elementu wiadomości możesz uruchomić niektóre akcje, wybierając przyciski nas siatką:

- **Usuń** — ten przycisk jest dostępny, jeśli jest zaznaczone pole wyboru **Zezwalaj na usuwanie** dla bieżącego stanu wybranego elementu wiadomości.
- **Aktualizuj stan** — ten przycisk jest skojarzony z akcjami typu **Przetwarzanie przez użytkownika**.
- **Oryginalny dokument** — otwiera stronę, na której znajduje się oryginalny dokument dla elementu wybranej wiadomości.

Wszystkie raporty, które zostały już wygenerowane i odebrane dla wiadomości, są dołączone do tej wiadomości. Aby przejrzeć załączniki związane z wiadomością, wybierz wiadomość, a następnie wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.

![Przycisk Załącznik](media/attachment-icon.png)

Strona **Załączniki** pokazane wszystkie załączniki, które są związane z wybraną wiadomością. Aby wyświetlić plik, wybierz go z listy po lewej stronie, a następnie wybierz **Otwórz** w okienku akcji.

![Przycisk Otwórz](media/open-button.png)

Można także przejrzeć załączniki, które są związane z określoną akcją uruchomioną wcześniej dla danej wiadomości. Na stronie **wiadomości elektroniczne** wybierz wiadomość na skróconej karcie **wiadomości**, wybierz akcję na skróconej karcie **dziennik akcji**, a następnie wybierz przycisk **załącznik** w prawym górnym rogu strony.

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
<td>Numer konta odbiorcy lub dostawcy (lub wartość innego pola, w zależności od pola, które jest określone w akcji Wypełnij rekordy). To pole może być wypełnione automatycznie tylko wtedy, gdy faktura jest dodawana do tabeli Elementy wiadomości.</td>
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

Wybierz **Wiadomości elektroniczne** w okienku akcji, aby przejrzeć wiadomość elektroniczną powiązaną z pozycją wybranej wiadomości.

Można także przejrzeć wszystkie pliki, które odpowiadają elementowi wiadomości. Wybierz pole **Wiadomość** dla elementu wiadomości lub wybierz **Wiadomości elektroniczne** w okienku akcji. Następnie, na stronie **Wiadomości elektroniczne** wybierz wiadomość, dla której chcesz przejrzeć pliki, po czym wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.

![Przycisk Załącznik](media/attachment-icon.png)

Strona **Załączniki** pokazane wszystkie załączniki, które są związane z wiadomością. Aby wyświetlić plik, wybierz go z listy po lewej stronie, a następnie wybierz **Otwórz** w okienku akcji.

![Przycisk Otwórz](media/open-button.png)

#### <a name="original-document"></a>Dokument oryginalny

Wybierz **Oryginalny dokument** w okienku akcji, aby otworzyć oryginalny dokument dla elementu wybranej wiadomości.

## <a name="example-set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Przykład: konfigurowanie i uruchamianie przetwarzania do wywołania prostego formatu eksportowania ER to wygenerować raportu programu Excel

Po utworzeniu formatu ER, przyporządkowaniu go do źródeł danych i wykonaniu go, można uruchomić go za pomocą obszaru roboczego **Raportowanie elektroniczne** . Generowany jest raport, który można zapisać tylko lokalnie.

Aby kontrolować następujące aspekty procesu raportowania, należy skonfigurować przetwarzanie wiadomości elektronicznych:

- Informacje dziennika o tym, kto wygenerował raport.
- Informacje dziennika o tym, kiedy został wygenerowany raport.
- Zapisz raporty, które zostały wygenerowane za poprzednie okresy.

Ta sekcja zawiera przykład, który pokazuje, jak można skonfigurować wiadomości elektroniczne do generowania raportu, który jest oparty na formacie eksportowania ER do programu Excel. Aby podążać za tym przykładem, format eksportowania ER Excel musi już być utworzony, mapowany na źródła danych i zakończony. Ponadto numer sekwencji musi być skonfigurowany w wiadomościach elektronicznych.

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
3. Tworzenie akcji o nazwie **Aktualizuj do stanu Przygotowane** i ustaw następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Wiadomość dotycząca przetwarzania poziomu użytkownika**.
    - Na skróconej karcie **początkowe stany** w polu **stan wiadomości** zaznacz **nowa**.
    - Na skróconej karcie **Stany wyników** w polu **stan wiadomości** zaznacz **Przygotowane**. W polu **typu odpowiedzi** wprowadź **Pomyślnie wykonane**.

4. Utwórz akcję o nazwie **Generuj raport** i ustaw następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Eksport raportowania elektronicznego**. W polu **mapowanie formatu** wybierz format eksportu ER. Dostępne opcje to **Excel**, **XML**, **JSON**, **Tekst** i **Inne**.
    - Na skróconej karcie **Stany początkowe** w polu **stan wiadomości** zaznacz **Przygotowane**.
    - Na skróconej karcie **Stany wyników** w polu **stan wiadomości** zaznacz **Wygenerowane**. W polu **typu odpowiedzi** wprowadź **Pomyślnie wykonane**.

    ![Akcja Generowanie raportu](media/generate-report-action.png)

5. Opcjonalnie: aby umożliwić użytkownikom ponowne generowanie raportu wiele razy, możesz utworzyć akcję **aktualizacji do stanu początkowego** i ustawić następujące pola:

    - Na skróconej karcie **ogólne** w polu **typu akcji** zaznacz **Wiadomość dotycząca przetwarzania poziomu użytkownika**.
    - Na skróconej karcie **Stany początkowe** w polu **stan wiadomości** zaznacz **Wygenerowane**.
    - Na karcie skróconej **Stany wyników** dodaj osobny wiersz dla każdego z dwóch stanów wiadomości (**Przygotowana** i **Nowa**). W przypadku obu wierszy należy ustawić pole **typu odpowiedzi** jako **Wykonano pomyślnie**.

#### <a name="electronic-message-processing"></a>Przetwarzanie wiadomości elektronicznych

W tym przykładzie wszystkie akcje powinny być ustawione tak, żeby działały oddzielnie. Zakłada się, że każda akcja zostanie zainicjowana przez użytkownika.

1. Przejdź do menu **Podatek \>ustawienia \>wiadomości elektroniczne \>Przetwarzanie wiadomości elektronicznych**.
2. Dodaj rekord do przetwarzania i dodaj wszystkie uprzednio zdefiniowane akcje oraz dodatkowe pole.
3. Opcjonalnie: Na skróconej karcie **ról zabezpieczeń** zdefiniuj role zabezpieczeń do przetwarzania, aby ograniczyć dostęp do określonego raportowania.
4. Przejdź do menu **Podatek \>Zapytania i raporty \>wiadomości elektroniczne \>wiadomości elektroniczne**.
5. Wybierz **Nowa**, aby utworzyć wiadomość. W tym momencie można dodać daty i opis. Można też zaktualizować wartość dodatkowego pola, jeśli jest to konieczne.

    ![Tworzenie wiadomości elektronicznej](media/create-electronic-message.png)

Siatka na skróconej karcie **dziennik akcji** jest automatycznie wypełniany na podstawie dziennika wszystkich akcji wykonanych w odniesieniu do wiadomości.

Można teraz usunąć lub zaktualizować stan wiadomości. Aby zaktualizować stan wiadomości, zaznacz **aktualizacja stanu**. W polu **Nowy stan** wybierz opcję **Przygotowana**, a następnie wybierz **OK**.

![Aktualizowanie stanu wiadomości](media/update-status.png)

Stan wiadomości jest ustawiony na **Przygotowane** i możesz teraz wygenerować raport, wybierając **Generowanie raportu**. Raport zostanie wygenerowany, a stan wiadomości i dziennik akcji zostaną zaktualizowane. Aby obejrzeć wygenerowany raport, wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]