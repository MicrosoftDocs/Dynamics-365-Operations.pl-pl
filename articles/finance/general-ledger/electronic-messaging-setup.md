---
title: Ustawianie wiadomości elektronicznych
description: Ten artykuł zawiera informacje dotyczące konfigurowania funkcji wiadomości elektronicznych (EM).
author: AdamTrukawka
ms.date: 11/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 12beb1adbfa4e2f235c8a7c69e786d342c4a4f68
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279311"
---
# <a name="set-up-electronic-messages"></a>Ustawianie wiadomości elektronicznych

[!include [banner](../includes/banner.md)]

**Wiadomości elektroniczne** mogą ułatwić obsługę różnych elektronicznych procesów raportowania dla różnych typów dokumentów. W niektórych złożonych scenariuszach, które obsługują [funkcje raportowania specyficzne dla danego kraju](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality), funkcjonalność EM jest skonfigurowana w taki sposób, że posiada kombinację wielu statusów komunikatów, statusów pozycji komunikatów, działań, dodatkowych pól i klas wykonywalnych. W tych scenariuszach pakiety jednostek danych są dostępne do importu. Korzystając z tych pakietów jednostek danych należy importować je do firmy przy użyciu narzędzia do zarządzania danymi. Aby uzyskać więcej informacji dotyczących sposobu używania narzędzia do zarządzania danymi, zobacz [zarządzanie danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Jeśli nie importujesz pakietu jednostek danych, możesz ręcznie ustawić funkcje wiadomości elektronicznych. W takim przypadku należy skonfigurować następujące elementy:

- [Sekwencje identyfikatorów](#sequences)
- [Typy elementów wiadomości](#types)
- [Stany elementów wiadomości](#item)
- [Stany wiadomości](#statuses)
- [Dodatkowe pola](#additional)
- [Ustawienia klasy wykonywalnej](#executable)
- [Akcje wypełniania rekordów](#populate)
- [Wypełnianie rekordów z wielu firm](#multiple-companies-populate)
- [Aplikacje sieci Web](#applications)
- [Ustawienia usługi sieci Web](#settings)
- [Akcje przetwarzania wiadomości](#actions)
- [Przetwarzanie wiadomości elektronicznych](#processing)

Poniższe sekcje zawierają więcej informacji o każdym z tych elementów.

## <a name="number-sequences"></a><a id="sequences"></a>Numery kolejne

Ustaw sekwencje numerów, zarówno dla wiadomości i elementów wiadomości. Sekwencje numerów umożliwiają automatyczne numerowanie wiadomości i elementów wiadomości. Przypisane numery posłużą jako unikatowe identyfikatory dla wiadomości i elementów wiadomości w systemie. Można ustawić sekwencje numerów dla elektronicznego przesyłania wiadomości, przechodząc do **Księga główna** \> **Ustawienia księgi** \> **Parametry księgi głównej**.

## <a name="message-item-types"></a><a id="types"></a>Typy elementów wiadomości

Typy elementów wiadomości określają typy rekordów, które są używane w wiadomościach elektronicznych. Można skonfigurować typy elementów wiadomości, przechodząc do **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Typy elementów wiadomości**.

## <a name="message-item-statuses"></a><a id="item"></a>Stany elementów wiadomości

Stany elementu wiadomości określają stany, które są stosowane w elementach wiadomości w przetwarzaniu, które konfigurujesz. Można skonfigurować stany elementów wiadomości, przechodząc do **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Stany elementów wiadomości**.

Parametr stanu elementu wiadomości **Zezwalaj na usuwanie** określa, czy użytkownik może usunąć pozycję wiadomości w tym stanie przez stronę **wiadomości elektroniczne** lub **Elementy wiadomości elektronicznych**.

## <a name="message-statuses"></a><a id="statuses"></a>Stany wiadomości

Ustaw stany wiadomości, które mają być dostępne w przetwarzania wiadomości. Można skonfigurować stany wiadomości, przechodząc do **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Stany wiadomości**.

W poniższej tabeli opisano pola znajdujące się na stronie **Stany wiadomości**.

| Nazwa pola          | Opis |
|---------------------|-------------|
| Stan wiadomości      | Wprowadź unikatową nazwę stanu wiadomości. Stany wiadomości są używane do charakteryzowania stanu wiadomości elektronicznej w każdym momencie. Wprowadzona nazwa jest wyświetlana na stronie **wiadomości elektroniczne** i w dzienniku, który jest powiązany z elektronicznymi wiadomościami. |
| Opis         | Wprowadź opis wybranego stanu wiadomości. |
| Typ odpowiedzi       | Wybierz typ odpowiedzi dla wybranego stanu wiadomości. Niektóre akcje w przetwarzaniu mogą spowodować więcej niż jeden typ odpowiedzi. Na przykład akcja **usługa sieci Web** może spowodować typ odpowiedzi albo **pomyślnie wykonane** albo **błąd techniczny** w zależności od wyniku jej wykonania. W tym przypadku należy zdefiniować statusy komunikatów dla obu typów odpowiedzi. Zobacz sekcję [Typy akcji przetwarzania wiadomości](#action-types) w dalszej części tego artykułu, aby uzyskać więcej informacji dotyczących typów akcji i związanych z nimi typów odpowiedzi. |
| Stan elementu wiadomości | Czasami stan wiadomości elektronicznej musi mieć wpływ na stan elementów pokrewnych wiadomości. Wybierz stan elementu wiadomości w tym polu, aby skojarzyć go ze stanem wiadomości. |
| Zezwalaj na usuwanie        | Zaznacz to pole, jeśli chcesz, aby użytkownicy mogli usuwać wiadomości elektroniczne z tym stanem na stronie **wiadomości elektroniczne**. |

## <a name="additional-fields"></a><a id="additional"></a>Dodatkowe pola

Funkcja EM umożliwia zbieranie rekordów z tabel transakcyjnych w Microsoft Microsoft Dynamics 365 Finance jako elementów wiadomości. W ten sposób można przygotować rekordy do raportowania i je raportować. Jednak tabele transakcji czasami nie mają wystarczających informacji, aby wypełnić rekordy w sposób, który spełnia wymagania dotyczące raportowania. Możesz wypełnić wszystkie informacje, które muszą zostać przekazane dla rekordu, ustawiając dodatkowe pola. Dodatkowe pola mogą być skojarzone z wiadomościami i elementami wiadomości. Można skonfigurować dodatkowe pola, przechodząc do **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Dodatkowe pola**.

W poniższej tabeli opisano ogólne pola znajdujące się na stronie **Dodatkowe pola**.

| Pole       | opis |
|-------------|-------------|
| Nazwa pola  | Wprowadzić nazwę dodatkowego pola dla komunikatów elektronicznych lub pozycji komunikatów, które są związane z procesem. Ta nazwa jest wyświetlana w interfejsie użytkownika podczas pracy z procesem. Nazwa ta może być również używana w konfiguracjach raportowania elektronicznego (ER), które są związane z procesem. |
| opis | Należy wpisać opis dodatkowego pola. |
| Edycja użytkownika   | Ustaw tę opcję na **tak**, jeśli chcesz, aby użytkownicy mogli zmieniać wartość dodatkowego pola w interfejsie użytkownika. |
| Licznik     | Ustaw tę opcję na **tak**, jeśli dodatkowe pole powinno zawierać sekwencję numerów w wiadomościach elektronicznych. Wartości dodatkowego pola są wypełniane automatycznie podczas uruchamiania akcji typu **Eksport raportowania elektronicznego**. |
| Ukryte      | Ustaw tę opcję na **Tak**, jeśli dodatkowe pole ma być ukryte w interfejsie użytkownika na stronie **Wiadomości elektroniczne** lub na stronie **Elementy wiadomości elektronicznych**. |

Na skróconej karcie **Wartości** można wstępnie zdefiniować wartości, które mogą mieć dodatkowe pole. Wartości te są następnie dostępne do wyboru dla użytkowników. Dzięki temu nie trzeba ich ręcznie wypełniać podczas przetwarzania danych. W poniższej tabeli opisano dostępne pola.

| Pole                | opis |
|----------------------|-------------|
| Wartość pola          | Wprowadź wartość pola, która ma być użyta w odniesieniu do wiadomości lub elementu wiadomości podczas raportowania. |
| Opis          | Należy wpisać opis wartości pola. |
| Typ konta         | Niektóre wartości pola mogą być ograniczone do określonych typów kont. Wybierz jedną z następujących wartości: **wszystkie**, **odbiorca** lub **dostawca**. |
| Kod konta         | Jeśli wybrano opcję **odbiorcy** lub **dostawcy** w polu **typ konta**, możesz dodatkowo ograniczyć użycie wartości pól do określonej grupy lub tabeli. |
| Numer konta/grupy | W przypadku wybrania **odbiorcy** lub **dostawcy** w polu **typ konta** i po wprowadzeniu grupy lub tabeli w polu **kod konta** można wprowadzić określoną grupę lub kontrahenta w tym polu. |
| Weszła w życie            | Umożliwia wybranie daty rozpoczęcia uwzględniania wartości. |
| Data wygaśnięcia           | Umożliwia wybranie daty zakończenia uwzględniania wartości. |

Domyślnie kombinacje różnych kryteriów, które są definiowane przez pola **numer konta/grupy**, **kod konta**, **Data wprowadzenia** i **Data ważności** nie wpływają na wybór wartości dodatkowych pól. Jednak te kombinacje mogą być używane w klasie wykonywalnej do implementacji określonej logiki, która oblicza wartości dla dodatkowych pól.

## <a name="executable-class-settings"></a><a id="executable"></a>Ustawienia klasy wykonywalnej

Klasa wykonywalna jest metodą X ++ lub klasą, której przetwarzanie wiadomości elektronicznej można wywołać w odniesieniu do akcji, jeżeli ocena jest wymagana dla procesu.

Można ręcznie skonfigurować klasę wykonywalną, która musi być wywoływana podczas przetwarzania, przechodząc do **Podatek** \> **Ustawienia** \> **Wiadomości elektroniczne** \> **Ustawienia klasy wykonywalnej**. Na stronie **Ustawienia klasy wykonywalnej** utwórz wiersz i ustaw następujące pola.

| Pole                 | opis |
|-----------------------|-------------|
| Klasa wykonywalna      | Wprowadź nazwę, która będzie używana podczas akcji przetwarzania wiadomości, w związku z którą będzie wywoływana ta klasa. |
| opis           | Wpisz opis klasy wykonywalnej. |
| Nazwa klasy wykonywalnej | Wybierz klasę wykonywalną X ++. |
| Poziom wykonywania       | To pole jest ustawiane automatycznie, ponieważ wartość jest predefiniowana dla wybranej klasy wykonywalnej. To pole ogranicza poziom, przy którym jest uruchamiana powiązana ocena. |
| Opis klasy     | To pole jest ustawiane automatycznie, ponieważ wartość jest predefiniowana dla wybranej klasy wykonywalnej. |
| Typ akcji           | To pole jest dostępne po **\[EM\] włączeniu funkcji typu akcji klasy wykonywalnej** w obszarze roboczym **Zarządzanie funkcjami**. To pole służy do określania typu akcji dla klasy wykonywalnej. To pole zapewnia bardziej precyzyjną kontrolę nad kolejnymi akcjami, które są dostępne dla wiadomości elektronicznej na **stronie Wiadomości elektroniczne**. |

Niektóre klasy wykonywalne mogą mieć wymagane parametry, które muszą być zdefiniowane zanim klasa wykonywalna zostanie uruchomiona po raz pierwszy. Aby zdefiniować te parametry, w okienku akcji wybierz polecenie **Parametry**. W wyświetlonym oknie dialogowym ustaw pola, a następnie wybierz przycisk **OK**. Należy pamiętać o wybraniu **OK**. W przeciwnym razie parametry nie zostaną zapisane w bazie danych, a klasa wykonywalna nie zostanie poprawnie wywołana.

## <a name="populate-records-actions"></a><a id="populate"></a>Akcje wypełniania rekordów

Używaj akcji wypełniania rekordów, aby skonfigurować akcje, które dodają rekordy do tabeli elementów wiadomości, dzięki czemu można je dodawać do wiadomości elektronicznych. Na przykład, jeśli wiadomość elektroniczna musi zgłosić fakturę dla odbiorcy, należy skonfigurować akcję wypełnienia rekordów, która jest połączona w polu **Źródło danych** w tabeli Arkusz faktur dla odbiorcy.

Można ustawić akcje wypełniania rekordów, wybierając **Podatek** \> **ustawienia** \> **wiadomości elektroniczne** \> **akcje wypełniania rekordów**. Utwórz nowy rekord dla każdej akcji, która ma dodawać rekordy do tabeli i ustaw następujące pola.

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
| Pole numeru dokumentu  | Wybierz pole, z którego ma być pobrany numer dokumentu w wybranej tabeli. Wartość tego pola jest używana jako wartość **pola Numer dokumentu** dla elementu wiadomości. |
| Pole daty dokumentu    | Wybierz pole, z którego ma być pobrana data dokumentu w wybranej tabeli. Wartość tego pola jest używana jako wartość pola **Data wysłania elementu** dla elementu wiadomości. |
| Pole konta dokumentu | Wybierz pole, z którego ma być pobrane konto dokumentu w wybranej tabeli. Wartość tego pola jest używana jako wartość **pola Numer konta** dla elementu wiadomości. |
| Firma                | To pole jest dostępne, gdy jest włączona funkcja **Kwerendy międzyfirmowe dotyczące działań wypełniania rekordów** w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja służy do konfigurowania międzyfirmowych źródeł danych dla akcji wypełniania rekordów. Dane można pobierać z wielu firm. |
| Zapytanie użytkownika             | <p>Jeśli kwerenda zostanie skonfigurowana przez wybranie opcji **Edytuj kwerendę** nad siatką i określisz kryteria, które muszą zostać zastosowane do wybranej tabeli wzorcowej, z której są wypełniane dane, to pole wyboru jest automatycznie zaznaczone. W przeciwnym razie wszystkie rekordy są wypełniane z wybranego źródła tabeli głównej.</p><p>Gdy jest włączona funkcja **zapytań międzyfirmowych dla funkcji akcji wypełniania rekordów** w obszarze roboczym **Zarządzanie funkcjami**, a rekordy muszą być zbierane z kilku firm, dodaj wiersz dla każdej dodatkowej firmy, którą należy uwzględnić w raportowaniu. Dla każdego nowego wiersza wybierz pozycję **Edytuj kwerendę** i określ powiązane kryterium specyficzne dla firmy określonej w polu **Firma** w wierszu. Po zakończeniu siatka konfiguracji **Źródła danych** będzie zawierać wiersze dla wszystkich firm, które muszą zostać uwzględnione w raportowaniu.</p> |

## <a name="populate-records-from-multiple-companies"></a><a id="multiple-companies-populate"></a>Wypełnianie rekordów z wielu firm

Jeśli firma musi raportować z wielu firm w tej samej bazie danych Finance, skonfiguruj [akcja wypełniania rekordów](#populate) dla wszystkich firm, których dane muszą być uwzględniane w raportach.

Aby włączyć tę możliwość w środowisku Finance, postępuj zgodnie z tymi krokami. 

1. Kliknij kolejno opcje **Obszary robocze** \> **Zarządzanie funkcjami**.
2. Znajdź i wybierz z listy **Zapytania między firmami dla akcji wypełniania rekordów**.
3. Wybierz **Włącz teraz**. 

Aby skonfigurować [akcję wypełniania rekordów](#populate) dla wielu firm, z których dane muszą być uwzględniane w raportach, należy wykonać następujące kroki.

1. Przejdź do **Podatek** \> **Konfiguracja** \> **Wiadomości elektroniczne** \> **Akcje wypełniania rekordów**.

    Gdy jest włączona funkcja **Zapytań międzyfirmowych dla funkcji akcji wypełniania rekordów**, siatka **ustawień źródeł danych** na stronie akcji **Akcja wypełniania rekordów** zawiera pole **Firma**. Dla istniejących rekordów, które zostały utworzone podczas ogólnej konfiguracji [akcji wypełniania rekordów](#populate), w tym polu jest przedstawiany identyfikator bieżącej firmy.

2. W siatce **Ustawienia źródeł danych** dodaj wiersz dla każdej podległej osoby prawnej, która musi zostać uwzględniona w raportowaniu, i ustaw następujące pola.

    | Nazwa pola             | Wartość |
    |------------------------|-------|
    | Nazwa                   | Wprowadź wartość tekstową, która pomoże w zrozumieniu, skąd pochodzi ten rekord. Nap przykład wprowadź **Nazwa źródła danych — oddział 1**. |
    | Typ elementu wiadomości      | Wybierz typ elementu komunikatu, który jest wymagany do przetwarzania wiadomości elektronicznej. |
    | Typ konta           | Określ typ konta, który jest wymagany do przetwarzania wiadomości elektronicznej. Jeśli w przetwarzaniu wiadomości elektronicznej nie ma określonych typów kont, wybierz opcję **Wszystkie**. |
    | Nazwa tabeli głównej      | Określ nazwę tabeli głównej, która jest wymagana do przetwarzania wiadomości elektronicznej. |
    | Pole numeru dokumentu  | Określ pole zawierające numer dokumentu w rekordach przetwarzania wiadomości elektronicznej. |
    | Pole daty dokumentu    | Określ pole zawierające datę dokumentu w rekordach przetwarzania wiadomości elektronicznej. |
    | Pole konta dokumentu | Określ pole zawierające konto dokumentu w rekordach przetwarzania wiadomości elektronicznej. |
    | Firma                | Wybierz identyfikator oddziału osoby prawnej. |
    | Zapytanie użytkownika             | To pole wyboru jest zaznaczane automatycznie podczas definiowania kryteriów przez wybranie opcji **Edytuj zapytanie**. |

3. Dla każdego nowego wiersza wybierz pozycję **Edytuj zapytanie** i określ powiązane kryteria dla firmy określonej w polu **Firma** w wierszu.

## <a name="web-applications"></a><a id="applications"></a>Aplikacje sieci Web

Ustawienia aplikacji sieci web umożliwiają konfigurowanie aplikacji sieci web, tak aby obsługiwała Open Authorization (OAuth) 2.0. OAuth jest otwartym standardem umożliwiającym użytkownikom przyznanie bezpiecznego delegowanego dostępu do aplikacji w ich imieniu, bez udostępniania poświadczeń dostępu. Można także przejść przez proces autoryzacji, otrzymując kod autoryzacji i token dostępu. Istnieje możliwość ustawienia aplikacji sieci web na **Podatek** \> **ustawienia** \> **wiadomości elektroniczne** \> **ustawienia aplikacji sieci Web**.

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
| Token dostępu wygaśnie za  | Pozostały czas do wygaśnięcia tokenu dostępu. To pole jest aktualizowane automatycznie. | 
| Akceptacja                       | Określ właściwość **akceptacji** żądania sieciowego. Na przykład wpisz **application/vnd.hmrc.1.0+json**. |
| Typ zawartości                 | Określ typ zawartości: Na przykład wpisz **application/json**. |

Ponadto dostępne są następujące przyciski w okienku akcji na stronie **aplikacje sieci Web**, które służą do obsługi procesu autoryzacji:

- **Pobierz kod autoryzacji:** Inicjowanie autoryzacji aplikacji sieci web. Ta funkcja używa formatu ER określonego w polu **mapowanie formatu autoryzacji** do wygenerowania żądania autoryzacji.
- **Uzyskać tokenu dostępu** — inicjowanie procesu pobierania tokenu dostępu.
- **Odśwież token dostępu** — odświeżanie tokenu dostępu. Ta funkcja używa formatu ER określonego w polu **Importowanie modelu mapowania tokenu** do importowania informacji o otrzymanym tokenie dostępu.

Gdy token dostępu do aplikacji sieci web przechowywany w bazie danych systemu w formacie zaszyfrowanym może służyć do żądań do usługi sieci web. Ze względów bezpieczeństwa dostęp do tokenu dostępu musi być ograniczony tylko do tych ról zabezpieczeń, które muszą mieć możliwość odpowiedzi na te żądania. Jeśli użytkownik spoza grupy zabezpieczeń spróbuje odpowiedzieć na żądanie, zostanie wyświetlony komunikat o błędzie z informacją, że użytkownik nie ma uprawnień do współpracy za pomocą wybranej aplikacji sieci web. Aby skonfigurować role zabezpieczeń, które muszą mieć dostęp do tokenu dostępu, należy użyć skróconej karty **ról zabezpieczeń** na stronie **aplikacji sieci Web**. Gdy role zabezpieczeń nie zostały zdefiniowane dla aplikacji sieci web, tylko administrator systemu będzie mógł współpracować przy użyciu tej aplikacji sieci web.

Dla każdej akcji z wybraną aplikacją sieci web na skróconej karcie **Dziennik akcji** zapisuje informacje o użytkowniku oraz datę i czas.

Niektóre usługi WWW mogą wymagać dołączenia do żądań różnych nagłówków. Administrator systemu może skonfigurować dodatkowe nagłówki i ich wartości na skróconej karcie **Nagłówki dodatkowe**, a następnie używać ich podczas generowania żądania.

## <a name="web-service-settings"></a><a id="settings"></a>Ustawienia usługi sieci Web

Ustawienia usługi sieci web umożliwiają konfigurowanie bezpośredniego przesyłania danych do usługi sieci web. Istnieje możliwość ustawienia usługi sieci web na **Podatek** \> **ustawienia** \> **wiadomości elektroniczne** \> **Wstawienia usługi sieci Web**.

W poniższej tabeli opisano pola znajdujące się na stronie **Ustawienia usługi sieci Web**.

| Pole                          | opis |
|--------------------------------|-------------|
| Usługa sieci Web                    | Wprowadź nazwę składnika usługi sieci Web. |
| opis                    | Umożliwia wprowadzanie opisu usługi sieci web. |
| Adres internetowy               | <p>Umożliwia wprowadzenie adresu internetowego usługi sieci Web. Jeśli dla usługi sieciowej jest określona aplikacja sieci web i adres internetowy usługi sieciowej powinien być taki sam, jak zdefiniowany dla wybranej aplikacji sieci web, wybierz **Kopiuj bazowy URL**. Do tego pola zostanie wówczas skopiowany podstawowy adres URL aplikacji sieci web.</p><p>**Ostrzeżenie:** Usługi innych firm lub inne usługi, które można tutaj skonfigurować, nie wymagają certyfikacji i mogą nie spełniać standardów prywatności firmy Microsoft. Należy zapoznać się z dokumentacją dotyczącą prywatności każdej usługi i współpracować z każdym dostawcą usług, aby dowiedzieć się więcej o poziomie zgodności zapewnianym przez jego usługę. Ponosisz odpowiedzialność za zapewnienie, że te usługi spełniają Twoje standardy bezpieczeństwa, prywatności i prawa. Ponosisz ryzyko korzystania z usług. Firma Microsoft nie udziela żadnych wyraźnych gwarancji ani warunków. Zdecydowanie zalecamy korzystanie wyłącznie z usług, które zapewniają bezpieczne i autoryzowane połączenia, takich jak HTTPS.</p> |
| Certyfikat                    | Wybierz certyfikat Azure Key Vault, który został wcześniej skonfigurowany. |
| Aplikacja sieci Web                | Wybierz aplikację internetową, która została wcześniej skonfigurowana. |
| Typ odpowiedzi — XML        | Ustaw tę opcję na **Tak** w przypadku typu odpowiedzi XML. |
| Metoda żądania                 | Określ metodę żądania. HTTP definiuje zestaw metod zapytania, który wskazuje akcję, która powinna być wykonywana dla danego zasobu. Metodą żądania może być **GET**, **POST** lub inna metoda HTTP. |
| Nagłówki żądań                | Określ żądania nagłówka. Nagłówek żądania jest nagłówkiem HTTP, który może być używany w żądaniu HTTP. Nie jest on powiązany z zawartością wiadomości. |
| Akceptacja                         | Określ właściwość akceptacji żądania sieciowego. |
| Akceptuj kodowanie                | Określ wartość akceptowanie kodowania. Nagłówek HTTP żądania akceptowania kodowania anonsuje kodowanie zawartości, które klient może zrozumieć. To kodowanie zawartości jest zazwyczaj algorytmem kompresji. |
| Typ zawartości                   | Określ typ zawartości: Nagłówek jednostki typu zawartości HTTP wskazuje typ nośnika zasobu. |
| Kod pomyślnej odpowiedzi       | Określ kod stanu HTTP określający, że żądanie zakończyło się pomyślnie. |
| Mapowanie formatu nagłówków żądań | Wybierz odpowiedni format encja-relacja używany do generowania nagłówków żądań sieciowych. |

## <a name="message-processing-actions"></a><a id="actions"></a>Akcje przetwarzania wiadomości

Czynności przetwarzania wiadomości służą do tworzenia akcji dla procesów i konfigurowania ich parametrów. Możesz skonfigurować działania przetwarzania wiadomości, wybierając **Podatek** \> **ustawienia** \> **wiadomości elektroniczne** \> **Działania związane z przetwarzaniem wiadomości**.

W poniższych tabelach opisano pola na stronie **Akcje przetwarzania wiadomości**.

### <a name="general-fasttab"></a>Skrócona karta Ogólne

| Pole                                     | opis |
|-------------------------------------------|-------------|
| Typ akcji                               | Umożliwia wybranie typu akcji. Aby uzyskać informacje o dostępnych opcjach, zobacz sekcję [Typy akcji przetwarzania wiadomości](#action-types) w dalszej części artykułu. |
| Mapowanie formatu                            | Wybierz format ER, który powinien zostać wywołany dla akcji. To pole jest dostępne tylko dla działań tupu **Eksport raportowania elektronicznego**, **Import raportowania elektronicznego**, i **Wiadomość dotycząca eksportu raportowania elektronicznego**. |
| Mapowanie formatu w ścieżce URL               | Wybierz format ER, który powinien zostać wywołany dla akcji. Ten format służy do określania ścieżki adresu URL, który zostanie dodany do podstawowego adresu internetowego określonego dla wybranego serwera sieci web. To pole jest dostępne tylko dla działań typu **Usługa sieci Web**. |
| Typ elementu wiadomości                         | Wybierz typ rekordów, dla których powinna być oceniana akcja. To pole jest dostępne dla działań typu **Poziom wykonywania elementu wiadomości**, **Eksport raportowania elektronicznego** i **Import raportowania elektronicznego**, **Usługa sieci Web** i innych typów. Jeśli to pole pozostanie puste, wszystkie typy elementów wiadomości zdefiniowanych dla przetwarzania wiadomości są sprawdzane. |
| Klasa wykonywalna                          | Wybierz istniejące ustawienie klasy wykonywalnego. To pole jest dostępne tylko dla działań typu **Poziom wykonywania elementu wiadomości** i **Poziom wykonywania elementu wiadomości**. |
| Akcja wypełniania rekordów                   | Wybierz istniejącą akcję wypełniania rekordów. To pole jest dostępne tylko dla działań typu **Wypełnij rekordy**. |
| Usługa sieci Web                               | Wybierz istniejącą usługę sieci web. To pole jest dostępne tylko dla działań typu **Usługa sieci Web**. |
| Nazwa pliku do wysłania                         | Umożliwia wprowadzenie nazwy załącznika do wiadomości elektronicznej, która musi zostać wysłana przez tę akcję. Jeśli wiele załączników ma taką samą oryginalną nazwę pliku, zostanie wysłana najnowsza. Jeśli nie znaleziono załącznika o określonej oryginalnej nazwie pliku, żądanie zostanie wysłane bez zawartości. To pole jest dostępne tylko dla działań typu **Usługa sieci Web**. |
| Nazwa pliku                                 | Określ nazwę pliku, który będzie wynikiem akcji. Ten plik może być odpowiedzią z serwera sieci web lub raportu, który zostanie wygenerowany. To pole jest dostępne tylko dla działań **usługi sieci Web** i **Wiadomość eksportu raportowania elektronicznego**. |
| Dołącz pliki do dokumentów źródłowych          | Zaznacz to pole wyboru, aby dołączyć wygenerowane pliki do rekordów w przywoływanej tabeli głównej dla elementów EM. To pole jest dostępne tylko dla działań **Eksport raportowania elektronicznego** i **Usługi sieci Web**. |
| Dołącz pliki z archiwum wyjściowego do elementów | Zaznacz to pole wyboru, aby wyodrębnić oddzielne pliki XML z wyjściowego pliku archiwum i dołączyć je do odpowiednich elementów wiadomości elektronicznych. To pole jest dostępne tylko dla działań typu **Eksport raportowania elektronicznego**. |
| Liczba elementów wiadomości na eksport        | Określ limit liczby elementów wiadomości, które muszą być zawarte w jednym pliku (wiadomości). To pole jest dostępne tylko dla działań typu **Eksport raportowania elektronicznego**. |
| Użyj źródła ER                             | Zaznacz to pole wyboru, aby użyć parametrów źródła ER do importu. W przeciwnym razie używany jest załącznik z wiadomości elektronicznej. To pole jest dostępne tylko dla działań typu **Import raportowania elektronicznego**. |
| Pokaż okno dialogowe                               | Ustaw tę opcję jako **Tak**, jeśli okno dialogowe musi być widoczne dla użytkownika przed generowaniem raportu. To pole jest dostępne tylko dla działań typu **Wiadomość eksportu raportowania elektronicznego**. |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>Typy akcji przetwarzania wiadomości

W polu **Typ akcji** są dostępne następujące opcje:

- **Utwórz wiadomość** — użycie tego typu akcji umożliwia użytkownikom ręczne tworzenia wiadomości na stronie **Wiadomość elektroniczna**. Stanu wyniku nie można skonfigurować dla tego typu akcji.
- **Wypełnij rekordy** — ten typ akcji musi być już ustawiony. Powiąż go z akcją wypełniania rekordów, aby umożliwić uwzględnienie akcji w przetwarzaniu. Zakłada się, że ten typ akcji jest używany dla pierwszej akcji w trakcie przetwarzania wiadomości (gdy nie jest tworzona wiadomość z wyprzedzeniem) lub jako akcja dodawania elementów wiadomości do wcześniej utworzonej wiadomości (przez akcję typu **Utwórz wiadomość**). Z tego względu można ustawić tylko stan wyniku elementów wiadomości dla tego typu akcji. Stan początkowy można ustawić tylko dla wiadomości.
- **Poziom wykonywania wiadomości** — Użyj tego typu akcji, aby skonfigurować wykonywalną klasę, która powinna zostać oceniona na poziomie wiadomości.
- **Poziom wykonywania elementu wiadomości** — Użyj tego typu akcji, aby skonfigurować wykonywalną klasę, która powinna zostać oceniona na poziomie elementu wiadomości.
- **Eksport raportowania elektronicznego** — użyj tego typu akcji dla akcji, które powinny generować raport, który opiera się na eksportowaniu konfiguracji ER na poziomie elementu wiadomości.
- **Wiadomość dotycząca eksportu raportowania elektronicznego** — użyj tego typu akcji dla akcji, które powinny generować raport, który opiera się na eksportowaniu konfiguracji ER na poziomie wiadomości (np. kiedy wiadomość nie ma żadnego elementu wiadomości).
- **Import raportowania elektronicznego** — użyj tego akcji dla akcji, które powinny generować raport, który opiera się na importowaniu konfiguracji ER.
- **Wiadomość dotycząca przetwarzania poziomu użytkownika** — użyj tego typu akcji dla akcji, które zakładają wykonywanie niektórych akcji ręcznie przez użytkownika na poziomie wiadomości. Na przykład użytkownik może aktualizować stan wiadomości.
- **Przetwarzanie użytkownika** — użyj tego typu akcji dla akcji, które zakładają wykonywanie niektórych akcji ręcznie przez użytkownika na poziomie elementu wiadomości. Na przykład użytkownik może aktualizować stan elementów wiadomości.
- **Usługa sieci Web** — użyj tego typu akcji dla akcji, które powinny przekazywać wygenerowany raport do usługi sieci web. Ten typ akcji nie jest używany do raportów komunikacji związanej z fakturami sprzedaży/zakupu we Włoszech. W przypadku tego typu akcji strona **Akcje przetwarzania wiadomości** zawiera kartę skróconą **Dodatkowe szczegóły**, na której można określić tekst potwierdzenia. Ten tekst potwierdzenia jest wyświetlany użytkownikom przed skierowaniem żądania do wybranej usługi sieciowej.
- **Weryfikacja żądania** — użyj tego typu akcji, aby żądać weryfikacji z serwera.

### <a name="initial-statuses-fasttab"></a>Skrócona karta Stany początkowe

> [!NOTE]
> Skrócona karta **Stany początkowe** nie jest dostępna dla akcji, które mają typ początkowy **Utwórz wiadomość**.

| Pole               | Opis |
|---------------------|-------------|
| Stan elementu wiadomości | Wybierz status elementu wiadomości, dla której ma być oceniana wybrana akcji przetwarzania wiadomości. |
| opis         | Opis wybranego stanu elementu wiadomości. |

### <a name="result-statuses-fasttab"></a>Skrócona karta Stany wyników

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

## <a name="electronic-message-processing"></a><a id="processing"></a>Przetwarzanie wiadomości elektronicznych

Wiadomość elektroniczna jest pojęciem podstawowych funkcji EM. Agreguje akcje, które mają być wykonywane dla wiadomości elektronicznych. Akcje można połączyć za pomocą stanu początkowego i stanu wynikowego. Ewentualnie akcje typu **Przetwarzanie użytkownika** mogą być rozpoczynane niezależnie. Aby skonfigurować przetwarzanie wiadomości elektronicznych, przechodząc do **Podatek** \> **Konfiguracja** \> **Wiadomości elektroniczne** \> **Przetwarzanie wiadomości elektronicznych**.

Skrócona karta **Akcja** pozwala na dodanie wstępnie zdefiniowanych akcji do przetwarzania. Można określić, czy akcję należy uruchomić osobno lub czy może być zainicjowana przez przetwarzanie. Aby określić, że działanie podczas przetwarzania może być inicjowane tylko przez użytkownika, ustaw pole **uruchom oddzielnie** jako **tak** dla tej akcji. Jeśli akcja powinna zostać włączona przez przetwarzanie wiadomości lub elementów wiadomości, które mają stan zdefiniowany jako początkowy dla akcji, ustaw pole **uruchom osobno** jako **Nie**. Akcja typu **akcji użytkownika** musi być zawsze uruchomiona oddzielnie.

Czasami kilka akcji trzeba zagregować w sekwencję, nawet jeśli pierwsza akcja jest ustawiona tak, aby została wykonana oddzielnie. Użytkownik musi na przykład zainicjować generowanie raportu. Jednak natychmiast po utworzeniu raport musi zostać wysłany do usługi sieciowej i odpowiedź z usługi sieci web musi być zarejestrowana w systemie. W takiej sytuacji można utworzyć nierozdzielną sekwencję czynności, które będą zawsze razem wykonywane. Na skróconej karcie **Akcja** wybierz **Nierozdzielne sekwencje** powyżej siatki i utwórz sekwencję. Następnie, dla wszystkich akcji, które muszą być wykonywane w jednej sekwencji, wybierz sekwencję w polu **nierozdzielnych sekwencji**. W tym przykładzie pole **uruchom oddzielnie** można ustawić jako **tak** dla pierwszej akcji w sekwencji, ale trzeba je ustawić jako **Nie** dla wszystkich innych akcji.

Akcje typów komunikatów **Eksportuj raportowanie elektroniczne** i **Eksportuj raportowanie elektroniczne** uruchamiają format ER, który ma parametry wejściowe. Jeśli przetwarzanie wiadomości elektronicznych obejmuje akcje jednego z tych typów, przed wygenerowaniem raportu należy określić wartości parametrów wejściowych. W ten sposób system może generować raport przy użyciu funkcji przetwarzania wsadowego. Nad siatką można wybrać **parametry**, aby skonfigurować parametry dla wybranego typu akcji (**eksport raportowania elektronicznego** lub **Wiadomość dotycząca eksportu raportowania elektronicznego**). Zaznacz pole wyboru **Użyj parametrów** dla akcji, która musi zostać uruchamiana z określonymi parametrami w trybie wsadowym.

Skrócona karta **Dodatkowe pola elementów wiadomości** pozwala na dodanie wstępnie zdefiniowanych dodatkowych pól, które są związane z elementami wiadomości. Należy dodać dodatkowe pola dla każdego typu elementu wiadomości do którego odnoszą się pola. Możesz określić wartość domyślną, która zostanie przypisana do dodatkowego pola podczas przetwarzania.

Skrócona karta **Dodatkowe pola wiadomości** pozwala na dodanie wstępnie zdefiniowanych dodatkowych pól, które są związane z wiadomościami. Możesz określić wartość domyślną, która zostanie przypisana do dodatkowego pola podczas przetwarzania.

Skrócona karta **Role zabezpieczeń** pozwala skonfigurować role zabezpieczeń, które są wstępnie zdefiniowane w systemie do określonego przetwarzania. Użytkownicy, którzy mają określoną rolę widzieli tylko przetwarzanie zdefiniowane dla tej roli.

Skrócona karta **Partia** umożliwia skonfigurowanie przetwarzania do pracy w systemie przetwarzania wsadowego. Zaleca się skonfigurowanie trybu przetwarzania wsadowego dla przetwarzania bezpośrednio na stronie **Wiadomości elektroniczne** lub **Elementy wiadomości elektronicznej**, po wybraniu opcji **Uruchom przetwarzanie** w okienku akcji w celu zainicjowania przetwarzania.
