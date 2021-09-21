---
title: Omówienie samoobsługi dla pracownika etatowego i menedżera
description: Ten artykuł umożliwia przegląd informacji o obszarze roboczym samoobsługi pracowników i menedżerów.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cea92092701f960f12aa74efe4c82c379a2b2c6d
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431218"
---
# <a name="employee-and-manager-self-service-overview"></a>Omówienie samoobsługi dla pracownika etatowego i menedżera

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ten artykuł umożliwia przegląd informacji o obszarze roboczym samoobsługi pracowników i menedżerów.

## <a name="edit-personal-details"></a>Edytuj dane osobowe

Aby dodać lub zmienić dowolne informacje osobiste, należy zapoznać się z [Edytuj informacje osobiste](hr-employee-manager-self-service-edit-personal-information.md).

## <a name="user-not-assigned-to-a-worker-record"></a>Użytkownik nie został przypisany rekord pracownika

Jeśli użytkownik nie ma przypisanego rekordu **Pracownika** na stronie **Użytkownicy**, zostanie wyświetlony następujący komunikat:

**Twój identyfikator użytkownika nie jest skojarzony z rekordem pracownika etatowego w systemie. Dopóki tak będzie, nie będziesz mieć możliwości wyświetlania ani aktualizowania swoich informacji. Skontaktuj się ze swoim menedżerem albo zespołem pomocy technicznej, aby uzyskać pomoc.**

Aby przypisać użytkownikowi rekord **Pracownika**, przejdź do sekcji **Użytkownicy** i wybierz użytkownika. Wybierz opcję **Edycja**, dodaj odpowiedniego pracownika w polu **Osoba** na stronie, a następnie wybierz opcję **Zapisz**. Powinien być teraz możliwy dostęp do **samoobsługi pracownika etatowego**.

## <a name="security-requirements-for-employee-and-manager-self-service"></a>Wymagania dotyczące zabezpieczeń dla pracownika i kierownika samoobsługi

Wymagania dotyczące zabezpieczeń dla pracownika i kierownika samoobsługi:

- Pracownicy wymagają posiadania roli „pracownik”.
- Kierownicy wymagają zarówno roli pracownika, jak i kierownika.

>[!NOTE]
>Role niestandardowe mogą być również używane do uzyskania dostępu do samoobsługi pracowników i kierownika, tak długo jak udzielono im dostępu do obszarów roboczych dla pracowników i kierowników.<br>
>Dostęp kierownika do informacji o pracownikach jest oparty na bieżącej hierarchii wierszy stanowisk zdefiniowanej w module Human Resources.

## <a name="employee-self-service"></a>Samoobsługa pracownika etatowego

Na karcie **Moje informacje** są wyświetlane następujące informacje dotyczące modułu **Samoobsługa pracownika etatowego**.  

### <a name="summary"></a>Sumaryczny

**Elementy pracy przypisane do mnie** służą do wyświetlania wszystkich zatwierdzeń i elementów przepływu pracy przypisanych do pracownika. Możesz skonfigurować elementy przepływu pracy, aby wysyłały wiadomości e-mail do użytkownika.

**Kwestionariusze przypisane do mnie** umożliwiają wyświetlenie wszystkich zaplanowanych kwestionariuszy przypisanych bezpośrednio do pracownika lub grupy.

**Katalog firm** umożliwia wyszukiwanie informacji związanych z osobami w organizacji. Publiczne informacje kontaktowe są dostępne dla wszystkich pracowników etatowych. Katalog firmy jest ograniczony do firmy, do której zarejestrował się pracownik etatowy.

**Kalendarz zespołu** pokazuje informacje kalendarza zespołu. Aby uzyskać więcej informacji, zobacz temat [Wyświetlanie kalendarzy zespołów i firm](hr-employee-self-service-calendar.md).

### <a name="my-career-information"></a>Moje informacje o przebiegu kariery

Sekcja **Moje informacje o przebiegu kariery** modułu **Samoobsługa pracownika etatowego** zawiera kafelki związane z urlopem i nieobecnością, zarządzaniem wydajnością, kwalifikacjami, korzyściami, zadaniami i załącznikami.

Na kafelku **Bilans czasu wolnego** są wyświetlane bilanse dla zarejestrowanych planów. Ten kafelek służy do prognozowania bilansu na podstawie metody naliczania. Można wprowadzać i przesyłać żądania dotyczące czasu, które będą następnie przechodzą przez proces przepływu pracy zatwierdzania. Aby uzyskać więcej informacji dotyczących Urlopów i nieobecności, zobacz [Zarządzanie urlopami i nieobecnościami](hr-leave-and-absence-overview.md).

Na kafelku **Zadania** są wyświetlane zadania przypisane do użytkownika i pozwalające na przeglądanie tych zadań i zarządzanie nimi.

Obszar **Następny zarejestrowany kurs** zawiera następny kurs, na który Cię zarejestrowano. Możesz przeglądać i rejestrować się na dowolne otwarte kursy. Wszystkie kursy otwarte do zarejestrowania mają stan **rozpoczęty** i umożliwiają pracownikom samoobsługową rejestrację. W zależności od ustawień organizacji rejestracja na kurs może przejść przez procedurę zatwierdzania.

Na kafelku **Certyfikaty** jest wyświetlany certyfikat i data ważności certyfikatu kończącego się najbliżej daty bieżącej. Certyfikaty można aktualizować, dodawać i usuwać. W zależności od ustawień organizacji aktualizacje certyfikatów mogą przejść proces zatwierdzania.

Obszar **Następny zaplanowany przegląd** zawiera następną ocenę wydajności. Możesz rozpocząć nowy przegląd z tego kafelka. Kierownik lub przedstawiciel działu kadry mogą również inicjować przeglądy. W zależności od ustawień organizacji można również wyświetlać, aktualizować i przesyłać przeglądy.

Celami tymi można zarządzać w obszarze **Cele wydajności**. Na tym kafelku jest wyświetlana liczba celów w każdym stanie (**Nierozpoczęte**, **śledzone** i **wymagające ulepszenia**). W zależności od przypisanego zabezpieczenia opartego na rolach można tworzyć, aktualizować i usuwać cele. W razie potrzeby można dodawać nowe cele z grup lub szablonów. Menedżerowie i pracownicy działu kadr mogą również tworzyć cele w imieniu pracowników i określać, jak szczegółowe będą poszczególne cele. Kierownicy i pracownicy mogą współpracować na cele i aktualizować działania, miary i stany. Można również uwzględnić załączniki.

Użytkownik może wyświetlić swoje istniejące umiejętności na kafelku **Całkowita liczba kwalifikacji**. Można zaktualizować kwalifikacje, dodać nowe lub usunąć te, które nie są już potrzebne. W zależności od ustawień organizacji zmiany umiejętności mogą przechodzić proces zatwierdzania.

Bieżące wynagrodzenie można wyświetlić w obszarze **Wynagrodzenie**. Wybierz opcję **Pokaż**, aby wyświetlić kwotę rocznej wypłaty i ostatniej podwyżki. Jeśli użytkownik jest zatrudniony w więcej niż jednej firmie, jest wyświetlana każda roczna kwota. Aby wyświetlić historię szczegółowej wynagrodzenia, wybierz kwotę **Wynagrodzenie roczne**, aby otworzyć stronę **Historia wynagrodzeń o stałej i zmiennej wysokości**. Przyszłe wynagrodzenie nie jest wyświetlane na tej stronie. Jeśli istnieje więcej niż jedno zatrudnienie, można przełączać się między firmami w ramach tej strony, aby wyświetlić historię wynagrodzenia bez rejestrowania się w każdej firmie.

Wyświetl dokumenty i zarządzaj nimi przy użyciu kafelka **Załączniki**. Można zarządzać wszystkimi załącznikami **Zewnętrznymi**. Dział kadr i pracownicy etatowi mogą dodawać załączniki za pomocą strony **Samoobsługa pracownika etatowego** lub **Pracownik**. Załączniki są domyślnie ustawione jako **zewnętrzne**.

### <a name="additional-information"></a>Informacje dodatkowe

W tej sekcji znajdują się linki do innych obszarów **samoobsługi pracownika etatowego**, podobnie jak w sekcji **Moje informacje o przebiegu kariery**.

Utwórz konto do świadczeń za pomocą łącza **Świadczenia**. Aby uzyskać więcej informacji o zarządzaniu świadczeniami, zobacz [Omówienie świadczeń](hr-benefits-management-overview.md).

W obszarze **Wydajność** można wybrać **Arkusz wydajności** w celu utworzenia wpisów arkusza wydajności, które będą używane zarówno w celach, jak i przeglądach wydajności. Możesz wybrać opcję **Wyślij opinię**, aby przekazać opinie innym pracownikom w organizacji. W zależności od ustawień organizacji wiadomości e-mail mogą być wysyłane do adresata, nadawcy i menedżerów. Opinie można przesyłać do wszystkich pracowników w organizacji. Przesyłanie opinii nie jest ograniczone przez firmę.

W obszarze **Kwalifikacje** można wprowadzać zmiany w **Kursach**, **Wykształceniu**, **Stanowiskach zaufania** i **Doświadczeniu zawodowym**. W zależności od ustawień organizacji aktualizacje tych kompetencji mogą przejść proces zatwierdzania.

Istnieje możliwość wyświetlania szczegółów zadania w **Organizacji**. Szczegóły stanowiska obejmują kwalifikacje, certyfikaty i zakres odpowiedzialności dla stanowiska głównego. Można również przejrzeć wszystkie wypożyczone sprzęty, które zostały wyewidencjonowane dla danego użytkownika. W zależności od ustawień organizacji zmiany w wypożyczonym sprzęcie mogą przechodzić proces zatwierdzania.

W obszarze **Kwestionariusz** można wyświetlać wypełnione kwestionariusze. Można także wyświetlać kwestionariusze dotyczące całej firmy, które nie zostały wypełnione. Kwestionariusz można wypełniać w dowolnym momencie. Autor kwestionariusza może określić ramy czasowe i dla których kwestionariusza ma być zastosowana.

Istnieje możliwość skonfigurowania łączy zdefiniowanych przez użytkownika w **parametrach zasobów ludzkich**. Można na przykład zdefiniować łącza do sprawozdań o wynagrodzeniach, dokumentacji na koniec roku lub rozwiązań zewnętrznych. Łącza te są wyświetlane u dołu tej sekcji, ale można je przenosić za pomocą narzędzia personalizacji.

Można także utworzyć dodatkowe karty, osadzając usługę Power Apps w obszarze roboczym **samoobsługi pracownika etatowego**. Menu **Ustawienia** umożliwia spersonalizowanie strony za pomocą dowolnego z Power Apps. W menu **Ustawienia** możesz wybrać opcję dodania Power App, uzupełnić szczegóły i wstawić aplikację. Domyślnie Power Apps pojawia się jako pierwsza karta w sekwencji. Kolejność można zmieniać przy użyciu personalizacji standardowej.

## <a name="my-team"></a>Mój zespół

Na karcie **Mój zespół** są wyświetlane następujące informacje dotyczące modułu **Samoobsługa menedżera**. Dostęp do karty **Mój zespół** mogą uzyskać tylko menedżerowie.

### <a name="personnel-actions"></a>Akcje dotyczące pracowników

Akcje dotyczące pracowników są wyświetlane na podstawie konfiguracjiopcji w **udostępnionych parametrów rozwiązania Human Resources** i **parametrów rozwiązania Human Resources**. W przypadku włączenia akcji dotyczących **Pracowników** akcje dotyczące pracowników umożliwiają włączanie nowych opcji menu, w tym:

- **Zażądaj nowego pracownika etatowego**
- **Zażądaj nowego zleceniobiorcy**
- **Zażądaj ponownego przypisania pracownika**
- **Zażądaj zwolnienia**
- **Zażądaj zmiany wynagrodzenia**

Te opcje można skonfigurować w celu przechodzenia przez opcjonalny przepływ pracy przeglądu i zatwierdzania.

Włączenie **Akcji dotyczących stanowisk** umożliwia włączenie następujących opcji:

- **Zażądaj nowego stanowiska**
- **Zażądaj zmiany szczegółów stanowiska**

Te opcje można również skonfigurować w celu przechodzenia przez opcjonalny przepływ pracy przeglądu i zatwierdzania.

### <a name="summary"></a>Sumaryczny

Informacje w sekcji **Podsumowanie** zależą od opcji dostępnych w obszarze **parametrów zasobów ludzkich**. Na karcie **Menedżer samoobsługi** na stronie **Parametry zasobów ludzkich** można skonfigurować opcje wyświetlania wygasających rekordów i otwartych stanowisk. Włączenie tych opcji decyduje o tym, co menedżerowie mogą widzieć w sekcji **Podsumowania**.

Dla menedżerów można skonfigurować następujące kafelki:

- **Wygasające certyfikaty dla mojego zespołu**
- **Numery identyfikacyjne wygasające dla mojego zespołu**
- **Okresy próbne wygasające dla mojego zespołu**
- **Kontrole wygasające dla mojego zespołu**
- **Testy wygasające dla mojego zespołu**
- **Otwarte stanowiska dla podwładnych bezpośrednich i/lub rozszerzonych**
- **Czas oczekiwania na nierealizację żądania dla mojego zespołu**
- **Ocena kwalifikacji zespołu**
- **Analiza kwalifikacji, które trzeba zdobyć**
- **Arkusze wydajności zespołu**
- **Cele dotyczące wydajności zespołu**
- **Przeglądy wydajności zespołu**
- **Odchodzący pracownicy**

Można skonfigurować następujące opcje dla menedżerów w celu wprowadzenia zmian lub dodania żądań urlopu w imieniu ich bezpośrednich podwładnych:

- Certyfikaty
- Kursy
- Przedmioty pożyczek
- Umiejętności
- Wnioski o urlopy i nieobecności

### <a name="my-team-information"></a>Informacje dotyczące mojego zespołu

Informacje o **moim zespole** umożliwiają menedżerom wyświetlanie i aktualizowanie bezpośrednich i rozszerzonych podwładnych. Aby uzyskać dostęp do podwładnych rozszerzonych, wybierz pracownika, który ma podwładnych, a następnie wybierz opcję **Wyświetl zespół** na kafelku. Wszystkie te same opcje są stosowane do podwładnych rozszerzonych jako bezpośrednich. 

#### <a name="summary-tab"></a>Karta Podsumowanie

Karta **Podsumowanie** zawiera szybki przegląd bezpośrednich podwładnych. Jeśli podwładny bezpośredni na również podwładnych, na karcie wyświetlana jest liczba bezpośrednich podwładnych w górnej sekcji wraz z przyciskiem **Wyświetl zespół**. Opcje powyżej każdego kafelka mają zastosowanie do wybranego pracownika. Na przykład, jeśli chcesz wprowadzić żądanie opuszczenia w imieniu pracownika, wybierz pracownika, a następnie wybierz **Żądanie czasu wolnego**. 

Jeśli po wybraniu pracownika zostanie wybrany przycisk **Szczegóły**, zostaną wyświetlone następujące opcje:

- **Certyfikaty**
- **Kompensata**
- **Kursy**
- **Przeglądy**
- **Czas wolny**
- **Wypożyczone elementy**
- **Cele dotyczące wydajności**
- **Zarejestrowane kursy**
- **Umiejętności**
- **Wyślij opinię**

W zależności od ustawień organizacji można modyfikować lub tylko wyświetlać zmiany.

#### <a name="position-tab"></a>Karta stanowiska

Karta **Stanowisko** zawiera widok podsumowania pracowników na swoim stanowisku głównym. Nazwy, tytuł i dział są wyświetlane w obszarze nagłówka każdego kafelka. Ten kafelek zawiera następujące obszary:

- **Data stażu pracy** — wyświetlana w sekcji podsumowania pracownika na stronie **Pracownik**.
- **Lata stażu pracy** — obliczone na podstawie daty rozpoczęcia zatrudnienia pracownika.
- **Liczba poprzednich stanowisk** — na podstawie historii stanowisk, wybranie tego numeru powoduje otwarcie widoku szczegółowego wszystkich uprzednio zablokowanych stanowisk.
- **Data urodzenia** — miesiąc i dzień daty urodzenia pracownika.

Można wyświetlać dane dotyczące stanowisk zarówno dla podwładnych bezpośrednich, jak i rozszerzonych.

#### <a name="compensation-tab"></a>Karta Wynagrodzenie

Na karcie **Wynagrodzenie** jest wyświetlane wynagrodzenie roczne danego pracownika. Identyfikator firmy jest wyświetlany pod kwotą wynagrodzenia. Jeśli pracownik ma więcej niż jedno zatrudnienie i jest opłacany z wielu podmiotów prawnych, pracownik będzie miał wiele planów wynagrodzeń. Aby wyświetlić wszystkie plany wynagrodzeń w różnych firmach bez przełączania firm, należy włączyć kompensację krzyżową w obszarze **Zasoby ludzkie > Parametry współużytkowane > Dostęp zaawansowany > łącz widok wynagrodzeń między firmami**.

Aby wyświetlić historię wynagrodzeń, wybierz opcję **Kwota wynagrodzenia**, aby otworzyć formularz **Szczegóły**. Na stronie **Wynagrodzenia** są wyświetlane tylko bieżące i historyczne rekordy wynagrodzeń o stałej i zmiennej wysokości. Jeśli pracownik ma więcej niż jedno zatrudnienie, można przełączać się między firmami w celu wyświetlenia historii wynagrodzeń w każdej firmie lub włączyć wynagrodzenie w różnych firmach w obszarze **Parametry współużytkowane zasobów ludzkich**, aby wyświetlić wszystkie plany wynagrodzeń.

Można wyświetlać wynagrodzenia zarówno dla podwładnych bezpośrednich, jak i rozszerzonych.

#### <a name="leave-and-absence-tab"></a>Karta Urlopy i nieobecności

Na karcie **Urlopy i nieobecności** wyświetlane są bilanse najlepszych pracowników, którzy są aktywni. Aby wykonać akcję lub wyświetlić pełną listę działań, wybierz **Szczegóły**, a następnie wybierz opcję **Czas wolny**. Na stronie **Czas wolny** można przeglądać salda, wnioski, zatwierdzony czas wolny, a także prognozować salda, aby ułatwić pracownikom lepsze zarządzanie czasem. W zależności od ustawień organizacji można również żądać czasu wolnego dla bezpośrednich i rozszerzonych podwładnych.

#### <a name="performance-goals-tab"></a>Karta Celów dotyczących wydajności

Na karcie **Cele wydajności** są podsumowywane cele dotyczące wydajności według stanu. Aby wyświetlić wszystkie cele pracownika, należy wybrać numer stanu lub wybrać cele wydajności ze **Szczegółów**. Kierownicy i pracownicy mogą w razie potrzeby aktualizować cele w czasie trwania celu.

Kierownictwo może zobaczyć wszystkie cele zespołu za pośrednictwem kafelka **Cele wydajności zespołu** w sekcji **Podsumowania** **Mojego zespołu**.

#### <a name="reviews-tab"></a>Karta Recenzje

Na karcie **Recenzje** znajduje się podsumowanie przeglądów pracowników w poszczególnych stanach: **w toku**, **gotowe do przejrzenia** i **końcowe recenzje**. Aby uzyskać dostęp do recenzji pracownika, wybierz przycisk **Szczegóły**, a następnie wybierz opcję Recenzje, które chcesz współpracować. W zależności od tego, gdzie znajduje się przegląd w ramach procesu przepływu pracy, można sprawdzić, czy przegląd jest dostępny do aktualizacji. 

Możesz  zobaczyć wszystkie recenzje twojego zespołu za pośrednictwem kafelka **Recenzje wydajności zespołu** w sekcji **Podsumowania** **Mojego zespołu**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
