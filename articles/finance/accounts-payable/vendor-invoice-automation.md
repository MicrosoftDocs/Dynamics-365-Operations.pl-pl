---
title: Automatyzacja obsługi faktur dla zeskanowanych dokumentów
description: W tym temacie opisano dostępne funkcje kompleksowej automatyzacji obsługi faktur od dostawców, w tym nawet faktur zawierających załączniki.
author: abruer
ms.date: 03/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02fcb6ce49156c32f23bfb37478a1076f62aa868
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716417"
---
# <a name="invoice-automation-for-scanned-documents"></a>Automatyzacja faktur dla zeskanowanych dokumentów

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono jednostki danych, które są dostępne do kompleksowej automatyzacji faktur od dostawców, w tym faktur z załącznikami.

Organizacje, które chcą usprawnić swoje procesy rozrachunków z dostawcami (AP), często wskazują na przetwarzanie faktur jako na jeden z głównych obszarów przetwarzania, który powinien być bardziej efektywny. W wielu przypadkach takie organizacje przekazują przetwarzanie papierowych faktur zewnętrznym dostawcom usług optycznego rozpoznawania znaków (OCR). Następnie otrzymują metadane faktur nadające się do odczytu maszynowego razem z zeskanowanego obrazem każdej faktury. Aby pomóc w automatyzacji, jest następnie budowane rozwiązanie „ostatniej mili”, które umożliwia wykorzystywanie tych artefaktów w systemie fakturowania. Teraz umożliwia tę automatyzację „ostatniej mili” włączoną w standardzie, za pomocą rozwiązania do automatyzacji obsługi faktur.

## <a name="solution-context"></a>Kontekst rozwiązania

Rozwiązanie automatyzacji obsługi faktur oferuje standardowy interfejs, który może akceptować metadane nagłówków i wierszy faktur, a także załączniki odnośnych faktur. Każdy system zewnętrzny, który może generować artefakty zgodne z tym interfejsem, będzie mógł wysyłać te dane na potrzeby automatycznego przetwarzania faktur i załączników.

Na poniższej ilustracji przedstawiono przykładowy scenariusz integracji, w którym firma Contoso współpracuje z usługodawcą OCR w celu przetwarzania faktur od dostawców. Dostawcy firmy Contoso przesyłają faktury dostawców do usługodawcy za pomocą poczty e-mail. Za pomocą przetwarzania OCR usługodawca generuje metadane faktur (nagłówek i/lub wiersze) oraz zeskanowany obraz faktury. Następnie warstwa integracji przekształca te artefakty, aby mogły być wykorzystywane.

![Przykładowy scenariusz integracji.](media/vendor_invoice_automation_01.png)

Jest możliwych kilka odmian powyższego scenariusza, jeśli jest wymagana integracja faktur. Migracja danych jest kolejnym przypadkiem użycia, w którym ten interfejs może być wykorzystywany do tworzenia faktur i załączników.

### <a name="solution-components"></a>Składniki rozwiązania

Rozwiązanie zawiera następujące składniki:

+ Jednostki danych dla nagłówka, wierszy i załączników faktury
+ Wyjątek przetwarzanie dla faktur
+ Przeglądarkę umożliwiającą wyświetlanie załączników faktur obok siebie

Pozostała część tego tematu zawiera szczegółowe opisy tych składników rozwiązania.

## <a name="data-entities"></a>Jednostki danych

Pakiet danych jest jednostką pracy, która musi zostać wysłana, aby można było tworzyć nagłówki, wiersze i załączniki faktur. Następujące jednostki danych są używane do artefaktów składających się na pakiet danych:

+ Nagłówek faktury od dostawcy
+ Wiersz faktury od dostawcy
+ Załącznik dokumentu faktury od dostawcy

Załącznik dokumentu faktury od dostawcy jest nową jednostką danych wprowadzoną w ramach tej funkcji. Jednostka Nagłówek faktury od dostawcy została zmodyfikowana, tak aby obsługiwała załączniki. Jednostka Wiersz faktury od dostawcy nie zmodyfikowana dla tej funkcji.

Aby uzyskać szczegółowe informacje o pakietach danych, zapoznaj się z [omówieniem zarządzania danymi](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md). Informacje na temat tworzenia pakietów danych przy użyciu przestrzeni roboczej zarządzania danymi można znaleźć w punkcie [Przetwarzanie i wykorzystywanie pakietów danych w rozwiązaniach Dynamics 365 aplikacji finansowych i operacyjnych](../../fin-ops-core/dev-itpro/lcs-solutions/process-data-packages-lcs-solutions.md).

Aby szybko wygenerować dane testowe zawierające faktury i załączniki, wykonaj następujące czynności.

1. Zaloguj się do swojego wystąpienia.
1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Faktury** > **Oczekujące faktury od dostawcy**.
1. Utwórz faktury zawierające wiersze i załączniki.

    > [!NOTE]
    > Załączniki muszą być załącznikami nagłówka. Obecnie jednostka Załącznik dokumentu faktury od dostawcy nie obsługuje załączników wierszy.

1. Otwórz obszar roboczy **Zarządzanie danymi**.
1. Utwórz zadanie eksportu zawierające jednostki Nagłówek faktury od dostawcy, Wiersz faktury od dostawcy i Załącznik dokumentu faktury od dostawcy.
1. Wyeksportuj dane.
1. Pobierz wyeksportowane dane jako pakiet. Teraz możesz użyć pakietu w celu zaimportowania danych do wystąpień docelowych dla celów testowych.

### <a name="determining-the-legal-entity-for-an-invoice"></a>Określanie firmy dla faktury

Faktury importowane za pośrednictwem pakietów danych mogą być skojarzone z firmą, do której należą, na dwa sposoby:

+ Zadanie importu przetwarzające fakturę importuje ją do tej samej firmy, w której zadanie zostało zaplanowane w obszarze roboczym **Zarządzania danymi**. Innymi słowy firma w zadaniu decyduje o firmie, do której należy faktura.
+ Po wysłaniu pakietu danych zawierającego faktury do programu Finance obiekt wywołujący (czyli aplikacja integrująca uruchomiona poza programem Finance) może jednoznacznie podać identyfikator firmy w żądaniu HTTP. W takim przypadku kontekst firmy, w którym zadanie przetwarzania zostało uruchomione w programie Finance, jest zastępowany, a faktury są importowane do firmy podanej za pośrednictwem żądania HTTP.

> [!NOTE]
> To zachowanie jest standardowym zachowaniem zarządzania danymi. Wyjaśniono je tutaj, w kontekście faktur, tylko dla kompletności.

## <a name="exception-processing"></a>Przetwarzanie wyjątków

W scenariuszach, gdzie faktury od dostawców wchodzą do programu Finance and Operations wskutek integracji, musi istnieć prosty sposób, w jaki członek zespołu rozrachunków z dostawcami może przetwarzać wyjątki lub niepomyślnie rozliczone faktury oraz tworzyć faktury oczekujące z niepomyślnie rozliczonych faktur. Taka funkcjonalność przetwarzania wyjątków faktur od dostawców jest obecnie częścią programu Finance and Operations.

### <a name="vendor-invoices-that-failed-to-import-list-page"></a>Faktura od dostawcy, dla których nie można zaimportować strony listy

Nowa strona listy dla wyjątków faktur jest dostępna w oknie **Rozrachunki z dostawcami** > **Faktury** > **Niepowodzenia importu** > **Faktury od dostawców, których importowanie nie powiodło się**. Na tej stronie są pokazane wszystkie rekordy nagłówków faktur od dostawców z tabeli tymczasowej jednostki danych Nagłówek faktury od dostawcy. Należy zwrócić uwagę, że te same rekordy można wyświetlić z obszaru roboczego **Zarządzanie danymi**. Możesz również wykonać te same czynności, które są dostępne w funkcji obsługi wyjątków z obszaru roboczego **Zarządzanie danymi**. Funkcja obsługi wyjątków została zoptymalizowana dla funkcjonalnego użytkownika, co ułatwia korzystanie z nich.

![Strona listy wyjątków.](media/vendor_invoice_automation_02.png)

Na tej stronie listy znajdują się następujące pola dostępne wskutek integracji:

+ **Firma** — firma, do której należy faktura
+ **Komunikat o błędzie** — komunikat o błędzie generowany przez środowisko zarządzania danymi w celu wyjaśnienia, dlaczego nie można utworzyć faktury
+ **Numer** — numer faktury
+ **Konto faktury**
+ **Nazwa** — nazwa dostawcy
+ **Konto dostawcy**
+ **Zamówienie zakupu** — numer zamówienia zakupu (ZZ) dla faktury
+ **Data księgowania**
+ **Data faktury**
+ **Opis faktury**
+ **Waluta**
+ **Dziennik**
+ **Odwołanie wiersza** — identyfikator pochodzący z systemu zewnętrznego

    > [!NOTE]
    > Odwołanie wiersza nie jest identyfikatorem faktury.

Ta strona listy ma również okienko podglądu, którego można używać w następujące sposoby:

+ Wyświetlenie całego komunikatu o błędzie, tak aby nie trzeba było rozwijać kolumny **Komunikat o błędzie** w siatce.

Na stronie listy można wykonywać następujące akcje:

+ **Edytuj** — Służy do otwierania rekordu wyjątku w trybie edycji umożliwiającym rozwiązywanie problemów.
+ **Opcje** — Przechodzenie do standardowych opcji dostępnych na stronach list. Można użyć opcji **Dodaj do obszaru roboczego**, aby przypiąć stronę listy wyjątków do swojego obszaru roboczego jako listę lub kafelek.

### <a name="vendor-invoices-that-failed-to-import-details-page"></a>Faktura od dostawcy, dla których nie można zaimportować stronę szczegółów

Po rozpoczęciu trybu edycji zostanie otwarta strona **Szczegółów faktur od dostawców**, dla których nie powiodło się zaimportowanie faktury z problemami. Jeśli występują problemy z fakturą z załącznikiem, załącznik nie zostanie wyświetlony. Załącznik musi być ponownie dołączony do faktury.

Strona **Szczegółów faktur od dostawców**, których nie udało się zaimportować, umożliwia utworzenie faktury oczekującej. Po rozwiązaniu problemów z fakturą w ramach przetwarzania wyjątków można kliknąć przycisk **Utwórz fakturę oczekującą**, aby utworzyć fakturę oczekującą. Faktura oczekująca zostanie utworzona w tle. 

### <a name="shared-service-vs-organization-based-exception-processing"></a>Usługa udostępniona a przetwarzanie wyjątków wewnątrz organizacji

Na stronie listy wyjątków są obsługiwane standardowe konstrukcje zabezpieczeń, które obszar roboczy **Zarządzanie danymi** obsługuje dla przetwarzania rekordów pośrednich. Zadanie importu faktur można zabezpieczyć w następujące sposoby:

+ Według roli użytkownika
+ Według użytkownika
+ Według firmy

![Zadanie importu zabezpieczone według roli użytkownika i firmy.](media/vendor_invoice_automation_04.png)

Jeśli skonfigurowano zabezpieczenia dla zadania importu faktur, strona listy wyjątków honoruje te ustawienia. Użytkownicy będą widzieć tylko te rekordy wyjątków faktur, które pozwala im zobaczyć ta konfiguracja.

Na przykład firma Contoso podjęła decyzję o przetwarzaniu wyjątków faktur według firmy. W związku z tym skonfigurowano zabezpieczenia dla zadania importu faktur w taki sposób, że użytkownik w firmie A widzi tylko wyjątki faktur z firmy A, podczas gdy użytkownik w firmie B może zobaczyć tylko wyjątki faktur z firmy B. Taka konfiguracja umożliwia podział obowiązków w zakresie zarządzania wyjątkami faktur.

Firma Contoso mogłaby również podjąć decyzję, aby nie wymuszać żadnych zabezpieczeń, dzięki czemu ci sami użytkownicy mogliby przetwarzać wyjątki faktur dla wszystkich firm. Taka konfiguracja wspiera scenariusz usług udostępnionych w zarządzaniu wyjątkami faktur.

## <a name="side-by-side-attachment-viewer"></a>Przeglądarka umożliwiająca wyświetlanie załączników obok siebie

Aby ułatwić przeglądanie załączników faktur od dostawców, następujące strony używane w procesie fakturowania teraz zawierają funkcjonalność przeglądarki załączników:

+ **Obsługa wyjątków**
+ Strona **Oczekujące faktury od dostawcy** (dostępna również w procesie przeglądu faktur)
+ Strona zapytań **Arkusz faktur** (dla zaksięgowanych faktur)

Poniżej przedstawiono główne funkcje zawarte w przeglądarce załączników:

+ Wyświetlanie wszystkich typów załączników obsługiwanych przez obszar roboczy Zarządzanie dokumentami (plików, obrazów, adresów URL i notatek).
+ Wyświetlanie wielostronicowych plików TIFF.
+ Wykonywanie następujących czynności na plikach obrazów:
  + Wyróżnianie części obrazu.
  + Blokowanie części obrazu.
  + Dodawanie adnotacji do obrazu.
  + Przybliżanie i oddalanie widoku obrazu.
  + Przesuwanie (panoramowanie) obrazu.
  + Cofanie i ponawianie operacji.
  + Dopasowywanie obrazu do rozmiaru.

> [!NOTE]
> Te akcje są dostępne tylko w przypadku plików obrazów (JPEG, TIFF, PNG itd.). Wszelkie zmiany wprowadzone w obrazie za pomocą tych czynności są zapisywane w pliku obrazu. Obecnie przeglądarka załączników nie zawiera funkcji tworzenia wersji ani audytowania.

### <a name="default-attachment"></a>Załącznik domyślny

Jeśli faktura od dostawcy ma więcej niż jeden załącznik, na stronie **Załączniki** można ustawić jeden z tych dokumentów jako załącznik domyślny. Opcja **Jest załącznikiem domyślnym** to nowa opcja dodana jako część tej funkcji. Ta opcja jest także widoczna w jednostce danych Załącznik dokumentu faktury od dostawcy. Dzięki temu poprzez integrację można ustawić załącznik domyślny.

Tylko jeden dokument można ustawić jako załącznik domyślny. Po ustawieniu dokumentu jako załącznika domyślnego jest on automatycznie wyświetlany w przeglądarce załączników po otwarciu faktury. Jeśli nie ustawiono żadnego dokumentu jako załącznika domyślnego, przeglądarka nie będzie automatycznie pokazywać żadnego załącznika po otwarciu faktury.

### <a name="showhide-invoice-attachments"></a>Pokazywanie/ukrywanie załączników faktur

Nowy przycisk dostępny na stronach zapytań **Przetwarzanie wyjątków**, **Faktura oczekująca** i **Arkusz faktur** umożliwia pokazywanie lub ukrywanie przeglądarki załączników.

## <a name="security"></a>Zabezpieczenia

Następujące akcje w przeglądarce załączników są kontrolowane przez zabezpieczenia oparte na rolach:

+ Wyróżnianie
+ Zablokuj
+ Adnotowanie

### <a name="pending-vendor-invoices-page"></a>Strona Oczekujące faktury od dostawcy

Następujące uprawnienia zapewniają dostęp tylko do odczytu lub odczytu i zapisu w przeglądarce załączników dla akcji wyróżniania, blokowania i adnotowania:

+ **Obsługa obrazów faktur od dostawców** — To uprawnienie zapewnia dostęp do odczytu/zapisu.
+ **Wyświetlanie obrazów faktur od dostawców** — To uprawnienie zapewnia dostęp tylko do odczytu.

Następujące obowiązki zapewniają dostęp tylko do odczytu lub odczytu i zapisu w przeglądarce załączników dla tych czynności:

+ **Obsługa faktur od dostawcy** — Do tego obowiązku jest przypisane uprawnienie Obsługa obrazów faktur od dostawców.
+ **Zapytanie o stan faktury od dostawcy** — Do tego obowiązku jest przypisane uprawnienie Wyświetlanie obrazów faktur od dostawców.

Następujące role zapewniają dostęp tylko do odczytu lub odczytu i zapisu w przeglądarce załączników dla tych czynności:

+ **Pracownik ds. rozrachunków z dostawcami** i **Menedżer ds. rozrachunków z dostawcami** — Do tych ról jest przypisany obowiązek Obsługa faktur od dostawcy.
+ **Pracownik ds. rozrachunków z dostawcami**, **Menedżer ds. rozrachunków z dostawcami**, **Pracownik ds. płatności scentralizowanych w rozrachunkach z dostawcami** i **Pracownik ds. płatności rozrachunków z dostawcami** — Do tych ról jest przypisany obowiązek Zapytanie o stan faktury od dostawcy.

### <a name="vendor-invoice-attachment"></a>Załącznik faktur od dostawców

Następujące uprawnienia zapewniają dostęp tylko do odczytu lub odczytu i zapisu w przeglądarce załączników dla akcji wyróżniania, blokowania i adnotowania.

> [!NOTE]
> Standardowo role wymienione w tej sekcji zapewniają dostęp tylko do odczytu wobec obrazów faktur w przeglądarce załączników. Jeśli rola musi mieć również uprawnienie zapisu wobec obrazów, można jej przyznać do uprawnienie, używając opisanych tutaj uprawnienia i obowiązku.

+ **Obsługa obrazu jednostki Nagłówek faktury od dostawcy** — To uprawnienie zapewnia dostęp do odczytu/zapisu wobec obrazów faktur w przeglądarce załączników.
+ **Wyświetlanie obrazu jednostki Nagłówek faktury od dostawcy** — To uprawnienie zapewnia dostęp tylko do odczytu wobec obrazu faktury w przeglądarce załączników.

Następujące obowiązki zapewniają dostęp tylko do odczytu w przeglądarce załączników dla tych czynności:

+ **Obsługa faktur od dostawcy** — Do tego obowiązku jest przypisane uprawnienie Obsługa obrazu jednostki Nagłówek faktury od dostawcy.

Następujące role zapewniają dostęp tylko do odczytu w przeglądarce załączników dla tych czynności:

+ **Pracownik ds. rozrachunków z dostawcami** i **Menedżer ds. rozrachunków z dostawcami** — Do tych ról jest przypisany obowiązek Obsługa faktur od dostawcy.

Domyślnie jeśli rola użytkownika zawiera prawa do edycji na każdej stronie, użytkownik będzie miał również prawa do edycji w przeglądarce załączników dla akcji wyróżniania, blokowania i adnotowania. Jednak jeśli istnieją scenariusze, w których określona rola powinna mieć prawa do edycji na stronie, ale nie w przeglądarce załączników, można użyć odpowiednich uprawnień z poprzedniej listy, aby zaspokoić wymogi tych przypadków użycia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
