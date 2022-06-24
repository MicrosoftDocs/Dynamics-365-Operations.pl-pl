---
title: Oferty zapieczętowane na potrzeby ZO
description: W tym artykule opisano sposób konfigurowania zapieczętowanego przetargu w celu zachowania odpowiedzi na oferty dostawcy w tajemnicy, dopóki nie zostaną one rozpieczętowane przez personel działu zakupów.
author: GalynaFedorova
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 40f1735d7efa5131b1462963758b6b48eec78fea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890894"
---
# <a name="sealed-bidding-for-rfqs"></a>Oferty zapieczętowane na potrzeby ZO

[!include [banner](../includes/banner.md)]

Zapieczętowany przetarg ma na celu zachowanie odpowiedzi na oferty dostawcy w tajemnicy, dopóki nie zostaną one rozpieczętowane przez personel działu zakupów. Wszystkie oferty związane z datą zapytanie ofertowe (ZO) są najpierw dostępne do rozpiekania po wygaśnięciu oferty. Zanim oferta zostanie rozpieczętowana, dostęp do niej mają tylko użytkownicy, którzy mają dedykowane role użytkowników i reprezentują dostawcę.

> [!IMPORTANT]
> Modyfikowanie lub rozszerzanie formularzy albo tworzenie nowych formularzy lub logiki biznesowej może złamać ochronę zapewnianą przez firmę Microsoft dla zapieczętowanych licytacji. Ponosisz ryzyko korzystania z jakichkolwiek modyfikacji, rozszerzeń, nowych formularzy lub logiki biznesowej lub niemożności korzystania z funkcji zapieczętowanej licytacji z powodu takich modyfikacji, rozszerzeń, nowych formularzy lub logiki biznesowej.  Firma Microsoft nie ponosi odpowiedzialności za jakiekolwiek szkody wynikające z jakichkolwiek modyfikacji lub rozszerzeń formularzy lub jakichkolwiek nowych formularzy lub logiki biznesowej, które tworzysz dla Ciebie lub jakiejkolwiek innej osoby trzeciej tworzonej dla Ciebie. Firma Microsoft nie zapewnia wsparcia technicznego ani innego w zakresie modyfikacji, rozszerzeń, nowych formularzy lub logiki biznesowej dokonanych przez użytkownika lub jakąkolwiek osobę trzecią w jego imieniu. Ponosisz wyłączną odpowiedzialność za przestrzeganie wszystkich obowiązujących przepisów i regulacji dotyczących licytacji zapieczętowanej.

## <a name="how-bids-are-kept-secure"></a>Na czym polega zabezpieczanie ofert

Zapieczętowany przetarg wykorzystuje szyfrowanie asymetryczne do szyfrowania klucza szyfrowania oferty (KEK) i szyfrowanie symetryczne w celu zaszyfrowania rzeczywistej oferty. System integruje się z usługą Microsoft Azure Key Vault w celu generowania kluczy szyfrowania, które są używane do szyfrowania zapieczętowanych ofert, i zarządzania nimi. Każda oferta ma własny klucz szyfrowania. To szyfrowanie jest bezpieczne w magazynie kluczy, który jest własnością organizacji uruchamiającej aplikację Dynamics 365 Supply Chain Management. System uzyskuje dostęp do magazynu kluczy na żądanie, gdy wymagane jest szyfrowanie i odszyfrowywanie.

## <a name="setup-and-configuration"></a>Instalacja i konfiguracja

W tej sekcji opisano wymagania wstępne do zastosowania, zanim będzie można wysyłać ZO, które wymagają zapieczętowanego przetargu.

### <a name="step-1-set-up-user-access-to-sealed-bidding"></a>Krok 1. Skonfiguruj dostęp użytkownika do zapieczętowanego przetargu

Gdy korzystasz z zapieczętowanego przetargu, tylko użytkownicy, którzy są ustawiani jako osoba kontaktowa dla dostawcy, mogą wyświetlać, edytować i przesyłać oferty dla tego dostawcy do czasu wygaśnięcia okresu przetargu. Ci użytkownicy muszą mieć rolę **Dostawca (zewnętrzny)** i muszą być ustawiani jako osoba kontaktowa dla konta dostawcy. Osoba kontaktowa musi mieć również uprawnienia do współpracy z dostawcami, zgodnie z opisem w sekcji [Konfigurowanie i utrzymywanie współpracy z dostawcami](set-up-maintain-vendor-collaboration.md).

Ponieważ użytkownicy, którzy mają odpowiednie uprawnienia i są skonfigurowani jako kontakty dostawców, mogą uzyskiwać dostęp do zapieczętowanych ofert dla dostawcy, ważne jest, aby śledzić, kim są ci użytkownicy. Administrator systemu, który konfiguruje użytkowników i role zabezpieczeń, jest odpowiedzialny za ograniczenie dostępu do zapieczętowanych ofert dla tych użytkowników, którzy naprawdę mogą je wyświetlać.

### <a name="step-2-enable-the-sealed-bidding-feature"></a>Krok 2. Włącz funkcję zapieczętowanego przetargu

Przed rozpoczęciem konfigurowania lub używania tej funkcji należy upewnić się, że jest ona dostępna w systemie. Administratorzy mogą skorzystać z obszaru roboczego **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**, aby sprawdzić stan funkcji i ją włączyć. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zaopatrzenie i sourcing*
- **Nazwa funkcji:** *Zapieczętowany przetarg dla ZO*

### <a name="step-3-set-up-azure-key-vault"></a>Krok 3. Skonfiguruj usługę Azure Key Vault

Aplikacja Supply Chain Management używa kluczy szyfrowania, aby chronić wszystkie zapieczętowane oferty i przechowywać je w tajemnicy do odpowiedniego czasu. Korzysta z możliwości usługi Key Vault do generowania wymaganych kluczy i zarządzania nimi. W związku z tym należy skonfigurować połączenie z aplikacji Supply Chain Management do magazynu kluczy, aby włączyć system.

> [!IMPORTANT]
> Magazyny kluczy używane do licytowania zapieczętowanego muszą spełniać następujące wymagania:
>
> - Jeśli używasz piaskownicy do programowania i testowania, musisz mieć jeden dedykowany magazyn kluczy dla piaskownicy i osobny dla produkcji.
> - Każdy magazyn kluczy musi zostać utworzony w ramach subskrypcji platformy Azure należącej do organizacji (a nie subskrypcji, w której jest uruchomiona aplikacji Supply Chain Management).
> - Każdy klucz musi być używany wyłącznie w zapieczętowanych przetargach. Nie wolno używać magazynów kluczy z zapieczętowaną licytacją do żadnych innych celów.

Każda oferta pobiera własny klucz tajny. Ten klucz jest używany za każdym razem, gdy użytkownik wyświetla, aktualizuje lub rozpieczętowuje przetarg.

Usługa Key Vault generuje klucz używany do pobierania klucza tajnego, gdy dostawca wybiera opcję **Oferta** w interfejsie współpracy z dostawcami. Następnie klucz wygasa po określonym czasie, który menedżer zaopatrzenia ustawia na stronie **Parametry modułu Zaopatrzenie i sourcing** w aplikacji Supply Chain Management. Po wygaśnięciu klucza nikt nie będzie mógł wyświetlać, edytować ani rozpieczętowywać oferty. Dlatego ważne jest, aby skonfigurować wygaśnięcie klucza, tak aby było wystarczająco dużo czasu na zakończenie procesu przetargu.

W następnych trzech krokach skonfigurujesz połączenie z usługą Key Vault. Najpierw skonfigurujesz magazyn kluczy do użycia z zapieczętowanymi przetargami. Następnie skonfigurujesz aplikację Supply Chain Management do komunikacji z magazynem kluczy. Na koniec ustawisz czas wygaśnięcia klucza.

### <a name="step-4-set-up-a-key-vault-to-use-with-sealed-bidding"></a>Krok 4. Skonfiguruj magazyn kluczy do użycia z zapieczętowanymi przetargami

Aby skonfigurować magazyn kluczy, wykonaj następujące kroki. Kolejność kroków jest ważna.

1. Jeśli nie masz jeszcze skonfigurowanej subskrypcji platformy Azure, która jest niezależna od subskrypcji, w której jest uruchomiona aplikacja Supply Chain Management, skonfiguruj ją.
1. Skonfiguruj magazyn kluczy w oddzielnym magazynie platformy Azure. Aby uzyskać więcej informacji, przejrzyj temat [Obsługa magazynu Azure Key Vault](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
1. Skonfiguruj aplikację Supply Chain Management, aby działała jako klient magazynu kluczy. Aby uzyskać więcej informacji, przejrzyj temat [Konfigurowanie klienta usługi Azure Key Vault](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client).

### <a name="step-5-configure-key-vault-parameters-in-supply-chain-management"></a>Krok 5. Skonfiguruj parametry usługi Key Vault w aplikacji Supply Chain Management

Aby skonfigurować Supply Chain Management do komunikowania się z magazynem kluczy podczas zapieczętowanego przetargu, wykonaj następujące kroki.

1. Zaloguj się do aplikacji Supply Chain Management i przejdź do pozycji **Administrowanie systemem \> Konfiguracja \> Parametry usługi Key Vault**.
1. Wybierz pozycję **Nowy**, aby utworzyć rekord, i ustaw dla niego następujące pola:

    - **Nazwa** — wprowadź nazwę.
    - **Opis** — wprowadź opis.
    - **Adres URL magazynu kluczy** — wprowadź domyślny adres URL magazynu kluczy.
    - **Klient usługi Key Vault** — wprowadź identyfikator klienta interaktywnego aplikacji usługi Active Directory skojarzony z magazynem kluczy w celu uwierzytelnienia.
    - **Klucz tajny usługi Key Vault** — wprowadź tajne odwołanie certyfikatu.
    - **Włączono dla zapieczętowanego przetargu** — ustaw tę opcję na *Tak*.

![Strona parametrów usługi Key Vault](media/sealed-bidding-key-vault-param.png "Strona parametrów usługi Key Vault")

> [!NOTE]
> Możesz włączyć tylko jedną konfigurację magazynu kluczy dla zapieczętowanego przetargu naraz. Przed wyłączeniem istniejącej konfiguracji magazynu kluczy należy upewnić się, że wszystkie zapieczętowane przetargi, które z niej korzystają, są rozpieczętowane. Sprawdź każdy przypadek ZO typu *Zapieczętowano* i upewnij się, że wszystkie odpowiedzi na nie są rozpieczętowane.

### <a name="step-6-set-the-key-expiration-time"></a>Krok 6. Ustaw czas wygaśnięcia klucza

Aby ustawić czas wygaśnięcia, który jest stosowany do klucza generowanego dla każdej nowej oferty, wykonaj następujące kroki.

1. Przejdź do pozycji **Parametry modułu Zaopatrzenie i sourcing \> Konfiguracja \> Parametry modułu Zaopatrzenie i sourcing**.
1. Na karcie **Zapytanie ofertowe** w polu **Przesunięcie w dniach** wprowadź liczbę dni, przez które powinien trwać okres ZO. Podczas tworzenia ZO liczba dni, które należy wprowadzić w tym miejscu, jest dodawana do daty systemowej w celu zdefiniowania domyślnej daty wygaśnięcia ZO.
1. W polu **Przesunięcie wygaśnięcia klucza szyfrowania w dniach** wprowadź liczbę dni, przez które każdy klucz szyfrowania powinien być prawidłowy po jego wystawieniu. Po wygaśnięciu klucza szyfrowania nikt nie będzie mógł wyświetlać, edytować ani rozpieczętowywać korzystającej z niego zapieczętowanej oferty.

> [!TIP]
> Wartość pola **Przesunięcie wygaśnięcia klucza szyfrowania w dniach** nie powinna być mniejsza niż wartość pola **Przesunięcie w dniach**.

### <a name="step-7-set-the-default-bid-type"></a><a name="set-default-bid-type"></a>Krok 7. Ustaw domyślny typ oferty

Każda sprawa ZO ma typ oferty. Typ oferty określa, czy ta sprawa ZO zapewnia otwartą czy zapieczętowaną ofertę.

#### <a name="rfq-cases-that-dont-have-a-solicitation-type"></a>Sprawy ZO, które nie mają typu zdobywania zamówień

Aby ustawić domyślny typ oferty przypisany do nowych przypadków ZO, którym nie przypisano typu zdobywania zamówień podczas tworzenia, wykonaj następujące kroki.

1. Przejdź do pozycji **Parametry modułu Zaopatrzenie i sourcing \> Konfiguracja \> Parametry modułu Zaopatrzenie i sourcing**.
1. Na karcie **Zapytanie ofertowe** ustaw pole **Typ oferty** na *Zapieczętowane*.

#### <a name="rfq-cases-that-have-a-solicitation-type"></a>Sprawy ZO, które mają typ zdobywania zamówień

Aby ustawić domyślny typ oferty przypisany do nowych przypadków ZO, którym przypisano typ zdobywania zamówień podczas tworzenia, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Konfiguracja \> Zapytanie ofertowe \> Typ zdobywania zamówień**.
1. Utwórz nowy typ zdobywania zamówień lub wybierz istniejący typ zdobywania zamówień, w którym chcesz użyć typu oferty *Zapieczętowane*.
1. W polu **Typ oferty** ustaw wartość *Zapieczętowane*.
1. Powtórz te kroki dla każdego dodatkowego typu zdobywania zamówień, w którym chcesz wdrożyć zapieczętowane przetargi.

> [!TIP]
> Typ zdobywania zamówień nie musi być przypisany podczas tworzenia nowego ZO. Jeśli przypisany jest typ zdobywania zamówień, domyślny typ stawki ZO może go pobrać. W przeciwnym razie można użyć domyślnego typu zdobywania zamówień zdefiniowanego w parametrach zaopatrzenia i sourcingu.

## <a name="the-sealed-bidding-process"></a>Proces zapieczętowanego przetargu

Zapieczętowane przetargi przebiegają zgodnie z prawie tym samym procesem, który jest opisany w [przeglądzie zapytań ofertowych (ZO)](request-quotations.md). Główna różnica polega na tym, że dane ofertowe i ich załączniki są szyfrowane do momentu rozpieczętowania oferty.

> [!IMPORTANT]
> [Kwestionariusze](/dynamicsax-2012/appuser-itpro/view-and-respond-to-questionnaires) nie są szyfrowane i nie powinny być używane do zbierania poufnych informacji

Poniżej znajduje się omówienie procesu:

1. Tworzysz i wysyłasz ZO do jednego lub większej liczby dostawców.
1. Dostawcy odpowiadają, przesyłając zapieczętowaną ofertę.
1. Rozpieczętowujesz oferty po upływie terminu wygaśnięcia oferty.
1. Stawki stają się widoczne i możesz je ocenić i porównać.
1. Po zaakceptowaniu oferty wygenerujesz zamówienie zakupu, wygenerujesz umowę zakupu lub zaktualizujesz zapotrzebowanie na zakup.

### <a name="create-an-rfq-case-that-uses-sealed-bidding"></a>Tworzenie przypadku ZO, który używa zapieczętowanego przetargu

Proces tworzenia przypadku ZO do zapieczętowanego przetargu jest prawie taki sam jak proces przetargu niezapieczętowanego. Aby uzyskać informacje dotyczące tworzenia obu typów przypadków ZO, zobacz [Tworzenie zapytania ofertowego](tasks/create-request-quotation.md). W tej sekcji przedstawiono kilka ważnych zagadnień podczas tworzenia ZO do zapieczętowanego przetargu.

Przypadki ZO dla zapieczętowanego przetargu muszą mieć wartość **Typ oferty** równą *Zapieczętowane*. Istnieją trzy sposoby przypisania tej wartości do przypadku ZO:

- Ustaw wartość bezpośrednio w przypadku ZO po jego utworzeniu.
- Zdefiniuj zapieczętowane przetargi jako domyślny typ stawki dla wszystkich przypadków ZO w parametrach zaopatrzenia i sourcingu. (Zobacz sekcję [Ustawianie domyślnego typu oferty](#set-default-bid-type) wcześniej w tym artykule).
- Podczas tworzenia nowej sprawy ZO wybierz typ zdobywania zamówień skonfigurowany dla zapieczętowanych przetargów. (Zobacz sekcję [Ustawianie domyślnego typu oferty](#set-default-bid-type)).

W przypadku zapieczętowanego przetargu **data i godzina wygaśnięcia przypadku ZO** określa, kiedy złożone oferty mogą zostać rozpieczętowane. Wartość **daty i godziny wygaśnięcia** w każdym wierszu będzie zgodna z wartością w nagłówku.

Nie można zmienić typu stawki po wysłaniu sprawy ZO.

### <a name="vendors-respond-to-an-rfq"></a>Dostawcy odpowiadają na ZO

Dostawcy, którzy odpowiadają na zapieczętowaną ofertę, stosują tę samą procedurę, której używają do odpowiadania na otwarte oferty, zgodnie z opisem w części [Praca z ZO w obszarze roboczym Składanie ofert przez dostawców](vendor-collaboration-work-customers-dynamics-365-operations.md#working-with-rfqs-in-the-vendor-bidding-workspace). Aby uzyskać szczegółowe instrukcje dotyczące pracy zarówno z ofertami otwartymi, jak i zapieczętowanymi, zobacz [Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień](tasks/enter-compare-rfq-bids-award-contracts.md). Jedyną różnicą między przetwarzaniem zapieczętowanych ofert a przetwarzaniem ofert otwartych jest to, że do czasu upływu okresu przetargu specjaliści ds. zaopatrzenia nie mogą otworzyć zapieczętowanej oferty dostawcy. Tylko osoba kontaktowa dla dostawcy może otworzyć zapieczętowaną ofertę tego dostawcy.

> [!IMPORTANT]
> W przypadku zapieczętowanych przetargów dostawcy mogą przesyłać załączniki tylko w formacie PDF. Żadne inne formaty nie będą akceptowane.

Gdy zarejestrowany użytkownik dostawcy wybierze **Oferta** dla ZO z zapieczętowaną ofertą, może wprowadzić swoje dane oferty, a dane te będą bezpieczne. Dostawcy mogą zapisywać swoją pracę, przygotowując ofertę, zwracać do niej tak często, jak jest to wymagane, a następnie przesyłać ją, gdy będzie gotowa. Dostawcy mogą również wyświetlać swoją ofertę po jej przesłaniu. Jeśli dostawcy muszą zmienić swoją ofertę po jej przesłaniu, mogą ją odwołać, zaktualizować i przesłać ponownie w dowolnym momencie, dopóki nie upłynie okres przetargu.

Podczas zapieczętowanego przetargu obowiązują następujące warunki:

- Podczas zapieczętowanego przetargu system tworzy arkusz *Zapytanie ofertowe*.
- Gdy dostawca przesyła ofertę, tworzone są arkusze ZO bez wierszy, które mają zapieczętowaną cenę.
- Po rozpieczętowaniu przypadku tworzone są arkusze ZO, które mają cenę i kwotę. Dostęp do tego arkusza można uzyskać, wybierając pozycję **Arkusze zapytań ofertowych** na stronie **Wszystkie zapytania ofertowe**.
- System przechowuje dziennik każdej akcji wykonywanej przez użytkowników przy zapieczętowanej ofercie. Działania te obejmują wyświetlanie, edytowanie i zapisywanie oferty. Ten dziennik jest widoczny zarówno dla dostawcy, jak i dla specjalistów od zaopatrzenia, którzy mają dostęp do oferty.
- W miarę postępów w przetargu specjaliści od zamówień publicznych mogą zobaczyć jego stan. Stan będzie mieć wartość *Dostawca aktualizuje* lub *Przesłana przez dostawcę*.
- Stan wierszy w zapieczętowanej ofercie pozostaje jako *Wysłane* do momentu rozpieczętowania oferty.
- Jeśli dostawca zdecyduje się odrzucić ofertę, oferta będzie miała stan **Postęp odpowiedzi** o wartości *Odrzucona przez dostawcę*. Ten stan będzie widoczny dla pracowników działu zaopatrzenia.
- Odpowiedzi w kwestionariuszach **nie** są przechowywane w postaci zaszyfrowanej w bazie danych. Dlatego nie są one zapieczętowane. Jednak nie będą one widoczne w interfejsie użytkownika ZO, dopóki przypadek nie zostanie rozpieczętowany.

### <a name="all-sealed-bid-activities-are-logged"></a>Wszystkie zapieczętowane działania związane z ofertami są rejestrowane

Szczegółowy dziennik rejestruje wszystkie działania użytkownika i akcje dotyczące oferty. Dziennik aktywności umożliwia organizacjom określenie, kto zaktualizował ofertę w okresie jej istnienia i jakie były aktualizacje. Umożliwia również organizacjom potwierdzenie, że tylko upoważnione osoby uzyskały dostęp do zapieczętowanej oferty. Dziennik aktywności jest dostępny na stronie **Aktywność** każdej oferty.

### <a name="review-rfq-activity"></a>Przeglądanie działań dla ZO

Każda interakcja z ofertą jest rejestrowana i można ją wyświetlić na stronie **Aktywność**. Na poniższej ilustracji pokazano przykład.

![Przykład strony Aktywność](media/sealed-bidding-rfq-activity.png "Przykład strony Aktywność")

Dostawcy mogą uzyskać dostęp do strony **Aktywność**, wybierając pozycję **Aktywność** na stronie **Zapytanie ofertowe — oferta zapieczętowana**. Pracownicy działu zaopatrzenia mogą uzyskać dostęp, wybierając pozycję **Aktywność** na stronie **Zapytanie ofertowe**. Dziennik aktywności zapewnia pełną widoczność dla dostawców i pracowników działu zaopatrzenia, którzy uzyskiwali dostęp do oferty. W związku z tym może ujawnić wszelki nieautoryzowany dostęp.

### <a name="unseal-sealed-bids"></a>Rozpieczętowywanie zapieczętowanych ofert

Po upływie wartości **daty i godziny wygaśnięcia**, która została skonfigurowana dla przypadku ZO z zapieczętowaną ofertą, przycisk **Rozpieczętuj** staje się dostępny. Wybierz opcję **Rozpieczętuj**, aby rozpieczętować wszystkie oferty dla wybranego przypadku ZO. Wszystkie dane ofert i załączniki stają się widoczne, dzięki czemu można zarządzać odpowiedziami na przypadek. Ponadto tworzone są arkusze zawierające przesłane dane ofert.

Zdarzenie rozpieczętowywania jest rejestrowane i można je wyświetlić na stronie **Aktywność**.

### <a name="process-accepted-bids"></a>Przetwarzanie zaakceptowanych ofert

Proces porównywania i zatwierdzania wcześniej zapieczętowanych ofert jest taki sam jak proces dla ofert otwartych. Aby uzyskać informacje na temat oceniania, porównywania, odrzucania i akceptowania rozpieczętowanych ofert, zobacz [Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień](tasks/enter-compare-rfq-bids-award-contracts.md).

## <a name="the-rfq-activity-log-can-never-be-deleted"></a>Nigdy nie można usunąć dziennika aktywności ZO

Nikt, nawet administratorzy i pomoc techniczna firmy Microsoft, nie może edytować ani usuwać dziennika aktywności ZO. Ograniczenie to pomaga zapewnić uczciwość procesu przetargu zapieczętowanego. Pomaga również zapewnić, że jest utrzymywana dokładna historia rekordów.
