---
title: Udoskonalenia cXML dotyczące zakupów
description: Funkcja udoskonaleń cXML dotyczących zakupów opiera się na istniejącej funkcji zewnętrznego katalogu PunchOut, która jest używana dla zapotrzebowań na zakup.
author: dasani-madipalli
manager: tfehr
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: cd0435fd89050311ecd4f24400d5830cbcf8fdfd
ms.sourcegitcommit: b281ac04157f6ccbd159fc89f58910b430a3b6a9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826932"
---
# <a name="purchasing-cxml-enhancements"></a>Udoskonalenia cXML dotyczące zakupów

[!include [banner](../includes/banner.md)]

Funkcja _udoskonaleń cXML dotyczących zakupów_ opiera się na [istniejącej funkcji zewnętrznego katalogu](set-up-external-catalog-for-punchout.md), która jest używana dla zapotrzebowań na zakup. Ta istniejąca funkcjonalność jest nazywana _PunchOut_. Chociaż zamówienie zakupu nie musi pochodzić z zapotrzebowania na zakup, musi istnieć połączenie między dostawcą w zamówieniu zakupu a parametrami, które są używane do wysyłania dokumentu zamówienia zakupu.

## <a name="turn-on-the-purchasing-cxml-enhancements-feature"></a>Włącz funkcję ulepszeń cXML zakupów

Aby włączyć tę funkcję, otwórz stronę **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** i wyszukaj funkcję o nazwie *Udoskonalenia cXML dotyczące zakupów*. Wybierz funkcję, a następnie wybierz **Wyłącz teraz** i włącz ją.

Po włączeniu tej funkcji należy skonfigurować ustawienia w następujących trzech obszarach:

- **[parametry cXML](#cxml-parameters)** — te ustawienia służą do konfigurowania niektórych parametrów globalnych dotyczących funkcji wysyłania zamówień zakupu.
- **[Ustawienia dostawcy](#vendor-setup)** — Jeśli język commerce eXtensible Markup Language (cXML) powinien być używany domyślnie dla wszystkich nowych zamówień zakupu, które zostały utworzone dla dowolnego dostawcy, w polu **Wyślij zamówienie zakupu przez cXML** ustaw wartość _Tak_ dla tego dostawcy.
- **[Katalogi zewnętrzne](#external-catalog-setup)** — Użyj nowych ustawień **Właściwości zamówienia**, aby zdefiniować format dokumentu zamówienia i sposób jego wysłania.

Poniższa ilustracja podsumowuje tę konfigurację.

![Obszary służące do konfigurowania funkcji cXML](media/cxml-settings-areas.png "Obszary służące do konfigurowania funkcji cXML")

Ponadto należy skonfigurować [Zadanie wsadowe żądania o zamówienie zakupu](#po-batch). To zadanie wsadowe służy do wysyłania potwierdzonych zamówień zakupu.

## <a name="set-up-global-cxml-parameters"></a><a name="cxml-parameters"></a>Konfigurowanie parametrów globalnego cXML

Na stronie **parametry cXML** można określić kilka ustawień globalnych, które mają zastosowanie do funkcji wysyłania zamówień zakupu.

![Strona parametry cXML](media/cxml-parameters.png "Strona parametry cXML")

Przejdź do **Zaopatrzenie i sourcing \> Konfiguracja \> zarządzanie cXML \> parametry cXML** i ustaw następujące parametry:

- **Tryb testowy cXML** — ten globalny parametr ma wpływ na sposób fizycznego wysyłania zamówień zakupu z tego zadania wsadowego. Należy wybrać jedną z następujących opcji:

    - **Testowanie** — w tym trybie można uruchomić zadanie wsadowe, a następnie generowany jest dokument XML dla wiadomości, ale nie jest on wysyłany. Zamiast tego jest on zapisany w żądaniu zamówieniu zakupu w celu dokonania przeglądu. Ten tryb jest pomocny podczas wstępnej implementacji, a użytkownik chce zobaczyć, jak dane są wprowadzane w komunikacie cXML. Można również wygenerować przykładowe wiadomości, które można wysłać do dostawców w celu wstępnego sprawdzenia poprawności.
    - **Aktywne** — w tym trybie funkcja używa [ustawień katalogu zewnętrznego](#external-catalog-setup) do fizycznego przekazania każdego dokumentu do dostawcy.

- **Wyślij aktualizacje żądań zakupu** — ustawienie tej opcji na wartość *Tak* powoduje wysłanie komunikatu aktualizacji dla zamówień zakupu. Aby zapobiec wysyłaniu wiadomości, należy ją skonfigurować na wartość *Nie*. Większość dostawców preferuje otrzymywanie komunikatów aktualizacji. Zamiast tego wymagają, aby odbiorcy mogli kontaktować się z nimi przez telefon lub pocztę e-mail, jeśli zamówienie zakupu powinno zostać zmienione. Ten parametr jest parametrem globalnym i nie można określić nadpisania w katalogu zewnętrznym dla każdego dostawcy. Zamówienie zakupu zostanie oznaczone jako zaktualizowane, jeśli opublikujesz drugie potwierdzenie w zamówieniu zakupu, ale pierwsze potwierdzenie zostało już wysłane i potwierdzone przez dostawcę. Jeśli istnieje drugie potwierdzenie, ale pierwsze potwierdzenie nie zostało wysłane, drugie potwierdzenie będzie traktowane jako nowy dokument. Zamówienie zakupu można zatwierdzić dowolną liczbę razy do momentu wysłania jednego potwierdzenia. Następne potwierdzenie będzie traktowane jako wiadomość aktualizująca.
- **Usuń wysyłanie żądań zakupu** — ustawienie tej opcji na wartość *Tak* powoduje usunięcie komunikatu dla zamówień zakupu. Aby zapobiec wysyłaniu wiadomości, należy ją skonfigurować na wartość *Nie*. Większość dostawców preferuje otrzymywanie komunikatów o usunięciu. Zamiast tego wymagają, aby odbiorcy mogli kontaktować się z nimi przez telefon lub pocztę e-mail, jeśli zamówienie zakupu zostało wysłane przez przypadek. Ten parametr jest parametrem globalnym i nie można określić nadpisania w katalogu zewnętrznym dla każdego dostawcy. Zamówienie zakupu zostanie oznaczone jako usunięte, jeśli zamówienie zakupu zostanie anulowane w Supply Chain Management.
- **Plik archiwum** — Określ ścieżkę do pliku, do którego chcesz eksportować i zapisywać zarchiwizowane dokumenty cXML. Ścieżka jest używana po uruchomieniu funkcji przeczyszczania na stronie **Żądania zamówienia zakupu**.
- **Maksymalna liczba znaków w wierszu ulicy** — umożliwia wprowadzenie maksymalnej liczby znaków, która może być używana w polu ulica dla adresów w dokumencie cXML. Ten parametr globalny ma wpływ na wszystkich dostawców, chyba że w właściwościach zewnętrznego katalogu określono zastąpienie.

## <a name="set-up-vendor-purchase-orders-to-use-cxml"></a><a name="vendor-setup"></a>Konfigurowanie zamówień zakupu dostawców w celu korzystania z cXML

Za każdym razem, gdy użytkownik potwierdzi zamówienie zakupu, w którym opcja **Wyślij zamówienie zakupu za pomocą cXML** ma wartość _Tak_, system automatycznie generuje komunikat cXML i dostarcza go dostawcy skojarzonemu z tym zamówieniem zakupu. Istnieją dwa sposoby sterowania tą opcją w zamówieniach zakupu:

- Aby skonfigurować dostawcę w taki sposób, aby automatycznie używał cXML dla wszystkich nowych zamówień zakupu utworzonych z zapotrzebowania, należy przejść do **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**, a następnie wybrać lub utworzyć dostawcę, aby otworzyć jego stronę szczegółów. Następnie na skróconej karcie **Domyślne zamówienia zakupu** należy określić opcję **Wyślij zamówienie zakupu przez cXML** wartość _Tak_. Jeśli cXML ma być również automatycznie używany do nowych zamówień zakupu, które **nie** są tworzone na podstawie zapotrzebowania, należy również ustawić właściwość zamówienia **ENABLEMANUALPO** na wartość _True_ dla powiązanego katalogu zewnętrznego, zgodnie z opisem w sekcji [Ustawianie właściwości zamówienia](#set-order-properties) później w tym temacie.
- W przypadku poszczególnych zamówień zakupu przejdź do **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**, a następnie wybierz lub utwórz zamówienie zakupu, aby otworzyć jego stronę szczegółów. Przełącz się na widok **Nagłówek**, a następnie na skróconej karcie **Ustawienia** ustaw opcję **Wyślij zamówienie zakupu za pomocą cXML** zgodnie z wymaganiami.

![Ustawienia domyślne zamówień zakupu dostawcy](media/cxml-order-defaults.png "Ustawienia domyślne zamówień zakupu dostawcy")

## <a name="set-up-an-external-catalog-to-use-cxml"></a><a name="external-catalog-setup"></a>Skonfiguruj katalog zewnętrzny, aby używać cXML

Na stronie **Katalogi zewnętrzne** dla każdego z katalogów można skonfigurować funkcje PunchOut oraz funkcje wysyłania zamówień zakupu. Aby znaleźć odpowiednie ustawienia, należy przejść do **Zaopatrzenie i sourcing \> Katalogi \> Katalogi zewnętrzne**. Zacznij od [skonfigurowania każdego katalogu w zwykły sposób](set-up-external-catalog-for-punchout.md). Ten proces obejmuje przypisanie dostawcy, wybranie kategorii, które dostawca może dostarczyć, oraz uaktywnienie katalogu. Następnie skonfiguruj dodatkowe ustawienia opisane w tej sekcji.

> [!NOTE]
> Po potwierdzeniu zamówienia, które można wysłać za pośrednictwem cXML, system wyszukuje dostawcę powiązanego z zamówieniem, a następnie znajduje pierwszy aktywny katalog zewnętrzny, który jest powiązany z tym dostawcą. System używa ustawień z tego zewnętrznego katalogu do wysłania zamówienia zakupu. Jeśli skonfigurowanych jest wiele katalogów zewnętrznych, system używa tylko pierwszego znalezionego katalogu zewnętrznego na podstawie dostawcy w zamówieniu zakupu. Dlatego zaleca się utworzenie tylko jednego zewnętrznego katalogu dla każdego dostawcy.

![Ustawienia katalogu zewnętrznego](media/cxml-supplier-catalog.png "Ustawienia katalogu zewnętrznego")

### <a name="set-the-punchout-protocol-type"></a>Ustaw typ protokołu PunchOut

Na skróconej karcie **Ogólne** na stronie **Katalogi zewnętrzne**, w polu **Typ protokołu Punchout** należy określić wartość _cXML_. Ta opcja będzie jedyną dostępną opcją, o ile partner nie rozszerzył funkcjonalności i udostępnia dodatkową opcję w rozszerzeniu.

Jeśli używany jest również katalog PunchOut, należy również [skonfigurować format wiadomości](set-up-external-catalog-for-punchout.md). Format wiadomości jest używany do nawiązywania połączenia z dostawcą w transakcji PunchOut z poziomu zapotrzebowania. Po wysłaniu zamówienia zakupu do nawiązania połączenia z dostawcą zostaną użyte właściwości zamówienia.

### <a name="set-the-order-properties"></a><a name="set-order-properties"></a>Ustaw właściwości zamówienia

Funkcja _Udoskonalenia cXML dotyczące zakupów_ dodaje nową kartę skróconą **Właściwości zamówienia** dla katalogów zewnętrznych. Ta skrócona karta dostarcza siatkę, w której można zdefiniować właściwości zamówienia. Dostępny jest również pasek narzędzi. Ten pasek narzędzi zawiera trzy przyciski, których można wykorzystać do zarządzania właściwościami zamówienia:

- **Właściwości domyślne** – Podczas konfigurowania nowego katalogu wybierz ten przycisk, aby dodać wstępnie zdefiniowaną kolekcję często używanych właściwości do siatki.
- **Nowy** – umożliwia dodanie nowej właściwości do siatki.
- **Usuń** – służy do usuwania aktualnie wybranej właściwości z siatki. Jeśli przypadkowo usuniesz domyślną właściwość, wybierz **Właściwości domyślne**, aby przywrócić wszystkie brakujące właściwości.

Za każdym razem, gdy do siatki dodawana jest jedna lub więcej właściwości, należy za pomocą prawej kolumny określić wartość dla każdej z nich.

Właściwości domyślne należy stosować w następujący sposób:

- **BUYER\_COOKIE** – to pole śledzenia może być używane do wskazywania konkretnych informacji dotyczących firmy użytkownika. Jeśli użytkownik nie dysponuje umową z dostawcą dotyczącym sposobu używania tej właściwości, nie ma bardzo istotnego znaczenia podczas wysyłania zamówienia zakupu. Dlatego należy ją skonfigurować na wartość prostą.
- **DELIVERTO** – Jeśli adres wysyłki jest wprowadzony w dokumencie z zamówienia zakupu, pole **Ważne informacje** jest używane do ustawiania pola **DeliverTo** w wiadomości XML. Jeśli chcesz, aby ta wartość była nazwą żądającego i ustawisz pole żądającego w nagłówku zamówienia, wprowadź wartość _REQUESTER_ dla tej właściwości, tak aby nazwa żądającego została wpisana w polu **DeliverTo** w plik XML. W tym przypadku podstawowy adres e-mail i używany numer telefonu będą się znajdować w zleceniodawcy zamiast w zamówieniu.
- **DEPLOYMENTMODE** – ustawia tę właściwość zgodnie z wymaganiami dostawcy. Wartości to zazwyczaj _PRODUKCJA_ lub _TESTOWANIE_. Umożliwia ustawienie wartości na podstawie komunikacji z dostawcą. Zazwyczaj musi odpowiadać planowanemu systemowi za wartość **ORDERCHECKURL**, którą dostawca wskazuje jako system testowy lub produkcyjny.
- **FIXEDBILLADDRESSID** – gdy pole **addressID** w wiadomości XML jest ustawione, pobiera lokalizację określoną w adresie. Jeśli wartość identyfikatora pokazana dostawcy różni się od wartości w lokalizacji z jakiegoś powodu, można wymusić zastąpienie, określając wartość w tym miejscu. Założeniem jest, że do dostawcy będzie używany tylko jeden adres, a adres jest ustawiany w systemie dostawcy. Adres na fakturze to podstawowy adres faktury określony dla firmy w Supply Chain Management.
- **FIXEDSHIPADDRESSID** – gdy pole **addressID** w wiadomości XML jest ustawione, pobiera lokalizację określoną w adresie. Jeśli wartość identyfikatora pokazana dostawcy różni się od wartości w lokalizacji z jakiegoś powodu, można wymusić zastąpienie, określając wartość w tym miejscu. Założeniem jest, że do dostawcy będzie używany tylko jeden adres, a adres jest ustawiany w systemie dostawcy. Adres wysyłki to adres określony w nagłówku zamówienia zakupu. Większość dostawców akceptuje tylko adresy nagłówków, a nie adresy wierszy. Mimo że dla adresów wierszy w kodzie XML istnieją pola, zostaną one ustawione na adres nagłówka.
- **FROM\_DOMAIN** – umożliwia wprowadzenie wartości używanej do wysyłania dokumentów zamówienia zakupu. Ta wartość jest dostarczana przez dostawcę.
- **FROM\_IDENTITY** – umożliwia wprowadzenie wartości używanej do wysyłania dokumentów zamówienia zakupu. Ta wartość jest dostarczana przez dostawcę.
- **ORDERCHECKURL** – umożliwia wprowadzenie adresu URL, do którego mają być transmitowane dokumenty zamówienia zakupu. Ten adres URL zaczyna się od `https://` i jest dostarczany przez dostawcę.
- **PAYLOAD\_ID** – umożliwia wprowadzenie wartości prefiksu dla identyfikatora ładunku, który jest wymagany w przypadku procesów biznesowych obowiązujących dla bieżącego dostawcy.
- **SENDER\_DOMAIN** – umożliwia wprowadzenie wartości używanej do wysyłania dokumentów zamówienia zakupu. Ta wartość jest dostarczana przez dostawcę.
- **SENDER\_IDENTITY** – umożliwia wprowadzenie wartości używanej do wysyłania dokumentów zamówienia zakupu. Ta wartość jest dostarczana przez dostawcę.
- **SHARED\_SECRET** – umożliwia wprowadzenie wartości używanej do wysyłania dokumentów zamówienia zakupu. Ta wartość jest dostarczana przez dostawcę.
- **STREETLENGTH** – umożliwia wprowadzenie liczby oznaczającej maksymalną liczbę znaków akceptowanych przez dostawcę jako nazwę ulicy. Wprowadzenie wartości w tym polu powoduje zastępowanie wartości określonej na stronie **parametry cXML**. System usunie podziały wierszy i spacje, aby spróbować dopasować standardowy adres w rozwiązaniu Supply Chain Management do liczby znaków określonej w tym miejscu. Wszelkie dodatkowe znaki zostaną obcięte.
- **TO\_DOMAIN** – umożliwia wprowadzenie wartości używanej do wysyłania dokumentów zamówienia zakupu. Ta wartość jest dostarczana przez dostawcę.
- **TO\_IDENTITY** – umożliwia wprowadzenie wartości używanej do wysyłania dokumentów zamówienia zakupu. Ta wartość jest dostarczana przez dostawcę.
- **USERAGENT** – umożliwia wprowadzenie wartości identyfikującej używany system. Na przykład wpisz _Dynamics 365 Supply Chain Management_.
- **VERSION** – Wprowadź numer wersji cXML, jeśli dostawca żąda tych informacji. Wersjadomyślna to *1.2.008*. Ta wersja jest stabilna i akceptowana przez większości dostawców.
- **RESPONSETEXT** – Wprowadź dowolny niestandardowy tekst, który dostawca powinien zwrócić w wiadomości odpowiedzi cXML po wysłaniu zamówienia. W ten sposób system może oznaczyć wiadomość jako _Potwierdzona_. Jeśli odpowiedź nie jest zgodna ze standardowym tekstem lub tekstem klienta, który tu wprowadzisz, żądanie zostanie oznaczone jako _Błąd_.
- **RESPONSETEXTSUB** – ustawienie tej właściwości na wartość _TRUE_, jeśli ma być wyszukiwany tekst odpowiedzi dostawcy dla wartości określonych w polu **RESPONSETEXT**. Na przykład dostawca może zwrócić długi ciąg, który w odpowiedzi zawiera tekst „OK”. W takim przypadku można wprowadzić _OK_ w polu **RESPONSETEXT** i określić dla opcji **RESPONSETESTSUB** wartość _TRUE_, aby w dowolnym miejscu odpowiedzi szukać „OK”. Następnie można określić zamówienie jako _Potwierdzone_.
- **CONTENTTYPE** – w typowej konfiguracji katalogu nie ma konieczności ustawiania tej właściwości. Jeśli otrzymasz błąd serwera 500 z systemu dostawcy podczas wysyłania zamówienia zakupu, możesz przeprowadzić testy, ustawiając tę właściwość na _FALSE_. Ta wartość zmieni ustawienie w żądaniu sieci Web i może umożliwić wysłanie wiadomości dla niektórych platform.
- **ENABLEHEADERS** – Ustaw tę właściwość na _TRUE_, aby wysyłać nagłówki wraz z zamówieniem. Tę właściwość należy ustawiać tylko wtedy, gdy jest ona wymagana przez dostawcę. Jeśli dla tej właściwości zostanie ustawiona wartość _TRUE_, należy dodać dodatkowe właściwości niestandardowe oparte na nazwach dostarczanych przez dostawcę, a następnie poprzedzić je znakiem _H\__. Typowe przykłady to **H\_USERID**, **H\_PASSWORD**, **H\_RECEIVERID** i **H\_ACTIONREQUEST**. Następujące właściwości niestandardowe znajdują się w właściwościach domyślnych:

    - **H\_USERID** – Jeśli partner handlowy wymaga wysłania identyfikatora użytkownika jako części adresu URL w celu przesłania zamówienia zakupu, wprowadź wartość w tym miejscu.
    - **H\_PASSWORD** – Jeśli partner handlowy wymaga wysłania hasła jako części adresu URL w celu przesłania zamówienia zakupu, wprowadź wartość w tym miejscu.

- **ENABLEMANUALPO** – Jeśli ta właściwość ma wartość _TRUE_, podczas ręcznego tworzenia zamówień zakupu (czyli nierozpoczynających się od zapotrzebowania) przez użytkowników te zamówienia zakupu odziedziczą ustawienie opcji **Wyślij zamówienie zakupu przez cXML** od dostawcy. Jeśli ta właściwość nie jest ustawiona lub ma wartość _FALSE_, w nagłówku zamówienia zakupu nie zostanie ustawiona opcja **Wyślij zamówienie zakupu za pomocą cXML** dla ręcznie utworzonych zamówień zakupu. W przypadku zamówień zakupu utworzonych z zapotrzebowania ustawienie **Wyślij zamówienie zakupu za pomocą cXML** jest zawsze dziedziczone od dostawcy, niezależnie od ustawienia tej właściwości. Aby uzyskać więcej informacji, zajrzyj do sekcji [Konfigurowanie zamówień zakupu dostawców w celu korzystania z cXML](#vendor-setup) wcześniej w tym temacie.
- **PUNCHOUTPOONLY** – Jeśli ta właściwość ma wartość _TRUE_, tylko wiersze zapotrzebowania zakupu utworzone na podstawie procesu PunchOut będą miały ustawioną opcję **Wyślij zamówienie zakupu przez cXML** w nagłówku zamówienia zakupu. Ponadto typ wiersza zapotrzebowania zakupu dla wszystkich wierszy zamówienia zakupu musi być _Pozycja z zewnętrznego katalogu_. W przeciwnym razie nie można utworzyć zamówienia zakupu cXML.
- **PUNCHOUTSHIPTO** – Jeśli ta właściwość ma wartość _TRUE_, domyślny adres firmy zostanie dodany do komunikatu żądania konfiguracji PunchOut, gdy użytkownik otworzy katalog zewnętrzny. Ten adres jest dodawany jako adres **ShipTo**. Dostawca będzie używał adresu **ShipTo** do wyświetlania ceny na podstawie lokalizacji firmy.
- **TRACEPUNCHOUT** – Ta właściwość jest ustawiana na wartość _TRUE_, jeśli podczas próby wyszukania zewnętrznego katalogu z zapotrzebowania zostanie wyświetlony komunikat o błędzie. Informacje o śledzeniu będą następnie wprowadzane dla wiadomości **PunchOutSetupRequest** i **PunchOutResponse**, które są przesyłane między Supply Chain Management a witryną dostawcy. Informacje te można wyświetlić na stronie **Dziennik wiadomości koszyka cXML**, który można otworzyć z poziomu strony **Konfiguracja katalogu zewnętrznego** dla katalogu dostawcy, z którym występują problemy. Właściwość tę należy ustawiać na wartość _TRUE_ tylko w przypadku rozwiązywania problemów, ponieważ powoduje to utworzenie dużego obciążenia bazy danych dla każdego PunchOut. Aby uzyskać więcej informacji, zobacz sekcję [Wyświetl dziennik komunikatów koszyka cXML dla zewnętrznego katalogu PunchOut](#message-log) w dalszej części tego tematu.
- **REPLACENEWLINE** – ustaw tę właściwość na _TRUE_, jeśli wystąpi problem, ponieważ system dostawcy wysyła wiadomość **PunchOutResponse** zawierającą znaki końca linii (\\n). Ten problem może wystąpić, jeśli wiadomości dostawcy są analizowane za pośrednictwem oprogramowania pośredniczącego lub centrum zaopatrzenia. Jeśli wystąpił problem z konfiguracją nowego dostawcy, ustaw właściwość **TRACEPUNCHOUT** na wartość _TRUE_, aby wyświetlić komunikat **PunchOutResponse**, i określ, czy znaczniki XML mają być podzielone na znaki końca linii.
- **POCOMMENTS** – ustaw właściwość na _TRUE_, jeśli dokument cXML ma zawierać notatki dołączone do zamówienia zakupu w Supply Chain Management. Tekst załącznika zostanie uwzględniony w komentarzach nagłówka w wiadomości zamówienia zakupu. Aby uzyskać więcej informacji o sposobach wybierania i przetwarzania tych załączników przez system, zapoznaj się z sekcją [Dołącz uwagi do zamówienia zakupu](#attach-po-notes) w dalszej części tego tematu.
- **VENDCOMMENTS** – ustaw właściwość na _TRUE_, jeśli dokument cXML ma zawierać notatki dołączone do zamówienia zakupu w Supply Chain Management. Tekst załącznika zostanie uwzględniony w komentarzach nagłówka w wiadomości zamówienia zakupu. Aby uzyskać więcej informacji o sposobach wybierania i przetwarzania tych załączników przez system, zapoznaj się z sekcją [Dołącz uwagi do zamówienia zakupu](#attach-po-notes).
- **CLEANAMP** – Ustaw tę właściwość na _TRUE_, jeśli pojawi się komunikat o błędzie podczas próby wykonania operacji PunchOut do dostawcy, a zwrotny adres URL dostawcy zawiera nieprawidłowo zakodowane znaki Et (\&).
- **PUNCHOUTTZ** – Ustaw tę właściwość na _TRUE_, jeśli dostawca, z którym współpracujesz, używa standardu Międzynarodowej Organizacji Normalizacyjnej (ISO) 8601, aby przeprowadzić konkretną weryfikację daty/godziny komunikatu żądania PunchOut. Supply Chain Management używa daty uniwersalnego czasu koordynowanego (UTC) w komunikacie **PunchOutSetupRequest**. Dlatego po ustawieniu tej właściwości na _TRUE_, *+00:00* jest dodawane do formatu daty/godziny.
- **WMSADDRESSID** – Ustaw tę właściwość na _TRUE_, aby używać numeru magazynu w nagłówku zamówienia zakupu jako wartości **addressID** w adresie **ShipTo** dla żądania zamówienia, które jest wysyłane do dostawcy. W przypadku ustawienia wartości właściwości **FIXEDSHIPADDRESSID** ta wartość ma pierwszeństwo przed tą wartością. Dlatego należy używać jednej właściwości lub drugiej w celu ustawienia wartości **addressID** w adresie **ShipTo** dla dokumentu.
- **PUNCHOUTSHIPTOUSER** – Ta właściwość działa razem z właściwością **PUNCHOUTSHIPTO**. Jeśli **PUNCHOUTSHIPTO** ma wartość _TRUE_, wybierany jest adres podmiotu prawnego. Jeśli **PUNCHOUTSHIPTOUSER** ma wartość _TRUE_, zamiast adresu firmy jest używany adres podstawowy użytkownika PunchOut.

### <a name="activate-the-external-catalog"></a>Aktywuj katalog zewnętrzny

Po zakończeniu ustawiania wszystkich właściwości i innych ustawień katalogu zewnętrznego, wróć do skróconej karty **Ogólne** strony **Katalogi zewnętrzne** i ustaw opcję **Aktywny** na *Tak*.

### <a name="attach-notes-to-a-purchase-order"></a><a name="attach-po-notes"></a>Dołączanie notatek do zamówienia zakupu

Jak wspomniano w sekcji [Ustaw właściwości zamówienia](#set-order-properties), jeśli chcesz, aby dostarczony cXML zawierał tekst z notatek dołączonych do odpowiedniego zamówienia zakupu i / lub rekordów dostawcy, możesz ustawić **POCOMMENTS** i/lub **VENDCOMMENTS** na _TRUE_ w konfiguracji katalogu zewnętrznego. W tej sekcji przedstawiono więcej szczegółów na temat wybierania i przetwarzania tych załączników przez system, jeśli są one używane.

Aby określić typy notatek, dla których będzie wyglądał system, przejdź do **Zaopatrzenie i sourcing \> Ustawienia \> Formularze \> Ustawienia formularza**. Następnie na karcie **Zamówienie zakupu** w polu **Uwzględnij dokumenty typu** wybierz typ notatki, która ma być dołączana. Zostaną uwzględnione tylko notatki tekstowe, a nie załączniki dokumentów.

![Strona Ustawienia formularza](media/cxml-form-setup.png "Strona Ustawienia formularza")

Załączniki będą dołączane do zamówienia zakupu tylko wtedy, gdy w polu **Typ** ustawiono wartość, która została wybrana w polu **Uwzględnij dokumenty typu**, a pole **Ograniczenia** jest ustawione na _Zewnętrzne_. Aby utworzyć, wyświetlić lub edytować załączniki dla zamówienia zakupu, przejdź do **Zaopatrzenie i sourcing \> Wszystkie zamówienia zakupu**, wybierz lub utwórz zamówienie zakupu, a następnie wybierz przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu.

![Dołączona notatka, która jest skonfigurowana do wysłania do dostawcy](media/cxml-note-to-vendor.png "Dołączona notatka, która jest skonfigurowana do wysłania do dostawcy")

## <a name="view-the-cxml-cart-message-log-for-external-catalog-punchout"></a><a name="message-log"></a>Wyświetl dziennik komunikatów koszyka cXML dla zewnętrznego katalogu PunchOut

W przypadku ustawienia pola **Typ protokołu Punchout** na _cXML_ dla zewnętrznego katalogu system będzie rejestrował dziennik komunikatów z koszyków, które powracają z dostawców. Ten dziennik może być używany do rozwiązywania problemów i innych celów danych.

Aby otworzyć dziennik dla zewnętrznego katalogu, wybierz odpowiedni katalog, a następnie w okienku akcji wybierz opcję **Dziennik wiadomości koszyka cXML**. Na stronie **Dziennik wiadomości koszyka cXML** jest wyświetlana lista zwróconych koszyków, kod XML powiązany z tymi koszykami oraz wiersze utworzone w powiązanym zapotrzebowaniu zakupu.

![Strona dziennika wiadomości koszyka cXML](media/cxml-cart-message-log.png "Strona dziennika wiadomości koszyka cXML")

## <a name="set-the-extrinsic-elements-for-external-catalog-punchout"></a>Umożliwia ustawienie elementów zewnętrznych dla PunchOut katalogu zewnętrznego

W przypadku ustawienia pola **Typ protokołu Punchout** na *cXML* dla zewnętrznego katalogu można dodać niestandardowe elementy zewnętrzne, które będą wstawiane w odpowiednim miejscu komunikatu XML żądania.

Aby dodać elementy zewnętrzne do katalogu zewnętrznego, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Katalogi \> Katalogi zewnętrzne**.
1. Wybierz odpowiedni katalog.
1. Na skróconej karcie **Format wiadomości** w sekcji **Zewnętrzne** wybierz opcję **Dodaj**, aby dodać wiersz do siatki dla każdego elementu zewnętrznego, który chcesz uwzględnić. Dla każdego wiersza ustaw następujące pola:

    - **Nazwa** – wprowadź nazwę dla elementu. Ta wartość stanie się wartością atrybutu **nazwy** dla elementu XML **Zewnętrznego** tworzonego przez każdy wiersz. Zazwyczaj użytkownik pracuje z dostawcą w celu uzgodnienia nazwy każdego elementu zewnętrznego.
    - **Wartość** — umożliwia wybór wartości dla elementu. Ta wartość stanie się wartością elementu XML tworzonego przez każdy wiersz. Dostępne są następujące wartości:

        - **Nazwa użytkownika** – Użyj nazwy użytkownika, który wykonuje PunchOut. Ta nazwa jest nazwą rejestrowania dla Supply Chain Management.
        - **E-mail użytkownika** – Użyj adresu e-mail użytkownika, który wykonuje PunchOut. Ten adres jest adresem skonfigurowanym przez użytkownika na karcie **Konto** na stronie **Opcje użytkownika**.
        - **Wartość losowa** — używana jest unikatowa wartość losowa.
        - **Pełna nazwa użytkownika** — służy do używania pełnej nazwy osoby kontaktowej, która jest skojarzona z użytkownikiem, który korzysta z zewnętrznego katalogu.
        - **Imię** — służy do używania imienia osoby kontaktowej, która jest skojarzona z użytkownikiem, który korzysta z zewnętrznego katalogu.
        - **Nazwisko** — służy do używania nazwiska osoby kontaktowej, która jest skojarzona z użytkownikiem, który korzysta z zewnętrznego katalogu.
        - **Numer telefonu** — służy do używania głównego numeru telefonu osoby kontaktowej, która jest skojarzona z użytkownikiem, który korzysta z zewnętrznego katalogu.

![Ustawienia elementu zewnętrznego](media/cxml-extrinsics.png "Ustawienia elementu zewnętrznego")

Użytkownik lub administrator nie zobaczy elementów zewnętrznych, ponieważ nie zostaną one dodane, dopóki użytkownik nie wykona PunchOut. Zostaną one automatycznie wstawione między elementami **BuyerCookie** i **BrowserFromPost** w komunikacie żądania ustawienia cXML. Z tego względu nie trzeba ustawiać ich ręcznie w formacie XML podczas konfigurowania zewnętrznego katalogu.

![Elementy zewnętrzne dodane do pliku XML](media/cxml-extrinsics-xml.png "Elementy zewnętrzne dodane do pliku XML")

## <a name="create-and-process-a-purchase-order"></a><a name="create-po"></a>Tworzenie i przetwarzanie zamówienia zakupu

Podczas tworzenia zamówienia zakupu dla dostawcy system odziedziczy ustawienie opcja **Wyślij zamówienie zakupu za pośrednictwem cXML** od tego dostawcy. Jednak ustawienie pozostaje dostępne na skróconej karcie **Ustawienia** w widoku **Nagłówek** zamówienia zakupu, dzięki czemu będzie można zmienić je później w razie potrzeby.

![Zamówienie zakupu ustawione do używania cXML](media/cxml-purchase-order.png "Zamówienie zakupu ustawione do używania cXML")

Podczas tworzenia zamówienia zakupu na podstawie zapotrzebowania na zakup pochodzącego z przepływu PunchOut wszystkie wymagane szczegóły wiersza zostaną wypełnione. Następnie można ręcznie dodać wiersze zamówienia zakupu lub skopiować je z innych zamówień zakupu. Upewnij się, że wszystkie wymagane pola zostały ustawione. Wymagane pola zawierają numer odwołania zewnętrznego, który jest numerem dostawcy, który zostanie użyty w komunikacie cXML.

![Przykład zewnętrznego numeru odwołania](media/cxml-line-details.png "Przykład zewnętrznego numeru odwołania")

Po zakończeniu wypełniania wszystkich szczegółów zamówienia zakupu należy go potwierdzić. Żaden komunikat nie zostanie wysłany, chyba że zamówienie zakupu zostanie potwierdzone. Aby potwierdzić zamówienie zakupu, w okienku akcji na karcie **Zakup**, w grupie **Akcje** kliknij **Potwierdź**. 

Po potwierdzeniu zamówienia zakupu można wyświetlić stan potwierdzenia za pomocą arkuszy **Potwierdzenie zamówienia zakupu**. W okienku akcji na karcie **Zakup**, w grupie **Arkusze** kliknij **Potwierdzenia zamówień zakupu**.

Każde zamówienie zakupu może mieć wiele potwierdzeń. Każde potwierdzenie jest oznaczone numerem przyrostowym. Na poniższym rysunku zamówienie zakupu jest *00000275*, a potwierdzenie *00000275-1*. Ta numeracja odzwierciedla standardową funkcjonalność Supply Chain Management, w której zmiany w zamówieniu zakupu, a tym samym typ wiadomości cXML, który powinien zostać wysłany do dostawcy, są identyfikowane na podstawie potwierdzenia. Jak widać na ilustracji, strona **Potwierdzenia zamówienia zakupu** zawiera również pola **Stan wysyłania zamówienia** i **Stan dostawcy żądania zamówienia**. Aby uzyskać więcej informacji o różnych wartościach stanu, które mogą być widoczne na tej stronie, zapoznaj się z sekcją [Monitoruj żądania zamówienia zakupu](#monitor-po-requests) w dalszej części tego tematu.

![Strona potwierdzenia zamówienia zakupu](media/cxml-po-confirmations.png "Strona potwierdzenia zamówienia zakupu")

Aby wyświetlić więcej informacji o dokumencie, wybierz **Żądanie zamówienia zakupu** powyżej siatki.

Strona **Żądanie zamówienia zakupu** zawiera dwie siatki. Siatka w górnej części strony ma jeden rekord dla każdego zamówienia zakupu, które jest oznaczone do wysłania. Siatka na karcie **Historia żądań zamówień zakupu** w dolnej części strony może zawierać kilka rekordów dla wybranego zamówienia zakupu, aby wskazać stan każdego potwierdzenia. Na poniższej ilustracji przedstawiono 00000275 zamówienia zakupu w górnej siatce oraz dokument 00000275-1 w siatce na karcie **Historia żądań zamówień zakupu**.

![Strona żądania zamówienia zakupu](media/cxml-po-request.png "Strona żądania zamówienia zakupu")

Jeśli zadanie wsadowe jest skonfigurowane i uruchomione, dokument zostanie wysłany. Po wysłaniu dokumentu można wyświetlić zmianę stanu. Na poniższej ilustracji pole **Stan wysyłania zamówienia** ma wartość _Wysłane_. Pole **Stan dostawcy żądania zamówienia** jest ustawione na _Potwierdzone_, aby wskazać, że dostawca otrzymał dokument i mógł go odczytać i zapisać w systemie. W siatce na karcie **Historia żądań zamówień zakupu** jest wyświetlany czas wysłania dokumentu. Aby uzyskać więcej informacji o różnych wartościach stanu, które mogą być widoczne na tej stronie, zapoznaj się z sekcją [Monitoruj żądania zamówienia zakupu](#monitor-po-requests).

![Komunikaty o stanie na stronie żądanie zamówienia zakupu](media/cxml-po-request-2.png "Komunikaty o stanie na stronie żądanie zamówienia zakupu")

## <a name="schedule-the-purchase-order-request-batch-job"></a><a name="po-batch"></a>Planowanie zadania wsadowego żądania zamówienia zakupu

Aby uaktywnić zadanie wsadowe w celu wysłania żądań zamówień zakupu, przejdź do **Zaopatrzenie i sourcing \> Ustawienia \> Zarządzenie cXML \> Żądanie zamówienia zakupu**, a następnie w okienku akcji na karcie **Żądanie zamówienia zakupu** w grupie **Zadań wsadowych** wybierz opcję **Prześlij zadanie**, aby otworzyć okno **Dialogowe przygotowywanie i wysyłanie żądania zakupu**. W tym oknie dialogowym można skonfigurować cykl, tak jak zwykle w przypadku zadań wsadowych w Supply Chain Management. Wybierz interwał na podstawie wielkości zamówienia. Chociaż zadanie wsadowe można uruchomić co minutę, najlepszym rozwiązaniem jest prawdopodobnie wysłanie partii w ciągu dnia roboczego na podstawie okien przyjęć zamówień, które odpowiadają harmonogramom dostawców.

Na przykład Twój dostawca ma zasady, zgodnie z którymi wszystkie zamówienia otrzymane do godziny 13:00 zostaną wysłane tego samego dnia. W takim przypadku konieczne może być uruchomienie zadania wsadowego tylko kilka razy rano, aby powiadomić o wszystkich posiadanych zamówieniach. Pozostałe zamówienia zostaną wysłane do następnego dnia. Niniejsza decyzja jest czysto decyzją biznesową. Można go przejrzeć i odpowiednio określić parametry.

Proces będzie szukał dokumentów wniosku o zamówienie zakupu, które mają stan *Oczekujące*. Jeśli istnieje zamówienie, które należy wysłać do dostawcy natychmiast, można wybrać **Prześlij zadanie** i skonfigurować opcję **Przetwarzania wsadowego** na wartość *Nie*.

## <a name="monitor-purchase-order-requests"></a><a name="monitor-po-requests"></a>Monitorowanie żądań zamówienia zakupu

### <a name="view-the-status-of-a-purchase-order"></a>Umożliwia wyświetlenie stanu zamówienia sprzedaży

Jeśli zamówienia, które można wysłać za pośrednictwem cXML, zostaną potwierdzone w stanie _Oczekiwania_. Jak opisano w sekcji [Tworzenie i przetwarzanie zamówienia zakupu](#create-po), stan zamówienia zakupu można wyświetlić na stronie **Żądania zamówienia zakupu**. Każde żądanie zamówienia zakupu może mieć jeden z kilku stanów, w zależności od parametrów i danych. W tej sekcji opisano różne typy stanów i wartości, które mogą mieć. Te informacje mogą ułatwić zarządzanie problemami i zrozumienie stanu zamówień zakupu.

![Status zamówienia na stronie zamówienia](media/cxml-monitor-po-request.png "Status zamówienia na stronie zamówienia")

Siatka w górnej części strony **Żądanie zamówienia zakupu** może zawierać następujące wartości stanu:

- **Zewnętrzny stan zlecenia** - To pole może przyjmować jedną z nastepujących wartości:

    - **Oczekiwane** — dokument oczekuje na wysłanie.
    - **Wysłano** — dokument został wysłany.
    - **Zatrzymane** — dokument został oznaczony jako _Zatrzymany_ przed wysłaniem. (Aby oznaczyć dokument jako _Zatrzymany_, zaznacz opcję **Zatrzymaj** w okienku akcji na stronie **Żądanie zakupu**.)
    - **Archiwalne** — dokument został przeczyszczony. (Aby wyczyścić dokument jako **Oczyść**, zaznacz opcję Zatrzymaj w okienku akcji na stronie **Żądanie zakupu**.)

- **Stan dostawcy żądania zamówienia** - To pole może przyjmować jedną z nastepujących wartości:

    - **Oczekiwane** — dokument oczekuje na wysłanie.
    - **Potwierdzony** — dokument został potwierdzony przez dostawcę jako otrzymany. Szczegółowy komunikat XML zwrócony przez dostawcę można przejrzeć, wybierając kartę **Odpowiedź XML** w dolnej części strony.
    - **Błąd** — dokument został wysłany do dostawcy, ale wystąpił błąd. Komunikat o błędzie można przejrzeć, wybierając kartę **Odpowiedź XML** w dolnej części strony.

W siatce na karcie **Historia żądań zamówień zakupu** w dolnej części strony **Żądanie zamówienia zakupu** mogą być wyświetlane następujące wartości:

- **Typ żądania zamówienia** - To pole może przyjmować jedną z nastepujących wartości:

    - **Nowy** — wiersz jest oznaczany jako nowy bezpośrednio po potwierdzeniu zamówienia zakupu.
    - **Aktualizacja** — Jeśli potwierdzenie zostało już wysłane i potwierdzone przez dostawcę, następne potwierdzenie zostanie oznaczone jako _Zaktualizowane_. Aktualizacje będą wysyłane tylko wtedy, gdy dla opcji **Wyślij żądanie zakupu** jest ustawiona wartość *Tak* w [parametrach globalnych cXML](#cxml-parameters).
    - **Usuń** — Jeśli potwierdzenie zostało już wysłane i potwierdzone przez dostawcę, ale zamówienie zakupu zostanie anulowane, potwierdzenie oczekujące zostanie oznaczone jako _Usuń_. Usunięcia będą wysyłane tylko wtedy, gdy dla opcji **Usun żądanie zakupu** jest ustawiona wartość *Tak* w [parametrach globalnych cXML](#cxml-parameters).

- **Czas żądania** — czas utworzenia potwierdzenia zamówienia. Czas żądania wraz z czasem stanu zamówienia można porównać w celu określenia czasu między potwierdzeniem a potwierdzeniem dostawcy.
- **Stan wysyłania zamówień** — to pole jest takie samo, jak pole **Stan wysyłania zamówienia** w górnej części strony. W tym miejscu należy powtórzyć pracę, aby ułatwić Wyświetlanie stanu na poziomie potwierdzenia. Jeśli w polu **Typ żądania zamówienia** wybrano wartość *Nowy*, a zamówienie zakupu zostanie ponownie potwierdzone przed wysłaniem potwierdzenia, w polu **Stan wysyłania** zamówienia zostanie ustawiona wartość *Archiwizuj*.
- **Godzina stanu zamówienia** — godzina ostatniej aktualizacji rekordu historii żądania zamówienia zakupu. (Aktualizacje zawierają zmiany stanu.)
- **Stan dostawcy żądania zamówienia** — to pole jest takie samo, jak pole **Stan dostawcy żądania zamówienia** w górnej części strony. W tym miejscu należy powtórzyć pracę, aby ułatwić Wyświetlanie stanu na poziomie potwierdzenia.
- **Umożliwia ponowne przesłanie czasu** — godzina ponownego przesłania rekordu.
- **Licznik ponownego przesyłania** — liczba przypadków ponownego przesłania rekordu. Duża liczba wskazuje wiele błędów i dlatego może wskazywać na problemy z konfiguracją danych lub konfiguracją danych dostawcy.

### <a name="view-the-xml-for-a-purchase-order-request-message"></a>Wyświetlanie kodu XML wiadomości z żądaniem zamówienia zakupu

Aby wyświetlić kod XML wiadomości z żądaniem zamówienia zakupu, wybierz kartę **Rekst żądania XML** u dołu strony **Żądania zamówienia zakupu**. Informacje na tej karcie mogą być pomocne podczas sprawdzania poprawności testów lub błędów. Aby ułatwić odczytywanie informacji, można wyświetlić ją jako wiadomość sformatowaną. Skopiuj zawartość karty do pliku tekstowego, a następnie wyświetl ją w edytorze XML.

![Karta tekst XML żądania](media/cxml-request-xml-text.png "Karta tekst XML żądania")

### <a name="view-the-details-of-the-vendor-response"></a>Służy do wyświetlania szczegółów odpowiedzi dostawcy

Aby wyświetlić zawartość potwierdzenia dostawcy lub odpowiedzi na błędy, wybierz kartę **Odpowiedź XML** na dole strony **Żądanie zamówienia zakupu**.

![Karta XML odpowiedzi](media/cxml-response-xml.png "Karta XML odpowiedzi")

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Konfigurowanie katalogu zewnętrznego dla rozwiązania PunchOut e-procurement](set-up-external-catalog-for-punchout.md)
- [Używanie katalogów zewnętrznych dla rozwiązania PunchOut e-procurement](use-external-catalogs-for-punchout.md)
